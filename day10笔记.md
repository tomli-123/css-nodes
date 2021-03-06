---
typora-copy-images-to: mdImg
---

# 学习目标

>
>- [x] 能说出定位常见的使用场景(定位的目的）
>  - 盒子与盒子之间的层叠问题
>- [x] 能够说出绝对定位和相对定位是否占有位置，是以谁为准对齐位置
>  - 绝对定位
>    - 相对谁？
>      - 如果祖先元素中没有定位的元素——》相对于浏览器的可视区域进行移动
>      - 如果祖先元素中有定位的元素——》相对于最近的有定位的祖先元素进行移动
>    - 不占位置——》已经脱标：脱标之后的元素宽高默认由内容撑开
>  - 相对定位
>    - 相对于自己原来的位置进行移动
>    - 占位置——》没有脱标
>- [x] 能够说出固定定位是否占有位置，是以谁为准对齐位置
>  - 不占位置——》已经脱标了
>  - 始终相对于浏览器进行 移动
>- [x] 能够说出定位中为什么常用子绝父相(子绝父相的由来）
>  - 子绝父相了之后，父元素相对定位还占位置，不影响其他盒子的布局
>- [x] 能够说出定位的盒子水平垂直居中对齐的算法
>  - 子绝父相
>  - left：50%
>  - top：50%
>  - transform：translate(-50%,-50%)
>- [x] 能够使用z-index控制定位元素的层级
>  - z-index：定位元素的层叠
>  - 取值：数字——》数字越大，层级越高
>- [x] 能够说出结构伪类nth-child小括号中公式的常用写法
>  - 偶数
>    - 2n
>    - even
>  - 奇数
>    - 2n+1
>    - 2n-1
>    - odd
>
>
>。。。。。。



**理解上课的知识点......**



# 定位

> 可以解决盒子与盒子之间的层叠问题

**需求：**现在在页面上有两个盒子，其中第二个盒子将第一个盒子压住了一半，怎么完成？？？

![1](mdImg/1.png)

**解决方案：**

- **使用margin的单方向应用**

  > 但是实际开发中并不会使用marign完成层叠的效果

- 使用 **定位** 来完成效果

  ```css
  .blue {
    /*定位：position*/
    position: absolute;
    /*定位需要配合方位属性一起使用的！！*/
    top: 150px;
    left: 150px;
  }
  ```

## 定位初体验

`position：absolute；` 设置定位

**方位属性：**

> 水平和垂直方向各选一个使用即可，选取的原则是**就近原则** （离哪边近用哪个）

- 水平方向：
  - left：相对于左边框的距离
  - right：相对于右边框的距离
- 垂直方向：
  - top：相对于上边框的距离
  - bottom：相对于下边框的距离

## 静态定位：static

> 标准流中的元素默认都是静态定位

**代码：** `position: static;` （默认值）静态定位

> 静态定位是有一定争议的（有些人认为静态定位不算定位）

**面试时候回答：**三种定位方式，优先回答其他三个（相对、绝对、固定），如果四种再写静态定位

**注意点： **

- 静态定位不能通过方位属性进行移动
- 之后说的定位都特指相对、绝对、固定，不包括静态定位。



## 相对定位：relative

> 自恋型：盒子相对于自己之前的位置定位移动

**代码：**`position: relative；` 相对定位

**特点：**

- 要配合方位属性使用，不然无法移动

- 相对于自己原来的位置进行偏移

- 设置了相对定位的元素在页面上占据了位置——》**没有脱标**

**应用场景：**

- 配合绝对定位组CP（子绝父相），用的最多
- 用于小范围的移动（比如让某个标签稍微往下移动几个像素）



## 绝对定位：absolute

> 拼爹型：绝对定位相对于非静态定位的父元素进行定位移动

**代码：**`position: absolute; ` 绝对定位

**特点：**

- 需要配合方位属性移动使用

---


- 绝对定位相对谁移动？

  > 默认相对于浏览器进行移动，但是如果祖先元素中有定位（相对、绝对、固定），则相对于最近的有定位的祖先元素进行移动
  >

  - 祖先元素没有定位→ 默认相对于浏览器进行移动
  - 祖先元素有定位→ 相对于最近的有定位的祖先元素进行移动

- 绝对定位的元素在页面中 **不占位置** → 脱标

**应用场景：**

- 子绝父相

## 子绝父相

> 让子元素相对于父元素进行移动 → 使用子绝父相，即子元素绝对定位，父元素相对定位

子绝父相在定位中使用的最常见，并且子绝父相不会影响页面的布局

##### ヾ(๑╹◡╹)ﾉ"比较子绝父相的好处

> 不会影响之后的布局

**特殊情况：** 当使用子绝父相的时候，父元素已经有绝对定位了，此时忽略父元素，直接使用子绝即可

> 子绝父绝的特殊情况

---

##### ヾ(๑╹◡╹)ﾉ"子绝父相定位居中案例

```
父盒子：600*400  子盒子：200*100
```

**需求1：** 通过定位让子盒子在父盒子水平居中

**思路：**

1. 先让子盒子往右移动父盒子的一半

   > 子绝父相，`left：50%;`

2. 再让子盒子往左移动自己的一半

   - 普通做法：`margin-left:负子盒子宽度的一半` → 属性值是**负数**

     > 缺点：子盒子宽度变化之后，需要重新改代码

   - 优化做法：CSS3的新属性：`transform：translateX（-50%）`

     > `transform：translateX（-50%）` → 表示沿着x轴的负方向移动自己的一半

##### ------------------

**需求2：** 通过的定位让子盒子在父盒子中水平垂直都居中

同理嘛~

> 但是需要注意，transform属性也会层叠。



##### ヾ(๑╹◡╹)ﾉ"课堂练习：网站头部hot图标

![hot](mdImg/hot.png)

##### ヾ(๑╹◡╹)ﾉ"课堂练习：小米商品页半透明效果

![toumin](mdImg/toumin.png)

## 固定定位：fixed

> 死心眼型：盒子相对于浏览器进行定位移动

**代码：**`position: fixed; `  固定定位

**特点：**

- 配合方位属性一起使用

- 永远相进行移动
- 固定定位的元素也不在页面中占据位置 → **脱标**



##### ヾ(๑╹◡╹)ﾉ"课堂练习：新浪网页

> 注意的是：脱标后的元素宽度默认由内容撑开
>
> 就算是div，脱标之后宽度也不再默认是父元素宽度

##### -----------------------------

## 四种定位总结

| 定位方式 |  属性值  |            相对于谁移动             |    占不占位置    |
| :------: | :------: | :---------------------------------: | :--------------: |
| 静态定位 |  static  |        不能通过方位属性移动         |      占位置      |
| 相对定位 | relative |        相对于自己原来的位置         |      占位置      |
| 绝对地位 | absolute | 默认浏览器/相对于有定位的父元素移动 | 不占位置（脱标） |
| 固定定位 |  fixed   |          永远相对于浏览器           | 不占位置（脱标） |



# 元素的层级关系

> 开发者有时候需要设置元素的层级关系，层叠是谁在上面



## 标准流、浮动、定位的层级关系

> 两个盒子之间的比较

```
三种层叠关系：
标准流 < 浮动 < 定位（相对、绝对、固定）
```


## 定位的层级关系

**总结：**

- 三者的层叠关系**相同**，HTML中写在下面元素的覆盖上面的

- 可以通过 `z-index` 属性手动设置定位元素的层级关系

  **取值：**没有单位的数字

  **效果：**数值越大，层级越高



# 垂直对齐方式：vertical-align

> 在开发中可能会遇到行内块元素垂直对齐的问题，此时可以使用 `vertical-align` 属性让图片

**问题：**  当图片和文字在一行中显示时，其实底部是不对齐的！

> 图片和文字底部对齐怎么做？

![q1](mdImg/q1.png)

**解决方法：**

此时可以给图片设置 `vertical-align:bottom;` 即可

> `vertical-align` 就是用来设置行内/行内块元素垂直对齐的问题的

---

**取值：**

- baseline：基线对齐
- top：顶部对齐
- middle：中线对齐
- bottom：底部对齐

**项目中可以使用 `vertical-align` 解决的bug：**

- 场景1 :  文本框（text）和表单按钮（button）无法对齐问题；
- 场景2 :  input 和 img无法对齐的问题；
- 场景3 : div里放一个文本框 ，此时文本框无法靠顶；
- 场景4：div有img标签撑开，此时img标签下方有间隙（给img标签设置vertical-align即可）；
- 场景5 : 使用line-height让img标签垂直居中，需要给img标签单独设置vertical-align：middle

**注意点：**

在学习完浮动之后，就不推荐优先使用行内块元素让div一行中显示，因为会出现垂直对齐的问题，以后**优先使用浮动完成效果**

##### -----------------------------

# css3拓展

## 结构伪类选择器

> 通过标签的结构关系找到对应的元素
>
> 如果现在想找到ul标签下面的第几个li标签的时候，除了使用class大法之外，还可以使用结构伪类选择器完成效果

**如果要找第一个li标签呢？**

- **E:first-child** ：选择其父元素的第一个子元素并且是E元素

  > 还会判断是否是E元素，是才设置样式。（既是E标签，又是父元素的第一个子元素）

  ```html
  比如：li：first-child {css样式}
  查找过程如下：
  1、首先找到li 
  2、找li标签的父元素
  3、找父元素第一个子元素
  4、看这个子元素是不是li
  	1、是-》加样式
  	2、不是-》不加样式
  ```

------

**如果要找最后一个li标签呢？**

- **E:last-child** ：选择其父元素的最后一个子元素并且是E元素

  > 还会判断是否是E元素，是才设置样式。（既是E标签，又是父元素的最后一个子元素）

  ```html
  比如：li：last-child {css样式}
  查找过程如下：
  1、首先找到li 
  2、找li标签的父元素
  3、找父元素最后一个子元素
  4、看这个子元素是不是li
  	1、是-》加样式
  	2、不是-》不加样式
  ```

------

**如果要找第12个li标签呢？**

- **E:nth-child(n)** ： 选择其父元素的第n个子元素并且是E元素

  > 还会判断是否是E元素，是才设置样式（既是E元素，又是父元素的第n个子元素）

  ```html
  比如：li：nth-child(n) {css样式}
  查找过程如下：
  1、首先找到li 
  2、找li标签的父元素
  3、找父元素第n个子元素
  4、看这个子元素是不是li
  	1、是-》加样式
  	2、不是-》不加样式
  ```

  **注意：**

  针对于nth-child括号中可以写一个带n的式子，n的取值范围是**0~正无穷的整数**

  - 找到所有的**偶数**：`2n/even`
  - 找到所有的**奇数**：`2n-1 / 2n+1 /odd`
  - 找到**前12个**：`-n+12`
  - ......(更多新奇的玩法等待你的发现)

------

**如果要找倒数第12个li标签呢？**

- **E:nth-last-child(n)**：选择其父元素的**倒数**第n个子元素并且是E元素

  > 判断是否是E元素。（既是E元素，又是父元素的**倒数**第n个子元素）

  ```html
  比如：li：nth-last-child(n) {css样式}
  查找过程如下：
  1、首先找到li 
  2、找li标签的父元素
  3、找父元素倒数第n个子元素
  4、看这个子元素是不是li
  	1、是-》加样式
  	2、不是-》不加样式
  ```

------

**如果列表中混入了奸细，怎么才能找到第一个li标签呢？**

- **E:nth-of-type(n)**：选择其父元素的第n个E元素

  > 选择的是子元素中的第n个E元素

  ```html
  比如：li：nth-of-type(n) {css样式}
  查找过程如下：
  1、首先找到li 
  2、找li标签的父元素
  3、找父元素的第li个E元素
  ```

