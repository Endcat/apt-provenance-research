## 任务

关系 & 抽象

## 问题

![image-20200614132405878](https://picturefac.oss-cn-hangzhou.aliyuncs.com/img/20200614132406.png)

## 改变思路

Point -> Line -> Surface

![image-20200614140237699](https://picturefac.oss-cn-hangzhou.aliyuncs.com/img/20200614140237.png)

![image-20200614140646389](https://picturefac.oss-cn-hangzhou.aliyuncs.com/img/20200614140646.png)

![image-20200614141426978](https://picturefac.oss-cn-hangzhou.aliyuncs.com/img/20200614141427.png)

![image-20200614141803825](https://picturefac.oss-cn-hangzhou.aliyuncs.com/img/20200614141803.png)

时间event1 event2 。。。stage阶段

![image-20200614142744120](https://picturefac.oss-cn-hangzhou.aliyuncs.com/img/20200614142744.png)

![image-20200614145303259](https://picturefac.oss-cn-hangzhou.aliyuncs.com/img/20200614145303.png)

## 新的想法

![image-20200614162627690](https://picturefac.oss-cn-hangzhou.aliyuncs.com/img/20200614162627.png)



### 如何通过任意日志分析出具体行为

**具体行为**对应的日志，都会呈现某种**共同的特征**。（找特征）

![image-20200614221348147](https://picturefac.oss-cn-hangzhou.aliyuncs.com/img/20200614221348.png)

特征组合得到的是更加完善、具体化的点（Point）

Log1 = 特征1 +特征3 +xxxx

xxx.xxx.xxx.xxx [port] GET 200 (我访问成功了√) 向量化

### 如何根据具体行为确定具体行为之间的关联

共同特征的日志集合，成为了一个完整的攻击步骤。（聚类）

xxx.xxx.xxx.xxx [port] GET 404 （我访问失败了）

xxx.xxx.xxx.xxx [port] GET 404（我访问失败了）

xxx.xxx.xxx.xxx [port] GET 404（我访问失败了）

xxx.xxx.xxx.xxx [port] GET 404（我访问失败了）

xxx.xxx.xxx.xxx [port] GET 404（我访问失败了）

（可能是扫描）

### 如何根据关联组合得到攻击链

- 准则：从一般的实际攻击角度来看，攻击步骤是有先后顺序的。（比如说上传后门大概率在搜集信息的后面）
- 具体行为之间的关联？



------

阶段细化

算法指导 LCS ELK（软件）（参考论文）

Longest Common Sub-sequence 最长公共子序列 (需要有先验 训练样本)

String1: aaaaaaaaaabbbbbbbbbbbbbcccccccccccccccccccddddddddddd

String2: blablalba

社区发现 Community Discovery （聚类）（改进算法）

路径回溯 tracing

两篇文章