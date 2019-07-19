# [Attention Is All You Need](https://arxiv.org/abs/1706.03762)

### 著者
Ashish Vaswani, Noam Shazeer, Niki Parmar, Jakob Uszkoreit, Llion Jones, Aidan N. Gomez, Lukasz Kaiser, Illia Polosukhin

### 会議名

## 概要
Attentionのみを使って計算効率も性能も良いモデルを構築。
学習済みモデルは様々なタスクに汎用的に用いることが出来る。

## 先行研究と比べてここがすごい
言語処理タスクにおいてRNNやCNNが用いられてきたが、それらのモデルよりも
高い精度と計算効率が良い結果を出している。

## 手法のキモ
* Transformer：再起と畳み込みを調合するアテンションメカニズムを提案➡全体の単語を考慮
    * 再起を避けて包括的な依存関係の学習をアテンションで学習。
    * 全部の入力から同時に全出力単語を予測  
    * 予測ターゲットが先に見えないようにマスク
* Scaled dot-product attention : 次元が大きいときにもスケールすることで関係を学習可能に
* Multi head attention : アテンションのヘッドを複数に分けて処理することで、別の内容ごとにアテンションがかかる
* Position-wise Feed-Forward Networks : 全結合のニューラルネットで入力の順番を反映した結果に


## 有効性の評価
2種類の翻訳タスクにおいて並列処理とトレイン時間の削減を行う際のモデル品質向上を計っている。

### データセット
1. WMT2014 English-to-German : BLEU 28.4
2. WMT2014 English-to-French : BLEU 41.8 (training for 3.5 days)

### 評価尺度
BLEU

## その他の議論


## 次に読むべき論文

## コメント
