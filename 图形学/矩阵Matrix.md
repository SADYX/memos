# 矩阵

---

> 矩阵即映射

### 各种类型的矩阵

| 名称   | 属性                          |
| ---- | --------------------------- |
| 零矩阵  | 所有数都为0的矩阵                   |
| 单位矩阵 | 对角线上的数都为1，其他的数都为0的矩阵        |
| 方阵   | 行数和列数相同的矩阵                  |
| 对角矩阵 | 对角线外的数都为0的矩阵                |
| 逆矩阵  | 若矩阵A乘以矩阵B的结果为单位矩阵，则A和B互为逆矩阵 |



### 矩阵满足结合律和分配律，但是不满足交换律

![](https://github.com/SADYX/memos/blob/master/assets/images/2023-03-19-21-53-07-image.png)

### 矩阵的转置Transpose

公式即行和列互换，例如

![](https://github.com/SADYX/memos/blob/master/assets/images/2023-03-19-21-55-53-image.png)

矩阵的转置有如下属性

![](https://github.com/SADYX/memos/blob/master/assets/images/2023-03-19-22-15-57-image.png)

> 对于旋转矩阵而言，转置之后得到的矩阵实际上就是这个旋转矩阵的 逆矩阵
> 
> 

### 如何理解 <u>向量x先进行矩阵A变换再进行矩阵B变换</u> 写成 BA 而不是 AB ?

可以将A、B理解成FUNC_A、FUNC_B，此时公式为

> FUNC_B(FUNC_A(X)) 即 BAx

即先进行A运算再进行B运算


