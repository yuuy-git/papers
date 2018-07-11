# Image Super-Resolution Using Deep Convolutional Networks
https://arxiv.org/pdf/1501.00092.pdf  
  
# Abstract
この論文では、単一画像のsuper-resolution(SR)のためのdeep learning methodを提案している。  
この手法では低解像度から高解像度へのend-to-end mappingを直接学習している。  
inputは低解像度の画像、outputは高解像度の画像のdeep convolutional neural network(CNN)を採用。  
更にこの論文では今までの伝統的なsparse-coding-based SRをdeep convolutional networkとみなせることも示している。  
しかし、それぞれの要素を個別に扱う伝統的な手法とは異なり、本稿では全てのレイヤーを一緒に最適化している。  
本稿のモデルは軽量な構造ではあるが、state-of-the-art（SOTA）な品質の復元を実現しており、実践的なオンラインでの活用に必要な早さを兼ね備えている。  
性能とスピードのトレードオフを達成するために、本稿では様々なネットワーク構造やパラメーターを模索している。  
更に、3色チャネルを同時に処理できるように本稿のネットワークを拡張し、総合的に既存のモデルよりも高品質な復元を実現している。  
  
# Category
super-resolution(SR)  

# Context
  
低解像度を高解像度に直す場合、多くの選択肢があり、それをひとつに定めることができない。  
そこで、一般的には重要で強い情報を元に処理を決定する。  
その重要な情報を学習するために、今までのSOTAな手法ではexample-based strategyを採用していた。  
sparse-coding-based methodは代表的なexternal example-based strategyである。  


# Contoribution
1. deep convolutional neural networkを採用することで、シンプルな構造でありながら、既存のSOTAなexternal example-based methodよりも優れた精度をあげている。 
2. sparse-coding-based methodのpipelineがdeep convolutional neural networkに等しいことを示した。
既存の手法とdeep convolutional neural networkとの関係を示すことで今後のネットワークデザインの参考になる。  
3. SRというcomputer visionの典型的な問題においてもdeep learningが有用であり、高品質で高速な処理を実現できることを示した。
