# [EmotionLines: An Emotion Corpus of Multi-Party Conversations](http://www.lrec-conf.org/proceedings/lrec2018/pdf/581.pdf)
### 著者
Sheng-Yeh Chen1, Chao-Chun Hsu1, Chuan-Chun Kuo1,
Ting-Hao (Kenneth) Huang2, Lun-Wei Ku1
Academia Sinica, Taiwan
Carnegie Mellon University, USA
1falan012102, joe32140, william0617, lwkug@iis.sinica.edu.tw
2tinghaoh@cs.cmu.edu

### 会議名
LREC2018

## 概要
今まで文面の感情アノテーションはされてきたが、文脈を考慮したアノテーションまで至らなかったため、
対話モデルについて文脈考慮型のアノテーション方法を提案する。
今までのラベル付けと分類問題の精度を比べたところ、優位に高い値となっており、
前後の文脈を考慮した感情ラベル付けをすることでより感情豊かな発話生成などに繋げられる。

## 先行研究と比べてここがすごい
大規模な対話データに感情ラベル付けを行う際に、上層的な文面だけでなく内容を考慮したアノテーションを
行う。アノテーションの一致率(kappa係数)従来より高く、分類タスクでは以前のラベル付けデータを用いた場合よりも感情分類精度が向上したため、より
適切なアノテーションがされていると考えられる。

## 手法のキモ
* アノテーションでは直前の2発話を提示して文脈を見てもらいながら、その発話を7感情のうち1感情でラベル付けしてもう
* 分類タスクでは、CNNとCNN-BいLSTMを使用

## 有効性の評価
### データセット
* ベースラインコーパス：Friends　(FriendsTVのデータをアノテーション)
* 提案コーパス：EmotionPush　(FriendsTVのデータをアノテーション)

### 評価尺度
Kappa係数と分類タスクの精度をベースラインのコーパスと比較

## その他の議論
・分類タスクでは、感情によってばらつきが大きくFearの精度が０になっていたり、全体を見てもFriendsのほうが高い項目が
多く一概には良いと言えない。
・

## 次に読むべき論文


## コメント
contextの意味とかがあんまりよくわかっていない

 ![figure1](https://github.com/AsaiSara/Scholar/blob/master/picture/EmotionLines_LRECcorpus_exam1.png)
 ![figure2](https://github.com/AsaiSara/Scholar/blob/master/picture/EmotionLines_LRECcorpus__exam2.png)
 ![figure3](https://github.com/AsaiSara/Scholar/blob/master/picture/EmotionLines_LRECcorpus__exam3.png)
 ![figure4](https://github.com/AsaiSara/Scholar/blob/master/picture/EmotionLines_LRECcorpus_exam4.png)
 ![figure5](https://github.com/AsaiSara/Scholar/blob/master/picture/EmotionLines_LRECcorpus_result1.png)
