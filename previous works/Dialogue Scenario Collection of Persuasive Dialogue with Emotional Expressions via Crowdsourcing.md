# [Dialogue Scenario Collection of Persuasive Dialogue with Emotional Expressions via Crowdsourcing](http://www.lrec-conf.org/proceedings/lrec2018/summaries/462.html)

### 著者
Koichiro Yoshino, Yoko Ishikawa, Masahiro Mizukami,
Yu Suzuki, Sakti Sakriani, and Satoshi Nakamura

### 会議名
LREC2018

## 概要
* 感情ラベル及び受諾度合いラベル付きの説得対話データを、クラウドソーシングサービスによってクラウドワーカーに作成してもらう
* 評価は、アノテーション一致度と構築したシステムの人手評価を行う
* 結果は、アノテーション一致度は中程度で、システムの評価では人間性と親密性の向上、自然性と説得性の低下がみられた。


＝＝＝＝＝＝＝＝＝（メモ）＝＝＝＝＝＝＝＝＝＝＝

対話データの収集が行われている中、実際の対話を収録したりWoZを用いるのはコストがかかる。本研究ではクラウドワーカーに
シナリオを作成してもらう収集方法によって、感情表現を用いる説得対話のデータをクラウドソーシングによって収集した。
5つのシナリオについて200対話ずつを収集し計1000のシナリオを収集し、感情状態と受諾度合いのアノテーションを行った。
評価では、収集データを用いて説得対話システムを構築し、クラウドワーカーによって相互作用について評価してもらった。
評価結果から、収集時のトレーニングを課したとしたら、収集したラベルが十分な一致度であることがわかる。

## 先行研究と比べてここがすごい
統計的な対話データ収集方法がよくとられているが新しいタスクに従うデータ収集が困難である。また、
感情表現を含むデータ収集においては、親しい関係間の実対話が求められるがWEB上で収録することは困難である。
そのため、本研究ではクラウドワーカーがシナリオを作成し、その後に感情ラベルと受諾度ラベルのアノテーションを行い
感情ラベル付き説得対話データを収集する。

## 手法のキモ
* クラウドワーカーに対話をインストラクションに沿って一から考えてもらうデータ収集方法を取る
  * 1対話20発話以上で、一人の人が一つの対話を考えてもらう
* 感情ラベルに加えて受諾度ラベルのアノテーション
  * アノテーションは1発話を3人に着けてもらい、3人とも一致しない場合をNONEとして扱う
* ラベルを用いて両方の遷移を考慮したシステムを構築する
  * Belief-desireモデルを参照

![system1](https://github.com/AsaiSara/Scholar/blob/master/picture/Dialogue_sinario_collection_of_persuasive_LRECishikawa_system1.png)

![system2](https://github.com/AsaiSara/Scholar/blob/master/picture/Dialogue_sinario_collection_of_persuasive_LRECishikawa_system2.png)

## 有効性の評価
* アノテーションラベル(感情ラベル、受諾度ラベル)の一致度
* データを用いて構築した説得対話システムの(感情を用いた場合と用いない場合の)人手評価
### データセット
感情ラベルと受諾度ラベルの付いた説得対話データ

![data1](https://github.com/AsaiSara/Scholar/blob/master/picture/Dialogue_sinario_collection_of_persuasive_LRECishikawa_data1.png)

* 感情ラベルは3人にアノテーションしてもらい、3人とも一致しない場合はNONEとする。
* 全体的にポジティブが少なく、ネガティブが多い。
* 受諾度ラベルは低い値のほうが多い

  * 受諾度ラベルは5段階で3人に着けてもらう

![collect](https://github.com/AsaiSara/Scholar/blob/master/picture/Dialogue_sinario_collection_of_persuasive_LRECishikawa_collect1.png)

![data2](https://github.com/AsaiSara/Scholar/blob/master/picture/Dialogue_sinario_collection_of_persuasive_LRECishikawa_data2.png)

* Kappa係数(データセットごとに上の表に示している)
  * 感情ラベルについては0.4を超えており、受諾度ラベルについては超えていないが二乗誤差において一致率が高いことを確認


![data3](https://github.com/AsaiSara/Scholar/blob/master/picture/Dialogue_sinario_collection_of_persuasive_LRECishikawa_data3.png)

### 評価尺度
* システムの人手評価
  *  自然性、説得性は感情によって低下、人間性、親密性は感情によって向上

![result1](https://github.com/AsaiSara/Scholar/blob/master/picture/Dialogue_sinario_collection_of_persuasive_LRECishikawa_result1.png)


## その他の議論
* アノテータの訓練を行うことで一致率を上げたほうが良い
* 内容を考慮するようなリトリーバル方法を用いることで自然性を向上させる
* ユーザの嗜好に合わせて感情を使うか使わないかを決めたほうが良い

## 次に読むべき論文

## コメント
* Japanese datasetなのに、それについて何も書いていないのは良いのだろうか

