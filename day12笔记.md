---
typora-copy-images-to: mdImg
---

# 学习目标

> - [x] 能跟随课程完成学成在线banner部分制作
>
> - [x] 能跟随课程完成学成在线box部分制作
>
> - [x] 能跟随课程完成学成在线footer部分制作
>
> - [x] 能够引用和制作品优购favicon图标
>
>   ```html
>   <link rel="icon" href="路径">
>   ```
>
>   
>
> - [x] 能说出网页中TDK三大标签优化注意事项
>
>   - t:title
>   - d:描述标签
>   - k：keywords：关键字标签
>
> - [x] 能够解释品优购CSS初始化中常用代码的含义
>
> - [x] 能够跟随课程写出品优购shortcut（快捷菜单）
>
> - [x] 能够说出实际开发logo我们需要做哪些优化
>
>   - 整体是一个div
>     - h1
>       - a标签
>       - a标签需要设置背景图片
>       - 添加文字
>         - 不要文字显示
>           - 1、font-size：0
>           - 2、text-indent：-9999px；overflow:hidden
>
>
> 
>
> - [ ] 能够跟随课程写出品优购首页header部分
>
> - [ ] 能够跟随课程写出品优购首页推荐模块
>
> - [ ] 能够跟随课程写出品优购首页楼层模块
>
> - [ ] 能够跟随课程写出品优购首页footer焦点图模块
>
>
> 。。。。。。



**理解上课的知识点......**



# 样式初始化的补充

>对于页面中的文本框有默认的边框和点击之后出现的轮廓线，这写效果都是浏览器默认设置的，咱们一般在项目的样式初始化中需要把这些样式给清除掉。
>

**去除边框：**

- border：none

**去除input点击之后的边框轮廓线：**

- outline-style: none

**设置禁止textarea自由缩放：**

- resize：none



# 品优购项目搭建

> 每一个项目开始之前都要有项目的搭建。
>

**项目搭建步骤：**

- 新建项目文件夹

- 新建images文件夹，把样式类（背景图、精灵图）图片放在images文件夹中

- 新建upload文件夹，把产品类图片放在upload文件夹中

- 新建css文件夹，把所有页面的css文件放入，比如：index.css

  > 品优购作为一个大型的项目，**有很多页面** 的**大型的项目**，每个页面都有自己对应的css文件，为了查找方便，css文件需要单独放在一个**css文件夹**中

- 新建页面index.html

| 文件夹文字 |                含义                |
| :--------: | :--------------------------------: |
|   images   | 存放样式类（背景图片、精灵图）图片 |
|    css     |          存放css样式文件           |
|   fonts    |            存放字体图标            |
|   upload   |           存在产品类图片           |
|     js     |           存放js脚本文件           |

**样式的初始化：**

- index.css中进行样式的初始化（把项目中要用的样式先写好）

  - 因为样式的初始化每个项目都是一样的，所有公司开发的时候会把样式初始化代码写成一个单独的**base.css**文件，开发的时候直接引入即可

    > 在使用别人写好的base.css文件之前，需要知道base.css文件中有哪些代码，方便之后对页面样式的设置

    ##### ヾ(๑╹◡╹)ﾉ"查看别人写好的base.css的代码

    > 问题：为什么要进行css初始化？请举例说明

    **为什么要进行css初始化？**

    1. 因为不同浏览器对于不同标签有默认样式（比如默认padding和margin、a标签默认的下划线......）
    2. 开发的时候并不需要默认的样式。并且需要在不同浏览器中展示的效果是一样的
    3. 所以我们一般在项目开始的时候，会去除浏览器默认的样式即：css的初始化，需要的时候自己设置样式即可。

    ```html
    <!-- 举例说明 -->
    
    1.清除标签的默认margin和padding：
    * {
        margin: 0; 
        padding: 0;
    }
    
    2.清除li标签之前的小点：
    ul{
        list-style: none;
    }
    
    3.清除a的下划线：
    a {
        text-decoration:none；
    }
    
    ......（base.css中有一堆）
    ```

- 在index.html中通过link标签引入index.css



**注意点：**

一般会先引入初始化文件：base.css，在引入当前页面的css文件

> 目的是防止当前页面的css文件中的样式被base.css初始化样式给覆盖掉



## 页面ico图标的使用（了解）

> 较大的网站的title前面会有一个小的图标，这个小图标一般使用的就是ico图标

![1](mdImg/1-1552839478949.png)

**使用步骤：**

- 获取`ico图标`
  - 一般是由UI设计师提供.ico图片
  - 可以通过 [一些转换网站](http://www.bitbug.net/) 将图片上传，获取ico图标

- 使用`ico图标`

  -   `<link rel="icon" href=" favicon.ico的路径" type="image/x-icon">` 

**一般将ico图标放到根目录下面**



## TDK页面seo三大标签（了解）

> 对于线上页面，有三大标签对于seo比较重要的！！
>
> seo：搜索引擎优化：提升网页的排名
>
> 品优购作为一个正经的项目，需要加上对应的三个seo较为重要的标签

### Title：标题标签

> 表示网页的标题，对于网页的seo权重很高

**title标签的内容：**具有不可替代性，是网页的第一个重要标签，是搜索引擎了解网页的入口和对网页主题归属的最佳判断点。

![](mdImg/title标签.png)

**建议：**网站名（产品名）- 网站的介绍  （尽量不要超过30个汉字）

**例如：**

- 京东(JD.COM)-综合网购首选-正品低价、品质保障、配送及时、轻松购物！
- 小米商城 - 小米5s、红米Note 4、小米MIX、小米笔记本官方网站

```html
<title>品优购-正品低价、品质保障、配送及时、轻松购物！</title>
```



### Description：描述标签

> 表示对于网页内容的描述，可以是对于标题的补充，一般文字不超过120个字。

**建议：**description 作为网站的总体业务和主题概括，多采用“我们是…”、“我们提供…”、“×××网作为…”、“电话：010…”之类语句。

![description标签](mdImg/description标签.png)

```html
<meta name="description" content="品优购-专业的综合网上购物商城,销售家电、数码通讯、电脑、家居百货、服装服饰、母婴、图书、食品等数万个品牌优质商品.便捷、诚信的服务，为您提供愉悦的网上购物体验!" />
```

### Keywords：关键字标签

> 是页面内容的关键字，对于seo也较为重要。

**建议：**keywords 关键词之间用英文逗号隔开，采用 关键词1,关键词2 的形式

![Keywords标签](mdImg/Keywords标签.png)

```html
<meta name="Keywords" content="网上购物,网上商城,手机,笔记本,电脑,MP3,CD,VCD,DV,相机,数码,配件,手表,存储卡,品优购" />
```

> **对于我们前端人员来说，我们只需要准备好这三个标签，具体里面的内容，有专门的 SEO 人员准备**



![image-20200618120045214](mdImg/image-20200618120045214.png)



## logo部分的seo优化

> 一般网页的logo需要考虑到seo的优化，实际的做法是会使用h1标签包裹

- **logo** 部分中先需要一个 **h1**标签包裹，提升seo
- 一般logo部分点击能跳转，需要h1中包裹一个a标签，并且a标签的范围需要占满h1标签
- 为了给seo提供文字类信息，还需要给a中添加文字，但是又不需要用户看到
  - 方法一：设置`text-indent`将文字移出盒子（`text-indent: -999px`），然后配合`overflow:hidden` 溢出隐藏
  - 方法二：直接设置`font-size:0` 
- 一般还会给链接设置一个title属性，鼠标悬停有文字提示



