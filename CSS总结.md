## 1. 何为 CSS

**CSS**是级联样式表（Cascading Style Sheets）的缩写。HTML 用于撰写页面的内容，而 CSS 将决定这些内容该如何在屏幕上呈现。

网页的内容是由 HTML的元素构建的，这些元素如何呈现，涉及许多方面，如整个页面的布局，元素的位置、距离、颜色、大小、是否显示、是否浮动、透明度等等。

1、CSS的定义：层叠样式表。属性和属性值用冒号分隔开，以分号结尾(这些符号都是英文的)。

2、CSS得引入方式：

- 行内引入：<div style="这里写样式">我是一个块级的标签</div>
- 嵌入式：将CSS样式表放到head中用<style>标签包裹起来
- 导入式：  将一个独立的.css文件引入HTML文件中，导入式使用@import 引入外部CSS文件，<style>标记也是写在<head>标记中。 导入式会在整个网页装载完后再装载CSS文件。
- 链接式引入：将一个独立的.css文件引入到HTML文件中，使用<link>标记写在<head>标记中。 链接式会以网页文件主体装载前装载CSS文件。

3、样式的应用顺序：

- 行内样式优先级最高

- 针对相同的样式属性，不同的样式属性将以合并的方式呈现

- 相同样式并且相同属性，呈现方式在<head>中的顺序决定，后面会覆盖前面属性

- !important 

   指定样式规则应用最优先

## 2.选择器 

基本选择器：

1、通用元素选择器：

　　* 表示应用到所有的标签。

```
*{margin：0；padding：0；}
```

2、标签选择器

　　 匹配所有使用 div 标签的元素（可以匹配所有标签）

```
div {color: yellow}
```

3、类选择器

　　匹配所有class属性中包含info的元素。

　　语法：.类名{样式}（类名不能以数字开头，类名要区分大小写。）

```
.yanse{color:yellow}
 
<div class="yanse"/>我的div</div>
```

4、id选择器

　　使用id属性来调用样式，在一个网页中id的值都是唯一的（是W3C规范而不是规则，所以不会报错）。

　　语法：#ID名{样式}（ID名不能以数字开头

```
#Mycolor {color: yellow}
<h3 id="Mycolor">H3</h3>
```

 组合选择器：

1、多元素组合选择器

同时匹配两个或多个标签，用逗号隔开

2、后代元素选择器

 匹配所有div标签里嵌套的P标签，之间用空格分隔。

3、子代元素选择器

匹配所有div标签里嵌套的子P标签，之间用>分隔。

4、毗邻元素选择器

　　 匹配所有紧随div标签之后的同级标签P，之间用+分隔（只能匹配一个）。

伪类选择器：

**1. link、hover、active、visited**

-  a:link（未访问的链接状态）,用于定义了常规的链接状态。
-  a:hover（鼠标放在链接上的状态）,用于产生视觉效果。
-  a:active（在链接上按下鼠标时的状态）。
-  a:visited（已访问过的链接状态）,可以看出已经访问过的链接。

**2.** **before、after**

- P:before 在每个<p>元素的内容之前插入内容;
- P:after 在每个<p>元素的内容之后插入内容。

常用的属性：

**1. 颜色属性：**

 **color** 

- HEX（十六进制色：color: #FFFF00 --> 缩写：#FF0）
- RGB（红绿蓝，使用方式：color:rgb(255,255,0)或者color:rgb(100%,100%,0%)）
- RGBA（红绿蓝透明度，A是透明度在0~1之间取值。使用方式：color:rgba(255,255,0,0.5)）
- HSL（CSS3有效,H表示色调，S表示饱和度，L表示亮度，使用方式：color:hsl(360,100%,50%)）
- HSLA（和HSL相似，A表示Alpha透明度，取值0~1之间。）

**transparent**

- 全透明，使用方式：color: transparent

**opacity**

- 元素的透明度，语法：opacity: 0.5;
- 属性值在0.0到1.0范围内，0表示透明，1表示不透明。
- filter滤镜属性（只适用于早期的IE浏览器，语法：filter:alpha(opacity:20);）。

**2. 字体属性:**

 **font-style: 用于规定斜体文本**

- normal  文本正常显示
- italic  文本斜体显示
- oblique  文本倾斜显示

 **font-weight: 设置文本的粗细**

- normal（默认）
- bold（加粗）
- bolder（相当于<strong>和<b>标签）
- lighter （常规）
- 100 ~ 900 整百（400=normal，700=bold）

 **font-size: 设置字体的大小**

- 默认值：medium
- <absolute-size>可选参数值：xx-small、 x-small、 small、 medium、 large、 x-large、 xx-large
- <relative-size>相对于父标签中字体的尺寸进行调节。可选参数值：smaller、 larger
- <percentage>百分比指定文字大小。
- <length>用长度值指定文字大小，不允许负值。

**font-family：字体名称**

- 使用逗号隔开多种字体（优先级从前向后，如果系统中没有找到当前字体，则往后面寻找）

**font：简写属性**

- 语法：font：字体大小/行高 字体;（字体要在最后）

**3. 文本属性:**

 **white-space: 设置元素中空白的处理方式**

- normal：默认处理方式。
- pre：保留空格，当文字超出边界时不换行
- nowrap：不保留空格，强制在同一行内显示所有文本，直到文本结束或者碰到br标签
- pre-wrap：保留空格，当文字碰到边界时换行
- pre-line：不保留空格，保留文字的换行，当文字碰到边界时换行

**direction: 规定文本的方向** 

- ltr 默认，文本方向从左到右。
- rtl 文本方向从右到左。

**text-align:** **文本的水平对齐方式** 

- left
- center
- right

**line-height:** **文本行高**

- normal 默认

**vertical-align: \**文本\**所在行高的垂直对齐方式**

- baseline 默认
- sub 垂直对齐文本的下标，和<sub>标签一样的效果
- super 垂直对齐文本的上标，和<sup>标签一样的效果
- top 对象的顶端与所在容器的顶端对齐
- text-top 对象的顶端与所在行文字顶端对齐
- middle 元素对象基于基线垂直对齐
- bottom 对象的底端与所在行的文字底部对齐
- text-bottom 对象的底端与所在行文字的底端对齐

 **text-indent: 文本缩进**

 **letter-spacing: 添加字母之间的空白**

 **word-spacing: 添加每个单词之间的空白**

 **text-transform: 属性控制文本的大小写**

- capitalize 文本中的每个单词以大写字母开头。
- uppercase 定义仅有大写字母。
- lowercase 定义仅有小写字母。

 **text-overflow:** **文本溢出样式**

- clip 修剪文本。
- ellipsis 显示省略符号...来代表被修剪的文本。
- string 使用给定的字符串来代表被修剪的文本

 

**text-decoration: 文本的装饰**

- none 默认。
- underline 下划线。
- overline 上划线。
- line-through 中线。

**text-shadow：文本阴影**

- 第一个参数是左右位置
- 第二个参数是上下位置
- 第三个参数是虚化效果
- 第四个参数是颜色
- text-shadow: 5px 5px 5px #888;

**word-wrap：自动换行**

- word-wrap: break-word;

**4. 背景属性** 

- **url("http://images.cnblogs.com/cnblogs_com/suoning/845162/o_ns.png");  图片地址**

- **background-image:linear-gradient(green,blue,yellow,red,black); 颜色渐变效果**

 background-position 设置背景图像的位置坐标

- **background-position: center center; 图片置中，x轴center，y轴center**
- **1px -195px  截取图片某部分，分别代表坐标x，y轴**

 background-repeat 设置背景图像不重复平铺

- - **no-repeat 设置图像不重复，常用**
  - **round 自动缩放直到适应并填充满整个容器**
  - **space 以相同的间距平铺且填充满整个容器**

background-attachment 背景图像是否固定或者随着页面的其余部分滚动

background 简写

- **background: url("o_ns.png") no-repeat 0 -196px;**
- **background: url("o_ns.png") no-repeat center bottom 15px;**
- **background: url("o_ns.png") no-repeat left 30px bottom 15px;**

5. 列表属性

 list-style-type: 列表项标志的类型

- **none 去除标志**
- **decimal-leading-zero;  02.**
- **square;  方框**
- **circle;  空心圆**
- upper-alph; & disc; 实心圆

- **inside**
- **outside**

- -  5px #888;**

## 3.盒子模型

盒子模型指的是一个 HTML 元素可以看作一个盒子。从内到外，这个盒子是由**内容 content, 内边距 padding, 边框 border, 外边距 margin**构成的，如下图所示：

![box](http://10.1.74.238/web/brief-css/img/bd78f5d3be0673d6.jpg)

**说明：**

- Content 盒子的内容，如文本、图片等
- Padding 填充，也叫内边距，即内容和边框之间的区域
- Border 边框，默认不显示
- Margin 外边距，边框以外与其它元素的区域

## 4.边框与边距

######  边框

```
.example-1 {
  border: 1px dotted black; /* 上下左右都相同 */
}
.example-2 {
  border-bottom: 1px solid blue; /* 只设置底部边框 */
}
.example-3 {
  border: 1px solid grey;
  border-radius: 15px; /* 边框圆角 */
}
.example-4 {
  border-left: 5px solid purple;
}
```

###### 边距

```
padding: 20px; /* 上下左右都相同 */
padding-top: 20px;
padding-bottom: 100px;
padding-right: 50px;
padding-left: 80px;
padding: 25px 50px 75px 100px; /* 简写形式，按上，右，下，左顺序设置 */
padding: 25px 10px; /* 简写形式，上下为25px，左右为10px */
```

## 5.定位

`position`属性用于对元素进行定位。该属性有以下一些值：

- static 静态
- relative 相对
- fixed 固定
- absolute 绝对

设置了元素的`position`属性后，我们才能使用`top, bottom, left, right`属性，否则定位无效。

##### static

设置为静态定位`position: static;`，这是元素的默认定位方式，也即你设置与否，元素都将按正常的页面布局进行。
即：按照元素在 HTML出现的先后顺序从上到下，从左到右进行元素的安排。

##### relative

设置为相对定位`position: relative;`，这将把元素相对于他的静态（正常）位置进行偏移

##### fixed

设置为固定定位`position: fixed;`，这将使得元素固定不动（即使你上下左右拖动浏览器的滚动条）。
此时元素固定的位置仍由`top, bottom, left, right`属性确定，但相对的是视口（viewport，就是浏览器的屏幕可见区域）

##### absolute

设置为绝对定位`position: absolute;`，将使元素相对于其**最近设置了定位属性（非static）的父元素**进行偏移。
如果该元素的所有父元素都没有设置定位属性，那么就相对于`<body>`这个父元素

## 6.溢出浮动

当元素内容超过其指定的区域时，我们通过溢出`overflow`属性来处理这些溢出的部分。
溢出属性有一下几个值：

- visible 默认值，溢出部分不被裁剪，在区域外面显示
- hidden 裁剪溢出部分且不可见
- scroll 裁剪溢出部分，但提供上下和左右滚动条供显示
- auto 裁剪溢出部分，视情况提供滚动条

在一个区域或容器内，我们可以设置`float`属性让某元素水平方向上向左或右进行移动，其周围的元素也会重新排列。

## 7.不透明度和伪类和伪元素

我们可以用`opacity`对任何元素（不过常用于图片）设置不透明度。
值在`[0.0～`1.0]之间，值越低，透明度越高

伪类（pseudo-class）或伪元素（pseudo-element）用于定义元素的某种特定的状态或位置等。
比如我们可能有这样的需求：

- 鼠标移到某元素上变换背景颜色
- 超链接访问前后访问后样式不同
- 离开必须填写的输入框时出现红色的外框进行警示
- 保证段落的第一行加粗，其它正常
- ...

使用伪类/伪元素的语法如下：

```
/* 选择器后使用 : 号，再跟上某个伪类/伪元素 */
selector:pseudo-class/pseudo-element {
  property:value;
}
```

以下是常用的伪类/伪元素的简单使用：

```
a:link {color:#FF0000;}     /* 未访问的链接 */
a:visited {color:#00FF00;}  /* 已访问的链接 */
a:hover {color:#FF00FF;}    /* 鼠标划过链接 */
/* 鼠标移到段落则改变背景颜色 */
p:hover {background-color: rgb(226, 43, 144);}
p:first-line{color:blue;}   /* 段落的第一行显示蓝色 */
p:first-letter{font-size: xx-large;}   /* 段落的第一个字超大 */

h1:before { content:url(smiley.gif); } /* 在每个一级标题前插入该图片 */
h1:after { content:url(smiley.gif); } /* 在每个一级标题后插入该图片 *
```

