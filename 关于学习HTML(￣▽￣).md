# 关于学习HTML(￣▽￣)"

## HTML元素

指的是：从开始标签到结束标签的所有代码

某些HTML元素具有空内容（empty content）空元素在开始标签中进行关闭

`<br>`就是没有关闭标签的空元素，定义换行

在开始标签中加斜杠，关闭空元素 eg：<  XXX      />

## HTML属性

属性总是以 名称/值 的形式出现 eg：name = "hehe"

属性总是在开始标签中规定eg：align="center"(对齐方式属性)    bgcolor = "yellow"(背景颜色属性)

（上述属性不建议使用，应使用样式代替）

eg:

```html
<html>
	<body style="background-color:yellow">
		<h2 style="background-color:red"This is a heading</h2>
		<p style="background-color:green"This is a paragragh</p>
	</body>
</html>
```

字体、颜色和尺寸

font-family\color\font-size

文本对齐     text-align

## 标签

### 文本格式化

1.在`<body>`中

![](C:\Users\lenovo\Pictures\1.PNG)

2.预格式文本（很适合显示计算机代码，因为会保留空格和换行）

```html
<pre>xxx
xxxxx
 xxx xx
</pre>
```

3.计算机输出标签(code不保留空格和换行，如需使用，要在code里包裹一层pre)

`<code>`computer code      `<kbd>`keyboard input      `<samp>`sample text     `<var>`computer variable

![](C:\Users\lenovo\Pictures\2.PNG)

4.引用

![](C:\Users\lenovo\Pictures\3.PNG)

浏览器通常会在`<q>`的周围包围引号“”

浏览器通常会对`<blockquote>`元素进行缩进

对缩写进行标记能够为浏览器、翻译系统以及搜索引擎提供有用的信息，

eg:

```html
<p>abbr title="World Health Organization">WHO</abbr 成立于1948年。></p>
```

### 样式表

1.外部样式表

当样式需要被应用到很多页面的时候，通过改变一个外部样式表就可以改变所有应用这个样式的外观。

```html
<head>
	<link rel="stylesheet"type="text/css"href="mystlyle.css">
</head>
```



2.内部样式表

当单个文件需要特别样式时，可以在head部分通过style>标签定义内部样式表。

```html
<head>
    <style tepe="text/css">
        body{background-color:red}
        p{margin-lift:20px}
    </style>
</head>
```

3.内联样式

当特殊的样式需要应用到个别元素时，在相关的标签中使用样式属性。样式属性可以包含任何的CSS属性。

```html
<p style="color:red;margin-left:20px">
    This is a paragragh
</p>
```

### 链接

通过`<a>`标签定义 (在body>中)

eg:

```html
<a href="http://www.baidu.com">click here to goto baidu!</a>
```

1.name属性

规定锚（anchor）的名称，使用如下：

首先，创建一个书签（对锚进行命名）

`<a name="tips">基本的注意事项 - 有用的提示</a>`然后，在同一文档中创建指向该锚的链接

`<a href="#tips">有用的提示</a>`

[也可以在其他页面中创建指向该锚的链接

`<a href="http://www.baidu.com/#tips">有用的提示</a>`

在上面的代码中，直接将#符号和锚名添加到URL的末端，就可以直接链接到tips这个命名锚了]

![](C:\Users\lenovo\Pictures\4.PNG)

2.target属性

把链接的target属性设置为“_blank”,该链接会在新窗口打开

“_top”跳出框架

3.电子邮件链接

`<a href="mailto:xxxx@qq.com">发送邮件</a>`

### 图像

通过`<img>`标签定义（在`<body>`中）

eg：

`<img src = "haha.jpg" width = "200" height = "200" />`

`<img>`标签为空标签，也就是说，没有闭合标签。

·替换文本属性Alt

当浏览器无法载入图像时，替换文本属性告诉读者他们失去的信息

eg：   `<img src="boat.gif" alt="big boat">`

## 表格

1.表格有`<table>`标签定义，行由`<tr>`标签定义，单元格内数据由td>标签定义，数据单元格可以包含文本、图片、列表、段落、表单、水平线、表格等等。

2.边框属性border

3.表头用`<th>`标签定义

4.为了避免单元格为空不显示边框，则在空单元格加一个空格占位符&nbsp； 就可以将边框显示。

5.一些属性

​	表格的标题`< caption>我的标题</caption >`  ps:在table标签和tr标签之间

​	跨2行` <th rowspan="2">电话</th>`

​	跨2列 `<th colspan="2">电话</th>`

​	单元格边距cellpadding     单元格间距cellspacing

![](C:\Users\lenovo\Pictures\5.PNG)

## 列表

![](C:\Users\lenovo\Pictures\列表.PNG)

## HTML布局

1.div布局：div可以很好的管理布局位置，块式管理。

## 响应式Web设计（RWD：Responsive Web Design）

能够以可变尺寸传递网页

1.自己创建

2.使用Bootstrap：使用CSS框架

## 框架

通过使用框架，可以在同一个浏览器窗口显示不止一个页面。

每份HTML文档称为一个框架，并且每个框架都独立于其他框架。

坏处

- 开发人员必须同时跟踪更多的HTML文档
- 很难打印整张网页

#### 框架标签

Frame 标签定义了放置在每个框架中的HTML文档

eg：

```html
<frameset cols="25%,75%">
    <frame src="frame_a.html">
    <frame src="frame_b.html">
</frameset>
```

###### 注意事项

假如一个框架有可见边框，用户可以拖动边框来改变它的大小。为了避免这种情况，可以在`<frame>`标签中加入：noresize="noresize"

​		PS：不能将`<body></body>`标签与`<frameset></frameset>`标签同时使用

#### 内联框架iframe

语法

```html
<iframe src="URL"></iframe>
```

URL指向隔离页面的位置

iframe可用作链接的目标（target）链接的target属性必须引用iframe的name属性

eg：

```html
<iframe src="demo_iframe.htm" name="iframe_a"></iframe>
<p><a href="http://www.baidu.com" target="iframe_a">百度</a></p>
```

点击百度链接，网页会在iframe框架显示。

### HTML头部

`<head>`元素是所有头部元素的容器。

`<title><base><link><meta><script><style>`都可以被添加

### 实体

HTML不能使用大于号和小于号，会被浏览器误认为它们是标签。

如果希望正确的显示预留字符，我们必须在HTML源代码中使用字符实体

类似：

&entity_name 或者 &entity_number（浏览器对实体数字支持比实体名称强）

不间断空格（不会被浏览器忽略的空格）`&nbsp;`。

