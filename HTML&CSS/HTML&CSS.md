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

![网页三要素.PNG](.\source\imgs\网页三要素.PNG)


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
![CharSet.PNG](.\source\imgs\CharSet.PNG)
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

#### 1.3.2 meta& title
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
