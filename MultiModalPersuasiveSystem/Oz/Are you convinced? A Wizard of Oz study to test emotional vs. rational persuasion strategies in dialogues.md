# [Are you convinced? A Wizard of Oz study to test emotional vs. rational persuasion strategies in dialogues](https://reader.elsevier.com/reader/sd/pii/S0747563215302867token=3BB72B9B045EA41FB55B0B6EC2AD966E2476F3255DB6826DC994223B3B8EC1143B018CDCC71C7F90EC2C8DECDC41ADCD)

## 概要
OzによるWebベースのテキストチャットを用いて、感情的か合理的かどちらの戦略のほうが説得(太極拳を勧める)に効果的であるか検証。
* EP : EmotionalPositive
* EN : EmotionalNegative
* RP : RationalPositive
* RN : RationalNegative の4つを比較

結果では、感情的なポジティブな戦略が最も効果的であることが分かった。最後に自動化の話もしている。

## 先行研究と比べてここがすごい
コンピュータのチャットにおいて、感情的と合理的な戦略両方について検証している研究はなく、それらの組み合わせによって効果が変わる可能性がある。
複数の先行研究の実証実験を基に、感情的ポジティブな手法が効果的であり、全体的にも感情的なほうが合理的な戦略よりも有効であるという仮説を
立てたうえで、その仮説を検証できる実験方法を提案している。

## 手法のキモ
テキストチャット形式のツールを作成し、4手法を明確に定義したうえで4人の説得者を訓練して被験者に説得を行う。
それぞれの戦略をユーザの興味に基づいて順に使い分けていくことで、どの戦略に切り替えた時点で興味を持ったかを確認する。
主観評価では興味を持ったかどうかの設問だけではなく、実際に追加情報つきのチラシ希望人数も比較している。

## 有効性の評価

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
   
   
<img src="https://github.com/AsaiSara/Scholar/blob/picture/MultiModalPersuasiveSystem/Oz/Are_you_convinced2016_interface1.png"  width="320px">
<img src="https://github.com/AsaiSara/Scholar/blob/picture/MultiModalPersuasiveSystem/Oz/Are_you_convinced2016_interface2.png" width="320px">

### 評価尺度


## その他の議論

## 次に読むべき論文

## コメント
実験設定において、合理的ポジティブネガティブはポジネガがある時点で感情が入っているような気がした。

## 先行研究のまとめ
* (Mozzota 2006)　Posi-Nega　Positeve strategies are more effective
* (Fow 2001) Rational persuasion is often used
* (Heath 2006: Westen 2007) emotion is effective technique across many discilines, more so than rational persuasive arguments
上三つからどちらも説得の戦略として用いられるが、感情のほうが効く場合が多く、特にポジティブな方が説得に有効である可能性が高いと考えられる。

