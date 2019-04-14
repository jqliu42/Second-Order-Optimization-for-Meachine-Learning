# 一些论文笔记
## 目录

### Large Batch Optimization for Machine Learning
* [[VLBFGS] Large-scale L-BFGS using mapreduce(Microsoft NIPS2014)](https://github.com/jqliu42/paper-note/blob/master/Optimization/Large-scale%20L-BFGS%20using%20MapReduce.pdf)
  > 该文使用vector-free的策略，将L-BFGS中two loop recursion部分的所有向量点积运算转变为标量运算，以此节省运算时间的同时，使得将L-BFGS用map reduce分布式运算具有可实践性
* [On Large-Batch Training For Deep Learning: Generalization Gap and Sharp Minima(ICLR2017)](https://github.com/jqliu42/paper-note/blob/master/Optimization/On%20Large-Batch%20Training%20For%20Deep%20Learning%20Generalization%20Gap%20and%20Sharp%20Minima.pdf)
  > 在训练神经网络的时候，SGD及其变体是人们常用的选择，然而发现使用Large batch SGD相比于Small batch SGD会导致模型泛化能力下降，该文尝试解释这么一个现象，其论点是，large batch SGD会更倾向于收敛到尖锐的曲面(Sharp Minima),而small batch SGD会倾向于收敛到平坦的曲面(flat Minima),因此两者方法存在泛化差距。此外，该文还尝试提出了针对这个现象的解决方案(见附录E)：data augmentation, Conservative Training, Robust Training
* [Train longer,generalize better: closing the generalization gap in large batch training of neural networks(NIPS2017)](https://github.com/jqliu42/paper-note/blob/master/Optimization/Train%20longer%2C%20generalize%20better%20closing%20the%20generalization%20gap%20in%20large%20batch%20training%20of%20neural%20networks.pdf)
  > 该文同样尝试解释large batch SGD导致的generalization gap现象，通过分析，其将该现象的原因归结为当batch size较大时，参数更新的次数就减少了，导致更新不充分，于是模型泛化能力减小
* [ImageNet Training in Minutes](https://github.com/jqliu42/paper-note/blob/master/Optimization/ImageNet%20Training%20in%20Minutes.pdf)
  > 一篇实验结果，用LARS+warm-up 实现了large batch training,使得可以在十几二十分钟内训完imageNet
* [A Multi-Batch L-BFGS Method for Machine Learning(NIPS2016)](https://github.com/jqliu42/paper-note/blob/master/Optimization/A%20Multi-Batch%20L-BFGS%20Method%20for%20Machine%20Learning.pdf)
  > 提出了一种拟牛顿法的随机化变体，通过在batch之间增加overlap，通过overlap部分的数据来更新gradient difference，以达到算法的稳定
* [Accurate,Large Minibatch SGD Training InageNet in 1 Hour(facebook2017)](https://github.com/jqliu42/paper-note/blob/master/Optimization/Accurate%2CLarge%20Minibatch%20SGD%20Training%20InageNet%20in%201%20Hour.pdf)
  > 该文试图解决generalization gap问题，通过linearly scaling rule和warm up技巧来将分布式同步SGD的batch size做到了8192，以此在一个小时内训练完成了ImageNet
* [A Stochastic Quasi-Newton Method for Large-Scale Optimization](https://github.com/jqliu42/paper-note/blob/master/Optimization/A%20Stochastic%20Quasi-Newton%20Method%20for%20Large-Scale%20Optimization.pdf)
  > 随机化拟牛顿法，将拟牛顿法中的curvature pairs的更新和权重迭代解耦，在固定周期才更新curvature pair(其他时间的H都是沿用不变的), 并且不再计算gradient difference,而是计算在另一个小sample subset的二阶信息
* [A Linearly-Convergent Stochastic L-BFGS Algorithm](https://github.com/jqliu42/paper-note/blob/master/Optimization/A%20Linearly-Convergent%20Stochastic%20L-BFGS%20Algorithm.pdf)
  > 基本是SQN+variance reduction,并证明了线性收敛的性质
* [Scaling SGD Batch Size to 32K for ImageNet Training](https://github.com/jqliu42/paper-note/blob/master/Optimization/Scaling%20SGD%20Batch%20Size%20to%2032K%20for%20ImageNet%20Training.pdf)
  > 提出了layer-wise adaptive rate scaling(LARS),成功的将batch size提高到了32k
