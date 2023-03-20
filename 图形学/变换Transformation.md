# 变换

---

### 二维线性变换

> 线性变化：一个矩阵乘以一个向量，例如以下几种变化，故平移并不属于线性变换

- 缩放 scale

![](https://github.com/SADYX/memos/blob/master/assets/images/svg1.svg)

- 缩放 scale 

![](https://github.com/SADYX/memos/blob/master/assets/images/svg2.svg)

- 反射 reflect

![](https://github.com/SADYX/memos/blob/master/assets/images/svg3.svg)

- 切变 shear （所有点的的x(y)坐标不变，y(x)坐标移动固定的大小）

![](https://github.com/SADYX/memos/blob/master/assets/images/svg4.svg)

### 为什么变换中要使用齐次坐标（矩阵）

> 仿射变换：平移+线性变换

减少计算量，用一个齐次矩阵同时代表线性变换和平移（仿射变换），用空间换时间

### 齐次坐标的写法

#### 点的写法

![](https://github.com/SADYX/memos/blob/master/assets/images/svg5.svg)

#### 向量的写法

![](https://github.com/SADYX/memos/blob/master/assets/images/svg6.svg)

#### 矩阵的写法

> 由此公式也可以得出，齐次矩阵代表的变换是先进行 线性变换 再进行 平移 的

![](https://github.com/SADYX/memos/blob/master/assets/images/2023-03-21-00-27-23-image.png)

#### 为什么点的最后一位是1，而向量是0

假设有如下齐次变换

![](https://github.com/SADYX/memos/blob/master/assets/images/2023-03-21-00-01-07-image.png)

可以看到这个点的最后一位1和tx、ty相乘就代表了平移的偏移量。而因为向量具有平移不变性，即只代表方向，没有具体的位置，所以对向量的平移是没有意义的，故向量最后一位是0

或者换一个角度来看

- vector + vector = vector （0 + 0 = 0）

- point - point = vector（1 - 1 = 0）

- point + vector = point（1 + 0 = 0）

- point + point = midpoint（1 + 1 = 2  ===> 0.5 + 0.5 = 1）

#### 为什么两点相加等于两点的中点

因为点的表达式严格上来说并不是

![](https://github.com/SADYX/memos/blob/master/assets/images/svg5.svg)

而是

![](https://github.com/SADYX/memos/blob/master/assets/images/svg7.svg)
