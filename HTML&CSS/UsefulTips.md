# 常见的小技巧
## 快捷键
### VSCode
- “html”+tab: 快速生成html标准页面
- p(其他元素)+tab： 快速生成 p标签
- enter : 光标随着一起换行
- ctrl+enter:光标不随着一起换行
- alt+ shift+上方向键：往上复制
- alt+ shift+下方向键：往下复制
- Lorem + tab：快速生成随机文本
- ul>li +tab ：会生成ul包含li的结构，因为VSCode会根据CSS选择器来生成标签
- ul + ul + tab:会生成两个ul,因为VSCode会根据CSS选择器来生成标签

## 技术技巧
### 1. CSS
- **1.1 如何撑满父元素的内容区？**
    长度单位之百分比
    - 将属性设置为**相对于父元素属性**的百分比
    - 设置百分比可以使**子元素跟随父元素的改变而改变**
    - 使用百分比100%时不会延伸到内边距，只会将父元素的内容区域撑满
```
<head>
    <meta charset="UTF-8">
    <title>盒子模型</title>
    <style>
         .box1{
             width: 200px;
             height: 200px;
             background-color: orange;
             border:10px black  solid;
             padding:10px;
         }
         /*
            inner将父元素的内容区域撑满，不会延伸到内边距，使用百分比，如果不设置宽度和高度，默认是父元素内容区的宽度和高度
          */
         .inner{
             width:100%;
             height: 100%;
             background-color: #bbffcc;
         }
    </style>
</head>
<body>
    <div class="box1">
        <div class="inner"></div>
    </div>
</body>
```
- **1.2 CSS水平方向布局要点**
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

- **1.3 CSS垂直方向布局要点**
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

















