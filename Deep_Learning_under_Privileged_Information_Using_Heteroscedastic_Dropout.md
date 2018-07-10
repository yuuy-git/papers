# [Deep Learning under Privileged Information Using Heteroscedastic Dropout](http://openaccess.thecvf.com/content_cvpr_2018/papers/Lambert_Deep_Learning_Under_CVPR_2018_paper.pdf)
  
####  Category
LUPI(Learning Under Priviledged Information)
Deeplearning学習一般
データが少ないときの工夫など

LPUIは学習時には入力と正解の情報(x,y)だけでなく、教師から得られるヒント(x')も用いた、(x,x',y)で学習し、
推論時には入力と正解の情報(x,y)のみで推論する仕組みのこと。
先生から授業を受けているときは正解以外のアドバイスをもらえるが、テスト時には生徒が受けれないといった状況を想定するとわかりやすい。

#### Context
* 背景
人間の先生を考えてみたら、いい先生って正解不正解だけ教えるんじゃなくて、直感的なコメントとか比較とか説明とかいろいろ工夫してるやん？
そういうのDeeplearningでもやればええと思うねんな。
だから、学習時に正解から得られるヒントみたいなのを上手にモデルに組み込めば上記のようなものって達成できると思ってやってみました。

* 先行研究
Vapnik and VashistがSVMにてLUPIを実践

 
#### Correctness
すげえ

#### Contributions  
* Heteroscedastic Dropoutを導入することで、CNN・RNNともサンプル当たりの学習効率が向上した。(理論的にも説明している)

####  Clarity
読みやすい。

#### コメント
この分野すげえ面白そう。。
priviledge informationが使えるときは行けるって書いてたけど、実際どういうのがpriviledge informationなのかは詳しく読んでみないとわからないので、読みたい。
プロジェクト(特にアノテーションの手間がかかるもの)ではデータが少ないケースが多いので、ぜひ試してみたい。
