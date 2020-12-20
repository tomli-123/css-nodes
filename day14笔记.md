---
typora-copy-images-to: mdImg
---

# 学习目标

> - [ ] 能够写出3种常见的鼠标样式（cursor）
> - [ ] 能够说出CSS3新增的2个属性选择器使用方法
> - [ ] 能够说出结构伪类nth-child小括号中公式的常用写法
> 
> 。。。。。。

**理解上课的知识点......**



# 三种鼠标常见的样式

> 通过cursor属性来设置鼠标移入盒子中的样式

取值：

- **default** ：光标为一个箭头（默认样式） 
- **pointer** ：光标为一只小手（a标签的默认样式）
- **text** ：此光标指示文本 
- **move**：显示十字光标（表示可移动的效果）



# 属性选择器的一些匹配规则（知道即可）

> 可以通过标签的属性选择标签

```html
<style>
    /* 让带有class属性的div变成绿色*/
    div[class] {
        color: green;
    }
    /*让class属性值为sellmeng的div变红*/
    div[class="sellmeng"] {
        color: red;
    }
    /*让class属性值以very开头的div变粉色*/
    div[class^="very"] {
        color: pink;
    }
    /*让class属性值以meng结尾的div变蓝*/
    div[class$="meng"] {
        color: blue
    }
    /*让class属性值中有meng的div变黄*/
    div[class*="meng"] {
        color: yellow;
    }
</style> 
-------------------------------------------------
<body>
  <div class="sellmeng">小可爱</div>
  <div class="mengmengda">大可爱</div>
  <div class="veryclever">燕燕</div>
  <div class="verymeng">怡口莲</div>
  <div>棠哥</div>
</body>
```

- **E[class]**

  选择带有class属性的E元素。 

  如：选中**带有class属性**的元素为绿色

- **E[class="attr"]**

  选择带有class属性，并且属性值是attr的E元素

  如：选中**class属性值为sellmeng**的元素为黄色

- **E[class^="attr"]**

  选择带有class属性，并且属性值是 **以attr开头** 的E元素

  如：选中**class属性值以very开头**的元素为粉色

- **E[class$="attr"]**

  选择带有class属性，并且属性值是 **以attr结尾** 的E元素

  如：选中**class属性值以meng结尾**的元素为蓝色

- **E[class*="attr"]**

  选择带有class属性，并且属性值是 **包含attr** 的E元素

  如：选中**class属性值里包含meng**的元素为紫色

**常见的情况：**

选取input标签的不同形态

> 单独选中文本框或者按钮

**注意点：**

元素与[]之间不能有空格！！！



# CSS3相关属性拓展（了解）

> css这个语言是随着时间的推进，有不同的版本迭代更新的，而css3是对css2的一些效果的完善和拓充，新增了很多新功能。但是值得注意的是css3因为的新版本，一些老版本（低版本的浏览器是不支持的！！）这样就存在一些兼容性问题。

**遇到问题可以查阅相关的CSS手册** 



## 文字阴影（text-shadow）

> 在CSS3中可以给文字设置阴影效果

**代码：** `text-shadow: 10px 10px 5px red;`

```css
text-shadow:水平偏移 垂直偏移 模糊度 阴影颜色;
```

**取值：**

|    值    |               描述               |
| :------: | :------------------------------: |
| h-shadow | 必需。水平阴影的位置。允许负值。 |
| v-shadow | 必需。垂直阴影的位置。允许负值。 |
|   blur   |        可选。模糊的距离。        |
|  color   |        可选。阴影的颜色。        |

**有趣的案例：**

> 可以给一个文字设置多个阴影效果，中间使用逗号 "," 进行连接。

**火焰文字：**

![1](mdImg/1.png)

```css
h1:nth-child(3) {
    color: #fff;
    background-color: #000;
    text-shadow: 0 0 5px #fff, 0 0 20px #fefcc9, 10px -10px 30px #feec85, -20px -20px 40px #ffae34, 20px -40px 50px #ec760c, -20px -60px 60px #cd4606, 0 -80px 70px #973716, 10px -90px 80px #451b0e;
}
```

**霓虹文字：**

![2](mdImg/2.png)

```css
h1:nth-child(4) {
    background-color: #000;
    color: #fff;
    text-shadow: 0 0 10px #fff, 0 0 20px #fff, 0 0 30px #fff, 0 0 40px #ff00de, 0 0 70px #ff00de, 0 0 80px #ff00de, 0 0 100px #ff00de, 0 0 150px #ff00de;
}
```

**凹凸文字：**

![aotu](mdImg/aotu.png)

```css
/*凸出来文字*/
text-shadow: 1px 1px 1px #000,-1px -1px 1px #fff;
/*-----------------------------------------------------*/
/*凹进去文字*/
text-shadow: -1px -1px 1px #000,1px 1px 1px #fff;

/* 背景颜色和文字颜色为#666即可 */
```



## 盒子阴影/边框阴影（box-shadow）

> 类似于京东网页上，有盒子阴影的效果，同样可以通过CSS3中的box-shadow完成

![1](mdImg/1-1553007893501.png)

**代码：** `box-shadow: 10px 10px 10px #aaa;`

```css
box-shadow:水平阴影 垂直阴影 模糊距离 （外延值） 阴影颜色  （内/外阴影）；
```

|    值    |                   描述                   |
| :------: | :--------------------------------------: |
| h-shadow |     必需。水平阴影的位置。允许负值。     |
| v-shadow |     必需。垂直阴影的位置。允许负值。     |
|   blur   |             可选。模糊距离。             |
|  spread  |            可选。阴影的尺寸。            |
|  color   |            可选。阴影的颜色。            |
|  inset   | 可选。将外部阴影 (outset) 改为内部阴影。 |

**注意点：**

- 前两个属性是必须写的。其余的可以省略。
- 默认阴影是外部阴影，但是不能设置outset这个属性值。如果想要内部阴影，请设置inset 



## 背景图片大小（background-size）

> 有时候可以设置背景图片的大小

```css
background-size: 宽度 高度;
```



**取值（分别设置的是宽度和高度）：**

- 数字+px

- 百分比（相对于盒子的宽高百分比）

- 关键字

  **默认尺寸：**

  ![1.1](mdImg/1.1.png)

  - **contain（包含）**：将背景图片等比例缩放，直到**不会超出盒子**的最大

    > 直到宽度或者高度中**有一个和盒子相等**，并且背景图片**没有溢出部分**即止。

    ![1.3](mdImg/1.3.png)

  

  - **cover（覆盖）**：将背景图片等比例缩放，直到**填满整个盒子刚好**没有空白

    > 直到宽度或者高度中**有一个和盒子相等**，并且**背景图片填充满盒子**如果有溢出部分则被隐藏

    ![1.2](mdImg/1.2-1550336266662.png)

**注意点：**

- 在设置`background-size` 和`background`连写的时候注意覆盖问题

  - 要么单独写的写在连写的下面

  - 要么单独写的写在连写的里面

    ```css
    /* 连写完整版中，也有background-size属性，注意连写的覆盖问题 */
    background：color image repeat attachment position / size
    ```




## 多背景写法

> 在CSS3中，可以做到给一个盒子设置多个背景图片

使用背景的连写形式，通过逗号分隔不同的背景图片即可。

**注意点：**

- 每组背景属性之间需要通过逗号隔开
- 如果多组背景图片之间存在层叠关系，则前面的会覆盖在后面的背景图上
- 如果需要设置背景颜色，则背景颜色需要设置到最后一组中。

```css
background: url(images/d1.jpg) no-repeat right bottom,
		   url(images/dd.jpg) no-repeat left bottom,
		   pink url(images/d3.png) no-repeat center center; 
```



## 背景渐变

> 给一个元素设置 **background-image** 属性时，不仅可以通过url指定一张图片，还可以通过线性渐变(linear-gradient)或者径向渐变(radial-gradient)设置一张颜色渐变的背景图。

### 线性渐变

> 沿着一个方向颜色进行线性渐变

**例子：**`background-image: linear-gradient(green,yellow);` **（默认从上往下渐变）**

![2.9](mdImg/2.9.png)

**代码：** `background-image: linear-gradient(方向,颜色 范围,颜色 范围，......);`

**取值：**

- **方向：**
  - 方位名词：
    - `to top` 往上
    - `to bottom` 往下
    - `to left` 往左
    - `to right` 往右
  - 角度（deg）：记忆方法：时钟，往上是0deg，然后顺时针转动角度即可
- **颜色：**关键字、rgb表示法、rgba表示法、十六进制表示法
- **范围：**设置哪一点是纯色，不同颜色区间之间渐变

```js
//注意：渐变实际上相当与一张图片，因为需要加给background-image才会生效

//最简单的渐变(默认从上往下渐变)
background-image: linear-gradient(yellow, green);
//设定渐变的方向
background-image: linear-gradient(to right, yellow, green);
//也可以设定渐变的角度
background-image: linear-gradient(90deg, yellow, green);
//设定渐变的范围（不同颜色之间渐变，两端是最近的纯色）
background-image: linear-gradient(to right, yellow 30%, green 70%)
//特殊情况：纯色
background-image: linear-gradient(to right, yellow 50%, green 50%)
```



### 径向渐变

> 由中心向四周渐变（圆或者椭圆的效果）

**例子：** `background-image: radial-gradient(green,yellow);` （**默认从中点向四周渐变**）

![3.1](mdImg/3.1.png)

**代码：** `background-image:radial-gradient(半径 at 圆心位置 ，颜色 范围，颜色 范围，......)`

**取值：**

- **半径：**
  - 渐变范围圆的半径
- **圆心位置**
  - 关键字
    - 水平：left、center、right
    - 垂直：top、center、bottom
  - 数字+px
    - 具体的坐标
- **颜色：** 关键字、rgb表示法、rgba表示法、十六进制表示法
- **范围：**设置哪一点是纯色，不同颜色区间之间渐变

**取值：**

```css
/*1. 最简单的渐变*/
background-image: radial-gradient(red, green);

/*2. 指定圆心的关键字*/
background-image: radial-gradient(200px at center center, yellow, green);

/*3. 指定圆心的具体坐标*/
background-image: radial-gradient(200px at 100px 100px, yellow, green);

/*4. 指定范围*/
background-image: radial-gradient(200px at center center, yellow 50%, green 50%);
```



## 元素本身透明（opacity）

> 除了可以让背景颜色透明之外，还可以让元素整体（包括里面的内容）一起透明

**代码：** `opacity:0` 

**取值：** 0~1之间的一位小数

**注意点：**

- opacity会让元素整体透明，包括里面的内容（文字或者子元素）



