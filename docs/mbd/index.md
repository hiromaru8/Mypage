# Model-Based Design, MBD

## 1. モデルベースデザイン（MBD）とは

* **概要**  
  数学的・論理的なモデルを作成し、そこからコード生成やシミュレーションを行う開発手法。

* **利点**  

    * 仕様 → モデル → 自動コード生成 → ハードウェア実装まで一貫
    * デバッグ・検証が早期に可能
    * FPGA/SoC の設計では HDL コードや IP コア自動生成に直結

* **MathWorks 製品**

    * **Simulink**：ブロック図でモデルを作成
    * **MATLAB**：アルゴリズムやデータ解析
    * **HDL Coder**：Simulink/Matlabモデルから Verilog/VHDL を自動生成
    * **SoC Blockset / FPGA/SoC Support Packages**：ターゲットボードとの統合

---

## 2. FPGA/SoC 向けの学習ステップ

### ステップ 1: 基本モデル作成

1. Simulink で簡単な信号処理モデルを作成

    * 例：フィルタ、FFT、PID制御

2. モデルシミュレーションで動作確認

### ステップ 2: ハードウェアターゲット設定

* FPGA/SoC 開発向けサポートパッケージをインストール

    * Xilinx, Intel (Altera) FPGA 対応
    * SoC（Zynq, MicroBlaze 等）対応

* Hardware Implementation パラメータ設定

    * クロック周波数、データ幅、固定小数点など

### ステップ 3: HDL コード生成と検証

* HDL Coder で Verilog/VHDL コード生成
* HDL シミュレーションで動作確認（ModelSim, Vivado Simulator など）
* **重要**：固定小数点化、Pipeline 化、Resource 最適化

### ステップ 4: FPGA/SoC 実機への実装

* ターゲットボードに bitstream を書き込み
* **Simulink Hardware-in-the-Loop (HIL)** でリアルタイム動作検証
* 必要に応じてパラメータチューニング

---

## 3. 学習リソース

### MathWorks 公式

* [Model-Based Design for FPGA](https://www.mathworks.com/solutions/fpga.html)
* [FPGA and SoC Workflow](https://www.mathworks.com/help/hdlcoder/fpga-design.html)
* **チュートリアル例**

  * FIRフィルタ設計 → HDL コード生成
  * PID制御 → SoC 実装

### 書籍

* **“Embedded FPGA Design with MATLAB & Simulink”**
* **“FPGA-based System Design using MATLAB, Simulink, and HDL Coder”**

### 実践例

* Xilinx Zynq + Simulink で AD/DA 信号処理
* Verilog/VHDL の知識と組み合わせて最適化

---

## 4. 学習のコツ

* **小さなモデルから始める**
  → フィルタ、加算器、簡単な制御系
* **固定小数点とパイプライン化を早めに理解する**
* **シミュレーションと生成コードを比較する**
* **HIL を使って早期検証**
