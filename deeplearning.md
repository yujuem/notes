# 深度学习
https://courses.d2l.ai/zh-v2/

# 深度学习基础

## 线性代数
标量、向量、矩阵、张量：长度、维度和形状以及运算规则
范数：向量大小（距离）的度量，L1、L2、Frobenius norm
降维：调用求和函数会沿所有的轴降低张量的维度，使它变为一个标量

## 微积分
## 概率论

回归函数与感知机：线性、分类问题（损失函数求导获得最优解）
数据集：训练、验证、k-则交叉验证
训练防止过拟合：权重衰减（penalty）、dropout -> 简化模型
数值稳定性：梯度爆炸/消失问题 -> 激活函数（使得前向/后向输出结果的均值为0、方差不变）、学习率、模型深度

# 卷积神经网络
## pytorch神经网络基础

### 模型构造（层和块）
from torch import nn
层：nn.Linear线性层、nn.Sequential全连接层
块: nn.Module(任何一个层、神经网络都是是nn.Module的子类，可以方便地进行模型嵌套)
```
class MySequential(nn.Module):
  def __init__(self, *args):
    super().__init__()
    for block in args:
      self._modules[block]=block # OrderedDict()
  def forward(self, X):
    for block in self._modules.values():
      x = block(X)
    return X

X = torch.rand(2, 20) # batch=2, args=20
net = MySequential(nn.Linear(20,256), nn.ReLu(), nn.Linear(256, 10))
net(X)
```
### 参数管理
