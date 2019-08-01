# [EmotionLines: An Emotion Corpus of Multi-Party Conversations](http://www.lrec-conf.org/proceedings/lrec2018/pdf/581.pdf)
### 著者
Sheng-Yeh Chen, Chao-Chun Hsu, Chuan-Chun Kuo,
Ting-Hao (Kenneth) Huang, Lun-Wei Ku
Academia Sinica, Taiwan
Carnegie Mellon University, USA

### 会議名
LREC2018


## 概要
今まで文面の感情アノテーションはされてきたが、アノテーションの単位にばらつきがあり、
文脈を考慮した(感情遷移の把握を行うような)アノテーションがされていないという問題点
がある。本研究では、文脈考慮型のアノテーション方法としてアノテーション時に対話全文の提示することを提案する。
対話文を収集し、文脈や単語の意味に沿った感情ラベル付きコーパスを構築した。
コーパスを用いて分類モデルを学習し、ラベルを用いる場合(CNN)と用いない場合(CNN-BiLSTM)とモデルごとに精度を比較した。

## 先行研究と比べてここがすごい
大規模な対話データに感情ラベル付けを行う際に、上層的な文面だけでなく内容を考慮したアノテーションを
行う。アノテーションの一致率(kappa係数)は中程度に保ちながら、
分類タスクでは以前のラベル付けデータを用いた場合よりも感情分類精度が向上した。

* 文脈が捉えられていないアノテーション例
![figure1](https://github.com/AsaiSara/Scholar/blob/master/picture/EmotionLines_LRECcorpus_exam1.png)

* 同じ文面でも、文脈によって感情の捉え方が変わる発話文（"Okay!"）の例
![figure2](https://github.com/AsaiSara/Scholar/blob/master/picture/EmotionLines_LRECcorpus_exam2.png)


## 手法のキモ
* アノテーションでは対話文すべてを提示して文脈を見てもらいながら、その発話を7感情のうち1感情でラベル付けしてもう
 * Amazon Mechanical Turkを使用
 * 1発話を5人に見てもらい2人以上異なっていた場合、non-neutralに分類する

![figure3](https://github.com/AsaiSara/Scholar/blob/master/picture/EmotionLines_LRECcorpus_exam3.png)

* 分類タスクでは、CNNとCNN-BiLSTMを使用
  * 分類器：contextual LSTM (感情ラベルは文脈に依存するので文脈考慮型のモデル(ラベルを入れるだけ)を採用)を使用
  
## 有効性の評価
### データセット
* 構築コーパス１：Friends　(FriendsTVのデータをアノテーション)
  * FriendsTVの会話ログ１～９回目を使用
  * 5 ~ 9, 10 ~ 14, 15 ~ 19, 20 ~ 24 それぞれの発話長に区切ってその中から250発話をランダムに抽出
 
* 構築コーパス２：EmotionPush　(FriendsTVのデータをアノテーション)
  * Facebookのメッセンジャーの友達同士の会話（30分以下の会話で、間に300秒以上挟まないもの）
  * カテゴリ分けと抽出はベースラインと同様
  * 発話、話者、発話に対する感情ラベル(後からアノテーション)
 
![figure4](https://github.com/AsaiSara/Scholar/blob/master/picture/EmotionLines_LRECcorpus_exam4.png) 

 
### 評価尺度
Kappa係数と分類タスクの精度をベースラインのコーパスと比較
* Kappa係数：0.33以上なので中程度
* 分類精度(the weighted accuracy...WA, the unweighted accurracy...UWA)
  * CNN と CNN-BiLSTM(Topicとしてラベルを入れる)で比較
    * ラベルを考慮したほうが精度が良くなったのでラベルの信頼性が確認される

![figure5](https://github.com/AsaiSara/Scholar/blob/master/picture/EmotionLines_LRECcorpus_result1.png)

## その他の議論
* 分類タスクでは、感情によってばらつきが大きくFearの精度が０になっていたり、全体を見てもFriendsのほうが高い項目が
多く一概には良いと言えない。


## 次に読むべき論文


## コメント
* clowdSourcingとMTurkの違いは？
* ラベルを用いない場合もLSTMにするべきなんじゃないかって思ったんだけど…

