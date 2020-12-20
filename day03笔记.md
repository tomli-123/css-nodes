---
typora-copy-images-to: mdImg
---

# 学习目标

>
> - [x] 能够写出input标签中4-5个常用的type值
>
>   ```html
>     <input type="text">
>     <input type="password">
>     <input type="radio">
>     <input type="checkbox">
>     <input type="file">
>     <input type="submit">
>     <input type="reset">
>     <input type="button">
>     <input type="image" src="路径">
>   
>     <input type="url">
>     <input type="email">
>     <input type="date">
>     <input type="tel">
>     <input type="number">
>   ```
>
>   
>
> - [x] 能够写出单选框和复选框默认选中状态的属性
>
>   - checked="checked"：单选和多选的默认选中
>
>   
>
> - [x] 能够写出HTML5新增的3~4个语义化标签
>
>   - **header**
>   - **nav**
>   - **footer**
>   - aside
>   - section
>   - article
>
>   
>
> - [x] 能够写出HTML5新增video视频标签
>
>   - 视频标签：video
>     - src：路径
>     - controls：控制器
>     - autoplay：（有兼容性问题）自动播放
>     - loop：（有兼容性问题）循环播放
>
>   
>
> - [ ] 能简单说出CSS的作用及其语法格式
>



**理解上课的知识点**......



# 表单系列标签

> 表单的目的是收集用户信息，多用于注册或者登陆页面
>
> 比如：[百度注册页面](https://passport.baidu.com/v2/?reg&tt=1545956869395&overseas=undefined&gid=7DCB50E-95C0-413A-9672-D86435760F4E&tpl=mn&u=https%3A%2F%2Fwww.baidu.com%2F)
>
> 有一种生物叫做后端

## input系列标签

> 先简单的过一遍~

```html
<input type="text">

单标签、type：用于指定不同的控件类型
```

![表单元素](mdImg/表单元素.PNG)



### 文本框：text

### 密码框：password

```html
昵称：<input type="text" value="小姐姐" name="nicheng" maxlength="6"> 
密码：<input type="password" name="password" maxlength="6">
```

**属性：**

- value (**基础班知道有这个属性就行~**)：**表单标签的值 ** → 用户输入的数据

  > 提前在标签设置好就是默认值

- name (**基础班知道有这个属性就行~**)：**表单标签的名称** → 作用是告诉后端对应的值的含义

  > 后端接收到的格式：`name的属性值=value的属性值`

  **拓展：**

  页面中的信息需要传给后台服务器，但是直接发一个值（value）过去，后端不知道是什么，所以需要加上一个属性name  代表数据的含义。

  后端接收的数据结构为： name属性值=value属性值  这样后端就知道传过去的是什么（前后端交互在就业班会重点说明，基础班不会使用）

- maxlength：设置表单的最大输入值

**小bug** ：如果是密码输入框，`type="password"`  的password不能拼错且后面不能有空格，否则浏览器会认为type属性设置无效，会以默认的text方式显示，此时不会密文，相当于是文本框。



### 单选框：radio

```html
性别 : <input name="sex" type="radio" value="nan"> 男 
      <input name="sex" type="radio" value="nv" checked> 女
```

**属性：**

- name：
  - 分组：有相同name属性值的单选框是一组的，一组中同时只能有一个选中
  - 表单标签的名称：告诉后端对应的值的含义
- value：用户选择的数据
- checked：默认选中，属性值省略

##### ---------------------------

### 多选框：checkbox

```html
爱好：<input type="checkbox" name="hobby" value="code" checked>敲代码
     <input type="checkbox"  name="hobby" value="nosleep" checked>熬夜
     <input type="checkbox"  name="hobby" value="game">玩游戏 
```

**属性：**

- name：表单标签的名称，告诉后端对应的值的含义
- value：用户选择的数据
- checked：默认选中，属性值省略

### 文件选择框 file

```html
<input type="file">   单文件上传
<input type="file" multiple>   多文件上传
```

**属性：**

- multiple：（html5新属性）设置一次同时可以选中多个文件（ctrl+选中/鼠标框选），属性值可以省略



### input按钮

> 需要配合form表单一起使用——》说白了就是用form标签把表单标签都包起来~
>

#### 提交按钮：submit

> 将表单的内容提交给后端

```html
<input type="submit">
```

#### 重置按钮：reset

> 将表单的内容重置为默认值

```html
<input type="reset">
```
#### 普通按钮：button

> 之后配合js使用

```html
<input type="button">    // 配合后面的js使用
```
#### 图片按钮：image

> 功能相当于提交按钮，样式为一张图片

```html
<input type="image" src="a.jpg">
```



## 表单域标签：form

> form标签用于定义表单域，将各种表单包裹起来，用于表单提交

```html
<form action="url地址">
  各种表单控件
</form>
```

**属性：**

- action：用于指定处理请求的服务器URL地址（**就业班的内容**）

## 按钮标签：button

> 除了input标签可以完成按钮功能之外，button标签也可以完成按钮的功能

**代码：**`<button>一个按钮</button>`

**功能：** button标签里面可以嵌入其他标签，甚至 `<img>`标签也可以，并且在谷歌浏览器中，button标签默认的功能就是提交按钮。

**属性：**

| type的属性值 |           功能           |
| :----------: | :----------------------: |
|    submit    |         提交按钮         |
|    reset     |         重置按钮         |
|    button    | 可以点击的按钮（没作用） |



## 下拉菜单菜单：select

```html
出生年月：<select name="year">
            <option value="1996">1996</option>
            <option value="1997">1997</option>
            <option value="1998">1998</option>
            <option value="1999" selected>1999</option>
		</select>
```

**注意：**

- name：表单标签的名称，告诉后端对应的值的含义

  > 设置在select标签上

- value：用户选择的数据

  > 设置在option标签上

- selected：置默认选中，属性值可以省略



## 文本域：textarea

> 用于输入大段文字

```html
<textarea cols="规定文本区内的可见宽度" rows="规定文本区内的可见行数">
  文本内容
</textarea>
```

<img src="mdImg/textarea.png" />

**注意：**不能通过设置value使文本域有默认值，无效！



## label标签

> 示例 : [新浪网页注册](https://login.sina.com.cn/signup/signup?entry=homepage)

**作用：**让**文本**和**表单元素**绑定到一起（结拜兄弟）

![label](mdImg/label.jpg)

![猫哥](mdImg/猫哥.jpg)

**用法：**

- 写 for属性，属性值为 id，设置规定 label 与哪个表单元素绑定

```html
性别 : 
<input  id="nan" name="sex" type="radio"><label for="nan">男</label>
<input  id="nv" name="sex" type="radio"><label for="id名">女</label>   

步骤：
1、在表单元素上添加id属性
2、给label添加for属性，for的属性值与对应表单元素的id值相同即可
```
- 不写 for属性，默认绑定 label 内的表单控件

```html
<label><input type="radio" name="sex"> 男</label>

步骤：
1、用label把表单元素和文字包在一起即可
2、注意点：需要把label标签上的for属性删除
```

##### ---------------------------



# 没有语义的布局标签

> div和span是没有语义的标签，一般用于页面布局使用（项目中会经常使用到）

## div标签

```html
<div>长亭外</div><div>古道边</div>
```

**特点：**

- width由屏幕宽度决定（独占一行）height由内容撑开
- 默认占一整行（一行只能显示一个）



## span标签

```
<span>芳草碧连天</span>
```

**特点：**

- width、height由内容来决定（都由内容撑开）
- 一行里面可以显示多个



# HTML5新标签与属性

> HTML5可以看做是HTML这个语言的一个新版本，里面有一些新加的标签和属性。
>
> 今天先学习一部分，随着学习的深入会不断学习到

## 新增语义标签（记忆）

> 除了刚刚学习的没有语义的标签可以用于布局，html5中还有一些有语义的标签也可以用于布局

- **头部：header标签**

  ```html
  header：定义网页的头部---》头部语义 + div
  ```

- **导航：nav标签**

  ```html
  nav：定义网页的导航---》导航语义 + div
  ```

- **底部：footer标签**

  ```html
  footer：定义网页的底部---》底部语义 + div
  ```

- **侧边栏：aside标签**

  ```html
  aside：定义网页的侧边---》侧边语义 + div
  ```

- **区块：section标签**

  ```html
  section：定义网页的区块---》区块语义 + div
  ```

- **文章：article标签**

  ```html
  article：定义网页的文章---》文章语义 + div
  ```

![](mdImg/h5新标签.png)

**注意：**html5标签有兼容性问题（老浏览器没效果）



## 新增input表单（记忆）

> HTML5新增了input标签的形态，更多的是用在移动端开发中
>

![html5表单](mdImg/html5表单.png)

**代码：**

```html
/* 输入一个网址，浏览器会自动校验网址的格式，格式不对不能提交！ */
<input type="url">
/* 输入一个邮箱，浏览器会自动校验邮箱的格式，格式不对不能提交！ */
<input type="email">
/* 浏览器会显示默认的选择日期控件 */
<input type="date">
/* 点击之后会自动弹出数字输入框（在移动端才有效！！） */
<input type="tel">
/* 只能输入数字 */
<input type="number">
```

| type的属性值 |                功能描述                |
| :----------: | :------------------------------------: |
|     url      |        输入url格式（如：网址）         |
|    email     |              输入邮箱格式              |
|     date     |             显示日期输入框             |
|     tel      | 输入手机号码格式（只在移动设备上有效） |
|    number    |              输入数字格式              |

**针对于tel的效果：**

<img src="mdImg/tel.jpg" width="400px">

> 想体验效果可以课后用手机访问二维码看效果（一个简单的标签测试网页）：

![new](mdImg/new.png)


## 新增表单属性（记忆）

|      属性名      |               属性值                |                           功能描述                           |
| :--------------: | :---------------------------------: | :----------------------------------------------------------: |
| **placeholder**  |              任意文字               |                  占位符（用于提示用户输入）                  |
|  **autofocus**   |         autofocus（可省略）         |                   当页面加载时自动获取焦点                   |
| **autocomplete** | on：打开自动完成；off：关闭自动完成 | 规定input是否应该启用自动完成功能（**需要配合name属性一起使用**） |
|   **required**   |         required（可省略）          |                  规定这个input的值是必填的                   |

##### ---------------

## 多媒体标签（了解）

#### audio 音频

> 在网页中播放音频（声音）

**属性：**

- controls 是否显示播放控件 
- autoplay 自动播放（**有兼容性问题**）
- loop 循环播放（**有兼容性问题**）



#### video 视频

> 在网页中播放视频

**属性：**

- controls 是否显示播放控件 
- autoplay 自动播放（**有兼容性问题**）
- loop 循环播放（**有兼容性问题**）
