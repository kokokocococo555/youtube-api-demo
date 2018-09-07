# はじめに
YoutubeのAPIを用いて検索結果（動画の情報）をMongoDBに突っ込み、整形してcsvファイルに書き出したりpandasで分析したりします。

## 背景
最近、Web上の情報・データを取ってくる**「クローリング・スクレイピング」**がおもしろいなと思っています。

そこで、『Pythonクローリング＆スクレイピング』という本を参考に実践しているのですが、今回はその一環です。

なぜバーチャルYouTuberの輝夜月さんの動画なのか。

それは、**私が輝夜月さん大好きだから**です。

## やること
1. YouTubeのAPIを用いて検索結果から動画情報を収集し、MongoDBに保存
2. 保存したデータを整形してcsvに書き出し
3. csvをpandasで読み込んでデータを分析

# 環境
- Windows10 64bit
- Python3.5
- MongoDB 4.0.2

# 前準備
- pandasが必要なのとJupyter Notebookが便利なので、Anacondaも入れておきましょう。
- YouTubeからAPIでデータを取ってくるために、GoogleでAPIキーの取得と設定も行いましょう。
    - 参考：[YouTube Data APIを触ってみよう【導入編】｜プラカンブログ | WEB制作会社プラスデザインカンパニー](https://www.plusdesign.co.jp/blog/?p=7752)
- コードを実行する前にMongoDBをインストールし、起動させておく必要があります。
    - 参考：[Windows版MongoDBのインストール・MongoShellを通してCRUDコマンドを打ってみる - Morning Girl](http://kageura.hatenadiary.jp/entry/2018/01/09/Windows%E7%89%88MongoDB%E3%81%AE%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%83%BBMongoShell%E3%82%92%E9%80%9A%E3%81%97%E3%81%A6CRUD%E3%82%B3%E3%83%9E%E3%83%B3%E3%83%89%E3%82%92%E6%89%93)
