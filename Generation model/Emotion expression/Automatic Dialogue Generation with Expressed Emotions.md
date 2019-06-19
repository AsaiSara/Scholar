# [Automatic Dialogue Generation with Expressed Emotions](https://www.aclweb.org/anthology/N18-2008)

## 著者
Authors: Chenyang Huang, Osmar R. Za¨ıane, Amine Trabelsi, Nouha Dziri
## 会議名
Conference: Proceedings of the 2018 Conference of the North American Chapter of the Association 
for Computational Linguistics: Human Language Technologies, Volume 2 (Short Papers)

## 概要
NCMへの感情のラベルの与え方を3通り試している。

## 先行研究と比べてここがすごい
先行研究では試されていなかった、感情の与え方で精度を検証。エンコーダに与えるべきか(最初or最後),デコーダの各ステップで与えるべきか。
それぞれを、作成した分類器の正解率と主観評価によって実験。

## 手法のキモ
以下の３手法を提案

Encoder

手法1 Enc-bef : X={e, x_1, x_2, ..., x_m}  \\
手法2 Enc-aht : X={x_1, x_2, ..., x_m, e}  \\

Decoder

手法3 Dec : same as (Li et al. 2016a). each step, feed emotion vectore (v_e) ... [h^(De)_(t-1);c^(De)_(t-1);v_e]

![figure1](https://github.com/AsaiSara/Scholar/blob/picture/Generation%20model/Emotion%20expression/Automatic_Emo2018.png)

## 有効性の評価
# データセット
* Open-Subtitles dataset (lis, 2016) 
(2016. Opensubtitles2016: Extracting large parallelcorpora from movie and tv subtitles.)
* 9感情でラベル付けされたCBET(Yadollahi et al., 2017; Shahraki and Zaiane,2017)で感情分類器を作成し、
(anger, surprise, joy, love, sadness, fear, disgust, guilt, and thankfulnessのうち最大2ラベルが一つのinstanceについている.感情を表していないというラベル付けあ34.01％を占める。これはトレーニングでは使うがテストでは使わない。)
* 分類器(F1-score 68.4%)：bidirectional LSTM (Graves et al.,2005)

# 評価尺度
* 隠れ層600次元, optimizerはAdam, 学習率1e-4, 語彙数25000(Li et al. 2016a), LSTM, test data 50000 samples, training:evaluation = 95%:5%,

![figure1](https://github.com/AsaiSara/Scholar/blob/picture/Generation%20model/Emotion%20expression/Automatic_Emo2018_eval1.png)
* 作成した分類器で9感情に分類した正解率：Decoder に入れる方法が全体的には一番高かった、Encoderに入れる方法はほぼ精度が同じ




## その他の議論

## 次に読むべき論文

## メモ
Gloval Attention があまりよくわかっていない
