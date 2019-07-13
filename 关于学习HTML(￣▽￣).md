# 关于学习HTML(￣▽￣)"

## HTML元素

指的是：从开始标签到结束标签的所有代码

某些HTML元素具有空内容（empty content）空元素在开始标签中进行关闭

br>就是没有关闭标签的空元素，定义换行

在开始标签中加斜杠，关闭空元素 eg：<  XXX      />

## HTML属性

属性总是以 名称/值 的形式出现 eg：name = "hehe"

属性总是在开始标签中规定eg：align="center"(对齐方式属性)    bgcolor = "yellow"(背景颜色属性)

（上述属性不建议使用，应使用样式代替）

eg：

html>

body style="background-color:yellow">

h2 style="background-color:red">This is a heading</h2

p style="background-color:green">This is a paragragh</p

</body

</html

字体、颜色和尺寸

font-family\color\font-size

文本对齐     text-align

## 标签

### 文本格式化

1.在body>中

//图片(C:\Users\lenovo\Pictures\1.PNG)

2.预格式文本（很适合显示计算机代码，因为会保留空格和换行）

pre>XXX

XXXX

XX  XXX

</pre

3.计算机输出标签(code不保留空格和换行，如需使用，要在code里包裹一层pre)

code>computer code      kbd>keyboard input      samp>sample text      var>computer variable

//图片(C:\Users\lenovo\Pictures\2.PNG)

4.引用

//图片(C:\Users\lenovo\Pictures\3.PNG)

浏览器通常会在q>的周围包围引号“”

浏览器通常会对blockquote>元素进行缩进

对缩写进行标记能够为浏览器、翻译系统以及搜索引擎提供有用的信息，

eg:

p>abbr title="World Health Organization">WHO</abbr 成立于1948年。</p

### 样式表

1.外部样式表

当样式需要被应用到很多页面的时候，通过改变一个外部样式表就可以改变所有应用这个样式的外观。

head>

link rel="stylesheet" type="text/css" href="mystyle.css">

</head



2.内部样式表

当单个文件需要特别样式时，可以在head部分通过style>标签定义内部样式表。

head>

style type="text/css">

body {background-color:red}

p{margin-lift:20px}

</style

</head



3.内联样式

当特殊的样式需要应用到个别元素时，在相关的标签中使用样式属性。样式属性可以包含任何的CSS属性。

p style="color:red;margin-left:20px">

This is a paragragh

</p

### 链接

通过a>标签定义 (在body>中)

eg：a href = "http://www.baidu.com">  click here to goto baidu!</a

1.name属性

规定锚（anchor）的名称，使用如下：

首先，创建一个书签（对锚进行命名）

a name="tips">基本的注意事项 - 有用的提示</a

然后，在同一文档中创建指向该锚的链接

a href="#tips">有用的提示</a

[也可以在其他页面中创建指向该锚的链接

a href="http://www.baidu.com/#tips">有用的提示</a

在上面的代码中，直接将#符号和锚名添加到URL的末端，就可以直接链接到tips这个命名锚了]

//图片(C:\Users\lenovo\Pictures\4.PNG)

2.target属性

把链接的target属性设置为“_blank”,该链接会在新窗口打开

“_top”跳出框架

3.电子邮件链接

a href="mailto:xxxx@qq.com">发送邮件</a

### 图像

通过img>标签定义（在body>中）

eg：img src = "haha.jpg" width = "200" height = "200" />

ima>标签为空标签，也就是说，没有闭合标签。

·替换文本属性Alt

当浏览器无法载入图像时，替换文本属性告诉读者他们失去的信息

eg：   ima src="boat.gif" alt="big boat">

## 表格

1.表格有table>标签定义，行由tr>标签定义，单元格内数据由td>标签定义，数据单元格可以包含文本、图片、列表、段落、表单、水平线、表格等等。

2.边框属性border

3.表头用th>标签定义

4.为了避免单元格为空不显示边框，则在空单元格加一个空格占位符&nbsp； 就可以将边框显示。

5.一些属性

​	表格的标题 caption>我的标题</caption   ps:在table标签和tr标签之间

​	跨2行 th rowspan="2">电话</th

​	跨2列 th colspan="2">电话</th

​	单元格边距cellpadding     单元格间距cellspacing

//图片(C:\Users\lenovo\Pictures\5.PNG)

## 列表

//图片(C:\Users\lenovo\Pictures\列表.PNG)
