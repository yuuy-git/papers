# [Which Training Methods for GANs do actually Converge?](http://proceedings.mlr.press/v80/mescheder18a/mescheder18a.pdf)

#### Context
* GANの課題  
収束しねえ  

* 既存研究での収束問題に対する取り組み  
1 GANのより良い学習アルゴリズムの模索  
2学習のダイナミズムの理解(学習内部でどういうことが起こっているかの理解)　　
　→まだ完全には解明されていない
　　Meschederet al. (2017) and Nagarajan & Kolter (2017)ではヤコビアン行列の固有値の実部分が全て負であるなら、十分低い学習率を設定すれば収束するとされたし、Nagarajan& Kolter (2017)では、絶対連続なデータかつ絶対連続なジェネレータの分布（absolutely continuous　data and generator distributions）であれば、ヤコビアン行列の固有値の実部分が全て負であると示された。  
  しかし、現実に絶対連続なデータは稀である。
  
#### Correctness
  証明のappendixもあるためただしそう
  
#### Contributions  
* 例を用いながら、(unreguralized)GANは常に収束するわけではないことを示す。
* 最近のstandalization GAN のテクニックが例において局所的収束にどのように影響を与えるかを考察する。
　　→Wasserstein GANs (WGANs) (Arjovskyet al., 2017) ・ Wasserstein GANs with GradientPenalty (WGAN-GP) (Gulrajani et al., 2017) ・ DRAGAN(Kodali et al., 2017) はジェネレーターのアップデートごとに固定の数のディスクリミネーターのアップデートでは収束しなかった。  
  →一方で, instance noise (Sønderbyet al., 2016; Arjovsky & Bottou, 2017)・ zero-centered gradientpenalties (Roth et al., 2017) ・ consensus optimization(Mescheder et al., 2017) の３つは収束した。　　
*  simplified gradient penalties でGANは収束する！？
 
####  Clarity
難しい

#### コメント
とても良さそうな論文なので、GANを深掘りしたら戻ってくる。
GANとinstance noise (Sønderbyet al., 2016; Arjovsky & Bottou, 2017)・ zero-centered gradientpenalties (Roth et al., 2017) ・ consensus optimization(Mescheder et al., 2017) は読もうと思う。
