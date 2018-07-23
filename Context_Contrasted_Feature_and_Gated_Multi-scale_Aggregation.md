# [Context Contrasted Feature and Gated Multi-scale Aggregation for Scene Segmentation](http://openaccess.thecvf.com/content_cvpr_2018/papers/Ding_Context_Contrasted_Feature_CVPR_2018_paper.pdf)

####  Category
Semantic Segmentation

#### Context
* 背景
Segmentationは①物体の本質的な特徴をきちんと捉える、②位置情報も捉えるという課題があり、  
近年のDCNNの発展のおかげで、①はImagenetのpretrainedの重みを使うなど工夫をしているが、②はまだまだ議論がありそうだという感じ。  
特に、この論文ではDCCNをSegmentationに適応する際に２つの障害(Handicapp)があるとしている。  

* 多種多様なものの存在
目立った物体(画像の中で多くのピクセルを占めるものとか？)だけではなく、目立たない物体もきちんと特徴を捉えなければならない。  
Imagenet等でpretrainedしたものは画像レベルの抽象的な特徴量を捉えることができるが、位置情報などをきちんと区別して捉えられない  
Imagenetpretrainedを素直に適応すると、目立った物体の特徴は良く学習するが、目立たない物体は狭い範囲で予測されたり、最悪消えてしまったりする。  
(==Contextを重視したアプローチ)  
↓  
位置情報をきちんと区別する特徴が必要    
例えば、ピクセルpを予測するときに、きちんと位置を含めて特徴を捉えている限り、画像の他の部分の影響(context?)をうけないほうが良い  
↓  
a context contrasted local featureの提案  

* 様々な大きさの物体の存在  
大きさも多種多様なのでそれに対応しなければならない。  
    * 対策１ 様々なサイズにリサイズして違うネットワークに入れて特徴量を結合する  
      計算量多いとか制限がある  
    * 対策２ 中間レイヤーの特徴量を利用する。  
      今回はこちらの対策を採用。FCNのskipレイヤーを利用する
      従来は単純に足されたりしていただけなので、スケールの違いの重要性を無視していがた、今回は考慮
      

* 最近の流れ  
 

#### Contributions  
* a context contrasted local feature    
  contextとlocal infoのいいとこどり  
  有益なcontextだけでなく、位置情報も利用でき、さらに、contextに頼らず位置情報を取得できる
  
* 違ったスケールの特徴量のinformation flowをゲートを利用して制御する

#### コメント  

詳しく読んでみても面白そうかも。
