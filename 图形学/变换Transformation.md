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

# 

# 三维变换

---

### 绕X,Y,Z轴旋转的公式

![](https://github.com/SADYX/memos/blob/master/assets/images/2023-03-21-22-28-57-image.png)

> 为什么绕y轴旋转的公式中-sinα在左下角？因为三个basis应该依次叉乘以得到坐标系（X-Y-Z-X-Y-Z...），所以绕Y轴旋转的平面是ZOX而不是XOZ（详情见[旋转矩阵](https://blog.csdn.net/csxiaoshui/article/details/65446125)）

### 

### 欧拉角 Euler

![](https://github.com/SADYX/memos/blob/master/assets/images/2023-03-21-23-22-54-image.png)

用 roll、pitch、yaw 三个角度来描述旋转





# 视图变换 View/Camera Transformation

---

### 如何定义一个相机

想象一下为一个模特拍照，需要先把相机放在合适的地点，然后把相机看向模特，最后旋转手机找到正确的角度。所以得到了这三点

- 位置 Position

- 注视的方向 Look-at / gaze direction

- 头顶的角度 Up direction （想象一下euler中的roll）



### 相机的变换

我们总是把相机放在原点，并且以 Y 轴为up，看向 -Z 方向（约定俗成），这样做的好处是不用移动相机，只需要移动model就行（相对运动）

![](https://github.com/SADYX/memos/blob/master/assets/images/2023-03-22-00-00-25-image.png)



### 相机从空间中任意一点转化到原点的矩阵计算

例如有如下相机

![]()

把它转到

![](https://github.com/SADYX/memos/blob/master/assets/images/2023-03-22-00-00-25-image.png)

这样的位置，需要做的有以下几步

1. 将 e 放到原点

2. 旋转 向量 g 到 -Z 轴

3. 旋转 向量 t 到 Y 轴

4. 旋转 向量 g × t 到 X 轴



![](https://github.com/SADYX/memos/blob/master/assets/images/2023-03-21-23-59-37-image.png)

 

先平移再旋转，但是旋转的这一步很复杂，我们可以换种思路：

1. 旋转 X 轴 到 向量 g × t

2. 旋转 Y 轴 到 向量 t

3. 旋转 Z 轴 到 向量 -g

然后再进行转置transpose就可以得到结果

> 因为旋转矩阵是正交矩阵，逆矩阵即为转置矩阵
