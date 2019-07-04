# [A Dataset for Document Grounded Conversations](https://arxiv.org/abs/1809.07358)
### 著者
Kangyan Zhou, Shrimai Prabhumoye, Alan W Black
### 会議名
Conference on Empirical Methods in Natural Language Processing (EMNLP), 2018

## 概要
映画の話題に特化したウィキペディアデータセットを作成。対話履歴だけではなくモデルが使えるソース情報も
含んでおり、実験では応答生成性能を2つのニューラルネットワークで精度比較した結果流暢さと魅力が向上した。

## 先行研究と比べてここがすごい
対話コーパスの収集について,対話環境などの情報が与えられていない場合が多く、ある話題に特定した場合の多くのターン数を含む
データが不足している。そこで、実世界での人間同士の対話での一貫性と文脈を保持したコーパスを提案する。
実験では他のドキュメントを用いて評価結果を比較する。

## 手法のキモ
Wikipediaの映画記事を見せて対話を行ってもらう。片方の話者だけが記事を見ている場合と、両方の話者が見ている場合と二通り収録。

### 収集状況
* 映画記事30 種類　(幅広いジャンルをカバー)：Wiki記事の状況を4つのキー(セクション｛s1,s2,s3,s4｝)
    (基本情報と3つのシーン(平均7文(143語)ずつ))に自動分割。一貫したサイズと詳細にするための編集は人手。
* 状況：1. 一人のワーカーがドキュメントにアクセス可能(もう一人に説明→映画を観るか決める) 2. 2人のワーカーがアクセス可能(情報について議論)　それぞれ12ターンずつ
* ターン数：最初の挨拶6ターン-> 3ターン(s1) -> 他セクション（s2,s3,s4）それぞれ3ターンずつ 
### データセット（名前：CMU DocumentGrounded Conversasions, CMU_DoG）
* 全部で4112対話、平均21.43ターン、拡張後31ターン（w1, w2, w1 -> (w1, w2), (w2, w1）)
![figure2](https://github.com/AsaiSara/Scholar/blob/master/picture/Dataset_for_document_grounded_num.png)

### 収集データの妥当性
* 映画記事ドキュメントと収集対話(対話内で計算に使う単語の割合を変化)でBLEUを取ってドキュメント参照率を見る（Table5）→ データセットをRatingごとに3種類に分割（Table4）
  * Rating1：BLEU＜0.1 (ターン数は10以下のものは省いているため、ターン数＞11)
  * Rating2：1と3以外
  * Rating3：ターン数＞12, BLEU＞0.587(平均0.385, 標準偏差0.202)  
![figure1](https://github.com/AsaiSara/Scholar/blob/master/picture/Dataset_for_document_grounded_eval1.png)
* 評価結果：ドキュメントにアクセス可能な人の平均0.22に対し、アクセスできない人の平均0.3

## 有効性の検証
Seq2Seq(SEQ)モデルを使う場合とそれにセクション情報を付与するSEQSの二種類のモデルを構築。
（2層bi-LSTM,dropout0.3,hidden_size 300, embedding size 100, optimizer Adam, learning rate,1e-3. beam width 5, train/val/test 0.8/0.05/0.15）
### データセット
* 収集したデータセット（CMU_DoC）のみを使用
### 評価尺度
1. 自動評価１：NW (トークン集合･･･"N"=Current utter:xi, , "M"=Current Section:si, "H"=previous three utters, "S"=set of stop words, |((N∩M)\H)\S| 
    * ワーカーがドキュメント情報を対話に使えるかどうかを検証
    * 結果：Table6 より、人々は新しいセクションを見ていて、古いセクションに執着しないとわかる
![figure3](https://github.com/AsaiSara/Scholar/blob/master/picture/Dataset_for_document_grounded_eval2.png)
2. 自動評価２：Perplexity 
    * 生成発話の自然性を評価
    * 結果：SEQ21.8 SEQS10.11
3. 人手評価１：Engagement
    * モデル同士を比較
    * 結果：SEQ 36.4, SEQS 43.9%,NoPreference 19.6% つまりセクションを使ったほうがEngagementが高い
4. 人手評価２：Fluency
    * a scale of 1(unreadable) to 4(perfectly readable)
    * 結果：SEQ 2.88, SEQS 3.84
  
## その他の議論

## 次に読むべき論文

## コメント
* 収集したコーパスの分析では、セクション内の一貫性とセクションごとの独立性の検証が必要であると分かった
* 記事を見ながら対話をするというシチュエーションは対話システムによくありそうだと思った
