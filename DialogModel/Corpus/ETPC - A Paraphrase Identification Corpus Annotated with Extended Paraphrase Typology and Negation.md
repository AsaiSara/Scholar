# [ETPC - A Paraphrase Identification Corpus Annotated with Extended Paraphrase Typology and Negation](http://www.lrec-conf.org/proceedings/lrec2018/summaries/661.html)

### 著者
Venelin Kovatchev, M. Ant`onia Mart´ı, Maria Salam´o

Universitat de Barcelona

### 会議名
LREC2018

## 概要
* コーパスをアノテーションする差の現象について理解し、”textual paraphrases"と"atomic paraphrases”との関係を調査する
* 新たにパラフレーズシステムを構築するため、ETPC(Extended Paraphrase Typology)コーパスの評価と誤り分析を行う
* Semantic Similarity Textual Entailment Summarization Simplification 領域との関係を強調する。

## 先行研究と比べてここがすごい
* 今まで述べられてきたパラフレージングの性質をまとめる
* ETPCはパラフレーズだけでなく否定(negation)もアノテーションできる最初のコーパス
* Paraphrase Identification(PI)という分類タスク(binary classification)が存在する

## 手法のキモ
以下の点に着目して調査
RQ1. atomicとtextualパラフレーズの分布の違い
RQ2. textual non-paraphrasesの中でatomicなものの分布
RQ3. atomicパラフレーズの役割
RQ4. atomicパラフレーズの意味の保存がもたらす言語的現象


* パラフレージングを例を用いて分類
  * textual paraphrasing : 同じ意味の関係を持つ恣意的な長さの二つのテキスト
     * コンセプトとしては文章の簡易化
     
  * atomic paraphrasing : 同じ意味を保持したまま特定の条件を満たす文単位は決められた二つのテキスト
     * 問題１：一文で二つ以上の置き換えが起こる("same polarity sabstitution" "diathesis alternation" ...)
     * 問題２：パラフレーズされていな文同士内に"same polarity sabstitution"がありパラフレージングに
     * 問題３：文脈がない場合は全く違う意味であるが、文内では同じ意味として扱えるため"same polarity sabstitution"に
     * 問題４：単語同士は似た意味で統語構造も同じである("same polarity sabstitution"を満たす)が、文脈を見ると完全に違う意味に

* パラフレーズの種類の説明

![figure](https://github.com/AsaiSara/Scholar/blob/master/picture/ETPC_paraphrase_figure1.png)

* 上述の分類を使ってアノテーションすることで自動パラフレーズ手法PIに使えるコーパスを作成
  * パラフレーズされていない文とその質(本文のパラフレーズと本文そのものを比較)に注目
  
  
## 有効性の評価
### データセット
* ETPC corpus　（annotated the MRPC-A corpus by Vila et al.(2015))
  * 5801 text pair (annotated as paraphrases : 3900 pairs, as non-paraphrases : 1901) 
  * web-based annotationツールとしてPair-Annoを作成, tokenizeはNLTKを使用

### 評価尺度
 * IAPTA TPO by Vila et al (2015): 2人のアノテータに評価してもらう
 

## その他の議論


## 次に読むべき論文

## コメント
* パラフレーズ業界がいまいち理解できていないので、あまりわからなかった
* textual non-paraphrasing は意図的にパラフレーズしたわけではないペアってことなんかな
* PI って二つの文の内容が同じかどうかって分類かな。
* 私のコーパス収集において感情を変えると確実に意味もある程度は変わるのでパラフレーズとは言わないように思える
