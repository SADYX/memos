# 向量

***

### 向量的模

norm = ![](https://latex.codecogs.com/svg.image?\sqrt{V_{1}^{2}&plus;V_{1}^{2}&plus;V_{1}^{2}&plus;&space;...&space;&plus;&space;&plus;V_{n}^{2}})

例如：![](https://latex.codecogs.com/svg.image?\overrightarrow{ab}) 的模即为该<mark>向量的长度</mark>，记为![](https://latex.codecogs.com/svg.image?\left\|&space;\overrightarrow{ab}\right\|)

![](https://latex.codecogs.com/svg.image?\left\|&space;\overrightarrow{ab}\right\|) = ![](https://latex.codecogs.com/svg.image?\sqrt{x^{2}&plus;y^{2}})

在图形学中一般表示为列向量，即

![](https://latex.codecogs.com/svg.image?\binom{x}{y})

### 单位向量

单位向量记为![](https://latex.codecogs.com/svg.image?\hat{a})

![](https://latex.codecogs.com/svg.image?\hat{a}&space;=&space;\overrightarrow{a}&space;/&space;\left\|&space;\overrightarrow{a}\right\|)

通常<mark>单位向量用于代表方向</mark>，不关心它的长度

### 向量的点乘（内积、点积） Dot Product(Scalar)

![](https://latex.codecogs.com/svg.image?\overrightarrow{a}\cdot&space;\overrightarrow{b}=\left\|\overrightarrow{a}&space;\right\|\left\|&space;\overrightarrow{b}\right\|cos\theta&space;)

公式可以转化为

![](https://latex.codecogs.com/svg.image?cos\theta=\left&space;(&space;\overrightarrow{a}\cdot&space;\overrightarrow{b}&space;\right&space;)/\left&space;(&space;\left\|\overrightarrow{a}&space;\right\|\left\|&space;\overrightarrow{b}\right\|&space;\right&space;))

如果为单位向量，则

![](https://latex.codecogs.com/svg.image?cos\theta=\hat{a}\cdot&space;\hat{b})  （这个公式也直观说明了为什么单位向量适合用于表达方向）



###### *向量的点乘也符合交换律、结合律、分配律*

<img title="" src="file:///C:/Users/yy/AppData/Roaming/marktext/images/2023-03-18-13-38-37-image.png" alt="" width="253">

###### *向量的点乘的计算方法*

同行元素相乘再相加

<img src="file:///C:/Users/yy/AppData/Roaming/marktext/images/2023-03-18-13-43-32-image.png" title="" alt="" width="371">

###### *向量的点乘在图形学中的应用*

1. 获取<mark>两个向量的夹角</mark>

2. 获取一个向量<mark>在另一个向量上的投影</mark>projection



### 向量的叉乘（外积、向量积）Cross Product

在三维几何中，向量a和向量b的外积结果是一个向量，有个更通俗易懂的叫法是<mark>法向量</mark>，该向量垂直于a和b向量构成的平面

###### *二维平面中向量的叉乘的计算方法*

![](https://latex.codecogs.com/svg.image?\overrightarrow{c}=\overrightarrow{a}\times&space;\overrightarrow{b}=\left\|\overrightarrow{a}&space;\right\|\left\|\overrightarrow{b}&space;\right\|sin\theta&space;)

###### *三维空间中向量的叉乘的计算方法*

<img src="file:///C:/Users/yy/AppData/Roaming/marktext/images/2023-03-18-22-29-41-image.png" title="" alt="" width="285">

或者用矩阵的方式来理解

<img src="file:///C:/Users/yy/AppData/Roaming/marktext/images/2023-03-18-22-30-11-image.png" title="" alt="" width="409">

###### *向量的叉乘满足结合律和分配律，但是不满足交换律*

<img src="file:///C:/Users/yy/AppData/Roaming/marktext/images/2023-03-18-22-17-07-image.png" title="" alt="" width="237">

###### *叉乘的右手螺旋定则*

假设向量a叉乘向量b等于向量c，将除大拇指外的四指弯曲，弯曲方向为<mark>向量a旋转到向量b 的方向</mark>，此时大拇指的方向就是向量c的方向

###### *向量的叉乘在图形学中的作用*

1. 已知向量a和向量b，则a和b的叉乘可以<mark>计算出垂直于a和b的新向量c</mark>

2. <mark>判断左/右</mark>，如果a叉乘b的结果z若为正，则b在a的左侧，否则相反

3. <mark>判断内/外</mark>，比如有如下![](C:\Users\yy\AppData\Roaming\marktext\images\2023-03-18-22-50-58-image.png)
   
   一个由3个向量<mark>首尾相连</mark>构成的三角形和点P，计算AP×AB、BP×BC、CP×CA，若结果<mark>都为正</mark>（p在所有向量的右侧）或<mark>都为负</mark>（p在所有向量的左侧）则说明<mark>P在三角形内部</mark>；否则P在三角形的外部



###### *附：为什么二维中叉乘的结果是一个实数而不是向量？*

详情见 [二维向量的叉积是标量还是向量？ - RunningSnail - 博客园](https://www.cnblogs.com/tgycoder/p/4901600.html)
