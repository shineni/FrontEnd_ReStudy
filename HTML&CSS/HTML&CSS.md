# HTML&CSS
简介
1. 软件系统的分类
- 系统软件  windows/Linux/macOS
- 应用软件  office/qq
- 游戏软件  王者荣耀
2. 软件的组成
- 客户端：用户通过客户端使用软件（本地安装的）
    - 文字形式的客户端：通过命令行使用软件
    - 图形化界面（C/S）：通过点击拖动等来使用软件。windows,macOS中，Android,iOS中大部分应用 开发成本高，使用起来麻烦
    - 网页(B/S)：通过访问网页来使用软件。所有网站都属于这个范畴。[网页也属于图形化页面，只不过通过浏览器]
      网页的优点：不需要安装，无需更新，跨平台
      网页中使用的语言：HTML/CSS/JavaScript
- 服务器：负责在远程处理业务逻辑
    - 开发语言：Java, PHP,C#, Python,Nodejs
2. 网页的三要素：结构，表现和行为
- 结构（人的骨架）：HTML用于描述页面的结构
- 表现（人的衣服皮肤）：CSS用于控制页面中元素的样式
- 行为（人的活动，交互）：JavaScript用于响应用户操作

![网页三要素.PNG](.\HTML\source\imgs\网页三要素.PNG)


## 1 HTML（不区分大小写）
### 1.1 HTML是什么
HTML(Hyper Text Mark Language)
```
<html>
<!-- HTML的注释方式： 开发中养成良好的注释的习惯，注释要求简洁明了，注释是不能嵌套的
根标签HTML：有且只有一个：
两个子标签：head 和 body
head 网页的头部，给浏览器和搜索引擎看的,head中的内容不会出现在网页中
title 网页的标题
body 内容用户可以看到-->
	<head>
        <title>
        </title>
    </head>
    <body>
    </body>
</html>
```
### 1.2 HTML概要
#### 1.2.1 HTML的属性
属性：在标签中（开属性：在标签中（开始标签或自结束标签）还可以设置属性，属性是一个名值对（x=y）
属性用来设置标签中的内容如何显示
属性和标签名或者其他属性应该使用空格隔开
属性不能瞎写，应该根据文档中的规定来编写，有些属性有属性值，有些属性没有，如果有属性值，属性值应该使用引号引起来（可是是单引号也可以是双引号）始标签或自结束标签）还可以设置属性，属性是一个名值对（x=y）
属性用来设置标签中的内容如何显示
属性和标签名或者其他属性应该使用空格隔开
属性不能瞎写，应该根据文档中的规定来编写，有些属性有属性值，有些属性没有，如果有属性值，属性值应该使用引号引起来（可是是单引号也可以是双引号）
#### 1.2.2网页的基本结构
网页的版本：HTML4,XHTML2.0,HTML5...(迭代的过程)
怎样知道是什么网页的版本呢？文档声明,在文档的最上面,第一行<html>标签的外面用于告诉浏览器网页是HTML5还是其他的
<!doctype html>
<!Doctype HTML>
#### 1.2.3进制
- 十进制
	- 特点：满10进1
    - 计数：0 1 2 3 4 5 6 7 8 9 10 11 12 13... 19 20
    - 单位数字：10个（0-9）
- 二进制
	- 特点：满2进1
    - 计数：0 1 10 11 100 101 110 111
    - 单位数字：2个（0-1）
    - 扩展：
    	- 所有数据在计算机底层都会以二进制的形式保存
    	- 可以将内存想象为一个有多个小格子组成的容器，每个小格子中可以存储一个1或者一个0
    	  这一个小格子在内存中称为一个bit，一般可操作的最小单位是1byte(8个bit)
          8bit = 1byte(字节)
          1024byte = 1kb(千字节)
          1024kb= 1mb(兆字节)
          1024gb = 1tb
          1024tb = 1pb
- 八进制（很少使用）
	- 特点：满8进1
    - 计数：0 1 2 3 4 5 6 7 10 11...17 20
    - 单位数字：8个（0-7）
- 十六进制(一般显示一个二进制 数字是，都会转换为十六进制)
	- 特点：满16进1
    - 计数：0 1 2 3 4 5 6 7 8 9 a b c d e f 10 11 12 ... 1a 1b 1c 1d 1e 1f 20 ...
    - 单位数字：16个（0-f）

#### 1.2.4字符编码
		莹莹-->101001010
        101001010-->莹莹
        - 所有的数据在计算机中存储时都是以二进制的形式存储的，文字也不例外
        	- 所以一段文字在存储到内存时，都需要转换为二进制编码
        	- 当我们读取这段文字时，计算机会将编码转换为字符，供我们阅读
        - 编码
        	- 将字符转换为二进制编码的过程称为编码
        - 解码
        	- 将二进制码转换为字符的过程称为解码
        - 字符集（charset）
        	-编码和解码所采用的规则统称为字符集， 一个字符对于一个编码
        - 乱码问题
        	- 编码和解码所采用的字符集不同就会出现乱码问题
        -常见的字符集
        	ASCII
            ISO88591
            GB2312
            GBK
            UTF-8，开发时我们使用的字符集都是UTF-8
```
<!doctype html>
<html>
	<head>
	<!--可以通过meta标签来设置网页的字符集，避免乱码问题-->
		<meta charset="utf-8">
		<title>标签的属性</title>
	</head>
	<body>
		<h1>这是我的<font color="red">第三个</font>网页</h1>
	</body>
</html>
```
meta标签里面设置是告诉浏览器，我的网页是用UTF-8进行编码的，实际的编码方式是NotePad++里面的方式，所以要严格保持一致，否则会出错

![CharSet.PNG](.\HTML\source\imgs\CharSet.PNG)

【练习】
       1.安装VSCode
       2.安装中文语言包
       3.尝试安装ayu主题
       4.将一个目录作为项目目录
       5.创建一个网页
       6.安装live server（右击--->Open with Live Server）
       7.尝试通过live server来运行网页
       8.设置代码自动存储（Settins--->Auto Save -->afterDelay）
### 1.3 HTML详述
#### 1.3.1 实体
在网页中编写多个空格默认情况会自动被浏览器解析为一个空格
在HTML中有些时候，我们不能直接书写一些特殊的符号
-  比如： 多个连续的空格， 比如字母两侧的大于和小于号
     - 如果我们需要在网页中书写这些特殊的符号，则需要使用Html中的实体（转义字符）即HTML 中的预留字符必须被替换为字符实体

实体的语法：
```
        &nbsp; 空格
        &gt; 大于
        &lt;小于
        &copy;版权符号
```

#### 1.3.2 meta和title
 meta主要用于设置网页中的一些元数据，元数据不是给用户看的
- charset 指定网页的字符集
- name指定数据的名称
	- keywords 表示网站的关键字，可以同时指定多个关键字，关键字使用，隔开
` <meta name="Keywords" content="网上购物,网上商城,手机,笔记本,电脑,MP3,CD,VCD,DV,相机,数码,配件,手表,存储卡,京东">`
	- description 表示用于对指定网站的描述
` <meta name="description" content="京东JD.COM-专业的综合网上购物商城,销售家电、数码通讯、电脑、家居百货、服装服饰、母婴、图书、食品等数万个品牌优质商品.便捷、诚信的服务，为您提供愉悦的网上购物体验!">`
- content指定数据的内容
网站的描述会显示在搜索引擎的搜索结果中

title标签的内容会作为搜索结果的超链接上的文字显示
 `<title>京东(JD.COM)-正品低价、品质保障、配送及时、轻松购物！</title>`
 ```
   <meta name="keywords" content="HTML5,前端,CSS3">
    <meta name="description" content="这是一个很不错的网站">
    <meta http-equiv="refresh" content="3;url=http://www.baidu.com">
    <!-- <meta http-equiv="refresh" content="3;url=http://www.baidu.com"> 将页面重定向：3秒后跳转到百度的地址-->
    <title>Document</title>
```
#### 1.3.3 标签
块级元素和行内元素
- 块级元素：在页面中独占一行的元素成为块元素（block element）
- 行内元素：在页面中不会独占一行的元素，行内元素主要用来包裹文字
**几点说明：**
    - 一般情况下会在块级元素中放行内元素，而不会在行内元素中放块级元素
    - 块级元素基本上什么都能放
    - P元素中不能放任何块级元素
    - 浏览器在解析网页时，会自动对网页中不符合规范的内容进行修正比如：
        - 标签写在根元素外面
        - p元素嵌套了块级元素
        - 根元素中出现了除head和body以外的子元素
        - ...

在网页中HTML专门用来负责网页的结构, 所以在使用html标签的时候，应该关注的是标签的语义，而不是它的样式.
- 标题标签
	- h1-h6 一共有六级标题
	- 从h1-h6重要性递减，h1最重要，h6最不重要
	- h1在网页中的重要性仅次于title，一般情况下一个页面只会用一个h1
	- 一般情况下标题标签只会使用h1-h3,h4-h6很少用
    - 标题标签是块级元素（在页面中独占一行的元素成为块元素（block element））
```
     <h1>一级标题</h1>
     <h2>二级标题</h2>
     <h3>三级标题</h3>
     <h4>四级标题</h4>
     <h5>五级标题</h5>
     <h6>六级标题</h6>
```
- hgroup:  hgroup标签用来为标题分组，可以将一组相关的标题同事放入到hgroup 大标题，小标题
```
    <hroup>
        <h1>回乡偶书两首</h1>
        <h2>其一</h2>
    </hroup>
```
-p标签： p标签表示页面中的一个段落 p也是一个块级元素
```
<P>在p标签中的内容就表示一个段落</P>
```
- em: em标签用于表示语音语调的一个加重
```
<p>今天天气<em>真</em>不错</p>
```
- strong: strong表示强调，主要内容
```
<p>今天必须<strong>完成作业</strong></p>
```
- blockquote: blockquote表示一个长引用
```
 鲁迅说
  <blockquote>
        ....
  </blockquote>
```
-q:表示一个短引用
```
子曰<q>学而实习之</q>
```

#### 1.3.4 语义化标签
    - header表示网页的头部
    - main表示网页的主题部分（一个页面中只会有一个main）
    - footer表示网页的底部
    - nav 表示网页中的导航
    - aside 和主体相关的其他内容，或者注释（侧边栏）
    - article 表示一个独立的文章
    - section表示独立的一个区块，上边的标签都不能表示时使用section

    - div没有语义，就用来表示同一个区块，目前来讲div还是我们主要的布局元素
    - span行内元素，没有任何的语义，一般用于网页中选中文字
    - header和footer不仅仅可以表示整个网页的头部和底部，也可以表示网页某一个部分的头部和底部
- main在一个页面中只能出现一次
```
    <header></header>
    <main></main>
    <footer></footer>
    <nav></nav>
    <section></section>
```

#### 1.3.5 列表
在html中也有可以创建列表，html中一共有三种，列表之间是可以互相嵌套的:
    - 有序列表：使用ol标签来创建无序列表， li表示选项
    - 无序列表：使用ul标签来创建有序列表， li表示选项
    - 定义列表：使用dl来创建一个定义列表
        - 使用dt来表示定义的内容 title
        - 使用dd用来对 内容进行解释说明 description

```
    <ul>
        <li>结构</li>
        <li>行为</li>
        <li>表现</li>
    </ul>
    <ol>
        <li>结构</li>
        <li>行为</li>
        <li>表现</li>
    </ol>
    <dl>
        <dt>结构</dt>
        <dd>结构表示网页的结构，结构用来规定哪里是标题,哪里是段落</dd>
    </dl>
```

#### 1.3.6 超链接
超链接可以让我们从一个页面跳转到其他页面，或者是当前页面的其他位置使用a 标签来定义超链接
   - 属性：
    - href 指定跳转的目标路径,值可以是外部网站的地址,也可以是相对路径
    - target 用于指定超链接打开的位置, 可选值
        - self 默认值 在当前页面中打开超链接
        - blank 在一个新的标签中打开超链接

**使用a标签定位到页面的其他位置**
- 可以直接将超链接的href属性设置为#,这样点击超链接以后页面不会发生跳转，而是跳转到氮气页面的顶部的位置
- 可以跳转到页面的指定位置，只需将href属性设置 #目标元素的id属性值
- 在开发中可以将#作为超链接的路径的占位符使用
 ```
  <a href="#">超链接</a>
```
- 在开发中可以使用javascript:;来作为href的属性，此时点击这个超链接什么也不会发生
  ```
  <a href="javascript:;">超链接</a>
```
```
     <a href="http://www.baidu.com">超链接</a>
     <br>
     <a href="06list.html">超链接2</a>
     <br>
     <a href="./06list.html">超链接3</a>
     <br>
     <a href="./source/test2.html">超链接4</a>
     <br>
     <a href="#bottom">回底部</a>
     <br>
     <a href="#middleP">去指定位置</a>
     <br>
     <a href="javascript:;">超链接</a>
     <p>...</p>
     <p id="middleP"> 1111 Lorem ipsum, dolor sit amet consectetur adipisicing elit. Consequuntur dignissimos facilis aliquid quae hic delectus iure magnam perferendis rem ab ipsum fugiat, illum similique eaque aliquam! Magnam maiores aut laboriosam.</p>
     <p> ...</p>
    <a href="#" id="bottom">回到顶部</a>
```
超链接也是行内元素 ，在a标签中可以嵌套除了自身以外的任何元素

#### 1.3.7 图片
图片标签用于向当前页面中引入一个外部图片, 使用img标签引入外部图片，img标签是一个自结束标签
img 这种元素属于替换元素（块和行内元素之间，具有两种元素的特点）
	- 属性：
    - src 属性指定外部图片的相对路径（两种方式：相对路径，网址）
    - alt 图片的描述，这个描述默认情况下不会显示，有些浏览器会在图片无法加载时显示
         搜索引擎会根据alt中的内容来识别图片，如果不写alt属性则图片不会被搜索引擎所识别
    - width 图片的宽度（单位是像素）
    - height 图片的高度
   ** 宽度和高度如果只修改了一个，则另一个会等比例缩放，所以只建议修改一个**
【建议】一般情况在pc端，不建议修改图片的大小，需要多大的图片就裁多大,但是在移动端，经常需要对图片进行缩放（大图缩小）

    图片的格式
       - jpeg(jpg)
            - 支持的颜色比较丰富，不支持透明效果，不支持动图
            - 一般用来显示照片
       - gif
            - 支持的颜色比较少，支持简单透明，支持动图
            - 颜色单一的图片，动图
       - png
            - 支持的颜色丰富，支持复杂透明，不支持动图
            - 颜色丰富，复杂透明图片（专为网页而生）
       - webp
            - 这种格式是谷歌新推出的专门用来表示网页中的图片的一种格式
            - 它具备其他格式的所有优点，而且文件还特别小
            缺点：
               兼容性不好

        - base64
            - 将图片使用base64进行编码，这样可以将图片转为字符，通过字符的形式来引入图片
            - 一般是一些需要和网页一起加载的图片才会用base64

      **  图片格式选择的原则：效果一样，用小的，效果不一样用效果好的**
```
<img src="../HTML&CSS/source/imgs/网页三要素.PNG" alt="找不到了">
     <img width="200" src="https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1585312413509&di=de7b33b6d396362af4087f71d72ca268&imgtype=0&src=http%3A%2F%2Fimage.shumiao.net%2Fuploads%2F20190222%2F18%2F1550830811-cyvNlDsPeY.jpg">
```

#### 1.3.8 内联框架
内联框架，用于向当前页面中引入一个其他的页面
- src 指定要 引入的网页的路径
- frameborder指定 内联框架的边框
```
     <iframe src="https://www.qq.com"  width="800" height="600" frameborder="0"></iframe>
     <h1>内联框架</h1>
```
#### 1.3.9 音频视频
 audio 标签用于向页面中引入一个外部的音频文件，音视频引入时，默认情况下不允许用户自己控制播放停止
	属性
    - controls是否允许用户控制播放
    - autoplay音频文件是否自动播放 如果设置了autoplay则音乐打开也面试会自动播放，但是目前来讲大部分浏览器都不会自动对音乐进行播放
    - loop 是否循环播放

除了通过src来指定外部文件的路径以外，还可以通过source来指定文件


```
<!--方式一-->
<audio src="./source/imgs/偏偏喜欢你 - 轻音乐网.mp3" controls></audio>
<!--方式二-->
<audio controls>
    对不起，您的浏览器不支持播放音频
    <source src="./source/imgs/偏偏喜欢你 - 轻音乐网.mp3">
    <source src="./source/imgs/偏偏喜欢你 - 轻音乐网.ogg">
    <embed src="./source/imgs/偏偏喜欢你 - 轻音乐网.mp3" type="audio/mp3" width="300" height="100">
</audio>
<br>
<video controls="controls">
    <source src="./source/imgs/猴王跳跳.mp4" >
    <source src="./source/imgs/movie.ogv" type="video/mp4">
    <embed src="./source/imgs/猴王跳跳.mp4" type="video/mp4" >
</video>
<br>

<iframe frameborder="0" src="https://v.qq.com/txp/iframe/player.html?vid=v0033av0fcb" allowFullScreen="true"></iframe>
</html>
```


## 2.CSS
### 2.1 CSS简介
#### 2.1.1 CSS概述
CSS语法： 选择器 声明块
- 选择器 通过选择器可以选择页面中的指定元素, p的作用就是选中页面中的所有的p元素
- 声明块 通过声明块来指定要为元素设置的样式
    声明块由一个个声明组成
    声明是一个名值对结构,一个样式名对应一个样式，名和值之间以：连接，以；结尾

给元素添加样式的三种方式
- 第一种方式（内联样式，行内样式）【不推荐使用，与HTML耦合性强】：
    - 在标签内部通过style属性来设置元素的样式
    - 问题：不方便维护
        - 使用内联样式，样式只能对一个标签生效，如果希望影响到多个元素必须在每一个元素中复制一遍，并且当样式发生变化时，我们必须要一个个修改，非常不方便
        - 开发时，绝对不要使用内联样式
```
 <p style="color:red;font-size:60px">少小离家老大回</p>
```
- 第二种方式(内部样式表)：
    - 将样式编写到head中的style标签里，然后通过CSS选择器选中元素并且设置 各种样式
        可以同时为多个标签设置样式，并且修改时只需要修改一处即可全部应用
    - 内部样式表更f方便对样式进行复用
    问题：
        内部样式表只能对一个网页起作用，它里面的样式不能跨页面进行复用
```
     <style >
         p{
             color: green;
             font-size: 20px;
         }
     </style>
```
- 第三种方式：外部样式表 【最佳实践】
    - 可以将css样式编写到一个外部的css文件中,然后通过link标签来引入外部的css文件
    - 外部样式表需要通过link标签进行引入，意味着只要想使用这些样式的网页都可以对其进行引用，使样式可以在不同页面进行复用
    - 将样式编写到外部的css文件中，可以使用到浏览器的缓存机制，从而加速网页的加载速度，提高用户的体验
```
<link rel="stylesheet" href="./style.css">
```

#### 2.1.2 CSS选择器-基本选择器
- 元素选择器
	- 作用：根据标签名来选中指定的元素
    - 语法：标签名{}
    - 例子：p{} h1{} div{}
- id选择器
    - 作用：根据元素的id属性值选中一个元素
    - 语法：#id属性值{}
    - 例子：#box{} #red{}
- 类选择器: class 是一个标签的属性，它和id类似，不同的是class可以重复使用,可以通过class属性来为元素分组,可以同时为一个元素指定多个class属性
    - 作用：根据语速的class属性值选中一组元素
    - 语法：.class属性值{}
    - 例子：.red{}

- 通配选择器
    - 作用：选中页面中的所有元素
    - 语法： *{}

#### 2.1.3 CSS选择器-组合选择器
- 交集选择器
    - 作用：选中同时符合多个条件的元素
    - 语法：选择器1选择器2选择器3选择器n{}
   ** 注意点：**交集选择器中如果有元素选择器，必须使用元素选择器开头

- 并集选择器
    - 选择器分组（并集选择器）
    - 作用：同时选择多个选择器对应的元素
    - 语法：选择器1,选择器2,选择器3,选择器n{}

```
    <style>
            div.red{
               font-size: 30px;
            }
            .a.b.c{
                color: blue;
            }

            h1,span{
                color: green;
            }
    </style>

```

#### 2.1.4 CSS选择器-关系选择器
- 父元素
    - 直接包含子元素的元素叫做父元素
- 子元素
    - 直接被父元素包含的元素是子元素
- 祖先元素
    - 直接或者间接包含后代元素的元素叫做祖先元素
    - 一个元素的父元素也是它的祖先元素
- 后代元素
    -直接或间接被祖先元素包含的元素叫做后代元素
    - 子元素也是后代元素
- 兄弟元素
    - 拥有相同父元素的元素是兄弟元素

- 子元素选择器
    作用：选中指定父元素的指定子元素
    语法：父元素>子元素
```
	<style>
    	div.box > span{
            color: orange;
        }
        div > p > span{
            color: yellow;
        }
    </style>
```


- 后代元素选择器
    作用：选中指定元素内的所有后代元素
    语法：祖先 后代
```
	<style>
    	div span{
            color:blue;
        }
    </style>
```

- 兄弟元素选择器
    - 选择下一个兄弟(紧挨着, 如果p和span中间有个div,那么此时的span也不会选中)
    语法： 前一个 + 下一个
```
	<style>
		p + span{
            color:red;
        }
    </style>
```
    - 选择下面所有的兄弟
     语法： 兄 ~ 弟
```
	<style>
		p ~ span{
            color:red;
        }
    </style>
```



#### 2.1.5 CSS选择器- 属性选择器
	属性title的作用是当鼠标悬停的时候，会有解释说明
    [属性名] 选择含有指定属性的元素
    [属性名=属性值]选择含有指定属性和属性值的元素
    [属性名^=属性值]选择属性值以指定值开头的元素
    [属性名$=属性值]选择属性值以指定值结尾的元素
    [属性名*=属性值]选择属性值中含有某值的元素的元素
```
<head>
    <meta charset="UTF-8">
    <title>属性选择器</title>
    <style>

         [title]{
             color:red;
         }
          [title="abc"]{
             color: red;
         }
          [title^="abc"]{
             color: red;
         }
          [title$="abc"]{
             color: red;
         }
         [title*="abc"]{
             color: red;
         }
    </style>
</head>
<body>
    <h1>我是标题</h1>
    <p title="abc">少小离家老大回</p>
    <p title="abcdef">乡音无改鬓毛催</p>
    <p title="helloabc">儿童相见不相识</p>
    <p>笑问客从何处来</p>
    <p >秋水共长天一色</p>
    <p >落霞与孤鹜齐飞</p>
</body>
```
#### 2.1.6 CSS伪类
 伪类：不存在的类，特殊的类，伪类用来描述一个元素的特殊状态比如：第一个子元素，被点击的元素，鼠标移入的元素....
伪类一般情况下都是使用：开头
：first-child:第一个子元素
：last-child:最后一个子元素
：nth-child():选中第N个子元素
    - 特殊值
        n 第n个 n的范围0到正无穷
        2n 或者 even 表示选中偶数位的元素
        2n+1或者 odd 表示选中奇数位的元素
 以上这些伪类都是根据所有的子元素进行排序
：first-of-type
:last-of-type
:nth-last-of-type()
    这几个伪类的功能和上述的类似，不同点是她们是在同类型元素中进行排序

：not() 否定伪类
    将符合条件的元素从选择器中去除
:only-child
     ul li:only-child 选中ul中仅有一个li元素的
```
         ul>li:first-child{
             color: red;
         }
         ul> li:nth-child(2n+1){
             color: red;
         }
         ul> li:not(:first-child){
             color: green;
         }
```
:link 用来表示没有访问过的链接（正常的链接）【a标签特有】
：visited 用来表示访问过的链接【a标签特有】由于隐私的原因，所以vistied这个伪类只能修改链接的颜色
:hover 用来表示鼠标移入的状态
:active 用来表示鼠标点击
```
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>a元素的伪类</title>
    <style>
         a:link{
             color: red;
         }
          a:visited{
              color: orange;
          }

          a:hover{
              color: blue;
              font-size: 50px;
          }
           a:active{
            color:green;
            font-size: 12px;
           }
    </style>
</head>
<body>
    <a href="http://www.baidu.com">访问过的链接</a>
    <br> <br>
    <a href="http://www.baidu123.com">没有访问过的链接</a>
</body>
```
#### 2.1.7 CSS伪元素
 伪元素，表示页面中一些特殊的并不真实存在的元素（特殊的位置）
伪元素使用：：开头
- ::first-letter表示第一个字母
- ::first-line表示第一行
- ::selection表示选中的内容
- :: before 元素的开始
- :: after 元素的最后
   - before和after必须结合content属性来使用，可以直接通过CSS添加文本,不过添加的文本鼠标是选不中的

```
<head>
    <meta charset="UTF-8">
    <title>伪元素</title>
    <style>
        p::first-letter{
            color:red;
            font-size: 50px;
        }

        p::first-line{
            background-color: yellow;
        }

        p::selection{
            background-color: green;
        }
        div::before{
            content:"『";
        }
        div::after{
            content:"』";
        }
    </style>
</head>
<body>
    <div>How are you?</div>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Aliquam labore molestias consectetur ad facere</p>

</body>
```
#### 2.1.8 继承
样式的继承，我们作为一个元素设置的样式同时也会应用到它的后代元素上
继承是发生在祖先和后代之间的
继承的设计是为了方便我们的开发，利用继承我们可以将一些通用的样式统一设置到共同的祖先元素上,这样只需要设置一次即可让所用的元素都具有该样式

    注意：并不是所有的样式都会被继承, 比如： 背景相关的，布局相关等的这些样式都不会被继承
#### 2.1.9 权重
样式的冲突: 当我们通过不同的选择器，选中相同的元素，并且为相同的样式设置不同的值时，此时就发生了样式的冲突
样式发生冲突时，应用哪个样式由选择器的权重（优先级）决定

选择器的权重
- 内联样式        1000   1, 0, 0, 0
- id选择器        100    0, 1, 0, 0
- 类和伪类选择器   10     0, 0, 1, 0
- 元素选择器       1      0, 0, 0, 1
- 通配选择器       0      0, 0, 0, 0
- 继承的样式      没有优先级

比较优先级时，需要将所有的选择器的优先级进行相加计算，最后优先级越高，则越优先显示（分组选择器时单独计算的）
如果优先级计算后相同，则优先使用靠下的样式，下面的样式覆盖上面的
可以在某一个样式的后边添加！important,则此时该样式会获取到最高的优先级，甚至超过内联样式

	注意：一定要慎用!important

【思考】
1. 如果一个标签里面有10个class选择器，此时计算后的结果会大于一个Id的选择器吗？
    不会，只会无限接近，不会等于或超过。
2. 如果同一个class选择器，对背景色定义了两次，哪个会生效？
    定义在最后的一个样式会生效，因为层叠样式，后面的会覆盖前面的
3. 如果我们用通配选择器定义了一个字体为16px, 继承过去的字体是12Px,我们最终会使用哪个？
    16px,因为通配选择器有优先级，而继承的样式没有优先级
4. a 的四个伪类会有书写顺序的问题吗？

#### 2.1.10 单位
长度单位：
- 像素
    - 屏幕（显示器）实际上是由一个个的小点点构成的
    - 不同屏幕的像素大小是不同的，像素越小的屏幕显示的效果越清晰
    - 所以同样的200px在不同的设备下显示效果不一样
- 百分比
    - 也可以将属性设置为相对于父元素属性的百分比
    - 设置百分比可以使子元素跟随父元素的改变而改变
- em
    - em是相对于元素的字体大小来计算的
    - 1em = 1 font-size 默认的是16px
    - em会根据字体大小的改变而改变
- rem
    - rem是相对于根元素(html)的字体大小来计算的

#### 2.1.11 颜色单位
	在CSS中可以直接使用颜色名来设置各种颜色,如果，red， orange, yellow ,blue, green... ...,但是在css中直接使用颜色名是非常不方便的
RGB值
- RGB 通过三种颜色的不同浓度来调配处不同的颜色
- R red, G green, B blue
- 每种颜色的范围在0-255（1-100%）之间
语法：RGB(红色，绿色，蓝色)

RGBA
- 就是在RGB的基础上增加了一个a表示不透明度
- 需要四个值，前三个和rgb一样，第四个表示不透明度. 1表示完全不透明 0表示完全透明 .5表示半透明

十六进制的RGB值
- 语法： 红色绿色蓝色
- 颜色浓度通过00 -ff
- 如果颜色两位两位重复可以进行简写 #aabbcc ---->#abc

HSL值 和 HSLA值
- H 色相（0-360）
- S 饱和度，颜色的浓度（0%-100%）
- L 亮度，颜色的亮度（0%-100%）

### 2.2 CSS布局
#### 2.2.1文档流（normal flow）
- 网页是一个多层的结构，一层叠着一层
- 通过CSS可以分别为每一层来设置样式
- 作为用户来讲只能看到最顶层
- 这些层中，最底下的一层称为文档流，文档流是网页的基础，我们所创建的元素默认都是在文档流中进行排列
- 对于我们来说元素主要由两个状态
    - 文档流中
    	- 元素在文档流中有什么特点
            - 块级元素
                - 块元素会在页面中独占一行（自上向下垂直排列）
                - 默认宽度是父元素的全部（会把父元素撑满）
                - 默认高度是被内容撑开(子元素)
            - 行内元素
                - 行内元素不会独占页面的一行，只占自身的大小
                - 行内元素在页面中从左向右排列，如果一行容纳不了所有的行内元素
                    则会换到第二行继续从左往右排列（书写习惯一直）
                - 行内元素的默认宽度和高度都是被内容撑开
    - 不在文档流中（脱离文档流）
    	- 块元素：
            - 块元素不再独占页面的一行
            - 脱离文档流以后，块元素的高度和高度默认都被内容撑开
   		- 行内元素：
        	- 行内元素脱离文档流以后会变成块元素，特点和块元素一样

    脱离文档流以后，不再需要区分块和行内元素了

#### 2.2.2盒子模型
- 2.2.2.1盒子模型概述（ 盒模型/盒子模型/框模型）
	- CSS将页面中的所有元素都设置为一个矩形盒子
	- 将元素设置为矩形盒子后，对页面的布局就变成不同的盒子摆放到不同的的位置
	- 每个盒子都由以下几个部分组成：
        - 内容区(content): 元素中的所有的的子元素和文本内容都在内容区中排列,内容区的大小由width和height两个属性来设置
        	- width 设置内容区域的宽度
            - height 设置内容区域的高度
        - 内边距（padding)
            - 内容区和边框之间的额边距是内边距
            - 一共有四个方向的内边距：
                padding-top
                padding-right
                padding-bottom
                padding-left
            - 内边距的设置会影响到盒子的大小
            - 背景颜色会延伸到内边距上
           ** 盒子可见框的大小，由内容区，内边距和边框共同决定，所以在计算盒子大小是，需要将这三个区域加到一起计算**
        - 边框（border）: 边框属于盒子边缘，边框里面属于盒子内部，除了边框都是盒子的外部，边框的大小会影响到整个盒子的大小
        	要设置边框，至少需要设置三个样式：

        	- 边框的宽度 border-width ：可以用来指定四个方向边框的宽度，默认值是3个像素
                border-width值的情况:
                四个值：上右下左（顺时针）
                三个值： 上（左右）下
                两个值：（上下）（左右）
                一个值：上下左右
                除了border-width还有一组border-xxx-width： xxx可以是top right bottom left用来单独指定某一个边的宽度

        	- 边框的颜色 border-color：用来指定边框的颜色，同样可以分别指定四个边的边框规则和border-width一样
            【边框的临界点是斜的，保证四个边框一样大】
            color 前景色，如果不设置border-color则color生效

            - 边框的样式 border-style：指定边框的样式
                        solid 表示实线
                        dotted 点状许仙
                        dashed 虚线
                        double 双线
                border的简写属性，通过该属性可以同时设置边框所有的相关样式，没有顺序要求

                除了border以外还有4个 border-xxx
                    border-top
                    border-right
                    border-bottom
                    border-left
                使用场景：对某一个边做特殊处理
                border：10px red solid;
                border-right:none;
        - 外边距（margin）:外边距不会影响盒子可见框的大小,但是外边距会影响盒子的位置
            - 一共四个方向的外边距
                margin-top 上外边距， 设置一个正值， 元素会向下移动
                margin-right 默认情况下设置margin-right不会产生任何效果
                margin-bottom 下外边距，设置一个正值，其下边的元素会向下移动 
                margin-left 左外边距，设置一个正值，元素会向右移动
                - margin 也可以设置负值，如果是负值则会向相反的方向移动

            - 元素在页面中是按照自左向右的顺序排列的,所以默认情况下，如果我们设置的左和上外边距则会移动自己,而设置下和右外边距会移动其他元素

            - margin的简写属性:margin可以同时设置四个方向的外边距，用法和padding一样

            - margin 会影响到盒子实际占用的空间

- 2.2.2.2 盒子模型水平布局
元素在其父元素中水平方向的位置有以下几个属性共同决定
        margin-left
        border-left
        padding-left
        width : width的默认值就是auto
        padding-right
        border-right
        margin-right

![](CSS/imgs/2.png)

一个元素在其父元素中，水平布局必须要满足以下的等式
margin-left + border-left + padding-left + width + padding-right + border-right + margin-right =  其父元素内容区的宽度 （必须满足）
0 + 0 + 0 + 200 + 0 + 0 + 0 =800
0 + 0 + 0 + 200 + 0 + 0 + 600 =800
以上等式必须满足，如果相加结果使等式不成立，则成为过渡约束，则等式会自动调整
 调整情况：
- 如果这七个值中**没有auto**的情况，则浏览器会自动调整margin-right的值以使等式满足
    - 这七个之中有三个值可以设置为auto
            width
            margin-left
            margin-right
- 如果某个值为auto,则会自动调整为auto的那个值，以使等式成立
        0 + 0 + 0 + auto + 0 + 0 + 0 =800    auto=800
        0 + 0 + 0 + auto + 0 + 0 + 200 =800    auto=600
- 如果将一个宽度和一个外边距设置为auto,则宽度会调整到最大，设置为auto的外边距会自动为0
- 如果将三个值都设置为auto,则外边距都是0，宽度最大
- 如果将两个外边距设置为auto,宽度固定值，则会将外边距设置为相同的值
        所以我们经常利用这个特点来使一个元素在其父元素中水平居中示例：
            width:xxxpx;
            margin:0 auto;



- 2.2.2.3盒子模垂直布局
	- 垂直方向没有任何公式或者等式
	- 默认情况下父元素的高度如果没有设置，则实际高度是被内容撑开的高度
	- 如果设置了高度，那么设置多少就是多少
        - 出现问题：溢出
        - 解决方案： overflow
        **overflow的可选值：**
            visible 默认值 子元素会从父元素中溢出，在父元素外部的位置显示
            hidden 溢出内容将会被裁剪，不会显示
            scroll 生成两个滚动条，通过滚动条来查看完整的内容
            auto 根据需要生成滚动条
            overflow-x
            overflow-y

- 2.2.2.4 margin 相关问题（垂直外边距的重叠（折叠））

    - ***相邻***的***垂直方向***外边距会发生重叠现象
    - 兄弟元素
        - 兄弟元素间的相邻垂直外边距会取两者之间的较大值（两者都是正值）
        - 特殊情况：
            如果相邻的外边距一正一负， 则取两者的和
            如果相邻的外边距都是父值，则取两者中绝对值较大的
        - 兄弟元素之间的外边距的重叠，对于开发是有利的，所以我们不需要进行处理
    - 父子元素【父子的外边距折叠了】
        - 父子元素相邻外边距，子元素的回传给父元素（上外边距）
        - 父子外边距的折叠会影响到页面的布局，所以必须要进行处理
            - 解决方案1：父元素 加 padding , 将高度从父元素中减去，使其外边距不发生重叠
            - 解决方案2： 父元素，高度要重新计算，使其外边距不发生重叠

- 2.2.2.5 行内元素的盒子模型
    - 行内元素不支持宽度和高度
    - 行内元素可以设置padding, 但是垂直方向的padding不会影响布局,只会覆盖一些内容
    - 行内元素可以设置border,垂直方向的border不会影响页面的布局
    - 行内元素可以设置margin,垂直方向的margin不会影响页面的布局

    display 用来设置元素显示的类型
        可选值：
            inline  将元素设置为行内元素
            block  将元素设置为块元素
            inline-block 将元素设置为行内块元素 【开发中能不用就不用】
                行内块，既可以设置宽度和高度又不会独占一行
            table 将元素设置为一个表格
            none 元素不再页面中显示

    visibily 用来设置元素的显示状态
        可选值
             visible 默认值，元素在页面中正常显示
             hidden 元素在页面中隐藏不显示，但是依然占据页面的位置

- 2.2.2.6 默认样式
 默认样式：
    - 通常情况，浏览器会为元素设置一些默认样式
    - 默认样式的存在会影响页面的布局，通常情况下编写网页是必须要先去除浏览器的默认样式（PC端的样式）
重置样式表：专门用来对浏览器的样式进行重置的
        reset.css 直接去除浏览器的默认样式
        normalize.css 对样式进行了统一

- 2.2.2.7 box-sizing & outline & box-shadow & box-radius
	- box-sizing 用来设置盒子尺寸的计算方式（设置width和height的作用范围）
		- 可选值
			content-box 默认值，宽度和高度用来设置内容区域的大小
            border-box 宽度和高度用来设置整个盒子可见框（包括内容区， padding以及border）的大小, width 和 height指的是内容区和内边距和边框的总大小
```
	 <style>
        .box1{
            width: 100px;
            height: 100px;
            background-color: #bfa;
            padding:10px;
            border:10px red solid;
            box-sizing: content-box;
      </style>
    <div class="box1">
        <span>hello</span>
    </div>
```
![border-sizing.png](.\CSS\imgs\border-sizing.png)

	- outline 用来设置元素的轮廓线，用法和border一模一样
![outline.png](.\CSS\imgs\outline.png)

	- box-shawdow 用来设置元素阴影效果，阴影不会影响页面布局, 默认是大小和元素相同的正下方区域
		- 第一个值 左侧偏移量 设置阴影的水平位置，正值向右移动，负值向左移动
        - 第二个值 垂直偏移量 设置阴影的垂直位置，正值向下移动，负值向上移动
        - 第三个值，阴影的模糊半径，值越大越模糊
        - 第四个值，阴影的颜色（透明）
```
	box-shadow: 10px 10px 10px rgba(0, 0, 0, .3);
```
![box-shadow.png](.\CSS\imgs\box-shadow.png)

	- border-radius:用来设置圆角 ,圆角设置圆的半径大小，
        - border-top-left-radius
        - border-top-right-radius
        - border-bottom-left-radius
        - border-bottom-right-radius

        - border-radius:可以分别指定四个角的圆角
        四个值：左上 右上 右下 左下
        三个值：左上 右上/左下 右下
        两个值：左上/右下 右上/左下

      **  将元素设置为一个圆形**
       ` border-radius:50%;`
      **  将元素设置为一个20px**， 从四个顶点出发，找到边长为20px正方形的对角顶点，并以它为圆心，20px为半径绘制而成的
       ` border-radius:20px;`
![border-radius.png](.\CSS\imgs\border-radius.png)
![border-radius-circle.png](.\CSS\imgs\border-radius-circle.png)

#### 2.2.3 浮动
##### 2.2.3.1 浮动概述
通过浮动可以使一个元素向其父元素的左侧或者右侧移动,使用float属性来设置元素的浮动
float属性的可选值：
- none:默认值 元素不浮动
- left： 元素向左浮动
- right： 元素向右浮动

**注意，元素设置浮动以后，水平布局的等式便不需要强制成立**

元素设置浮动以后，会完全从文档流中脱离，不再占用文档流的位置，所以元素下边的还在文档流中的元素会自动向上移动

**浮动的特点：**
- 1.浮动元素会完全脱离文档流，不会占据文档流中的位置
- 2.设置浮动以后元素会向父元素的左侧或者右侧移动
- 3.浮动元素默认不会从父元素中移出(高度塌陷问题就是浮动元素从父元素中移出的情况)
- 4.浮动元素向左或者向右移动时，不会超过它前边的其他浮动元素
- 5.如果浮动的元素的上边是一个没有浮动的元素，则浮动元素无法上移
- 6.浮动元素不会超过它上边的浮动的兄弟元素，最多最多就是和他一样高

**浮动的特点2：**
- 1.浮动元素不会盖住文字，文字会自动环绕在浮动元素的周围，所以我们可以利用浮动来设置文字环绕图片的效果
- 2.元素设置浮动以后，将会从文档流中脱离，从文档流中脱离以后，元素的一些特点也会发生变化

脱离文档流以后：
- 块元素：
    - 1.块元素不再独占页面的一行
    - 2.脱离文档流以后，块元素的高度和高度默认都被内容撑开
- 行内元素：
	- 行内元素脱离文档流以后会变成块元素，特点和块元素一样


	简单总结：
    	1. 浮动的目前来讲它的主要作用就是让页面中的元素可以水平排列，通过浮动可以制作一些水平方向的布局
    	2. 脱离文档流以后，不再需要区分块和行内元素了
    	3. 浮动出现的初衷是实现文字环绕效果的，也就是说浮动元素不会盖住文字

##### 2.2.3.2 BFC
BFC 块级格式化环境，相当于元素变成了独立的区域，浮动是脱离文档流的，在空间上造成一种重叠现象，BFC就是为了在俯视图上不出现重叠，换言之，在标准文档流中为该元素空出它的位置，让它从表现上好像是回归了文档流

- BFC是CSS中的隐藏属性，可以为一个新的元素开启BFC
    开启BFC该元素会变成一个独立的布局区域
    - 元素开启BFC后的特点
    1.开启BFC的元素不会被浮动元素所覆盖
    2.开启BFC的元素子元素和父元素的外边距不会重叠
    3.开启BFC的元素可以包含浮动的子元素

    - 可以通过一些特殊方式开启元素的BFC
    1.设置父元素的浮动（不推荐）
    2.将元素设置为行内块元素（不推荐）
    3.将元素的overflow设置为非visible的值
        - 常用方式，为元素设置overflow:hidden 开启BFC以使其包含



##### 2.2.3.3 高度坍塌问题
![高度坍塌.png](.\CSS\imgs\高度坍塌.png)

高度坍塌问题：【如果父元素指定固定高度，那么如果内容少则会出现大部分空白区域，如果内容多，则会溢出】
在浮动布局中，父元素的高度默认是被子元素撑开的，当子元素浮动后，他会完全脱离文档流，子元素从文档流中脱离，将会无法撑起父元素的高度，导致父元素高度丢失，父元素高度丢失以后，其下的元素会自动上移，导致页面布局混乱
所以高度塌陷是浮动布局中比较常见的一个问题，这个问题我们必须进行处理，解决方案如下
- 为父元素设置固定的高度【不推荐】
- BFC
    ```
    <head>
        <meta charset="UTF-8">
        <title>BFC</title>
        <style>
            .outer{
                border:10px solid red;
                /* overflow: hidden; */
                /* float: left; */
                background-color: orange;
            }

            .inner{
                width: 100px;
                height: 100px;
                background-color: #bfa;
                float: left;
            }
        </style>
    </head>
    <body>
        <div class="outer">
            <div class="inner"></div>
        </div>
        <div style="width: 100px;height: 100px;background-color: yellow;">

        </div>
    </body>
    ```

##### 2.2.3.4 清除浮动的方式
```
<head>
    <meta charset="UTF-8">
    <title>clear</title>
    <style>
        div{
            font-size: 50px;
        }
        .box1{
            width: 200px;
            height: 200px;
            background-color: #bbffaa;
            float: left;
        }
        .box2{
            width: 300px;
            height: 300px;
            background-color: purple;
            float: right;
        }
        .box3{
            width: 200px;
            height: 200px;
            background-color: yellow;
             clear: both;
        }
    </style>
</head>
<body>
    <div class="box1">1</div>
    <div class="box2">2</div>
    <div class="box3">3</div>
</body>
```
 由于box1，box2的浮动，导致box3位置上移,也就是box3受到了box1浮动的影响，位置发生了变化
 如果我们不希望某个元素因为其他元素浮动的影响而改变位置，可以通过clear属性来清除浮动元素对当前元素所产生的影响

clear
- 作用:清除浮动元素对当期元素所产生影响
- 可选值
left 清除左侧浮动对当前元素的影响
right 清除右侧浮动对当前元素的影响
both 清除两侧中最大影响的那侧

    	原理：清除浮动以后，浏览器会自动为元素添加一个浮动元素高度大小的上外边距，以使其位置不受其他元素的影响

##### 2.2.3.5 高度坍塌问题的解决方案
- 解决方案一： 添加一个空的div,然后为其设置清除浮动[利用结构解决表现的问题，不算完美]
- 解决方案： 在父元素的最后添加一个块级元素，和box2是兄弟元素，并且让这个标签clear:both,利用伪元素在,在最后添加一个块级元素并清除浮动

```
<head>
    <meta charset="UTF-8">
    <title>高度塌陷的解决方案</title>
    <style>
         .box1{
             border: 10px red solid;
         }
         .box2{
             width: 100px;
             height: 100px;
             background-color: #bfa;
             float: left;
         }
         .box1::after{
             content: "";
             display: block;
             clear: both;
         }
         /* .box3{
             clear: both;
         } */

    </style>
</head>
<body>
    <div class="box1">
        <div class="box2">
        </div>
        <!-- <div class="box3"></div> -->
    </div>
</body>

```
##### 2.2.3.6 外边距重叠问题
外边距重叠的两个条件：相邻的 垂直方向
思想：用一个东西隔开box1和box2上边距
```
<head>
    <meta charset="UTF-8">
    <title>高度塌陷和外边距重叠的解决方案</title>
<style>
    .box1{
        width: 200px;
        height: 200px;
        background-color: #bfa;
    }
    .box2{
        width: 100px;
        height: 100px;
        background-color: orange;
        margin-top:30px;
    }
    .box1::before{
        content: "";
        display: table;
        /* 可以隔开本身还不占地方 */
    }
</style>
</head>
<body>
   <div class="box1 clearfix">
       <div class="box2"></div>
   </div>
</body>
```

**★★★★★★★★★★★★★★★  如何完美解决外边距重叠和高度坍塌两个问题？★★★★★★★★★★★★★★★★★★★★★★**
```
/* clearfix可以同时解决高度塌陷和外边距重叠问题，当你遇到这些问题时，直接使用clearfix */
    .clearfix::before,
    .clearfix::after{
        content: "";
        display: table;
        clear: both;
    }
```
#### 2.2.4 定位
##### 2.2.4.1 定位概述
- 定位是一种更加高级的布局手段
- 通过定位可以将元素摆放到页面的任何位置
- 使用postion属性来设置定位
可选值
    static 默认值， 元素是静止的，没有开启定位
    relative 开启元素的相对定位
    absolute 开启元素的绝对定位
    fixed  开启元素的固定定位
    stiky 开启元素的粘滞定位

- 偏移量（offset）
**【只有开启了定位的元素才可以使用偏移量，和margin不同的是他只会移动自身，不会影响其他元素】**
- 当元素开启了定位以后，可以通过偏移量来设置元素的位置
    top - 定位元素和定位位置上边的距离
    bottom- 定位元素和定位位置下边的距离

	- 定位元素垂直方向的位置由top和bottom两个属性来控制，通常只会使用其中给一个
    - top 值越大，定位元素越往下移
    - bottom 值越大，定位元素越往下走

 left - 定位元素和定位位置左边的距离
 right- 定位元素和定位位置右边的距离
    - 定位元素水平方向的位置由left和right两个属性来控制，通常只会使用其中给一个
    - left 值越大，定位元素越往右移
    - right 值越大，定位元素越往左走

##### 2.2.4.2 相对定位
- 当元素的position属性值为relative时则开启了元素的相对定位
- ** 参照物：元素在文档流中的位置 **
       1.如果祖先元素开启了定位，则是离它最近的那个
       2.如果祖先元素都没开启定位，则是根元素html
- 相对定位的特点
    1. 元素开启相对定位以后，如果不设置偏移量，元素不会发生任何的变化
    2. 相对位置是参照元素在文档流中的位置进行定位的
    3. 相对定位会提升元素的层级,甚至比浮动元素的层级还高
    4. 相对定位不会使元素脱离文档流
    5. 相对定位不会改变元素的性质，块还是块，行内还是行内

##### 2.2.4.3 绝对定位
- 当元素的position属性值为absolute时则开启了元素的绝对定位
-  ** 参照物：包含块，**
- 绝对定位的特点
    1. 元素开启绝对定位以后，如果不设置偏移量，元素的位置不会发生任何的变化
    2. 元素开启绝对定位以后， 元素会从文档流中脱离
    3. 绝对定位会改变元素的性质，行内变成块，块的宽高会被内容撑开
    4. j绝对定位会提升元素的层级,甚至比浮动元素的层级还高
    5.绝对定位元素是相对于其包含块进行定位的

包含块（containing block）
- 正常情况下：
    包含块就是离当前元素最近的祖先块元素

- 绝对定位的包含块
    包含块就是离它最近的开启了定位的祖先元素，如果所有的祖先元素都没有开启定位，则根元素就是他的包含块

- html （根元素，初始包含块）

**绝对定位后的变化**
- 水平布局公式
        **left** + margin-left + border-left + padding-left + width +padding-right +border-right + margin-right + **right** = 包含块的内容区的宽度
- 当我们开启了绝对定位以后
水平方向的布局等式就需要添加Left 和 right两个值
此时规则和之前一样，只是添加了两个值

	**当发生过度约束：**
    - 如果9个值没有auto 则自动调整right值使等式满足
    - 如果有auto,则自动调整auto的值以使等式满足
            可设置auto的值：margin width left right
    - 因为left 和right 的值默认，所以如果不知道Left和right或等式不满足时，会自动调整这两个值，
    - 如果需要Margin auto使其居中，则必须要将left和right设值为0

- 垂直方向布局的等式也必须要满足
top + margin-top/bottom + padding-top/bottom + border-top/bottom + right = 包含块的内容区的高度

        【如何让元素在包含块水平垂直居中】
        1、设置 bottom top right left 都为0
        2. 将Margin是这为 auto

##### 2.2.4.4 固定定位
- ** 参照物：浏览器的视口 **
- 当元素的position属性值为fixed时则开启了元素的固定定位
- 固定定位也是一种绝对定位，所以固定定位大部分特点都和绝对定位一样
不同点：
        固定定位永远参照浏览器的视口进行定位
        固定定位的元素不会随网页的滚动条滚动

![视口与网页图.png](.\CSS\imgs\视口与网页图.png)

##### 2.2.4.4 粘滞定位【一般不用，因为兼容性不太好】
- 当元素的position属性值为sticky时则开启了元素的粘滞
- 粘滞定位和相对定位的特点基本一致

网页侧边的一些回顶部的效果，当滚动到上面以后，就不再动了

![京东示例图1.png](.\CSS\imgs\京东示例图1.png)

![京东示例图2.png](.\CSS\imgs\京东示例图2.png)

##### 2.2.4.4 z-index
- 对于开启了定位的元素，可以通过z-index属性来指定元素的层级
- z-index需要一个整数作为参数，值越大的元素层级越高,
    - 元素的层级越高越优先显示
    - 如果元素的层级一样，则优先显示靠下面的元素
    - 祖先元素的层级再高也不会盖住后代元素

#### 2.2.5 字体和背景
##### 2.2.5.1 字体
- 字体相关的样式
    - color 用来设置字体颜色
    - font-size 字体大小
        - font-size相关的单位
        	- em 相对于当前元素的一个font-size 16px
        	- rem 相对于根元素的一个font-size
    - font-family 字体族（字体的格式）
        可选值：
            serif 衬线字体
            san-serif 非衬线字体
            monospace等宽字体
                - 指定了字体的类别，浏览器会自动使用该类别下的字体
        - font-family 可以同时指定多个字体，多个字体建使用，隔开
            - 字体生效时优先使用第一个，第一个无法使用则使用第二个，以此类推
            - 一般如果有空格或者特殊字符我们需要加一个引号引起来

```
            font-family: "Microsoft YaHei", "Heiti SC", tahoma, arial, "Hiragino Sans GB", 宋体, sans-serif;
        - 也可以使用@font-face 引入样式
```


- ** 【如何引入字体】**
	- font-family
```
font-family: 'Courier New', Courier, monospace;
```
	- 使用 @font-face

```
    <head>
        <style>

            @font-face{
                font-family: 'myfont';
                src: url('./font/ZCOOLKuaiLe-Regular.ttf');
            }
            p{
                color:red;
                font-size: 40px;
                font-family: 'myfont';
            }
        </style>
    </head>
    <body>
        <p>今天天气真不错</p>
    </body>
```
##### 2.2.5.1 图标字体
字体的优点：
    1. 矢量，不失真
    2. 字体可以随便切换颜色
    3. 字体文件比较小

- 图标字体（icon font）
    - 在网页中经常需要使用一些图标，可以通过图片来引入图标
        但是图片大小本身比较大，并且非常不灵活
    - 所以在使用图标是，我们还可以将图标直接设置为字体
        然后通过font-face的形式来对字体进行引入
    - 这样我们就可以通过字体的形式来使用图标

fontawsome 使用步骤
    1. 下载 https://fontawesome.com
    2.解压
    3. 将css和webfonts移动到项目中
    4. 将all.css引入到温昂也中
    5. 使用图标字体
        - 直接使用通过类名来使用图标字体
            class="fas fa-bell"
            class="fab fa-accessible-icon"

- 图标字体的使用
1.通过类
2.通过伪元素
3.通过实体

```
<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <link rel="stylesheet" href="./fa/css/all.css">
    <style>
        /* 用法2：伪元素 */
        li::before{
            content: "\f1b0";
            /* fbs
            font-family: 'Font Awesome 5 Brands'; */
            font-family: 'Font Awesome 5 Free' ;
            font-weight: 900; 
            /* font-family 和font-weight要一起粘贴过来才生效 */
            color: blue;
            margin-right: 10px;
        }
    </style>
</head>
<body>
    <ul>
        <li>锄禾日当午</li>
        <li>汗滴禾下土</li>
        <li>谁知盘中餐</li>
        <li>粒粒皆辛苦</li>
    </ul>
<!--
    用法3：
        通过实体来使用图标字体
            &#x图标编码;
 -->
    <span class="fas">&#xf0f3;</span>
</body>
```
- 阿里图标的使用图
![阿里图标字体的使用.png](.\CSS\imgs\阿里图标字体的使用.png)

































