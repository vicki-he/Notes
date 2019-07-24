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

## HTML表单

用于收集用户输入，由`<form>`定义

1. 所包含的表单元素：指的是不同类型的input元素/复选框/单选按钮/提交按钮等。

   - input元素

     | 类型（Type） | 描述                       |
     | ------------ | -------------------------- |
     | text         | 定义常规文本输入           |
     | radio        | 定义单选按钮输入（多选一） |
     | submit       | 定义提交按钮（提交表单）   |

     - 文本输入 `<input type="text">`定义用于文本输入的单行输入字段

     - 单选按钮输入`<input type="radio">`定义单选按钮

     - 提交按钮`<input type="submit">`定义用于向表单处理程序提交表单的按钮

       （表单处理程序通常是包含用来处理输入数据的脚本的服务器页面，在表单的action属性中指定。）

   - Action属性

     `<form action="action_page.php">`

     定义在提交表单时执行的动作，向服务器提交表单的通常做法是使用提交按钮，通常，表单会被提交到web服务器上的网页。

   - Method属性

     method属性规定在提交表单时所用的HTTP方法（GET or POST）

     `<form action="action_page.php" method="GET">`或者`<form action="action_page.php" method="POST">`

     使用GET时，表单数据在页面地址栏中是可见的，使用POST数据不可见故安全性更好。

   - Name属性

     如果要正确的被提交，每个输入字段必须设置一个name属性。

     `<input type="text" name="lastname" value="Mouse">`

   - `<fieldset>`组合表单数据

     `<fieldset>`元素组合表单中的相关数据，`<legend>`元素为`<fieldset>`元素定义标题。

     eg：

     ```html
     <form action="action_page.php">
         <fieldset>
             <legend>
                 Personal information:
             </legend>
             First name:<br>
             <input type="text" name="firstname" value="Mickey">
             <br>
             Last name:<br>
             <input ytpe="text" name="lastname" value="Mouse">
             <br><br>
             <input type="submit" value="Submit">
         </fieldset>
     </form>
     ```

`<form>`属性的列表

| 属性           | 描述                                                  |
| -------------- | ----------------------------------------------------- |
| accept-charset | 规定在被提交表单中使用的字符集   默认：页面字符集     |
| action         | 规定向何处提交表单的地址   提交页面                   |
| autocomplete   | 规定浏览器应该自动完成表单   默认：开启               |
| enctype        | 规定被提交数据的编码   默认：url-encoded              |
| method         | 规定在提交表单时所用的HTTP方法   默认：GET            |
| name           | 规定识别表单的名称   对于DOM使用：document.forms.name |
| novalidate     | 规定浏览器不验证表单                                  |
| targey         | 规定action属性中地址的目标   默认：_self              |

#### 表单元素

1. `<input>`

2. `<select>`（下拉列表）

   ```html
   <select name="cars">
       <option value="volvo">Volvo</option>
       <option value="saab">Saab</option>
       <option value="fiat">Fiat</option>
       <option value="audi">Audi</option>
   </select>
   ```

   `<option>`元素定义待选择的选项，列表通常会把首个选项显示为备选选项，可以通过selected属性预选某些选项   `<option value="audi" selected>Audi</option>`

3. `<textarea>`定义多行输入字段（文本域）

   ```html
   <textarea name="message" rows="10" cols="30">
       The cat was playing in the garden.
   </textarea>
   ```

4. `<button>`定义可点击按钮

   ```html
   <button type="button" onclick="alert('Hello World!')">
       Click Me!
   </button>
   ```

### 输入类型

1. text

2. password`<input type="password">`会被做掩码处理

3. checkbox复选框

   ```html
   <form>
       <input type="checkbox" name="vehicle" value="Bike">I have a bike.<br>
       <input type="checkbox" name="vehicle" value="Car">I have a car.<br>
   </form>
   ```

4. number`<input type="number">`用于应该包含数值的输入字段，能够对数字做出限制

5. date`<input type="date">`用于应该包含日期的输入字段。

   ```html
   <form>
       Birthday:
       <input type="date" name="bday">
   </form>
   ```

6. color用于应该包含颜色的输入字段

7. range用于应该包含一定范围内的值的输入字段

8. month允许用户选择月份和年份

9. week允许用户选择周和年

10. time允许用户选择时间（无时区）

11. datetime允许用户选择日期和时间（有时区）

12. datetime-local允许用户选择日期和时间（无时区）

13. email用于应该包含电子邮件地址的输入字段

14. search用于搜索字段（搜索字段的表现类似常规文本字段）

15. tel用于应该包含电话号码的输入字段

16. url用于应该包含URL地址的输入字段

### 输入属性

1. value属性规定输入字段的初始值
2. readonly属性规定输入字段为只读（不需要值，等同于readonly="readonly"）
3. disabled属性规定输入字段是禁用的（不需要值；被禁用元素不可点不可用不会被提交）
4. size属性规定输入字段的尺寸（以字符计）
5. maxlength属性规定输入字段允许的最大长度（不会有反馈，如果需要提醒用户，需要编写JS代码）
6. html5新增属性
   - autocomplete属性规定表单或输入字段是否应该自动完成（on或off）
   - novalidate属性规定在提交表单时不对表单数据进行验证
   - autofocus属性为布尔属性，规定当页面加载时`<input>`元素应该自动获得焦点
   - form属性规定`<input>`元素所属的一个或多个表单（如需引用一个以上的表单，使用空格分隔的表单id列表）
   - formaction属性规定当提交表单时处理该控件的文件的URL，覆盖`<form>`元素的action属性，适用于type=“submit”以及type=“image”
   - formenctype属性规定当把表单数据提交至服务器时对其进行编码（仅POST表单），覆盖`<form>`元素的enctype属性，适用于type=“submit”和type=“image”
   - formmethod属性定义用以向action URL发送表单数据的HTTP方法，覆盖`<form>`元素的method属性，适用于submit和image
   - formnovalidate布尔属性，规定在提交表单时不对`<input>`元素进行验证，覆盖`<form>`的novalidate属性，可用于submit
   - formtarget属性规定的名称或关键词指示提交表单后在何处显示接受到的相应，覆盖`<form>`的target，适用于submit和image
   - height和width属性，规定input元素高度和宽度，仅适用于image
   - list属性引用的`<datelist>`元素中包含了`<input>`元素的预定义选项
   - min和max规定input元素的最小值和最大值
   - multiple属性布尔属性，规定允许用户在input元素中输入一个以上的值，适用于email和file
   - pattern属性规定用于检查input元素的正则表达式   PS:使用全局的title属性对模式进行描述以帮助用户
   - placeholder属性规定用以描述输入字段预期值的提示（样本值或有关格式的简短描述），该提示会在用户输入值显示在输入字段中
   - required属性布尔属性，规定在提交表单之前必须填写输入字段
   - step属性规定input元素的合法数字间隔，eg：如果step=“3”，则合法数字应该是-3、0、0、6等。
