# HeroGRAPH
Code for my ORSUM @ RecSys 2020, HeroGRAPH: A Heterogeneous Graph Framework for Multi-Target Cross-Domain Recommendation

Paper, workshop proceedings are now online: http://ceur-ws.org/Vol-2715/

The code is still under approval as it is the company property. 

embedding分为了两部分：（1）各domain独有的user emb + item emb，有三个domain则有三份，（2）各domain共用的graph user emb + item emb，有一份。总计有4份。

计算domain A的用户-商品对时，取出domain A user emb + item emb，再取出共用的graph user emb + item emb，最后用公式5算正样本偏好。

计算domain B的用户-商品对时，取出domain B user emb + item emb，再取出共用的graph user emb + item emb，最后用公式5算正样本偏好。

计算domain C的用户-商品对时，取出domain C user emb + item emb，再取出共用的graph user emb + item emb，最后用公式5算正样本偏好

在每一个batch中，都取出A、B、C三组，得到三组loss，加和后作为batch loss。由于数据集大小不等，三个domain batch sizes取了不同值以使三个domain batch numbers差不多。其中music、instr、video分别取了100、15、50；cloth、beaut、healt分别取了80、60、100。

If you have other questions or confusions, please send email to [cuiqiang1990@hotmail.com].
