# LikeLupinTitle
表示文字列を打つだけで、ルパン三世のタイトル風の演出ができるexoファイルを出力する.py  
  
# なぜこんなものを作ったか  
端的に言えば,「ルパン三世のタイトル風の演出を動画で表現したかったから」. AviUtlの金の髭氏スクリプトの「ルパン」は、文字を適切に出してくれるが,音声ファイルまできちんと入れてくれない.   そのため,各文字のタイプライター音のファイルをタイミングよく挿入し,最後の音もきちんと入れたexoファイルを生成することはできないかと考えた.純粋にタイプライター音をタイミングに合わせて入れるのが手間なのと,文字サイズを大きくしたときにAviUtlが重くなるのでうまく入れられないという辛さを克服するためにこんなものを作った.  
# PandaNoteさんのpythonスクリプトとの出会い  
というわけで色々ネットを漁ってみると, [PandaNoteさんのスクリプト](https://pandanote.info/?p=2422) に当たった.このスクリプトは,表示文字列を入力したら, 適切なタイミングで文字オブジェクトを置くよう割り当てられたexoソースがコンソール上に出力されるという仕組みだった.これは面白いと思ったので,exoファイルを解読してみた.意外に行けないことはなさそうだと思ったので,以下の改善を行うようなpythonスクリプトを作ることに決めた.  
- 指定した音声ファイルを適切なタイミングで挿入するようにする  
- exoファイルのソースをコンソール上に出力するのではなく, exoファイルを生成するようにする  
- コンソール上の入力「\n」で改行できるようにする  
これができることによって,生成されたexoファイルをAviUtl上のタイムラインに投げてエンコードするだけで,ルパン三世タイトル風演出の動画.mp4が生成できる.  
# 必要な素材  
大前提として,  
- AviUtl  
- AviUtl拡張編集プラグイン  
  
が必要で、そのうえで  
  
- [金の髭氏のルパンタイトル風スクリプト](https://aviutlscript.wiki.fc2.com/wiki/%E3%82%A2%E3%83%8B%E3%83%A1%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E5%8A%B9%E6%9E%9C%EF%BC%91)  
- フリーフォント「 [幻ノにじみ明朝](http://www.fontna.com/blog/1912/) 」を導入する  
- 効果音ラボ様の[タイプライター音](https://soundeffect-lab.info/sound/anime/)(各文字表示時の音)  
- ニコニ・コモンズ様の[演出音](http://commons.nicovideo.jp/material/nc105836)(全文字表示時の音)  
  
これらをダウンロードすることが要求される.  
  
# 使用法
Anaconda Promptにおける実行例は以下のような感じ.  
  
```
python lupinLike.py 適当な\n文字
```
  
すると,lupin.exoが生成されるので, それをAviUtlのタイムラインに投げてエンコードする.  
test.mp4はそのできあがった動画ファイルである.  
  
一体誰の役に立つのだろうか. だがまあ共有しておくのも悪くない.  
