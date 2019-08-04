## CSS概述

CSS指层叠样式表（Cascading Style Sheets）

#### 层叠次序

样式表允许以多种方式规定样式信息。样式可以在单个的HTML元素中、HTML页的头元素中和一个外部的CSS文件中规定。可以在同一个HTML文档内部引用多个外部样式表。

一般而言，样式会根据下面的规则层叠于一个新的虚拟样式表中，其中数字4拥有最高的优先权。

1. 浏览器缺省设置
2. 外部样式表
3. 内部样式表（位于`<head>`标签内部）
4. 内联样式（在HTML元素内部）

### CSS语法

CSS规则由两个主要部分构成：选择器selector，以及一条或多条声明

`selector{declaration1;declaration2;...declarationN }`

选择器通常是需要改变样式的HTML元素。

每条声明由一个属性和一个值组成

eg：selector{property: value}

`h1{color:red; font-size:14px;}`

### CSS高级语法

可以对选择器进行分组，同一组的选择器可以分享相同的声明。

eg：`h1,h2,h3,h4,h5,h6{`

`				color:green;`				

`}`

4.0游览器无法理解继承，但是可以理解组选择器。所以可以如下方式使用继承：

```css
body{
	font-family: Verdana, sans-serif;
}
p,td,ul,ol,li,dl,dt,dd{
    font-family: Verdana, sans-serif;
}
```

创建一个针对P的特殊规则，这样就可以摆脱父元素的规则。

```css
body{
	font-family: Verdana, sans-serif;
}
td,ul,ol,li,dl,dt,dd{
    font-family: Verdana, sans-serif;
}
p{
    font-family: Times, "Times New Roman", serif;
}
```

##### id 选择器

以“#”来定义。

eg：

```css
#red{color:red;}
#green{color:green;}

<p id="red">这个段落是红色</p>
<p id="green">这个段落是绿色</p>
```

id选择器常用于建立派生选择器。

```css
#sidebar p {
    font-style: italic;
    text-align: right;
    margin-top: 0.5em;
}
```

上面的样式只会应用出现在id是sidebar的元素内的段落。id只能出现一次，但是id选择器作为派生选择器可以被使用很多次。

##### 类选择器

在CSS中，类选择器以一个点号显示：`.center {text-glign: center}`

在上面的例子中，所有拥有center类的HTML元素均为居中。

```css
<h1 class="center">
This heading will be center-aligned
</h1>

<p class="center">
This paragragh will also be center-aligned
</p>
```

和id一样，class也可以被用作派生选择器；

##### 属性选择器

下面的例子为带有title属性的所有元素设置样式：

```css
[title]
{
    color: red;
}
```

下面的例子为title=“W3School”的所有元素设置样式：

```css
[title=W3School]
{
    border: 5px solid bule;
}
```

下面的例子为包含指定值的title属性的所有元素设置样式。适用于由空格分隔的属性值：

`[title~=hello]{color: red;}`

下面的例子为带有包含指定值的lang属性的所有元素设置样式。适用于由连字符分隔的属性值：

`[lang|=en]{color: red;}`

### 插入样式表

1. 外部样式表：当样式需要应用于很多页面时，外部样式表将是理想的选择。在使用外部样式表的情况下，你可以通过改变一个文件夹来改变整个站点的外观。每个页面使用`<link>`标签链接到样式表。`<link>`标签在文档头部

   ```html
   <head>
       <link rel="stylesheet" type="text/css" href="mystyle.css" />
   </head>
   ```

   外部样式表可以在任何文本编辑器中进行编辑。文件不能包含任何的html标签。样式表应该以.css扩展名进行保存。下面是一个样式表文件的例子：

   ```css
   hr {color: sienna;}
   p {margin-left: 20px;}
   body {background-image: url("images/back40.gif");}
   
   ```

2. 内部样式表：当单个文档需要特殊的样式时，就应该使用内部样式表。你可以使用`<style>`标签在文档头部定义内部样式表：

   ```html
   <head>
       <style type="text/css">
           hr {color: sienna;}
           p {margin-left: 20px;}
           body {background-image: url("image/back40.gif");}
       </style>
   </head>
   
   ```

3. 内联样式：由于要将表现和内容混杂在一起，内联样式会损失掉样式表的许多优势，慎用。

   要使用内联样式，你需要在相关的标签内使用样式（style）属性。Style属性可以包含任何的CSS属性，本例展示如何改变段落的颜色和左外边距：

   ```html
   <p style="color: sienna; margin-left: 20px">
       This is a paragraph
   </p>
   
   ```

#### 多重样式

如果某些属性在不同的样式表中被同样的选择器定义，那么属性值将从更具体的样式表中被继承过来

## CSS样式

### 背景

背景属性不可继承

- 可以使用background-color属性设置背景色。这个属性接受任何合法的颜色值。

- 要把图像放入背景，需要使用background-image属性eg：`body {background-image: url(/i/eg_bg_04.gif);}`

- 在页面上对背景图像进行平铺，可以使用backgroung-repeat属性（repeat-x和repeat-y分别导致图像只在水平或垂直方向上重复，no-repeat不允许图像在任何方向上平铺）

- 可以利用background-position属性改变图像在背景中的位置

  ```css
  body{
      background-position: center;
  }
  
  ```

  为background-positon属性提供值的方法很多。首先，关键字（最多两个关键字eg：top right）：top/bottom/left/right/center。还可以使用长度值：如100px/5cm等。最后也可以使用百分数值。

- 如果文档比较长，那么当文档向下滚动时，背景图像也会随之滚动。当文档滚动到超过图像位置时，图像就会消失。可以通过background-attachment属性防止这种滚动 ，通过这个属性，可以声明图像相对于可视区时固定的（fixed），因此不会受到滚动的影响

```css
body {
    background-attachment: fixed;
}

```

### 文本

1. 缩进文本，可用text-indent属性实现文本缩进，所有元素的第一行都可以缩进一个给定的长度，甚至该长度可以是负值。下列规则会使所有段落的首行缩进5em：

   `p{text-indent: 5em;}`

   - text-indent可以使用所有长度单位，包括百分比值。百分数要相对于缩进元素父元素的宽度。下列缩进值是父元素的20%，即100个像素：

     ```html
     div {width: 500px;}
     p {text-indent: 20%;}
     
     <div>
         <p>this is a paragragh</p>
     </div>
     
     ```

   - 属性可以继承：如下标记中段落也会缩进50像素，这是因为这个段落继承了id为inner的div元素的的缩进值

     ```html
     div#outer {width: 500px;}
     div#inner {text-indent: 10%;}
     p {width: 200px;}
     
     <div id="outer">
         <div id="inner">some text. some text. some text.
             <p>this is a paragragh</p>
         </div>
     </div>
     
     ```

2. 水平对齐，可以使用text-align属性实现。值：left/right/center/`<CENTER>`/justify

   - `<CENTER>`不仅影响文本，还会把整个元素居中。text-align不会控制元素的对齐，而只影响内容部分。
   - justify两端对齐

3. 字间隔，可以使用word-spacing属性改变字之间的标准间隔。默认值normal与设置值为0是一样的。接受正、负长度值，正远负近。

   ```html
   p.spread {word-spacing: 30px;}
   p.tight {word-spacing: -0.5em;}
   
   <p class="spread">
       this is a paragragh.the spaces between words will be increased.
   </p>
   
   <p class="tight">
       this is a paragragh. the spaces between words will be decreased.
   </p>
   
   ```

4. 字母间隔，letter-spacing属性实现。与word-spacing属性的区别在于，字母间隔修改的是字符或者字母之间的间隔。

5. 字符转换，text-transform属性实现处理文本的大小写。有4个值：

   - none
   - uppercase
   - lowercase
   - capitalize：只对每个单词的首字母大写

6. 文本装饰，text-decoration属性，有5个值：

   - none
   - underline
   - overline
   - line-through
   - blink

   可以在一个规则中结合多种装饰，但是注意下面这种情况：

   ```css
   h2.stricken {text-decoration: line-through;}
   h2 {text-decoration: underline overline;}
   
   ```

   对于给定的规则，所有class为stricken的h2元素都只有一个贯穿线装饰，而没有下划线和上划线，因为**text-decoration值会替换而不是累积起来**

7. 处理空白符，white-space属性，值：normal/pre/nowrap（防止文本换行除了使用br元素）/pre-wrap(文本会保留空白符序列，但是文本行会正常的换行)/pre-line（合并空白符序列，但保留换行符）

### CSS 字体系列

- 指定字体系列，使用font-family属性定义文本的字体系列

  - 使用通用字体系列
  - 指定字体系列（更具体）

  建议在所有font-family规则中都提供一个通用字体系列。这样就提供了一条后路，在用户代理无法提供与规则匹配的特定字体时，就可以选择一个候选字体。

  当字体名字中有一个或多个空格，或者包括#或$之类的符号，需要在font-family声明中加引号。

- 字体风格，font-style属性最常用于规定斜体文本，值：normal-文本正常显示/italic-文本斜体显示/oblique-文本倾斜显示   （通常情况下，italic和oblique文本在web浏览器中看上去完全一样）

- 字体变形，font-variant属性可以设定小型大写字母`p {font-variant: small-caps;}`

- 字体加粗，font-weight属性设置文本粗细，关键字100~900为字体指定了9级加粗度。100对应最细的字体变形。400等价于nomal，700等价于bold。bolder浏览器会设置比所继承值更粗的一个字体加粗，与此相反，关键词lighter会导致浏览器将加粗度下移。

- 字体大小，font-size属性     1em=16px（父元素默认大小）

  在所有浏览器中均有效的方案是为body元素（父元素）以百分比设置默认的font-size值。

  ```css
  body {font-size: 100%;}
  h1 {font-size: 3.75em;}
  h2 {font-size: 2.5em;}
  p {font-size: 0.875em;}
  
  ```

### CSS链接

能够设置链接样式的CSS属性有很多，例如：color/font-family/background等。

链接的4中状态：

- a:link   普通的、未被访问的链接
- a:visited   用户已访问的链接
- a:hover   鼠标指针位于链接上
- a:active   链接被点击的时刻

一个次序规则：

1. a:hover必须位于a:link和a:visited之后
2. a:active必须位于a:hover之后

text-decoration属性大多用于去掉链接中的下划线

### CSS列表项

1. 修改标志类型：list-style-type 例如：`ul {list-style-type: spuare}`把无序列表中的列表项标志设置为方块。
2. 将标志改为图像：list-style-image 例如：`ul li {list-style-image: url(xxx.gif)}`
3. 列表标志位置：list-style-position （标志出现在列表项内容之外还是之内）

上述3个列表样式属性可以合并为一个方便的属性：list-style 例如`li {list-style: url(xxx.gif) spuare inside}`

list-style的值可以按任何顺序列出，而且这些值都可以忽略。只要提供了一个值，其他的就会填入其默认值。

### CSS表格

1. border属性可以为表格设置边框（颜色，宽度等）
2. border-collapse属性设置是否将表格边框折叠为单一边框
3. width height宽高
4. text-align设置水平对齐方式，vertical-align设置垂直对齐方式
5. padding表格内边距
6. color字体颜色，background-color背景颜色

### CSS轮廓

outline属性，规定元素轮廓的样式，颜色和宽度

| 属性          | 描述                           |
| ------------- | ------------------------------ |
| outline       | 在一个声明中设置所有的轮廓属性 |
| outline-color | 设置轮廓的颜色                 |
| outline-style | 设置轮廓的样式                 |
| outline-width | 设置轮廓的宽度                 |

### CSS定位

CSS有三种定位机制：普通流，浮动和绝对定位。

普通流中的元素的位置由元素在（X）HTML中的位置决定。块级框从上到下一个接一个的排列，框之间的垂直距离是由框的垂直外边距计算出来；行内框在一行中水平布置。

