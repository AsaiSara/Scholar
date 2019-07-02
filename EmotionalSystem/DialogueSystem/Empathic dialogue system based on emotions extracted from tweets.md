# [Empathic dialogue system based on emotions extracted from tweets](https://dl.acm.org/citation.cfm?id=3302281)
Authors:	Shunichi Tahara	KDDI Research, Inc, Fujimimo, Japan
Kazushi Ikeda	KDDI Research, Inc, Fujimimo, Japan
Keiichiro Hoashi	KDDI Research, Inc, Fujimimo, Japan
Published in:Proceeding　IUI '19 Proceedings of the 24th International Conference on Intelligent User Interfaces　Pages 52-56 
Marina del Ray, California — March 17 - 20, 2019 

## 概要
共感を呼ぶような汎用的な対話システムの構築に向けて、ユーザの感情(pos/neg/neu)を基にシステムが感情(pos/neg/neu)
を使い分けて応答を行うニュース紹介対話システムを提案。
発話はGoogleAPIから取得したツイートを感情ごとに分類して、ユーザ発話の感情と同様の感情を選択することで共感を
起こすことを期待したシステムである。

## 先行研究と比べてここがすごい
共感を起こす対話システムは、カウンセリングやヘルスケアなどトピックドメインが絞られていることが大半であるが、
本共感システムではWebニュース記事からトピック提供を行うことで幅広く多様なトピックの共感発話を生成する。
トピック内容が多様である場合の自然な感情表現が困難であると考えられるが、
ニュース記事に関連したツイートを感情分類しユーザ発話感情をシステムが表現することで共感を呼ぶ感情表現を行う。

## 手法のキモ
システムはニュース記事を紹介し、それに関するコメントをその記事に対してツイートされた発話を参照して生成する。

### 具体的な方法
1. ニュース記事をWebサイトから選択
2. ニュース記事サイトのURLから関連ツイートを集める->感情(pos/neg/neu)に分類 (GooglePlatForm提供のGoogleAPIを使用)
3. ニュースタイトルから発話生成し対話を始める
4. 受け取ったユーザ発話を感情カテゴリに分類　(GoogleAPIを使用)
5. 2.でカテゴリ分けされたツイートを選択し共感が最大化するようなツイートを選択(特に顔文字や！など主観的表現が多いもの)
<img src="https://github.com/AsaiSara/Scholar/blob/picture/EmotionalSystem/DialogueSystem/Empathic_Dialogue_System_system.png"  width="400px">

## 有効性の評価
どういった感情がニュース記事に対する対話で有効か事前実験して対話戦略を立てた提案手法で、RandomとBackChannelの二手法と比較。

### 事前実験
どういった感情を表現するのが効果的かをまず調べる(親密になるためには共感するような意見・感情の選択を行いたい)。
* データセット
  1. ニュース記事28個(Yahoo!Japan)
  2. ユーザ発話シミュレートのための自動感情分類済みの関連ツイート
  3. 1.2.を使って45発話ペアを生成(pos/neg/neuの組み合わせにそれぞれ5ペアずつ　3感情×3感情×5発話ペア=45発話ペア)
* 方法：被験者64名に対話を読んでもらい共感度合を7段階でつけてもらう(-3~3)
* 結果：Pos-Pos、Neg-Negはスコアが高く、Neuは差がなかったた
* 提案手法の決定：ユーザがposの時はPos、Negの時はNeg、NeuのときはBackChannel(先行研究でも共感に有効とされており、事前実験結果でもneuに対するBackChannnelスコアは0.899で兵器により高い)を使う。

### 本実験
* データセット：事前実験とユーザシミュレート発話以外は同じ　(ツイートは長すぎるものとURL、HachTagを省く)
* 比較モデル
  * 提案手法：ユーザ発話感情を基に応答
  * Random：ニューストピックに関連したツイートからランダムに発話
  * BackChannel：5つの予め選択しておいたBackChannelからランダムに発話("okay","right")
* 方法：被験者64名。1回の対話に5発話を含むシステムのニュース紹介->2往復発話応答　(テキストベースのスマートフォンチャットアプリケーション)
->事前実験んと同様の質問＋どの手法が最悪・最良だったかの質問
  
* 結果
  * Table3：平均ではRandomが最も高いが、どの手法も差がなかった
  * Table4：Pos,NegではProposedが最も高くKruskal-Wallis testで3手法に有意差あり、PosについてはMan-Whitney's test でbackchannnelとProposed間に有意差あり、NeuではRandomが高いが差がない。
  * Table5：BestではRandom＞Proposed>Bachchannel、WorstではBackChannel＞Random＞Proposed　…　BackChannelが好ましいと思われておらずRandomは意見が割れていることが分かる
<img src="https://github.com/AsaiSara/Scholar/blob/picture/EmotionalSystem/DialogueSystem/Empathic_Dialogue_System_eval1.png"  width="400px">

### 考察
* ProposedのPosNegでは同じ感情を得られるため共感を感じたと考えられる。一方で、ユーザ発話がneutralの時はBackChannelを選ぶので、その時にスコアが下がっている。それは、対話を本当に理解しているか疑っているから。
* BackChannnelは事前実験で発話ペアによる評価をした際に高評価であったが、対話で用いると評価が下がった。これはインタラクティブでないと捉えられるため、ユーザの話す気力を低下させると考えられる。
* ユーザ発話の感情が曖昧であるときneutralに分類されることが多く,RandomのPositiveではユーザ発話の一部を繰り返したり同意したりするため評価が上がったと考えられる。

## その他の議論
* 課題１：BackChannnelはニューストピックとは関係ないので、それとしか比べていないのは不十分
* 課題２：GoogleAPIではない既存の感情分類を使って3以上の分類を行うべき

## 次に読むべき論文
Dialogue System:
Bertero, D., Siddique, F. B., Wu, C. S., Wan, Y., Chan, R. H. Y., and Fung, P.
Real-time speech emotion and sentiment recognition for interactive dialogue
systems. In Proceedings of the 2016 Conference on Empirical Methods in
Natural Language Processing. 1042-1047(2016)


BackChannel:
Kawahara, T., Yamaguchi, T., Inoue, K., Takanashi, K., and Ward, N. G.
Prediction and Generation of Backchannel Form for Atentive Listening
Systems. In Interspeech. 2890-2894. (2016)

Lala, D., Milhorat, P., Inoue, K., Ishida, M., Takanashi, K., and Kawahara, T.
Atentive listening system with backchanneling, response generation and
flexible turn-taking. In Proceedings of the 18th Annual SIGdial Meeting on
Discourse and Dialogue.127-136 (2017)

Robot:
Fung, P., Bertero, D., Wan, Y., Dey, A., Chan, R. H. Y., Siddique, F. B., Yang,Y.,
Wu,C., and Lin, R. Towards empathetic human-robot interactions. In
International Conference on Intelligent Text Processing and Computational
Linguistics (pp. 173-193). Springer, Cham (2016)



## コメント
* どうやって発話選択しているのか、ツイートのデータ量が理解できていない
