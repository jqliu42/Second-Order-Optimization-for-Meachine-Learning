# 一些论文笔记
## 目录

### Large Scale Optimization for Machine Learning
* [[VLBFGS] Large-scale L-BFGS using mapreduce(Microsoft NIPS2014)](https://github.com/jqliu42/paper-note/blob/master/Optimization/Large-scale%20L-BFGS%20using%20MapReduce.pdf)
  > 该文使用vector-free的策略，将L-BFGS中two loop recursion部分的所有向量点积运算转变为标量运算，以此节省运算时间的同时，使得将L-BFGS用map reduce分布式运算具有可实践性
* [On Large-Batch Training For Deep Learning: Generalization Gap and Sharp Minima(ICLR2017)](https://github.com/jqliu42/paper-note/blob/master/Optimization/On%20Large-Batch%20Training%20For%20Deep%20Learning%20Generalization%20Gap%20and%20Sharp%20Minima.pdf)
  > 在训练神经网络的时候，SGD及其变体是人们常用的选择，然而发现使用Large batch SGD相比于Small batch SGD会导致模型泛化能力下降，该文尝试解释这么一个现象，其论点是，large batch SGD会更倾向于收敛到尖锐的曲面(Sharp Minima),而small batch SGD会倾向于收敛到平坦的曲面(flat Minima),因此两者方法存在泛化差距。此外，该文还尝试提出了针对这个现象的解决方案(见附录E)：data augmentation, Conservative Training, Robust Training
* [Train longer,generalize better: closing the generalization gap in large batch training of neural networks(NIPS2017)](https://github.com/jqliu42/paper-note/blob/master/Optimization/Train%20longer%2C%20generalize%20better%20closing%20the%20generalization%20gap%20in%20large%20batch%20training%20of%20neural%20networks.pdf)
  > 该文同样尝试解释large batch SGD导致的generalization gap现象，通过分析，其将该现象的原因归结为当batch size较大时，参数更新的次数就减少了，导致更新不充分，于是模型泛化能力减小
