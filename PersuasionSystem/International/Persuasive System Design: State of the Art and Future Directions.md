# [Persuasive system design : State of the art and future directions](https://www.researchgate.net/publication/220962630_Persuasive_system_design_State_of_the_art_and_future_directions)
### 著者
Kristian Torning      Harri Oinas-Kukkonen
### 会議名
Persuasive Technology, Fourth International Conference, PERSUASIVE 2009, Claremont, California, USA, April 26-29, 2009. Proceedings

## 概要
3つ説得技術に関する会議の51の論文について分析した。中でもむしろ態度(attitude)の変化より振る舞い(behavior)の変化を目的としている研究が多い。中でも7手法中ではTailoring、 tunneling、reduction(コメント参照)、Social comparison(社会的比較理論)が多い一方で、道徳的思考(echical consideration)は目的とされていなかった。

## 先行研究と比べてここがすごい
最新の説得システム会議の51の論文を、カテゴリ分けしてそれぞれの割合を算出した上で現状と今後の傾向について考察している。著名なカテゴリ分類方法についても要約している。

## 手法のキモ
4つの分野それに付随する2つの規律、PSDモデルの3要素、PSDモデルの4原理、PSDモデルの4変数を基に説得システムの成り立ちと傾向を説明
* computer-based field
   * 4つの分野
      1. Human-computer 
      2. interaction 
      3. computer-mediated communication
      4. Information system Affective computting)
   * 2つの人間科学分野による規律(1. psychology, 2. rhetoric)
* PSDモデルの要素、原理、変数
   * Persuasion contextが含む3要素
     1. The Intent(C1. Persuader, C2. Change type) 
     2. The Event(C3. Use context, C4. User context, C5. Techonology context) 
     3. The Strategy(C6. Message, C7. Route)
![contexts](https://github.com/AsaiSara/Scholar/blob/master/picture/Persuasive_system_design_contexts.png)
   * デザインの原理を4つの要素(変数)
      1. Primary task support(P1 ~ P7)
      2. Dialogue support(P8 ~ P14) 
      3. System credibility support(P15 ~ P21) 
      4. Social support(P22 ~ P28))
   * 4つの追加変数
      1. ethics(A1) 
      2. transformation(A2) 
      3. contribution type(A3) 
      4. sample size(A4))
      * sample size ･･･ experimental(62.7% n= 32) : conceptual (37.3% n=19)

## 有効性の評価
### データセット
3つの主要な説得技術に関する会議に投稿された研究論文(ジャーナルのみ)
### 評価尺度
カテゴリごとの論文の割合

### Persuasion Context
* C1. Persuader : 明確に定められているものは少ない(28.1% n=9)
* C2. Change type : experimental paper(84.4% n=32)の中では明確なマナーを目的とした研究が多い(81.3 % n=26)、また行動変容(befavioral change)に関しては大半である(84.4% n=27)
   * behavioral change (e.g.限られた予算と時間フレームで実験)はattitude change(複雑な調査が必要)に比べて評価が定量化できるので研究しやすい
   * unique and queantifiable measures of system success. そのためには明確に目的を示して目的を達成しそれが計測されないといけない。
   * change とtransfomationがコアとなる部分だがexperimental paperの71.8%(n=23)のみしかそそれらが起こったかのべ手おらずそれ以外は行動変容が起きたか分からない。
* C3. The context : 
* C4. User context : 
* C5. 
  
![principles](https://github.com/AsaiSara/Scholar/blob/master/picture/Persuasive_system_design_principles.png)

## その他の議論

## 次に読むべき論文

## コメント
* Tailoring : Persuasion thorough Customization　(BJ Fogg)
    * Personalization/Computer-tailoring、tailor ingredient(成分)　
    * "Fogg’s Principle of Tailoring:  Information provided by computing technology will be more persuasive if it is tailored to the individual’s needs, interests, personality, usage context, or other factors relevant to the individual."(Isis Information Service) [URL](http://www.isisinform.com/category/arrangement-as-persuasion/tailoring/)

* Tunnneling : Guided Persuasion (BJ Fogg)
    * "Fogg defines a tunnel as a committed journey, like an amusement park ride. "(Isis Information Service) .[URL](http://www.isisinform.com/category/arrangement-as-persuasion/tunneling/)
    
* Reduction : Persuading through simplifying (BJ Fogg)

* social comparison : 
  * "自己評価のために他者と比較する衝動があるという人の習慣に焦点を当てた理論"(Wikipedia) [URL](https://ja.wikipedia.org/wiki/%E7%A4%BE%E4%BC%9A%E7%9A%84%E6%AF%94%E8%BC%83%E7%90%86%E8%AB%96)
  * social comparison is defined as the process of thinking about information about one or more other people in relation to the self[URL](https://pdfs.semanticscholar.org/7384/4700dbaf6f15cfb364882d28f8724cb8a7c5.pdf) 
    * "Comparison may be integrally connected to persuasion when the communication source's relative standing with the target audience on relevant attributes is salient. For example, while listening to a political appeal, a message is generally more persuasive when it comes from someone of the same political party (e.g., Brock, 1965). Similarly, a common assumption is that a persuasive message from a person who is similar to the audience in gender, age, or life experience, lends credibility to the content of the communication. "
