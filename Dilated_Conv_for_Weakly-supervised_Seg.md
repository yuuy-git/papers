# [Revisiting Dilated Convolution: A Simple Approach for Weakly- and SemiSupervised Semantic Segmentation](http://openaccess.thecvf.com/content_cvpr_2018/papers/Wei_Revisiting_Dilated_Convolution_CVPR_2018_paper.pdf)

# Category  
Semantic Segmentation
Weakly-supervised Segmentation

# Context

#### Weakly-supervised Segmentation
少ないアノテーションでSegmentationができるようにという動機。
mage-levelアノテーションから学習  
Coarse-level アノテーションから学習  
という２レベルあるっぽい。


#### この研究の背景  
Segmentationの分野においては、まだ、supervised > weakly supervised   
これは、image-levelからでは質の良い密な物体のlocalization mapを作り出せないというのに原因がある  
これを解消するために、Dilated Convolutionをうまく使う。


# Correctness
SOTA出してるらしいしすごそう

# Contribution

異なるDilated rateを用いることで  
①Convolutionのカーネルサイズを効率的に大きくできる  
②区別できている輪郭情報を区別できていない物体の領域へと転移活用でき、区別手出来ていない物体領域をlocalization mapに反映させることができる。  

異なるdilated rateを用いたCNNブロックでSOTA以上を達成

# Clarity
まあまあ

# Comment
Dilated Convたびたび現れるので論文読んで実装理解して使いこなせるようにしたい。  
weakly-supervised segも一つくらい有名なの実装するか、動かすかしてどんなのか見てみたい。
