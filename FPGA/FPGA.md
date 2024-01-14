---
layout: default
title: FPGA
---
<!-- ---------------------------------------------------------------------------------------------------- -->
<!-- ヘッダ部 -->
<div class="column-one">
<!-- ---------------------------------------------------------------------------------------------------- -->

  [Topへ戻る](../index.md)

  --------------------------------------------------------------------------
  - FPGAやZYNQに関するRTL開発関係。主にAMD(旧Xilinx)。  
  - ファームウェア/ソフトウェア開発等は[Zynq](../Zynq/Zynq.md)または[C/C++](../C_Cplusplus/C_Cplusplus.md)にまとめる。  
  - IPコアを制御するソフトウェアは[Zynq](../Zynq/Zynq.md)にまとめる。
  
  --------------------------------------------------------------------------
</div>
<!-- ---------------------------------------------------------------------------------------------------- -->
<!-- セクション -->
<div class="column-one">
<!-- ---------------------------------------------------------------------------------------------------- -->

# AMD 公式
  <!-- left--------------------------------- -->
  <div class="column-left">
  
  1. <a href="https://support.xilinx.com/s/question/0D52E00006xR6q3SAC/axi-basic-blog-series?language=ja" target="_blank">AXI Basic Blog Series</a>	
     - AXI の基礎 1 - AXI の概要 
     - AXI の基礎 2 - AXI Verification IP (AXI VIP) を使用した AXI インターフェイスのシミュレーション 
     - AXI の基礎 3 - AXI VIP を使用したマスター AXI4-Lite のシミュレーション 
     - AXI の基礎 4 - AXI4 マスター インターフェイスに AXI VIP をプロトコル チェッカーとして使用 
     - AXI の基礎 5 - ザイリンクス Vivado IP インテグレーターで使用する AXI4-Lite Sniffer IP の作成 
     - AXI の基礎 6 - Vitis HLS での AXI4-Lite の概要
     - AXI の基礎 7 - AXI4-Lite と Vitis HLS を使用した PS への接続 

  </div>
  <!-- right--------------------------------- -->
  <div class="column-right">

  </div>
</div>

<!-- ---------------------------------------------------------------------------------------------------- -->
<!-- セクション -->
<div class="column-one">
<!-- ---------------------------------------------------------------------------------------------------- -->

# Vivadoテクニック集
  <!-- left--------------------------------- -->
  <div class="column-left">
  
  ## プロジェクト管理 参考ページ
  1. <a href="https://qiita.com/nahitafu/items/b8bfee046b197c0fb833" target="_blank">Vivadoのプロジェクトをgitで管理するための最小限のファイル構成</a>	
  1. <a href="https://github.com/tokuden/NahiViva" target="_blank">NahiViva (なひビバ)</a>	
  1. <a href="http://nahitafu.cocolog-nifty.com/nahitafu/2019/05/post-60422b.html" target="_blank">Vivadoのプロジェクトをgitで管理する最小限は何か</a>	  
  1. <a href="https://marsee101.blog.fc2.com/blog-entry-4545.html" target="_blank">なひたふさんの「Vivadoのプロジェクトをgitで管理する最小限は何か」を参考にしてVivado のプロジェクトをTCLファイルで復元した</a>	  

  </div>
  <!-- right--------------------------------- -->
  <div class="column-right">

  ## Mymemo
  1. [メモ帳](Vivado_manage_prg.md)
  </div>
</div>

<!-- ---------------------------------------------------------------------------------------------------- -->
<!-- セクション -->
<div class="column-one">
<!-- ---------------------------------------------------------------------------------------------------- -->

# デジタル・デザイン・ノート
  <!-- left--------------------------------- -->
  <div class="column-left">

  ## <a href="http://zakii.la.coocan.jp/index.htm" target="_blank">デジタル・デザイン・ノート</a>
  1. <a href="http://zakii.la.coocan.jp/hdl/index.htm" target="_blank">HDLによるFPGA設計</a>	
     1. 論理合成向けのVerilogHDLの書き方
     2. VerilogHDLコーディングのTips
     3. RTL記述に埋め込む合成制約
     4. FPGAアーキテクチャ向けのVerilog HDLの書き方
     5. テストベンチの書き方
     6. タイミング制約の書き方
     7. 回路構造を意識したRTL記述

  2. <a href="http://zakii.la.coocan.jp/hls/index.htm" target="_blank">CによるFPGA設計</a>	

  ## VHDL
  1. <a href="https://tetsufuku-blog.com/vhdl-package/" target="_blank">VHDL文法 パッケージ読み込み</a>	

  </div>
  <!-- right--------------------------------- -->
  <div class="column-right">

  ## メタステーブル  
  1. <a href="https://docs.xilinx.com/v/u/ja-JP/ug912-vivado-properties" target="_blank">Vivado Design Suite プロパティ リファレンス ガイド (UG912)</a>  
    第 3 章: 主なプロパティの説明 ASYNC_REG
  1. <a href="https://support.xilinx.com/s/question/0D52E00006hpZnVSAU/mtbf-equation-factors-for-metastability-synchronizers-slack-calculations-in-a-virtex7?language=ja" target="_blank">MTBF equation factors for Metastability synchronizers slack calculations in a Virtex7</a>  
  1. <a href="https://qiita.com/nv-h/items/3968f033404ca7e3704b" target="_blank">個人的によく使うベンダー(Xilinx, Intel)依存のHDL attribute</a>  
  1. <a href="https://dora.bk.tsukuba.ac.jp/~takeuchi/?%E9%9B%BB%E6%B0%97%E5%9B%9E%E8%B7%AF%2FHDL%2F%E9%9D%9E%E5%90%8C%E6%9C%9F%E4%BF%A1%E5%8F%B7%E3%82%92%E6%89%B1%E3%81%86%E3%81%9F%E3%82%81%E3%81%AE%E5%8D%B1%E3%81%86%E3%81%84Verilog%E3%83%A9%E3%82%A4%E3%83%96%E3%83%A9%E3%83%AA" target="_blank">非同期信号を扱うための危ういVerilogライブラリ</a>  
  1. <a href="https://support.xilinx.com/s/question/0D52E00006hphbiSAA/how-much-time-the-metastable-state-remains-?language=ja" target="_blank">How much time the metastable state remains ?</a>  
    私の質問は簡単です。FPGA ターゲット (Ultrascale および Ultrascale\+) に従って準安定状態がどのくらいの時間維持されるか知っていますか?
  1. <a href="https://www.wti.jp/contents/blog/blog210106.htm" target="_blank">非同期入力はメタステーブル対策が必要</a>  
  1. <a href="https://www.macnica.co.jp/business/semiconductor/articles/pdf/ELS0320_S000_10__1.pdf" target="_blank">ALTERAデバイスのメタスタビリティ</a>  
     - ２ メタスタビリティとは 
     - ３ メタスタビリティの動作 
     - ４ メタスタビリティの解析 
     - ５ ALTERAデバイスのメタスタビリティ特性 
     - ６ メタスタビリティの計算例 
     - ７ メタスタビリティの回避策 
     - ７-１ 同期用フリップ・フロップの使用 
     - ７-２ FIFOバッファーの使用
     - ７-３ 同期化によるレイテンシの増加を克服 
     - ８ メタスタビリティのシステムへの影響
    
  </div>




</div>
<!-- ---------------------------------------------------------------------------------------------------- -->
<!-- セクション -->
<div class="column-one">
<!-- ---------------------------------------------------------------------------------------------------- -->

# その他
  <!-- left--------------------------------- -->
  <div class="column-left">

  1. <a href="https://qiita.com/nahitafu/items/5bebc70c2fe14bed28dc" target="_blank">VivadoでRTLモジュールを使う場合のリセットの極性</a>	
  1. <a href="https://qiita.com/sttn/items/1c5385516e22a829c218" target="_blank">FPGAで回路設計する際に生じる配線遅延を調査してみた話</a>	

  1. <a href="https://www.cqpub.co.jp/dwm/contest/2001/dwm003700621.pdf" target="_blank">VHDLによる実践的ディジタル回路設計</a>	  
    - mod 演算器  
    - RSA 暗号

  ## TCL
  1. <a href="https://blog.it-see.net/it-dokata/tcl-tk/proc/" target="_blank">Tcl – 手続きのモジュール化 -proc,return-</a>	
  1. <a href="https://support.xilinx.com/s/article/56501?language=ja" target="_blank">AR# 56501: Vivado - Vivado コマンド ライン モードで argv/argc を Tcl に渡す方法</a>	



  </div>
  <!-- right--------------------------------- -->
  <div class="column-right">

  </div>
</div>

<!-- ---------------------------------------------------------------------------------------------------- -->
<!-- セクション -->
<div class="column-one">
<!-- ---------------------------------------------------------------------------------------------------- -->

  # 参考ブログ
  <!-- left--------------------------------- -->
  <div class="column-left">

  1. <a href="https://www.paltek.co.jp/techblog/tag/fpga" target="_blank">株式会社PALTEK > TECHブログ > FPGA</a>	
  1. <a href="https://www.acri.c.titech.ac.jp/wordpress/" target="_blank">ACRiブログ (FPGA, AI, IoT などの記事を発信)</a>	

  </div>
  <!-- right--------------------------------- -->
  <div class="column-right">
  </div>
</div>

<!-- ---------------------------------------------------------------------------------------------------- -->
<!-- セクション -->
<div class="column-one">
<!-- ---------------------------------------------------------------------------------------------------- -->

  # 雑多なメモ
  <!-- left--------------------------------- -->
  <div class="column-left">

  [BRAMについて](BRAM/bram.md)


  
  </div>
  </div>
  <!-- right--------------------------------- -->
  <div class="column-right">
  </div>
</div>
