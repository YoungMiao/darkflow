详细请参考：https://github.com/thtrieu/darkflow/blob/master/README.md
## 在使用过程中遇到的坑
### 1、环境问题
采用TensorFlow-gpu1.7只能使用cuda9.0和cudnn7.0及以下
opencv采用3.4即可
### 2、测试问题
测试自己的训练模型，模型load 最后一次迭代次数即可，不需要模型全称
需要添加labels.txt
网络结构cfg文件名称需要和模型的前缀名称保持一致
`eg:twoclassyolo2.cfg and twoclassyolo2-36375`
### 3、训练问题
#### 1) oom问题
修改batch和多尺度（random）即可
#### 2) ValueError: need at least one array to concatenate
根据GitHub上的issue修改batch和subdivisions 可以解决问题
但是，我的问题没有解决，我换了voc的数据集做训练，没有出现这个问题，估计是数据集的问题导致的
