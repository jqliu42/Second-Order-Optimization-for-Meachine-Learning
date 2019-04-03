# 一些论文笔记
## 目录

### Second Order Optimization for Machine Learning
* [[VLBFGS] Large-scale L-BFGS using mapreduce(Microsoft 2014)](https://github.com/jqliu42/paper-note/blob/master/Optimization/Large-scale%20L-BFGS%20using%20MapReduce.pdf)
  > 使用vector-free的策略，将L-BFGS中two loop recursion部分的所有向量点积运算转变为标量运算，以此节省运算时间的同时，使得将L-BFGS用map reduce分布式运算具有可实践性
