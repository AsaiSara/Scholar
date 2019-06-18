# [Automatic Dialogue Generation with Expressed Emotions](https://www.aclweb.org/anthology/N18-2008)

## 著者
Authors: Chenyang Huang, Osmar R. Za¨ıane, Amine Trabelsi, Nouha Dziri
## 会議名
Conference: Proceedings of the 2018 Conference of the North American Chapter of the Association 
for Computational Linguistics: Human Language Technologies, Volume 2 (Short Papers)

## 概要
NCMへの感情のラベルの与え方を3通り試している。

## 先行研究と比べてここがすごい


## 手法のキモ

![figure1](https://github.com/AsaiSara/Scholar/blob/picture/Generation%20model/Emotion%20expression/Automatic_Emo2018.png)

## 有効性の評価
# データセット
事前学習(11,300,000,000発話ペア)
* Open-Subtitles dataset (lis, 2016) 
* 2016. Opensubtitles2016: Extracting large parallelcorpora from movie and tv subtitles.
転移学習(81,000ペア)
* 9感情でラベル付けされたCBET(Yadollahi et al., 2017; Shahraki and Zaiane,2017)で感情分類器を作成
(anger, surprise, joy,
love, sadness, fear, disgust, guilt, and thankfulness.)
* 分類器(F1-score 68.4%)の作成：bidirectional LSTM (Graves et al.,2005)



# 評価尺度

## その他の議論

## 次に読むべき論文

## メモ
Gloval Attention があまりよくわかっていない
