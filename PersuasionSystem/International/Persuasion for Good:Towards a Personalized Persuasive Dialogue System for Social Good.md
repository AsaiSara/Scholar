# [Persuasion for Good:Towards a Personalized Persuasive Dialogue System for Social Good](https://arxiv.org/abs/1906.06725)

### 著者
Xuewei Wang, Weiyan Shi, Richard Kim, Yoojung Oh, Sijia Yang, Jingwen Zhang, Zhou Yu

### 会議名
ACL 2019 as a long paper

## 概要
* 行動変容を促す説得対話システムの構築に向けて、まず最初の段階として個人情報が説得に与える影響と効果的な戦略を理解するため、
説得対話データ収集と戦略予測モデルを構築　(説得対話システム構築のための土台となる研究)

* 大規模説得対話コーパスについては、1017対話を収集し、発話ごとに10個の戦略についてアノテーション
* 10個の戦略に分類するモデルを構築し、個人に対応した説得手順を開発するため個人の背景との関係を調査

## 先行研究と比べてここがすごい
今まで個人の背景や特色を考慮した説得対話システムの開発は行われてきたが、アクセス可能な個人情報に
限りがあり、ペルソナとして社会統計学的背景や理学的特性が不足しており、個人性と対話戦略の嗜好との関係を分析できなかった。

そこで、十分な人間同士の説得対話データを収集し、発話ごとに対話戦略のアノテーションを行って戦略分類モデルを
構築することで、個人に対応した説得の戦略を用いるシステムを開発することに繋がるような分析を行っている。

## 手法のキモ
一から説得対話データを収集し、発話ごとに戦略をアノテーションすることで、発話からの戦略の分類を行うモデルを構築している。

* データ収集：被験者は個人性(性格判断)テストの後、片方に寄付を募る説得を行う。そして、両者に意図した寄付金を入力してもらったうえで、年齢や収入などの情報を記入してもらう。(個人情報を説得者の戦略と説得される者の個人性を抽出出来るような収集設定)

* アノテーション：1発話ずつ戦略種類ラベル(計10種類)を付ける。
  * ラベルの種類(10戦略)
    * persuasive appeal(6種類)：Logical appeal, Emotion appeal, credibility appeal, Foot-in-the-door appeal, Self-modeling, Personal story
    * persuasive inquiry(3種類)：Source-related inquiry, Task-related inquiry, Personal-related inquiry
    * Non-persuasive dialogue act
  * 方法：10種類の説得の戦略でランダムに選択された10対話中の1発話ずつをアノテーションしてもらい、4人に評価(適切でない場合は修正)を二回行ってもらう。
* 寄付戦略の分類モデルの構築
  * hybrid RCNN model(CNNとRNNを結合させglobalとlocal両方のsemanticsを抽出できるモデル)を使用
    * Sentence embedding : word embeddingとLSTMのhiddenを結合し、max-pooling layerに入力することで意味的翻訳をする。最後にpooling lyaerで全体から効果的な情報を取得する。
    * Context embedding : 説得を受ける側の発話をLSTMにかけたembedding 
    * Turn position embedding：ターンごとに戦略分布が違うので、10次元のベクトル
    * Sentiment：VADER (Gilbert, 2014)を使って感情分類をした結果←Emotion appeal は共感を誘う発話によってnegativeが多かったがLogical appeal ではpositiveが多かった
    * Character embedding : pre-trained multiplicative LSTMを使用(4096次元→5次元)
    
    
![model]()

## 有効性の評価


### データセット
### 評価尺度


## その他の議論

## 次に読むべき論文

## コメント

## メモ
* FC-layer : Fully-Connected layer
