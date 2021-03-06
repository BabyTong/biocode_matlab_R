# About T-test 

**1.usage：**

```matlab
[sigall,sigup,sigdown]=ttestfuntion(group1,group2,Gid,fdr）
```

**2.相关描述**

t检验(t-test)是识别两类样本中差异表达基因的常用算法。其主要原理为：对每一个基因计算一个t统计量来衡量其在两类样本中表达水平的差异，然后根据t分布计算p值来衡量这种差异的显著性。其计算公式如下：

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml\wpsC3BF.tmp.png)



​        其中，分子代表基因i在两类样本中表达值的平均差值，分母代表基因i在所有样本中表达值的标准误。由于t检验要求数据呈现正态分布，所以公式中基因的表达值为测量值经过标准化后的值。基因i在两类样本中表达的平均差值（分子）反应的是两类样本间基因表达的倍数变化，故存在FC方法相同的偏向性。此外，对基础表达量低的基因来说，即使这个基因在两类条件下表达水平的平均差异很小，一个微小变异程度（标准误）可能导致一个大的绝对t统计值,从而被识别为差异基因即：相对于高表达的基因来说，低表达的基因更容易产生大的t统计量。因此，t检验同样倾向于识别表达水平低的基因作为差异基因.