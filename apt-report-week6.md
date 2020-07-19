论文摘要 基于用户信任和张量分解的社会网络推荐

- 主要是看一下 关联性 在这篇文章的实现
- 传统的推荐算法有两个缺陷
  - 基于一个假设 用户对其邻居的影响是单一的（而实际社会网络中是多因素的）
  - 假设训练数据是静态的（新数据加入带来重算的问题）



使用了张量表达了更多的因素

在实际生活运用中，有用户对某一个栏目进行1-5星的评分功能这样的需求，根据评分数据可以衡量用户与这个栏目之间的相关性。**在上下文感知的社会化推荐算法中**，模型维度拓展，加入了更加丰富的社会化网络数据（例如时间要素）。描述用户、栏目、上下文这样的参数，涉及到张量（tensor）。

之前理解的修正：

张量分解不是随便乱分解的，分解按照一定的标准去施行。（以Tucker分解为例，将一个张量分解成一个核张量与每一维矩阵的乘积）

![image-20200715201541716](https://picturefac.oss-cn-hangzhou.aliyuncs.com/img/20200715201541.png)

张量相关的学习（神经网络向）

https://blog.csdn.net/Flying_sfeng/article/details/80817904
