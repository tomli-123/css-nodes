---
typora-copy-images-to: mdImg
---



# 学习目标

>
>- [x] 能够说出WEB标准三个组成部分
>
>  - 结构：html
>  - 样式：css
>  - 行为：js（javascript）动态效果
>
>- [x] 能够写出HTML骨架结构标签
>
>  ```html
>  <html>
>      <head>
>          <title>网页的标题</title>	
>      </head>
>      <body>
>      	网页的主体内容，标签	
>      </body>
>  </html>
>  ```
>
>  
>
>- [x] 能够写出4-5个常见的双标签
>
>- [x] 能够说出图片标签以及alt和title区别
>
>  - 图片标签：img
>    - alt：替换文本
>      - 当图片加载失败（如：路径写错了）时，才显示的文字
>    - title：图片的标题
>      - 鼠标悬停在图片上时，才显示的文字
>
>- [x] 能够说出相对路径的三种形式
>
>  - 同级目录
>    - 直接写目标文件的名字
>  - 上级目录
>    - 去上一级目录 ../
>    - 直接写目标文件的名字
>  - 下级目录
>    - 先目标文件夹的名字
>    - 进入文件夹 /
>    - 直接写目标文件的名字
>
>。。。。。。



**理解上课的知识点**......



# 课前了解

## 课程整体安排

- html：3天
- css：6天
- 项目：5天

特点：慢、细、易

目的：为前端学习打基础



## 学习方法

- 预习和复习，特别是零基础

  > 上课的任务是听懂——》预习，
  >
  > 课后需要记忆的务必花时间记忆住——》复习

- 敢于问

  > 遇到问题时，敢于问同学或者老师
  >
  > ——》主动帮助同学解决方法



## 前端开发的准备工作

> 一些相关的操作

- 打字速度

  > 打字速度是程序员的基本操作

  - 严禁二指禅：要养成一个正确的指法（金山打字）
  - 打字速度越快越好：要求最终达到120单词/min

- 使用字典

  > 代码中有很多英文，词典帮助学习记忆

  - 随时使用词典, 不会的单词就查出来记忆

- 文件后缀名显示

  - 查看——》文件扩展名



## WIN常用快捷键

> 快捷键的使用可以提高开发效率

- Ctrl + C：复制
- Ctrl + V：粘贴
- Ctrl + X：剪切
- **Ctrl + S：保存**
- Ctrl + N：新建
- Ctrl + A：全选
- Ctrl + Z：撤销上一个操作
- win + E：打开资源管理器
- Alt + tab：切换程序（注意Alt键不松手）
- Win + D：切换到桌面
- Win + R：快速运行
  - cmd：运行命令行           
  - calc：运行计算器
  - mspaint：运行画图工具
  - notepad：运行记事本



## 学习要求

- 上课互动：防走神，防瞌睡

- 课后代码：老师上课的代码至少敲3遍（重要的是通过上课的代码理解知识点！！），之后再做作业，然后还有余力的同学预习第二天的笔记（会与熟练两码事）

- 注意点：

  - 精力放在重点，了解内容记住即可（不要钻牛角尖）
  - HTML和CSS比较灵活（不易报错），按照 **规范** 敲正确的代码




##### ------------------------课前安排



# 前端基本知识点铺垫

> 你觉得前端是做什么的？

## 认识网页（了解）

- 问题1：网页的基本组成元素有哪些？

  > 文字、图片、超链接、音频、视频

- 问题2：我们看到的网页背后是什么？

  > 程序员写的代码

- 问题3：代码如何转化成页面的？

  > 浏览器会把代码转化（解析）成网页



**少了浏览器可以吗？**

> 浏览器将代码解析成网页，供用户访问 ! 用户不会去看代码，所以浏览器很必要！



## 五大浏览器介绍（记忆）

> 浏览器是网页运行的平台。

![](mdImg/b.png)

**五大浏览器：**

- IE浏览器
- Firefox浏览器：火狐浏览器
- Chrome浏览器：谷歌浏览器
- Safari浏览器
- Opera浏览器：欧朋浏览器

**谷歌浏览器：**访问速度快、用户体验好、开发调试功能齐全，之后的学习过程中，统一使用谷歌

![浏览器市场份额](mdImg/浏览器市场份额-1534863774223.PNG)





### 浏览器内核（渲染引擎）

> 浏览器的内核（渲染引擎）相当于汽车的发动机，是最核心的存在。

**作用**：将代码解析并渲染成用户眼中的界面

**内核的种类：**

- Trident：IE浏览器、猎豹安全浏览器、360极速浏览器
- Gecko：Firefox 浏览器
- Webkit：Safari浏览器、傲游浏览器3、Symbian手机浏览器、Android 默认浏览器
- Blink（Webkit的分支）：Chrome浏览器、Opera浏览器



**回顾一下：**五大浏览器的内核分别是什么？

ie：trident

火狐：gecko

safari：webkit

谷歌浏览器：blink

欧朋：blink





## Web标准的组成（记忆）

> 在制作网页时需要有一个标准和规范

### Web 标准构成

> 将页面分为三层：结构、样式、行为。

- **结构：**HTML——》页面骨架（组成元素）
- **样式：**CSS——》页面样式
- **行为：**JS（JavaScript）——》页面动态效果

### 图解Web标准

> 如果把一个页面看成一个人

**结构标准：**决定是否有一个好的身体。

![hb1](mdImg/hb1.png)

**样式标准：**决定是否化妆的美丽漂亮。

![hb2](mdImg/hb2.png)

**行为标准：**决定是否有吸引人的行为。



![hb3](mdImg/hb3.jpg)

# HTML的基本认识

## HTML初识（了解）

**概念**：HTML（英文：**Hyper Text Markup Language**）中文译为：**超文本标记语言**

> 主要是通过HTML标签对网页中的文本、图片、声音等内容进行描述。——》用HTML标签表示需要显示的效果

##### ヾ(๑╹◡╹)ﾉ" 变粗案例（在网页中显示一个变粗的文字）

说白了HTML就是用尖括号包裹起来的英文单词（标签），浏览器看得懂标签，对不同的标签有对应的显示效果

```
如：<strong>加粗</strong>  <h1>大标题</h1>  等等
```

## HTML骨架结构 

> 写网页类似于写文章，文章有对应的格式，HTML也有规定的格式。

![mess](mdImg/mess.png)



**HTML的固定格式：**

```html
<html>
    <head>
        <title>页面的标题</title>
    </head>
    <body>
        写自己的代码
    </body>
</html>

为了便于阅读：包含关系的标签使用用缩进
```

**注意：**结构不会在我们的页面上显示，但是却会让我们的代码结构更加清晰明确（**规范**）



> 猪猪女孩记忆法

![](mdImg/pig.png)

##### ヾ(๑╹◡╹)ﾉ"书写我们的第一个HTML页面

1. 新建一个demo 的.txt文件
2. 把后缀名改为 .html
3. 使用记事本写入刚才的HTML骨架
4. 右击 —》谷歌浏览器打开

##### ----------------------------

## 开发工具的基本使用

> 使用记事本虽然可以敲代码，但是开发的效率实在太低，实际开发中，我们会通过使用开发工具来提高咱们的开发效率。

![](mdImg/s.png)

### VScode的使用

#### 使用 VScode 新建页面

1. 将代码文件夹拖进VScode中
2. 点击上方的 `+` 创建页面，注意：后缀名需要是 **`.html`** 

##### ヾ(๑╹◡╹)ﾉ"用VScode 写一个页面骨架

#### VScode 的快捷键

- 新建文件: `ctrl + n`
- 保存文件 : `ctrl + S `
- 快速生成一个标签：`英文+tab`
- 生成结构代码: `html:5 + tab` 或者 `! + tab`   (前提：必须是后缀.html文件)
- 快速复制一整行：`ctrl + c` 再`ctrl + v`
- 删除一行： `Ctrl+X`

- 注释 : ctrl + / 

  > 注释：在代码中展示，页面渲染时会忽略，用户看不到，给程序员看。`<!-- 需要注释的内容-->`

  ![zs](mdImg/zs.png)

##### ヾ(๑╹◡╹)ﾉ"偷偷夸老师

 

## HTML的其他介绍（了解）

> 需要知道的几个小点

### 标签的关系

> 嵌套关系（父子关系）

```html
父标签、父元素
<head>
    子标签、子元素
    <title></title>  
</head>
```

![father](mdImg/father.jpg)

> 并列关系（兄弟关系）

```html
<head></head>
<body></body>
```

![xiong](/mdImg/xiong.jpg)



##### ヾ(๑╹◡╹)ﾉ"测试题

请问下列哪个标签是错误的？（父子关系可以通过缩`tab`进表示）

- [ ] ```html
  <head></head>
  <body></body>
  ```
  
- [ ] ```html
  <div><p></p></div>
      ```
  
- [x] ```html
  <head><title></head></title>
  ```

- [ ] ```html
  <body><div></div></body>
  ```



### HTML的标签分类

**双标签：**

如：`<strong>标签的内容</strong> `

语法：`<开始标签> 标签内容 </结束标签>`

例：`<strong>我要变粗</strong>` ` <head></head>`......

> 在<>中写的英文单词——》标签名

**单标签：**

如：`<br>`

语法：`<标签名>`

例：`<br>` `<hr>` ......



# HTML的标签学习

> 标签其实就是用<>包裹的英文单词，所以记住对应的英文单词并且会使用即可

##  标题标签：h 系列的标签 (Head) 

> 例如：新闻网页的都会有一个新闻标题，效果就是用标题标签完成的

**作用** : 给页面上的文字加上标题的语义

**代码** : 

```html
<h1>1级标题</h1>
<h2>2级标题</h2>
<h3>3级标题</h3>
<h4>4级标题</h4>
<h5>5级标题</h5>
<h6>6级标题</h6>
```

**显示效果** :  

- 文字都有变大，但是从h1~h6文字逐渐减小
- 文字都有加粗
- 独占一行

**注意** :  一般网页中h1标签不能乱用，一般只会用在新闻的标题或者网页的logo上

> 因为h1标签对于seo：搜索引擎优化比较重要



## 段落标签：p 标签 (Paragraph) 

> 例如：网页中的段落，就是通过段落标签来完成效果的

**作用**:   给页面上的一段文字加上段落语义

**代码**:  `<p>这是段落</p>`

**特点**：

- 段落与段落之间有间隙
- 独占一行



## 水平线标签：hr 标签 (Horizontal Rule)

> 它就是在网页中显示一条水平线

**作用**: 在页面上显示一条`横线`

**代码**: `<hr>`

##### ヾ(๑╹◡╹)ﾉ"可以写一个新闻页面了

![sh](mdImg/sh.png) 

##### ---------------------------

## 换行标签：br 标签 (break row=行)

**作用**：强制换行

> 在代码中直接换行无效

**代码**：`<br>`



## 文本格式化标签   

> 网页中有时候需要让文字有加粗、下划线、倾斜、删除线这样的效果，在没有学习css之前，咱们可以使用文本格式化标签来完成效果

**第一组**:

- b: 加粗
- u: 下划线
- i: 倾斜
- s: 删除线

> **建议不要使用,  因为这些标签没有语义**
>
> **语义就是标签的含义**，比如：标题标签的语义就是标题的含义，段落标签的语义就是段落的含义

**第二组**: 

- strong: 加粗
- ins: 下划线
- em: 倾斜
- del: 删除线

> **可以使用**
>
> **语义: 起强调加强语气作用**



## 标签的属性（了解）

![标签的属性](mdImg/%E6%A0%87%E7%AD%BE%E7%9A%84%E5%B1%9E%E6%80%A7-1535339910214.png)

> 属性为 HTML 元素提供附加信息。
>
> ——》让同一种标签有不同的显示效果



**问题：**如果想让两个水平线颜色不一样，可以怎么完成呢？

> 可以通过添加颜色属性的方式来完成。

**代码：**

```html
<hr color="red" width="400" />
```

**格式：**

```html
<标签名 属性名1="属性值1" 属性名2="属性值2" …> 内容 </标签名>
```

**注意点：**

- 标签可以同时有多个属性，并且属性之间以空格隔开（规范）
- 标签名与属性名之间，必须以空格隔开！
- 属性与属性之间没有顺序关系！ 
- 每个标签上的属性并不是完全相同

> 提倡：尽量不使用样式属性，因为样式之后是通过css控制的



## 图片标签：img 标签 (image)

> 经常需要在网页中显示一张图片，此时可以通过图片标签来显示。

**作用：**  在页面中显示一张图片

**代码：** `<img src="图像路径" />`

**属性：** 

- src：图片的路径（**必须**）

  > 告诉浏览器要显示的图片是哪一张

- alt：替换文本

  > 如果图片加载不出来，会显示这个属性中的文字

- title：图片的标题

  > 当鼠标悬停在图片上时，才会显示的文字

- width：图片的宽度

  > 如果只设置了图片的宽度，此时图片的高度会等比例缩放

- height：图片的高度

  > 如果只设置的图片的高度，此时图片的宽度会等比例缩放

**注意点：**一般只会设置width或者height中的一个，如果同时设置了宽度和高度，图片有可能拉伸变形！！



# 路径问题（小难点）

> 类似于现实生活中坐地铁
>

![地图](mdImg/%E5%9C%B0%E5%9B%BE.PNG)

> **理解：当前文件找目标文件的过程**
>
> 当前文件：当前html页面
>
> 目标文件：要显示的图片

![文件路径](mdImg/%E6%96%87%E4%BB%B6%E8%B7%AF%E5%BE%84-1535340133797.PNG)

### 绝对路径

> 基础班中一般不用

- 在个人电脑中，带有盘符的路径： `C:/Users/梓越/Desktop/3.jpg`
- 外部链接，带有`http://` 开头的路径：`http://www.itcast.cn/`

##### ---------------------------

### 相对路径

> 用的较多

#### 同级目录

![同级目录](mdImg/同级目录.png)

如：页面与图片同一级目录——》**类比于：我们俩都在大厅**

**步骤：**

1. 直接写目标文件的名字即可

```html
<img src="目标图片.gif">
或者
<img src="./目标图片.gif">
```



#### 下级目录

![下级目录](mdImg/下级目录.png)



如：图片在同级目录的image文件夹里面——》**类比于：我在大厅，你在房间里**

**步骤：**

1. 写目标文件所在文件夹的名字
2. 进入文件夹 /
3. 直接写目标文件的名字即可

```
<img src="images/目标图片.gif">
```



#### 上级目录

![上级目录](mdImg/上级目录.png)

如：如果图片在页面的上一级目录——》**类比于：我在房间，你在大厅**

**步骤：**

1. 去上一级目录 ../
2. 直接写目标文件的名字即可



```html
<img src=”../目标图片.gif” >
```

##### ヾ(๑╹◡╹)ﾉ"路径例子