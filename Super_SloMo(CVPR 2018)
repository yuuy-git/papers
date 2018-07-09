# [Super SloMo High Quality Estimation of Multiple Intermediate Frames for Video Interpolation](https://arxiv.org/pdf/1712.00080.pdf)


####  Category
VIDEO PREDICTION
VIDEO INTERPOLATION

#### Context
* video interpolation  
2つの連続したフレームをinputとして間のフレームを生成する。

* 課題   

* 既存研究での取り組み１  
出力としてsingle frameを予測するものが多い。  
 multipleに適応するときの問題点１　パラレルに扱えないから遅い  
 multipleに適応するときの問題点１　$2^{i}-1$のフレームじゃないと扱えない

* 既存研究での取り組み２  

 
#### Correctness
  ただしそう。重みとコードを公開してほしい
  
#### Contributions  
* オクルージョン(物体がかぶって隠れてしまうこと)などを考慮しながら、multiple framesを出力できるようにした。  
　　方法  
    1.Unetを用いて２枚のinputにおける双方向のオプティカルフローを計算  
    2.2枚のオプティカルフローをタイムステップごとに足しあわせて、inputの間に入る双方向オプティカルフローを近似する　　
    3.このままだと動きのある境界部分に弱いので、別のUnetを用いてオプティカルフローをよりよく予測し、visibility mapも推定する。  
    4.2つのインプットイメージを重ね(wrap)、統合し(fuse)、中間フレームを生成する。統合する前に、visibility mapを重ねたイメージに用いることで、オクルージョンやartifactsといった不自然なものを取り除ける
  
####  Clarity
まあまあ読みやすい。

#### コメント
掘り下げて読みたい
step2をやって、先行研究読んで、step3読んで、実装できればやってみたい。

