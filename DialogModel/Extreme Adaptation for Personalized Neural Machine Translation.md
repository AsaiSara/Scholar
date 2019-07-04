# [Extreme Adaptation for Personalized Neural Machine Translation](https://arxiv.org/abs/1805.01817)
### 著者
Paul Michel, Graham Neubig
### 会議名
 a short paper at ACL 2018
 
## 概要
話者の属性を与えることで機械翻訳性能を向上させる試みが行われているが、基準となるモデルは得られていない。
そこで、現状のドメイン適応問題点を解決するため、
ドメイン情報を直接与えるまたは要素の近似を行い与えるようなパラメータの効率化を行う学習モデルを提案。
実験では3言語TEDtalksで翻訳性能が向上した。

## 先行研究と比べてここがすごい
属性を学習に用いる研究はされているが、特色として明示的なラベルを扱うだけにとどまっている。従来のの方法では
ドメイン数が膨大でドメインごとのデータ数が少ない場合、パラメータコストや過学習の問題で学習が困難である。
そこで、多様な話者が発話す状況（膨大なドメイン数を持つコーパスにおいてそれぞれのドメインのデータ数が少ない場合）における
ドメイン適応問題（話者特有の単語選択）を解決するようなパラメータの反映方法を提案した。
実験用にアノテーションしなおした提案手法の明示的にドメイン情報を与える方法では性能改善が見られた。

## 手法のキモ
ドメイン(話者の属性)を学習に用いるのが学習データ上の問題で困難な場合（以下）で学習を行うため、
ドメインパラメータをドメインパラメータをSoftmax層に組み込む二種類のモデルを構築。
### 問題の定式化
1. 話者数(1800近く)が多い状況で膨大な話者データを収録可能に
2. 話者ごとの発話数が小さい
3. 話者属性(性別・地位など)は似通っている状況
* ベースライン：通常のNMTモデル･･･話者ごとの文脈適応に対しナイーブなモデルになる（パラメータコストが膨大、過学習）
  * ドメイントークン：target文の最初にドメイントークン（spk_token）を与える（[Sennrich 2016](http://www.aclweb.org/anthology/N16-1005.), [Chu 2017](http://aclweb.org/anthology/P17-2061.)参照）
### モデル
![model](https://github.com/AsaiSara/Scholar/blob/master/picture/Extreme_adaptation_for_personalized_NMT_model.png)
* Full speaker bias : softmax層の前のバイアスに話者特有ドメインバイアスパラメータを足し合わせる。（語彙サイズ）(図１上)
* Factored speaker bias : ドメインバイアスパラメータとして話者特性ベクトルとr次元ベクトル、語彙サイズのバイアスを掛け合わせたものを使う（図１下）

## 有効性の評価
ドメインラベルを与えない場合、単純に与える方法(spk_token)、提案手法（full_bias, fact_bias）をBLUEとSpeaker crassificationの正解率で評価。

### データセット
* TED(SATED) based on TED Talks（3言語翻訳ペアEnglish-French, Englisn-German, English-Spanish、話者アノテーション付き）
![data](https://github.com/AsaiSara/Scholar/blob/master/picture/Extreme_adaptation_for_personalized_NMT_data.png)
### 評価尺度
* BLEU：en-frでfact_bias向上、gr-es ではfull_bias微小に向上, en-de は両モデル向上
![eval1](https://github.com/AsaiSara/Scholar/blob/master/picture/Extreme_adaptation_for_personalized_NMT_eval1.png)
* BLEU：fact_biasで向上（上のSATEDを使った評価では差があまり出なかったので再評価）
![eval3](https://github.com/AsaiSara/Scholar/blob/master/picture/Extreme_adaptation_for_personalized_NMT_eval3.png)
* 話者分類精度（bag-of-n-grams model）：baselineと比べて特定しやすくなった
![eval2](https://github.com/AsaiSara/Scholar/blob/master/picture/Extreme_adaptation_for_personalized_NMT_eval2.png)

## その他の議論

## 次に読むべき論文

## コメント
* full_biasが語彙サイズなのがよく分からない
