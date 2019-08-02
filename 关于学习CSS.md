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

