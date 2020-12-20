---
typora-copy-images-to: mdImg
---

# 学习目标

>
> - [x] 能够写出背景图片是否平铺、以及背景图片的位置
>   - 背景图片是否平铺
>     - background-repeat
>       - **不平铺：no-repeat**
>       - 平铺：repeat
>       - 水平平铺：repeat-x
>       - 垂直平铺：repeat-y
>   - 背景图片的位置
>     - background-position：水平  垂直
>       - 方位名词
>         - 水平方向：
>           - left
>           - center
>           - right
>         - 垂直方向:
>           - top
>           - center
>           - bottom
>       - 数字+px（坐标）
> - [x] 能够说出元素显示模式分为哪三种模式
>   - 块级元素
>     - display：block
>   - 行内元素
>     - display：inline
>   - 行内块元素
>     - display：inline-block
> - [x] 能说出行内元素和块级元素区别
>   - 行内元素
>     - display：inline
>     - 一行可以显示多个
>     - 不可以直接设置宽高
>     - 宽高默认都是由内容撑开的
>   - 块级元素
>     - display：block
>     - 独占一行
>     - 可以直接设置宽高
>     - 宽度默认占满父元素的一行，高度由内容撑开的
> - [x] 能够写出行内元素和块级元素的转换代码
>   - 转换成行内元素：display：inline
>   - 转换成行内块元素：display：inline-block
>   - 转换层块级元素：display：block
> - [x] 能够写出单行文本垂直居中的代码
>   - line-height：当前标签的高度
> - [x] 能够写出链接伪类选择器a语法
>   - a:link a标签未访问过的状态
>   - a:visited  a标签访问过之后的状态
>   - **a:hover a标签鼠标悬停的状态**
>   - a:active a标签鼠标按下的状态
>
> 。。。。。。



**理解上课的知识点**......



# CSS属性的学习

## 背景相关的属性

> 开发中经常会给标签设置背景颜色、背景图片等效果。

### 背景颜色：background-color

> 设置标签的背景颜色

**代码：**`background-color: red;`

**取值：**之前介绍的颜色的取值就可以



### 背景图片：background-image

> 设置标签的背景为图片

**代码：**`background-image: url(图片路径);`

**注意：** 背景图片默认有平铺效果



### 背景平铺：background-repeat

> 设置标签的背景图片是否平铺

**代码：**`background-repeat: no-repeat；`

**取值：**

|    值     |         描述          |
| :-------: | :-------------------: |
|  repeat   |  背景平铺（默认值）   |
| no-repeat |        不平铺         |
| repeat-x  | 水平方向（沿x轴）平铺 |
| repeat-y  | 垂直方向（沿y轴）平铺 |



### 背景附着：background-attachment（了解）

> 设置标签的背景图片是否随着页面的滚动而移动（用的不多）

**代码：** ` background-attachment: scroll;`

**取值：**

|   值   |                       描述                       |
| :----: | :----------------------------------------------: |
| scroll | 背景图像会随着页面其余部分的滚动而移动（默认值） |
| fixed  |    当页面的其余部分滚动时，背景图像不会移动。    |



### 背景位置：background-position

> 设置背景图片的位置

**代码：**`background-position: 水平方向的位置（x） 垂直方向的位置（y）；`

**取值：**

- 关键字
  - 水平方向
    - left：左边
    - center：中间
    - right：右边
  - 垂直方向：
    - top：上边
    - center：中间
    - bottom：下边

- 具体像素（坐标）

  > 以盒子的左上角为原点（0,0），水平向右为x轴，垂直向下为y轴，构建一个坐标系。

  - 第一个值：是X轴的坐标
  - 第二个值：是Y轴的坐标

  然后找到对应的坐标点，将图片的左上角与坐标点重合即可。



### 连写形式

> 可以通过background属性设置背景的连写形式

**代码：**

```css
div {
    /*背景颜色*/
    background-color: pink;
    /*背景图片*/
    background-image: url(200.jpg);
    /*背景平铺*/
    background-repeat: no-repeat;
    /*背景附着*/
    background-attachment: scroll;
    /*背景位置*/
    background-position: center center;
}
/*--------------------------------------*/
div {
    /*连写形式*/
    background: pink url(200.jpg) no-repeat scroll center center;
}
```

#### 书写顺序

```js
/* background：背景颜色  背景图片  背景平铺  背景附着  背景位置 */

/* background:color image repeat attachment position; */

background: red url(1.jpg) no-repeat scroll center center;
```

#### 省略问题

- 按照需求省略即可
- 特殊情况：当元素的大小和背景图片的大小一样时，此时可以只写`background:url(200.jpg)` 即可



**省略的覆盖问题：**

如果需要同时设置单独的样式和连写的样式，可以

- 把单独的样式写在连写的下面
- 把单独的样式写在连写的里面

##### ヾ(๑╹◡╹)ﾉ"英雄联盟案例（熟悉背景操作即可）

##### -----------------------------

# 元素三种显示方式（重要）

> 标签有很多，但是其显示的方式一般我们把它分为三种
>
> 学习显示方式之后，我们就可以属性各种标签的显示特点了



## 块级元素

> div就是一个块级元素

**属性：** `display : block；`

**显示特点：**

- 独占一行（一行只能显示一个）

- 宽度默认是父元素的宽度

- 可以设置宽高

  可以设置宽高！！

**代表：**

- div、p、h（记忆）

> 除此之外还有很多

```
div,p,ol,li,ul,dt,dd,dl,header,footer,aside,nav,article,section......
```



## 行内元素

> span就是一个行内元素

**属性：** `display : inline；`

**显示特点：**

- 一行可以显示多个

- 宽度和告诉默认都是由内容撑开的

- 不可以设置宽高

  不可以设置宽高的

**代表：**  

- span、a

> 除此之外还有很多

```
a,span,b,u,s,i,strong,ins,del,em......
```



## 行内块元素

> input就是一个行内块元素

**属性：** `display: inline-block ;` 

**特点：**

- 一行可以显示多个 (像是行内)
- 可以设置宽高  (像是块级)

**代表：**  

- input、img、textarea、select、button



## 三种显示方式的转换

> 如果需要让元素的显示效果改变，可以进行显示方式的转换

- `display: block;` 转成块级
- `display: inline;` 转成行内
- `display: inline-block;` 转成行内块



##### ヾ(๑╹◡╹)ﾉ"low导航（都是a标签 60*40）字体大小12px

![nav](mdImg/nav.png)

**注意：p这种段落标签不要嵌套块级元素**（**惊天BUG**）

> 用p标签里嵌套一个div，此时给p标签设置宽高100px，背景红色，给div设置宽高100px，背景颜色蓝色，请问此时页面中是什么效果？？

**html中的嵌套的规范：**

- p标签中不要嵌套块级元素（div、p、h）
- a标签里面可以嵌套任意，但是不要嵌套a

##### -----------------------------



# CSS属性的学习

## 行高：line-height

> 针对于设置的行高，也叫做行间距。
>
> 浏览器会自动计算 `行高-文字` 之后的值，将剩下的值上下对半分，形成默认的垂直居中的效果

![行间距](mdImg/行间距.png)

##### ヾ(๑╹◡╹)ﾉ"画图演示基线

> 行高有的概念中说的是：基线到基线的距离

![line-height](mdImg/line-height-1592557296570.png)

**注意点：**

- 一些文档中的行高指的是：两行文本之间基线到基线的距离，其实开发中可以直接量顶线到顶线的距离即可
- 文本在一行中默认是垂直居中的，所以需要让文本在标签中垂直居中，只需要设置一行的高度为标签的高度即可

**作用：**

- 让单行文本在标签中垂直居中

  > line-height: 标签的高度;

- 控制两行文本之间的上下距离





### 行高能让哪些元素垂直居中

> 行高除了可以让单行文本垂直居中之外，还可以让其他元素垂直居中

- 单行文本

- span、a标签（行内元素）

- input、img标签（行内块元素）

  > 特殊情况：要让 `img标签`  通过 `line-height垂直居中` ，需要单独给 `img标签` 设置 ` vertical-align: middle;` 属性

如果想让以上元素垂直居中，需要配合以上元素的所在标签（父元素）设置 `line-height:标签的高度` 



### 行高与font的连写

> 字体连写里面还有行高属性

**完整版的font连写形式：**

`font: style weight size/line-height family`

**注意点：**

- line-height 如果写在 font 连写前面，会被层叠掉

  ```css
  /*line-height书写位置：*/
  /*1. 写在font里 OK */
  font: italic bold 20px/200px '楷体';
  
  /*2. 写在font后面 OK*/
  font: italic bold 20px '楷体';
  line-height: 200px;
  
  /* 3. 写在font前面 会覆盖  */
  line-height: 200px;
  font: italic bold 20px '楷体';
  /* 因为font的连写中有行高属性，连写中省略相当于设置了默认值 */
  ```

- 如果用到了line-height和font的连写

  - 要么把 `line-height` 写在 `font连写`的下面
  - 要么把 `line-height` 写进 `font连写` 的里面 



# 选择器的学习

## 链接伪类选择器

> 不仅仅是选中某个标签，而是选择的元素的某种**状态**
>
> 我们可以手动设置a标签不同状态的颜色（或者其他样式）

```js
/*选中a标签没有点击过时状态*/
a:link {
    color: red;
}

/*选中a标签点击之后的状态*/
a:visited {
    color: pink;
}

/*选中鼠标移入时的状态*/
a:hover {
    color: yellow;
}

/*选中鼠标按下的状态*/
a:active {
    color: blue;
}
```

**注意点：**

- 四种链接伪类选择器的**顺序固定**

  `link visited hover active`

  可以联想记忆：

  `lvha → 看见lv包包就ha哈笑`

- hover用的较多，并且可以给其他标签使用。其他的几乎不用

##### ヾ(๑╹◡╹)ﾉ"五彩导航



## :focus 伪类选择器

> 针对于input系列标签还存在一个获取焦点的状态，同样也可以通过focus这种伪类选择器选中

**定义：**:focus 伪类选择器用于选取获得焦点的表单元素。

焦点就是光标，一般情况 `<input>`  类表单元素才能获取



# 居中方法小总结

## 水平居中的方法

```
text-align:center
1、文本
2、行内元素（span/a）
3、行内块元素（input/img）
```

```
margin：0 auto：
1、块级元素
```

## 垂直居中的方法

```
line-height：标签的高度；
1、单行文本
2、行内元素（span/a）
3、行内块元素（input/img）
   注意：img需要加 vertical-align : middle（垂直对齐方式居中）
```

> 那块级元素垂直居中怎么实现呢？→ 这个就需要使用到之后学习的定位知识来完成了
>