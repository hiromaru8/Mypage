## Markdown
  Markdownに関すること  


## 参考資料

  1. <a href="https://qiita.com/Qiita/items/c686397e4a0f4f11683d" target="_blank">Markdown記法 チートシート</a>	
  2. <a href="https://qiita.com/ossyaritoori/items/9f38113847ee65e68e76" target="_blank">Markdownで2カラムの文書を作りたい</a>	
  3. <a href="http://yoshikyoto.github.io/text/git/gh_pages_md.html" target="_blank">Markdownで書かれたページをGitHub Pagesで公開する</a>	


  ## 雑多なメモ
  ### リンクの表示先  
  1. <a href="https://web-camp.io/magazine/archives/82442" target="_blank">知らないと危険！target=”_blank”でリンク挿入しよう</a>  
  HTMLで以下のように、aタグにtarget属性を指定することでリンクの表示先の指定ができます。

  <a href="リンク先のURL" target="リンクの表示先の指定"></a>
  「リンクの表示先の指定」には、以下の4種類があります。

  1. 同じタブで開く   ：_self
  2. 新しいタブで開く ：_blank
  3. インラインフレーム内で開く
   
~~~
  <ul>
  <li><a href="index.md" target="sample">Topを表示</a></li>
  <li><a href="Programing/Python/python.md" target="sample">pythonを表示</a></li>
  </ul>
  <div><iframe src="index.md" width="500" height="1000" name="sample">代替内容</iframe></div>
~~~

  1. 新しいウィンドウで開く：window.open
