# [FlowNet](https://arxiv.org/abs/1504.06852)


####  Category
VIDEO PREDICTION
VIDEO INTERPOLATION
Optical Flow Prediction

#### Context
* Optical Flow予測に必要なもの　　
    ピクセル単位で位置をきちんと把握すること  
    ２枚の画像inputの間の対応関係を把握すること  
    * 画像の特徴表現だけではなく、学習した特徴を二つの画像において異なる場所にあるのに、それぞれを把握しなければならない。  
    
* 従来のCNNとの違い  
    CNNはinput-output relationはしっかりラベルされてたらいける
    Image pairsからその二枚の関係性を学ぶみたいなのはできるのか？  
    と言うチャレンジ
  
#### Contributions  
Optical flowをCNNで予測した最初の論文
2つのアーキテクチャを提案 end to end
・inputは二枚を一つにして、CNNでずっと    
・inputは二枚を別で学習して、途中で合体(correlation layer?)  

an archtecture with a correlation layer that explicity provides matching capabilities  
狙い  
multiple levels of scale and abstractionな強力な特徴を手に入れる  
その特徴量を用いて対応関係を見つけることができる  

データ少なすぎたので椅子が飛ぶやつ作って学習させたやで  



#### コメント  
コード見てみたい

