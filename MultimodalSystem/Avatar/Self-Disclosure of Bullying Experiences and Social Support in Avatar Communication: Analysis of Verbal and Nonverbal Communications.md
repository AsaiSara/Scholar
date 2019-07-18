# [Self-Disclosure of Bullying Experiences and Social Support in Avatar Communication: Analysis of Verbal and Nonverbal Communications(https://www.aaai.org/ojs/index.php/ICWSM/article/view/3353/3221)

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
   * 言語による自己開示と共感をサポートし、いじめ経験の会話をより容易に行わせ効果を上げた
   
### データセット
* ドメインを絞らず、SNS特有の関係性(実世界では話さない人)で、
いじめ体験者として10代が半数以上を占める学校に関連したトピックの対話データ

### 評価尺度
1. GML評価(ACI　赤池情報評価に基づいて選ばれたbt, ct を用いる)
  * 場所
    * Plivate : 10人以下の個人ルーム(申請orランダムエントリ)
    * Public : 誰でもはいれる
    * Temporary : その場で作る2時間で閉まる場所
![setup](https://github.com/AsaiSara/Scholar/blob/master/picture/Self-disclsure_of_bullying_support_abater_GLM.png)

 2. トーク分析(トーク 頻度、 トーク時間数、 出現単語頻度)
    * 単語分類
      * bullying and pain(6) : Bullying, Self-Body Shaming, Emotional, Damage, Family Strife, School Refusal, and Suicide 
      * school(3) : Class, School, and Sports
      * insult(2) : Aspersion and Provocation
![topic1](https://github.com/AsaiSara/Scholar/blob/master/picture/Self-disclsure_of_bullying_support_abater_topic1.png)

### 結果
* Bullied user：private room : positive effect, public room : negative effect
* Listener：private room and temporaly : positive effect
![eval1](https://github.com/AsaiSara/Scholar/blob/master/picture/Self-disclsure_of_bullying_support_abater_eval1.png)
* 最初に”bullying”の単語が出てきた時を0 min　とする
* 5a5b上: Private room がより深く自己開示をしていて、shoolについてはclassmateについての内容が頻繁
* 5a5b下: Private room においてEmotional Damage が多い(共感), Public roomではいじめに関することは話していない
* 5c : Temporaly room で中傷していることが多い
![eval2](https://github.com/AsaiSara/Scholar/blob/master/picture/Self-disclsure_of_bullying_support_abater_eval2.png)
* Bullied userもlistnerもPrivate room で頻繁にアクションが使われているし、temporary roomよりpositiveな感情を表現している
* bullied user はnegative expression を使う傾向にあるがラスト15分ではpositive expression を使う
![eval3](https://github.com/AsaiSara/Scholar/blob/master/picture/Self-disclsure_of_bullying_support_abater_eval3.png)

## その他の議論
* システムの改善に向けて
    * 自己開示のトリガーを作る
    * アクションのインプットフォームを効果的に
    * Second Life内で親密な関係を作れるアプリケーションにする
* 使用単語を前提としたシステムになっている
* 長期的な効果については見ていない
* アバターとは別のツールとの比較は行っていない

## 次に読むべき論文
LaCrosse, M. B. 1975. Nonverbal behavior and perceived
counselor attractiveness and persuasiveness. Journal of
Counseling Psychology 22(6):563–566

Sharma, E., and De Choudhury, M. 2018. Mental Health
Support and its Relationship to Linguistic Accommodation
in Online Communities. In Proceedings of the 2018 CHI
Conference on Human Factors in Computing Systems - CHI
’18, 1–13. New York, New York, USA: ACM Press.


## コメント
* イントロに調べたいこと3つとその結果のまとめをそれぞれ載せているから分かりやすかった、全部ちゃんとFirst, Second ...という風に書いていた
* 単語を使うなど自動評価が出来ることが大切だと感じた、そのための実験設計が難しい
* ジェスチャーの効用やコミュニケーション方法の違いの参考文献を読みたい
