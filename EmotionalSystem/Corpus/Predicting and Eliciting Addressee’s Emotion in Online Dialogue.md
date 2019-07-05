# [Predicting and Eliciting Addressee’s Emotion in Online Dialogue](https://pdfs.semanticscholar.org/2657/27e331647ee44ec83c6f9259a9ca24a2c40c.pdf)
### 著者
Takayuki Hasegawa 
GREE Inc.
Minato-ku, Tokyo 106-6101, Japan
takayuki.hasegawa@gree.net
Nobuhiro Kaji and Naoki Yoshinaga
Institute of Industrial Science,
the University of Tokyo
Meguro-ku, Tokyo 153-8505, Japan
### 会議名
In Proc. of SCL2013, pp.
964–972, 2013.

## 概要
発話の受けての感情をアノテーションしたコーパスをTwitterデータをによって作成し、
感情推定と応答文生成に用いることが出来るかを検証。
感情推定では新たな特徴量が話しての感情の推測に効果的に使えるかを調査。
応答生成では応答内容のコントロールにより発話の受け手側の感情を目的の感情に誘導。

## 先行研究と比べてここがすごい
感情推定については、発話単体のデータから推測するものが多いが、
対話データにおいて発話応答の応答を行った側（発話の受け手）の感情について推測している。
また、特定の感情を抽出する応答生成モデルの構築は行われてきたのに対し、8種類の目標感情を抽出する応答文生成を可能にする。
（翻訳への適応においても幅広い技術と言えるが、応答内容にはあまり触れられていないため、感情の考慮の必要性が考えられる。）

## 手法のキモ
* データの自動アノテーション
    * Table3のような感情ごとの単語を8感情それぞれの10表現のうち含まれていればラベル付け
    * 否定や仮定法などが含まれていて単語の意味が変わる場合はアノテーションしないことにしている
    * 2人のワーカにラベル付けされたデータ100ずつ評価してもらい一致率が高いことを確認

![annotation1](https://github.com/AsaiSara/Scholar/blob/master/picture/Predicting_and_eliciting_addresser's_eomotion_annotation1.png)

![annotation2](https://github.com/AsaiSara/Scholar/blob/master/picture/Predicting_and_eliciting_addresser's_eomotion_annotation2.png)

* 感情分類(Prediction of adresser's emotion)：タグ付けされた発話と前発話のペアを入力し8感情に分類
    * online passive-agrgressive algorithmを使う(すべてのn-gramを抽出して特徴として用いる)
* 感情誘導応答生成(Elicitation responce generation)：目標感情を入力し、その感情に誘導する応答文を生成
    * 統計的応答生成(5-gramの言語モデルSRIMと翻訳モデルGIZA++、最適な応答文の検索Moses decoder)
    * 生成ベースの応答生成(機械翻訳モデル＋言語モデルSRIME)
         * 例：URPRIZEについてTable2だと1,2文目を翻訳モデルの学習で使い、2分目だけを言語モデルの学習で使う
    
* 感情の定義：Pltchik(1980)（ANGER, ANTICIPATION, DISGUST, FEAR, JOY, SADNESS, SURPRISE and TRUST） 

## 有効性の評価
1.  膨大な雑談対話データから感情分類器と目標感情抽出応答生成器を構築
2. 人のワーカにアノテーションされたテストデータで評価

### データセット
* 学習データ：Japanese Twitter postsから64000万対話以上を自動構築

![train1](https://github.com/AsaiSara/Scholar/blob/master/picture/Predicting_and_eliciting_addresser's_eomotion_train.png)

* テストデータの構築
  1. 感情タグ付けされたコーパスを5人のワーカに見せて応答しやすそうな80発話を抽出（計400発話ペア）
  2. それぞれの発話に対する2応答を別々の人に考えてもらう（400応答+ 2発話*400発話分 = 400発話に対する1200応答）
  3. 2人のワーカに感情誘導に適切か判断してもらい、両方が不適切とした発話ペアを省く（396発話に対する1099応答）

![test](https://github.com/AsaiSara/Scholar/blob/master/picture/Predicting_and_eliciting_addresser's_eomotion_test.png)
  
### 評価尺度
  * 自動評価
      * 感情分類器：応答と感情を使用、応答と感情とその前の発話を使用、の二種類を比較
          * 感情分類する発話の前発話を入れることでスコアが上昇（論文にはaddreseeと書いてあるが恐らく発信者の方だと思う）
          * つまり感情誘導を考慮する分類が有効である
          * ポジティブ同士、ネガティブ同士の感情は分類しづらい
          ![result](https://github.com/AsaiSara/Scholar/blob/master/picture/Predicting_and_eliciting_addresser's_eomotion_result.png)
      * 応答生成：BLEUで比較 (NO_ADAOTATION0.64, PROPOSED1.05 OPTIMA 1.57)
          * モデル適応と最適化が有効
  * 人手評価
      * 147人にベースライン、157人に提案手法を評価（カッパ値0.59 一致率中程度）
      * ベースラインの74応答、提案手法の92応答が2人の両方の被験者から適切だと判断される
      * つまり提案手法のほうが適切な応答と判断された確率が高い
## その他の議論

## 次に読むべき論文

## コメント
  * addresser：発信人、addressee：受取人　これのどっちの発話がどこを指しているのか分からない箇所がいくつもあった
* n-gramがスパースに扱われるようなものだから、感情の見積もりが発話から出来るというのはデータの取り方に依存していると思った
