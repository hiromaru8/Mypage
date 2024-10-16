# memo

```
import os
import glob

import pandas as pd
from openpyxl import load_workbook
from openpyxl.styles import PatternFill, Border, Side

# まとめるCSVファイルがあるディレクトリを指定
csv_directory = './'  # 必要に応じて変更

# CSVファイルのリストを取得
path = '**/test*.csv'
globfile = os.path.join(csv_directory, path)
csv_files = glob.glob(globfile, recursive=True)

print(csv_files)

# 結果を格納するためのリストを用意
results = []

# 各CSVファイルを読み込み、結果をまとめる
for file in csv_files:
    try:
        df = pd.read_csv(file,encoding="shift_jis")
        result_row = [file] + df['result'].tolist()  # ファイル名と結果をリストにする
        results.append(result_row)
    except:
        continue
# カラム名を設定（ファイル名とテスト名）
columns = ['ファイル名'] + df['name'].tolist()

# DataFrameにまとめる
summary_df = pd.DataFrame(results, columns=columns)

# 結果を表示
print(summary_df)


# DataFrameをエクセルファイルに書き出す
excel_filename = 'summary_results_with_colors_and_borders.xlsx'
summary_df.to_excel(excel_filename, index=False)

# エクセルファイルの読み込み
wb = load_workbook(excel_filename)
ws = wb.active

# 不合格のセルを赤く塗りつぶすための設定
header_fill = PatternFill(start_color="CCCCCC", end_color="CCCCCC", fill_type="solid")
fail_fill   = PatternFill(start_color="FF9999", end_color="FF9999", fill_type="solid")

# 罫線のスタイルを定義
thin_border = Border(
    left    = Side(style='thin'),
    right   = Side(style='thin'),
    top     = Side(style='thin'),
    bottom  = Side(style='thin')
)

# セルの値に基づいてスタイルを適用（色と罫線）
for row in ws.iter_rows(min_row=1, max_row=ws.max_row, min_col=1, max_col=ws.max_column):
    
    for cell in row:
        # 罫線を設定
        cell.border = thin_border
        
        if cell.row == 1 :
            cell.fill = header_fill
        elif cell.column >= 2 :
            if cell.value == '不合格':
                cell.fill = fail_fill

# エクセルファイルを保存
wb.save(excel_filename)
wb.close()

```
