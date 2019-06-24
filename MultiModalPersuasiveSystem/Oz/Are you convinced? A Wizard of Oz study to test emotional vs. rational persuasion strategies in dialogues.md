# [Are you convinced? A Wizard of Oz study to test emotional vs. rational persuasion strategies in dialogues](https://reader.elsevier.com/reader/sd/pii/S0747563215302867token=3BB72B9B045EA41FB55B0B6EC2AD966E2476F3255DB6826DC994223B3B8EC1143B018CDCC71C7F90EC2C8DECDC41ADCD)

## 概要
OzによるWebベースのテキストチャットを用いて、感情的か合理的かどちらの戦略のほうが説得(太極拳を勧める)に効果的であるか検証。
* EP : EmotionalPositive
* EN : EmotionalNegative
* RP : RationalPositive
* RN : RationalNegative の4つを比較

結果では、感情的なポジティブな戦略が最も効果的であることが分かった。

## 先行研究と比べてここがすごい
コンピュータのチャットにおいて、感情的と合理的な戦略両方について検証している研究はなく、それらの組み合わせによって効果が変わる可能性がある。
複数の先行研究の実証実験を基に、感情的ポジティブな手法が効果的であり、全体的にも感情的なほうが合理的な戦略よりも有効であるという仮説を
立てたうえで、その仮説を検証できる実験方法を提案している。

## 手法のキモ
テキストチャット形式のツールを作成し、4手法を明確に定義したうえで4人の説得者を訓練して被験者に説得を行う。
それぞれの戦略をユーザの興味に基づいて順に使い分けていくことで、どの戦略に切り替えた時点で興味を持ったかを確認する。
主観評価では興味を持ったかどうかの設問だけではなく、実際に追加情報つきのチラシ希望人数も比較している。

## 有効性の評価
2つの仮説を検証する
H1. 感情的戦略が合理的戦略よりも成功する
H2. 感情的ポジティブな発言が最も説得性が高い


### 実験詳細
* 被験者　52名(女性14名、男性38名)
  * テキストチャットで説得される→リンクの載ったチラシがいるか聞かれる→前半のチャットと後半のチャットについて設問に答える。
  (被験者は７人中一人が$50のアマゾンギフトカードが抽選でもらえる。)
* 実験設定
  * 最初のアンケート：年齢、民族、健康、現時点での太極拳への興味
  * Ozの方法：ユーザとは別の部屋にいるWizardがユーザのログインを待っていてチャットする。ユーザはWizardの存在を知らない。
  * チャットの前半後半：先行研究でPos>Negの結果が出ているので、EP or RP からチャット開始(前半)。興味を持っていれば同じ戦略で後半も説得、
  興味が不足していたら変更(EP→RP or RP→EP)。それぞれで質問に答えてもらったらまた戦略変更するかしないかを決める、この時両方の戦略で
  効果的でなかった場合、ネガティブな戦略に移行(EP→RP→RN or RP→EP→EN)。もしその後まだ興味を持ってもらえていなければ、残った戦略を使う。
  Wizardは参加者が十分に太極拳を習う確信が持てた時または会話につかれてしまったときはチャットを終わらせてチラシがいるかどうかを聞き、
  興味度合いの設問に答えてもらう。
   * Wizardについて：4人。Wizard同士で訓練し合っていてすでに実験設計を把握済み。興味のあるなしは評価項目から判断するが、
   その理由をWizardは残しておく(返答がネガティブ、返答の長さが短いなど)
 * 感情の定義
   * EP ：ポジティブ/報酬を与える戦略、かつ、話者の感情をアピール
   * RP : ポジティブ/報酬を与える戦略、かつ、科学的/論理的主張を含む
   * EN : 太極拳をしなかった結果を主張、かつ、話者の感情をアピール  
   * RN : 太極拳をしなかった結果を主張、かつ、論理的な主張を含む  
<img src="https://github.com/AsaiSara/Scholar/blob/picture/MultiModalPersuasiveSystem/Oz/Are_you_convinced2016_interface1.png"  width="300px">
<img src="https://github.com/AsaiSara/Scholar/blob/picture/MultiModalPersuasiveSystem/Oz/Are_you_convinced2016_interface2.png" width="300px">

### 評価尺度と実験結果
1. チャットを行う前と後との**運動をしたいか**と**太極拳に興味があるか**についての主観評価結果でT検定を行う
<img src="https://github.com/AsaiSara/Scholar/blob/picture/MultiModalPersuasiveSystem/Oz/Are_you_convinced2016_eval1.png" width="320px">
* 運動をしたいかは有意差なし(したいという人数は減少)、太極拳への興味は優位に後のほうが高い


2. チャット後にチラシを求めた人数
<img src="https://github.com/AsaiSara/Scholar/blob/picture/MultiModalPersuasiveSystem/Oz/Are_you_convinced2016_eval2.png" width="320px">
* 36人/52人：チラシを求める、24人/36人：興味度が増加(Print&Interest group (PINT))
* PINT groupはpre-chatでは他の被験者と有意な興味の差はなかったが、post-chatでは有意な差を出していた
* PINT groupはRN,ENについては他の被験者よりも優位に低い興味度合いを出していた

3.それぞれの戦略(前と後)について、ある戦略の使用度合いと興味度合いの相関
* 恐らく pre-chat : EPはRPより前に合った場合、後に合った場合、ENはRNより前に合った場合、後に合った場合
<img src="https://github.com/AsaiSara/Scholar/blob/picture/MultiModalPersuasiveSystem/Oz/Are_you_convinced2016_eval1.png" width="320px">
* EPについてはRPより後に行った場合、EPを用いた場合と興味の値についてRPの使用時と比べて優位に正の相関があるため有効だと考えられる
* ENについては逆の結果であり、RNを用いた後に優位に負の相関が出ている
* RNについてはENの前でも後でも、負の相関が出ている

## その他の議論
* 実験について：被験者が理系、40歳以下、女性が少ないこと
* ドメインについて：太極拳に絞って実験を行っていること
* 今後の予定：自動チャットシステムの適用

## 次に読むべき論文

## コメント
実験設定において、ポジティブネガティブについて、ネガティブの定義が「太極拳をしなかった場合の不利益」というのはわかりづらかった。

## 先行研究のまとめ
* (Mozzota 2006)　Posi-Nega　Positeve strategies are more effective
* (Fow 2001) Rational persuasion is often used
* (Heath 2006: Westen 2007) emotion is effective technique across many discilines, more so than rational persuasive arguments
上三つからどちらも説得の戦略として用いられるが、感情のほうが効く場合が多く、特にポジティブな方が説得に有効である可能性が高いと考えられる。

