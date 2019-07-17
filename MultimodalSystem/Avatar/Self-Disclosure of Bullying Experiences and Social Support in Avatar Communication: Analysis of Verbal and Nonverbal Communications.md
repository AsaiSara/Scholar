# [Self-Disclosure of Bullying Experiences and Social Support in
Avatar Communication: Analysis of Verbal and Nonverbal Communications(https://www.aaai.org/ojs/index.php/ICWSM/article/view/3353/3221)

### 著者
Masanori Takano
CyberAgent, Inc

Takaaki Tsunoda
CyberAgent, Inc

### 会議名
Proceedings of the Thirteenth International AAAI Conference on Web and Social Media (ICWSM 2019)
## 概要
* いじめ経験の自己開示やsocial supportをSNS上のアバターを用いたコミュニケーションで行う効果を検証する。
* 聞き手に否定される恐れから辛い出来事の自己開示が難しい場面にアバターは有効であると示されているが、アバターによるsocial support研究は少ない
* いじめ経験を話した人に感情的な表現を行うsocial supportを受けさせたデモの効果として、少数の知人に対してアバターコミュニケーションの頻度が増えたことが分かった。

![picture1](https://github.com/AsaiSara/Scholar/blob/master/picture/Self-disclsure_of_bullying_support_abater_picture1.png)

## 先行研究と比べてここがすごい
アバターによる非言語コミュニケーションの有用性は主張されてきているが
様々なSNSコミュニケーションではアバターにあまり注目されていない。
そのため、いじめ経験者の自己開示について対話ログ(単語抽出➡内容・時間)やアクションログを基に定量的評価することにより、
アバターコミュニケーションのリアルタイムサポート（アクション提案、自己開示の促し）の改善を提案。


## 手法のキモ
* 対話データのログを使うことで、定量的な分析を可能にする。

## 有効性の評価
以下の点を、場所(plivate, public, temploraly)と時間(-15~0min, 0~15min, 15min~)ごとに評価する
1. まずそのでアバターコミュニケーションの自己開示がされるか
   * 少数の仲の良い知人に対して効果的なソーシャルサポートが見られた 
2. どういった内容について話す傾向があるか
   * いじめの経験や感情的なダメージを受けた内容が多く、聞き手はそれに対して議論し共感する
3. アバターアクションはどのように行われているか
   * 言語による自己開示と共感をサポートし、より容易にいじめ経験の会話を行わせ効果を上げた
   

1.トーク 頻度、2. トーク時間数、3. 出現単語頻度

### データセット
* ドメインを絞らず、SNS特有の関係性(実世界では話さない人)で、
いじめ体験者として10代が半数以上を占める学校に関連したトピックの対話データ

### 評価尺度
![setup](https://github.com/AsaiSara/Scholar/blob/master/picture/Self-disclsure_of_bullying_support_abater_GLM.png)
![eval1](https://github.com/AsaiSara/Scholar/blob/master/picture/Self-disclsure_of_bullying_support_abater_eval1.png)

### 結果
![eval2](https://github.com/AsaiSara/Scholar/blob/master/picture/Self-disclsure_of_bullying_support_abater_eval2.png)
![eval3](https://github.com/AsaiSara/Scholar/blob/master/picture/Self-disclsure_of_bullying_support_abater_eval3.png)

## その他の議論

## 次に読むべき論文

## コメント
* イントロに調べたいこと3つとその結果のまとめをそれぞれ載せているから分かりやすかった
