# Mypage

# 環境構築
## 仮想環境構築
~~~
py -m venv vmkdocs
~~~

## 仮想環境起動
~~~
.\vmkdocs\Scripts\activate
~~~

## mkdocsインストール
~~~
py -m pip install -r .\requirement.txt
~~~
py -m pip freeze

# githubへの同期

~~~
mkdocs build
~~~
を実行し
siteディレクトリの中身をrootディレクトリへ移動

