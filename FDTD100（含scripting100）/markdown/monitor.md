## 1. The frequency-domain field and power

#### 1.1 全局属性

monitor中的全局属性适用于所有的monitor，因此可以现在此处进行一些通用设置。

![](index_files/00668b97-d2f3-4604-be5f-254f5e398c70.png)

#### 1.2 频域场剖面和频域场功率monitor

这两个monitor只在插值方法上有区别，其余没有区别。对于profile而言，其插值方式是指定位置插值，而对于power而言，其插值方式是最近邻网格单元方式。通过在advanced设置中更改插值方式，可以将profile monitor改为power monitor。

官方推荐使用power monitor。

![](index_files/d64a0204-407a-4964-ac6e-eede630a0ff1.png)

#### 1.3 覆盖全局设置

当具体的monitor想要设置与global properties不同的属性时，选择覆盖全局设置即可：

![](index_files/0874d041-2e10-405f-ae3c-9d6475208b5d.jpg)

