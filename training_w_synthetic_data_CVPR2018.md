# Training Deep Networks with Synthetic Data: Bridging the Reality Gap by Domain Randomization
https://arxiv.org/abs/1804.06516

# Abstract
合成データ（or 人工データ）を用いた物体検知のdeep neural networkの学習システムを提案している。  
現実世界のデータの多様性に対応するために、既存の学習システムはdomain randomizationの技術に依存しており、証明やポーズ、物体のテクスチャなどのシミュレーターのパラメータが非現実的な方法でランダム化されているデータを用いてobjectの重要な特徴を学習せざるを得ない状況である。  
現実のデータのfine-tuningに加えて、合成データを用いて学習することで、現実のデータのみで学習したネットワークよりも精度が良くなる。この結果は、様々なアプリケーションでボトルネックになっている、人工的にアノテーションされた現実世界の大量のデータをかき集めたり、超リアルで精密なバーチャル世界を構築したりせずに、安価な合成データのみを用いてneural networkが学習できる可能性を示唆している。  
本稿の手法はKITTI dataset の車のbounding box detectionで評価している。  

# Category
Domain Randomization / Annotation / training with Synthetic Data

# Context
専門的な知識が必要であったり、精密な作業が求められるアノテーション作業を人力で行うにはには莫大な時間がかかる。（例：セグメンテーション）  
これを克服する方法として、graphic simulatorを使ってラベル付されたデータを自動で生成することができる。  
近年このようなシミュレーションされたデータセットがいくつか出てきた。  
でもこのデータセットはとても高価で、専門家がとても緻密なバーチャル環境を作り上げる必要がある。  
→ すでに幾何学的な問題ではこのようなデータセットは活用されている  
 optical flow, scene flow, stereo disparity estimation, camera pose estimationなど  
  
でも未だにこのような人工のデータを現実の画像を処理するためのneural networkを学習するのにどのように活用するのかが不明だった。  

そこで、近年domain randomization(DR)という安価な手法が出てきた。  
意図的にphotorealismを捨てて、non-photorealisticな手法で環境を不安定にし、画像の本質的な特徴をネットワークに学習させる。  
  
今まではoptical flowやscene flowなどの単純な作業でのネットワークの学習に用いられていた。    
本稿ではDRを拡張して、現実世界での物体検知に活用する。  

# Contribution
- DRを現実世界で複雑な背景の中にある物体を検知するような難易度の高い作業に拡張する
- flying distractorsという、検知や予測の精度を向上させる新たなDRの要素を紹介する
- DRの各パラメータがこれらのタスクにどれほど重要なのかという調査を行う
  
ちなみに人工のDRデータだけを用いて車の物体検知を学習させたら、KITTI datasetよりも精度が上がった。  
しかもそのデータセットはテストセットと高い相関性が見られていたにもかかわらず。すごい。  
また、現実データをfine-tuningしてsynthetic DRデータを用いて学習させると、KITTI dataのみの学習よりも精度が高くなった。
