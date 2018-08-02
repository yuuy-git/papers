# WESPE: Weakly Supervised Photo Enhance for Digital Cameras
https://arxiv.org/pdf/1709.01118.pdf

# Abstract
Low-endでコンパクトなモバイルカメラは容量やハードウェア、予算の関係で写真のクオリティーが制限されている。  
本稿では限られた性能のカメラで撮られた写真をdeep learningを用いてDSLR-qualityの写真（要するに一眼レフレベルの写真）に変換するsolutionを提案する。   
この問題に取り組むために、Weakly Supervised Photo Enhance(WESPE)という新たなimage-to-imagaeのGenerative Adversarial Network(GAN)-based architectureを取り入れた。  
  
本稿でのモデルはweak supervisionでtrainされている。つまり、今までの研究とは違い、オリジナル／修正済みのペアの写真を一枚に並べた、大量のアノテーションされたデータセットを用いる、strong supervisionが不必要になった。  
  
唯一必要なのが、2つの別々のデータセット：  
  
- ソースのカメラで撮影された画像
- 一般的にインターネット上で収集できるような高画質の画像セット（必ずしもソース画像と関係のあるものではない）
  
本稿のモデルは任意のカメラの画像で学習でき、データ収集からトレーニングまで2時間程度で完了する。  
  
本稿では学習で得られた結果の評価方法を拡張している点を強調したい。一般的なオブジェクト評価方法と主観的なユーザー学習に加えて、我々はvirtual rater（仮想評価者）というものも学習させている。これはFlickrのデータに評価を下す人間の評価方法を真似たCNNで構成されており、このネットワーッくを利用してオリジナル画像と修正後の画像のリファレンススコアを計算している。  
  
WESPEを利用することで、DPED, KITTI, Cityscapesデータセットのみならずスマートフォンの画像においても、state-of-the-artなstrongly supervised methodと同等の性能を叩き出している。  
  
# Category
super resolution, photo enhancement, weak supervision  
  
# Context
一般的にはimage enhancementは手作業あるいは、半自動的に行われており、専門的な知識が必要だった。
コストも時間もかかるので、大量のデータやリアルタイムでの修正は難しかった。
これとは全く違う方法として、様々なlearning-based methodsの学習による自動修正があるが、これには修正前と修正後のペア画像、所謂strong supervisionが必要だったし、color/texture transferやphoto enhancement methodの厳しい制約を生み出していた。  
  
# Contribution
全く新しいweakly supervised solutionの導入によって上記の制約を取り除いている。  
train画像にはソースカメラとhigh-end DSLRカメラで撮られた画像が必要だが、二枚の画像に何らかの対応関係や関連性は必要ない。  
  
ネットワークはGAN＋CNN。  
  
論文のIntroductionで挙げられているContributionsは以下の通り  
  
- WESPEという、ソース画像を一眼レフレベルの画像に修正する一般的な学習モデルの提案
- a transitive CNN-GAN architectureと、SOTAなlossと入力画像に見られるcontent lossの併用によるimage enhancementとimage domain transferタスクの最適化
- subjective ratingやSOTAなメソッドとの比較を含む、一般公開されている様々な種類のカメラによる大規模な実験
- Flickrのデータセットを利用して構成した、画像の質を独立して評価するCNNネットワーク
- 広く利用可能なモデルとコードの公開 
