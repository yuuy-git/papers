# [Mask-guided Contrastive Attention Model for Person Re-Identification](http://openaccess.thecvf.com/content_cvpr_2018/papers/Song_Mask-Guided_Contrastive_Attention_CVPR_2018_paper.pdf)

CVPR2018に採択された論文

オススメ度★★

####  Category
Person Re-Identification(人物照合, ReID)  
ReID is to identity the same person across mutiple cameras  
監視関係などで需要がある

#### Context
* preson Re-Identificationの課題  
背景情報は画像によって変化するので、背景に普遍な特徴抽出をどのようにやるのかが、この分野の現在の大きな課題らしい。　　

* なぜ課題なのか  
既存研究の多くは背景を含んだ画像全体から特徴を学習しているため、背景に対して普遍な特徴を取り出すことができていない。　　

* 既存研究での取り組み１  
幾つかの既存研究では、領域特定を行ったり、姿勢・重要な特徴点を推測して、身体のパーツから特徴を学習するといったものもある。  
 -背景を含んだ画像全体より身体部分から特徴を取り出す方が効果的であることがわかったという流れがある。

* 既存研究での取り組み２  
セグメンテーションを用いて身体部分のみを取り出して用いる(The binary body maskを取り出す)  
The binary body maskの利点は  
 1.マスク画像を用いて背景を取り除ける  
 2.マスク画像は身体の形に関する情報を持っている  
(え、こんなん猿でも思いつくよね。。と思ったけど、、)  
ただ単に、シンプルに背景をマスクしたものを入力にするだけだと結果が悪くなるらしい。(Section4)

 
#### Correctness
  シンプルにマスクしただけだと結果が悪くなるのは本当なのか？よく読んでみないとわからない。でも本当なんだろうなあ・
  
#### Contributions  
* 背景に強くするために、身体部分と背景をわけたマスク画像を用いて、contrastive attention modelを作ったこと。  
   マスクしたものを入力にするだけだと結果が悪くなるので、RGB画像とマスク画像をinputとして(4ch)特徴を取り出して、その特徴をまたネットワークに入れて、separateに学習して三つのロスを得る？(この辺は精読しないとわからない)
  
* rigion-level triplet(全体画像、身体部分、背景部分の３つ) lossの提案

* bodyマスク画像をRGB画像に加えてinputとすることで、特徴量学習効果を向上させた。

####  Clarity
まあまあ読みやすい。

#### コメント
人物照合を深掘りするときに帰ってきたい論文。
Figure1の(b)がどういうことなのかいまいち実感できていない。  
多分これはVisual Attention Mechanismがよくわからないからっぽいのでその辺の論文も読まないときちんと理解できなさそう。  
The proposed region-revel triplet loss can restrain the feature learnt from different regions.  
i.e pulling the features from the full image and body region close, wherease pushing the features from bacgrounds away.  
多分、適切なところから学習できるようにロス設計をしたのだと思うが、そのあとのi.eが日本語に上手くできなかった


