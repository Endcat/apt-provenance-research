## HERCULE: 基于社区发现的日志分析和攻击重现

### Work Flow

![image-20200629192443750](https://picturefac.oss-cn-hangzhou.aliyuncs.com/img/20200629192443.png)

### DFS Propagation

![image-20200629203725793](https://picturefac.oss-cn-hangzhou.aliyuncs.com/img/20200629203725.png)

![image-20200629204221559](https://picturefac.oss-cn-hangzhou.aliyuncs.com/img/20200629204221.png)

### Louvain Method

![image-20200629170032766](https://picturefac.oss-cn-hangzhou.aliyuncs.com/img/20200629170316.png)

![image-20200629191430138](https://picturefac.oss-cn-hangzhou.aliyuncs.com/img/20200629191430.png)

社区与社区之间 是松散的结构

社区内部的大家们 是亲密无间的关系

实现方法参考了**贪心算法**，达到局部最优解

![image-20200629193300961](https://picturefac.oss-cn-hangzhou.aliyuncs.com/img/20200629193301.png)

![image-20200629193417049](https://picturefac.oss-cn-hangzhou.aliyuncs.com/img/20200629193417.png)