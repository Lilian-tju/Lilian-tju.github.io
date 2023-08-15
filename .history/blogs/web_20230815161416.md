---
layout: page
permalink: /blogs/motifs/index.html
title: motifs
---

> ***个人练习代码记录***


# 基础

## HTML标题

HTML 标题（Heading）是通过 <h1> - <h6> 等标签进行定义的。

```text
<h1>This is a heading</h1>
<h2>This is a heading</h2>
<h3>This is a heading</h3>
```

## HTML段落

HTML 段落是通过 <p> 标签进行定义的。

```text
<p>This is a paragraph.</p>
<p>This is another paragraph.</p>
```

## HTML链接

HTML 链接是通过 <a> 标签进行定义的。

```text
<a href= "http://www.w3school.com.cn">This is a link</a>
```

## HTML 图像

HTML 图像是通过 <img> 标签进行定义的。

```text
<img src="w3school.jpg" width="104" height="142" />
```



# HTML 元素

**HTML 文档是由 HTML 元素定义的。**

## HTML 元素

HTML 元素指的是从开始标签（start tag）到结束标签（end tag）的所有代码。

注释：开始标签常被称为开放标签（opening tag），结束标签常称为闭合标签（closing tag）。

<img> 是空标签，意思是说，它只包含属性，并且没有闭合标签。

## HTML 元素语法

- HTML 元素以_开始标签_起始
- HTML 元素以_结束标签_终止
- _元素的内容_是开始标签与结束标签之间的内容
- 某些 HTML 元素具有_空内容（empty content）_
- 空元素_在开始标签中进行关闭_（以开始标签的结束而结束）
- 大多数 HTML 元素可拥有_属性_

## 嵌套的 HTML 元素

大多数 HTML 元素可以嵌套（可以包含其他 HTML 元素）。

HTML 文档由嵌套的 HTML 元素构成。

```text
<html>

<body>
<p>This is my first paragraph.</p>
</body>

</html>
```

## 空的 HTML 元素

没有内容的 HTML 元素被称为空元素。空元素是在开始标签中关闭的。

<br> 就是没有关闭标签的空元素（<br> 标签定义换行）。

在 XHTML、XML 以及未来版本的 HTML 中，所有元素都必须被关闭。

在开始标签中添加斜杠，比如 <br />，是关闭空元素的正确方法，HTML、XHTML 和 XML 都接受这种方式。

即使 <br> 在所有浏览器中都是有效的，但使用 <br /> 其实是更长远的保障。



# HTML 属性

**属性为 HTML 元素提供附加信息。**

## HTML 属性

HTML 标签可以拥有_属性_。属性提供了有关 HTML 元素的_更多的信息_。

属性总是以名称/值对的形式出现，比如：*name="value"*。

**属性总是在 HTML 元素的_开始标签_中规定。**

## 属性实例

HTML 链接由 <a> 标签定义。链接的地址在 href 属性中指定：

```text
<a href="http://www.w3school.com.cn">This is a link</a>
```

```text
属性例子 1:
<h1> 定义标题的开始。

<h1 align="center"> 拥有关于对齐方式的附加信息。

**TIY : 居中排列标题**

属性例子 2:
<body> 定义 HTML 文档的主体。

<body bgcolor="yellow"> 拥有关于背景颜色的附加信息。

TIY : 背景颜色

属性例子 3:
<table> 定义 HTML 表格。（您将在稍后的章节学习到更多有关 HTML 表格的内容）

<table border="1"> 拥有关于表格边框的附加信息。
```

## 始终为属性值加引号

属性值应该始终被包括在引号内。双引号是最常用的，不过使用单引号也没有问题。

在某些个别的情况下，比如属性值本身就含有双引号，那么您必须使用单引号，例如：

```text
name='Bill "HelloWorld" Gates'
```

### 完整的标签参考手册



### HTML 全局属性



![](https://secure2.wostatic.cn/static/vSo4jhUiHE2og6srtyYyRP/image.png?auth_key=1692087086-5Ggn9AwTh1x7wCW7a2gxHu-0-097af7689bf8531d51832e4104076f9d)

# HTML 标题

**在 HTML 文档中，标题很重要。**

## HTML 标题

标题（Heading）是通过 <h1> - <h6> 等标签进行定义的。

<h1> 定义最大的标题。<h6> 定义最小的标题。

## 标题很重要

请确保将 HTML heading 标签**只用于标题**。不要仅仅是为了产生粗体或大号的文本而使用标题。

搜索引擎使用标题为您的网页的结构和内容编制索引。

因为用户可以通过标题来快速浏览您的网页，所以用标题来呈现文档结构是很重要的。

应该将 h1 用作主标题（最重要的），其后是 h2（次重要的），再其次是 h3，以此类推。

## HTML 水平线

<hr /> 标签在 HTML 页面中创建水平线。

hr 元素可用于分隔内容。

```text
<p>This is a paragraph</p>
<hr />
<p>This is a paragraph</p>
<hr />
<p>This is a paragraph</p>
```

提示：使用水平线 (<hr> 标签) 来分隔文章中的小节是一个办法（**但并不是唯一的办法**）。

## HTML 注释

可以将注释插入 HTML 代码中，这样可以提高其可读性，使代码更易被人理解。浏览器会忽略注释，也不会显示它们。

注释是这样写的：

```text
<!-- This is a comment -->
注释：开始括号之后（左边的括号）需要紧跟一个叹号，结束括号之前（右边的括号）不需要。

```

## HTML 提示 - 如何查看源代码

您一定曾经在看到某个网页时惊叹道 “WOW! 这是如何实现的？”

如果您想找到其中的奥秘，只需要单击右键，然后选择“查看源文件”（IE）或“查看页面源代码”（Firefox），其他浏览器的做法也是类似的。这么做会打开一个包含页面 HTML 代码的窗口。

# HTML 段落

**可以把 HTML 文档分割为若干段落。**

## HTML 段落

段落是通过 <p> 标签定义的。

```text
<p>This is a paragraph</p>
<p>This is another paragraph</p>
```

注释：浏览器会自动地在段落的前后添加空行。（<p> 是块级元素）

提示：**使用空的段落标记 <p></p> 去插入一个空行是个坏习惯。**用 <br /> 标签代替它！（但是不要用 <br /> 标签去创建列表。不要着急，您将在稍后的篇幅学习到 HTML 列表。）

## HTML 折行

如果您希望在不产生一个新段落的情况下进行换行（新行），请使用 <br /> 标签：

```text
<p>This is<br />a para<br />graph with line breaks</p>
```

## <br> 还是 <br />

您也许发现 <br> 与 <br /> 很相似。

在 XHTML、XML 以及未来的 HTML 版本中，不允许使用没有结束标签（闭合标签）的 HTML 元素。

即使 <br> 在所有浏览器中的显示都没有问题，使用 <br /> 也是_更长远的保障_。

## HTML 输出 - 有用的提示

我们无法确定 HTML 被显示的确切效果。屏幕的大小，以及对窗口的调整都可能导致不同的结果。

对于 HTML，您无法通过在 HTML 代码中添加额外的空格或换行来改变输出的效果。

当显示页面时，浏览器会移除_源代码中_多余的空格和空行。所有连续的空格或空行都会被算作一个空格。需要注意的是，HTML 代码中的所有连续的空行（换行）也被显示为一个空格。

# HTML 样式

style 属性用于改变 HTML 元素的样式。

## HTML 的 style 属性

style 属性的作用：

**提供了一种改变所有 HTML 元素的样式的通用方法。**

样式是 HTML 4 引入的，它是一种新的首选的改变 HTML 元素样式的方式。通过 HTML 样式，能够通过使用 style 属性直接将样式添加到 HTML 元素，或者间接地在独立的样式表中（CSS 文件）进行定义。

您可以在我们的 [CSS 教程](https://www.w3school.com.cn/css/index.asp)中学习关于样式和 CSS 的所有知识。

在我们的 HTML 教程中，我们将使用 style 属性向您讲解 HTML 样式。

## 不赞成使用的标签和属性

在 HTML 4 中，有若干的标签和属性是被废弃的。被废弃（Deprecated）的意思是在未来版本的 HTML 和 XHTML 中将不支持这些标签和属性。

这里传达的信息很明确：请避免使用这些被废弃的标签和属性！

![](https://secure2.wostatic.cn/static/hgNqoXMPkaudbyebDqWfke/image.png?auth_key=1692087088-6otH8nDEPPnuZ9767ZgLkb-0-8f48205b538e969285adfea5ce017c9c)

对于以上这些标签和属性：请使用样式代替！

## HTML 样式实例 - 背景颜色

background-color 属性为元素定义了背景颜色：

```text
<html>
<body style="background-color:yellow">
<h2 style="background-color:red">This is a heading</h2>
<p style="background-color:green">This is a paragraph.</p>
</body>
</html>

```

旧方法：

```text
<html>

<body bgcolor="yellow">
<h2>This is a heading</h2>
<p>This is a paragraph.</p>
<p>The old bgcolor attribute only works on the body element.</p>
<p>For future proof HTML, use styles instead:</p>
</body>

</html>
```

## HTML 样式实例 - 字体、颜色和尺寸

font-family、color 以及 font-size 属性分别定义元素中文本的字体系列、颜色和字体尺寸

style 属性淘汰了旧的 <font> 标签。

## HTML 样式实例 - 文本对齐

text-align 属性规定了元素中文本的水平对齐方式：

style 属性淘汰了旧的 "align" 属性。

# HTML 文本格式化





**注意：**应该使用 %20 来替换单词之间的空格，这样浏览器就可以正确地显示文本了



表格有空格占位符&nbsp

# HTML Iframe 内联框架

**iframe 用于在网页内显示网页。**

```text
<iframe src="URL"></iframe>
URL 指向隔离页面的位置。

```

## Iframe - 设置高度和宽度

height 和 width 属性用于规定 iframe 的高度和宽度。

属性值的默认单位是像素，但也可以用百分比来设定（比如 "80%"）。

```text
<iframe src="demo_iframe.htm" width="200" height="200"></iframe>
```

## Iframe - 删除边框

frameborder 属性规定是否显示 iframe 周围的边框。

设置属性值为 "0" 就可以移除边框：

## 使用 iframe 作为链接的目标

iframe 可用作链接的目标（target）。

链接的 target 属性必须引用 iframe 的 name 属性：

```text
<iframe src="demo_iframe.htm" name="iframe_a"></iframe>
<p><a href="http://www.w3school.com.cn" target="iframe_a">W3School.com.cn</a></p>
```

# HTML JavaScript

## HTML <script> 标签

HTML `<script>` 标签用于定义客户端脚本（JavaScript）。

`<script>` 元素即可包含脚本语句，也可通过 `src` 属性指向外部脚本文件。

JavaScript 的常见用途是图像处理、表单验证和内容的动态更改。

如需选取 HTML 元素，JavaScript 最常用 `document.getElementById()` 方法。

这个 JavaScript 示例向 id="demo" 的 HTML 元素内写入 "Hello JavaScript!"：

## HTML <noscript> 标签

HTML `<noscript>` 标签定义了替代内容，这些内容将显示给在浏览器中禁用了脚本或浏览器不支持脚本的用户：



```text
<script>
document.getElementById("demo").innerHTML = "Hello JavaScript!";
</script>
<noscript>抱歉，您的浏览器不支持 JavaScript！</noscript>
```

# HTML 文件路径

## HTML 文件路径

文件路径描述了网站文件夹结构中某个文件的位置。

文件路径会在链接外部文件时被用到：

- 网页
- 图像
- 样式表
- JavaScript

## 绝对文件路径

绝对文件路径是指向一个因特网文件的完整 URL：

```text
<img src="[https://www.w3school.com.cn/images/picture.jpg](https://www.w3school.com.cn/images/picture.jpg)" alt="flower">
```

<img> 标签以及 src 和 alt 属性在 HTML 图像这一章做了讲解。

## 相对路径

相对路径指向了相对于当前页面的文件。

在本例中，文件路径指向了位于当前网站根目录中 images 文件夹里的一个文件：

```text
<img src="/images/picture.jpg" alt="flower">
```

在本例中，文件路径指向了位于当前文件夹中 images 文件夹里的一个文件：

### 实例

```text
<img src="images/picture.jpg" alt="flower">
```

在本例中，文件路径指向了位于当前文件夹的上一级文件夹中 images 文件夹里的一个文件：

### 实例

```text
<img src="../images/picture.jpg" alt="flower">
```

## 好习惯

使用相对路径是个好习惯（如果可能）。

如果使用了相对路径，那么您的网页就不会与当前的基准 URL 进行绑定。所有链接在您的电脑上 (localhost) 或未来的公共域中均可正常工作。

# HTML 头部元素

![](https://secure2.wostatic.cn/static/tnZmkXC4HHtpkHgxXULtcM/image.png)

## HTML <head> 元素

<head> 元素是所有头部元素的容器。<head> 内的元素可包含脚本，指示浏览器在何处可以找到样式表，提供元信息，等等。

以下标签都可以添加到 head 部分：<title>、<base>、<link>、<meta>、<script> 以及 <style>。

## HTML <title> 元素

<title> 标签定义文档的标题。

title 元素在所有 HTML/XHTML 文档中都是必需的。

title 元素能够：

- 定义浏览器工具栏中的标题
- 提供页面被添加到收藏夹时显示的标题
- 显示在搜索引擎结果中的页面标题

一个简化的 HTML 文档：

```text
<!DOCTYPE html>
<html>
<head>
<title>Title of the document</title>
</head>

<body>
The content of the document......
</body>

</html>
```

## HTML <base> 元素

<base> 标签为页面上的所有链接规定默认地址或默认目标（target）：

```text
<head>
<base href="http://www.w3school.com.cn/images/" />
<base target="_blank" />
</head>
```

## HTML <link> 元素

<link> 标签定义文档与外部资源之间的关系。

<link> 标签最常用于连接样式表：

```text
<head>
<link rel="stylesheet" type="text/css" href="mystyle.css" />
</head>
```

## HTML <style> 元素

<style> 标签用于为 HTML 文档定义样式信息。

您可以在 style 元素内规定 HTML 元素在浏览器中呈现的样式：

```text
<head>
<style type="text/css">
body {background-color:yellow}
p {color:blue}
</style>
</head>
```

## HTML <meta> 元素

元数据（metadata）是关于数据的信息。

<meta> 标签提供关于 HTML 文档的元数据。元数据不会显示在页面上，但是对于机器是可读的。

典型的情况是，meta 元素被用于规定页面的描述、关键词、文档的作者、最后修改时间以及其他元数据。

<meta> 标签始终位于 head 元素中。

元数据可用于浏览器（如何显示内容或重新加载页面），搜索引擎（关键词），或其他 web 服务。

### 针对搜索引擎的关键词

一些搜索引擎会利用 meta 元素的 name 和 content 属性来索引您的页面。

下面的 meta 元素定义页面的描述：

```text
<meta name="description" content="Free Web tutorials on HTML, CSS, XML" />
```

name 和 content 属性的作用是描述页面的内容。

# HTML 布局

## 使用 <div> 元素的 HTML 布局

注释：<div> 元素常用作布局工具，因为能够轻松地通过 CSS 对其进行定位。

这个例子使用了四个 <div> 元素来创建多列布局：

## 使用 HTML5 的网站布局

HTML5 提供的新语义元素定义了网页的不同部分：          a

![](https://secure2.wostatic.cn/static/843HFMsZxLpYKqVhWx7bUz/image.png)

## 使用表格的 HTML 布局

注释：<table> 元素不是作为布局工具而设计的。

<table> 元素的作用是显示表格化的数据。

使用 <table> 元素能够取得布局效果，因为能够通过 CSS 设置表格元素的样式：

# HTML 响应式 Web 设计

## 什么是响应式 Web 设计？

- RWD 指的是响应式 Web 设计（Responsive Web Design）
- RWD 能够以可变尺寸传递网页
- RWD 对于平板和移动设备是必需的

## 创建您自己的响应式设计

创建响应式设计的一个方法，是自己来创建它：

```text
<!DOCTYPE html>
<html lang="en-US">
<head>
<style>
.city {
float: left;
margin: 5px;
padding: 15px;
width: 300px;
height: 300px;
border: 1px solid black;
} 
</style>
</head>

<body>

<h1>W3School Demo</h1>
<h2>Resize this responsive page!</h2>
<br>

<div class="city">
<h2>London</h2>
<p>London is the capital city of England.</p>
<p>It is the most populous city in the United Kingdom,
with a metropolitan area of over 13 million inhabitants.</p>
</div>

<div class="city">
<h2>Paris</h2>
<p>Paris is the capital and most populous city of France.</p>
</div>

<div class="city">
<h2>Tokyo</h2>
<p>Tokyo is the capital of Japan, the center of the Greater Tokyo Area,
and the most populous metropolitan area in the world.</p>
</div>

</body>
</html>
```

## 使用 Bootstrap

另一个创建响应式设计的方法，是使用现成的 CSS 框架。

Bootstrap 是最流行的开发响应式 web 的 HTML, CSS, 和 JS 框架。

Bootstrap 帮助您开发在任何尺寸都外观出众的站点：显示器、笔记本电脑、平板电脑或手机：



# HTML 计算机代码元素

![](https://secure2.wostatic.cn/static/xGnP1V7bEem5QMqYrFp1Q/image.png)

# HTML5 语义元素

## 什么是语义元素？

语义元素清楚地向浏览器和开发者描述其意义。

_非语义_元素的例子：<div> 和 <span> - 无法提供关于其内容的信息。

_语义_元素的例子：<form>、<table> 以及 <img> - 清晰地定义其内容。

## HTML5 中新的语义元素

许多网站包含了指示导航、页眉以及页脚的 HTML 代码，例如这些：<div id="nav"> <div class="header"> <div id="footer">。

HTML5 提供了定义页面不同部分的新语义元素：

- <article>
- <aside>
- <details>
- <figcaption>
- <figure>
- <footer>
- <header>
- <main>
- <mark>
- <nav>
- <section>
- <summary>
- <time>

## HTML5 语义元素

![](https://secure2.wostatic.cn/static/mjjexDRyYXkwjK6n3KjJq3/image.png)

## HTML5 <section> 元素

<section> 元素定义文档中的节。

根据 W3C 的 HTML 文献：“节（section）是有主题的内容组，通常具有标题”。

可以将网站首页划分为简介、内容、联系信息等节。



```text
<section>
   <h1>WWF</h1>
   <p>The World Wide Fund for Nature (WWF) is....</p>
</section> 
```

## HTML5 <article> 元素

<article> 元素规定独立的自包含内容。

文档有其自身的意义，并且可以独立于网站其他内容进行阅读。

<article> 元素的应用场景：

- 论坛
- 博客
- 新闻



```text
<article>
   <h1>What Does WWF Do?</h1>
   <p>WWF's mission is to stop the degradation of our planet's natural environment,
  and build a future in which humans live in harmony with nature.</p>
</article> 
```

## 嵌套语义元素

在 HTML5 标准中，<article> 元素定义完整的相关元素自包含块。

<section> 元素被定义为相关元素块。

我们能够使用该定义来决定如何嵌套元素吗？不，我们不能！

在因特网上，您会发现 <section> 元素包含 <article> 元素的 HTML 页面，还有 <article> 元素包含 <sections> 元素的页面。

您还会发现 <section> 元素包含 <section> 元素，同时 <article> 元素包含 <article> 元素。

## HTML5 <header> 元素

<header> 元素为文档或节规定页眉。

<header> 元素应该被用作介绍性内容的容器。

一个文档中可以有多个 <header> 元素。

下例为一篇文章定义了页眉：



```text
<article>
   <header>
     <h1>What Does WWF Do?</h1>
     <p>WWF's mission:</p>
   </header>
   <p>WWF's mission is to stop the degradation of our planet's natural environment,
  and build a future in which humans live in harmony with nature.</p>
</article> 
```

## HTML5 <footer> 元素

<footer> 元素为文档或节规定页脚。

<footer> 元素应该提供有关其包含元素的信息。

页脚通常包含文档的作者、版权信息、使用条款链接、联系信息等等。

您可以在一个文档中使用多个 <footer> 元素。

```text
<footer>
   <p>Posted by: Hege Refsnes</p>
   <p>Contact information: <a href="mailto:someone@example.com">
  someone@example.com</a>.</p>
</footer> 
```

## HTML5 中的语义元素

下面列出了以字母顺序排列的 HTML5 新语义元素。

这些链接指向完整的 HTML 参考手册。

![](https://secure2.wostatic.cn/static/wGiUXiZxxnbn1LdxtoWGp2/image.png)

斜杠（/）在 XHTML 和 XML 中是必需的。

如果您期望 XML 软件来访问您的页面，保持这个习惯是个好主意。

# HTML 字符实体

**HTML 中的预留字符必须被替换为字符实体。**

## HTML 实体

在 HTML 中，某些字符是预留的。

在 HTML 中不能使用小于号（<）和大于号（>），这是因为浏览器会误认为它们是标签。

如果希望正确地显示预留字符，我们必须在 HTML 源代码中使用字符实体（character entities）。

字符实体类似这样：

```text
&entity_name;

或者

&#entity_number;
```

如需显示小于号，我们必须这样写：&lt; 或 &#60;

提示：使用实体名而不是数字的好处是，名称易于记忆。不过坏处是，浏览器也许并不支持所有实体名称（对实体数字的支持却很好）。

## 不间断空格（non-breaking space）

HTML 中的常用字符实体是不间断空格(&nbsp;)。

浏览器总是会截短 HTML 页面中的空格。如果您在文本中写 10 个空格，在显示该页面之前，浏览器会删除它们中的 9 个。如需在页面中增加空格的数量，您需要使用 &nbsp; 字符实体。

## HTML 中有用的字符实体

注释：实体名称对大小写敏感！

![](https://secure2.wostatic.cn/static/4bEJDgC8nysnrUPn7tw89i/image.png)

# HTML 符号

## HTML 符号实体

在上一章中已经讲解了 HTML 实体。

普通键盘上不存在众多数学、技术和货币符号。

如需将此类符号添加到 HTML 页面，您可以使用 HTML 实体名称（HTML entity name）。

如果不存在实体名称，则可使用实体编号，十进制或十六进制的引用。

## HTML 支持的一些数学符号

![](https://secure2.wostatic.cn/static/mk4cQf6Rf63peDdgXtbQeM/image.png)

[完整的数学参考](https://www.w3school.com.cn/charsets/ref_utf_math.asp)

## HTML 支持的一些希腊字母

[完整的希腊参考](https://www.w3school.com.cn/charsets/ref_utf_greek.asp)

## HTML 支持的一些其他实体。

![](https://secure2.wostatic.cn/static/5WTKVBoh4jaMH2z6FG8HUr/image.png)

# HTML 统一资源定位器

URL 也被称为网址。

URL 可以由单词组成，比如 “[w3school.com.cn](http://w3school.com.cn)”，或者是因特网协议（IP）地址：192.168.1.253。大多数人在网上冲浪时，会键入网址的域名，因为名称比数字容易记忆。

## URL - Uniform Resource Locator

当您点击 HTML 页面中的某个链接时，对应的 <a> 标签指向万维网上的一个地址。

统一资源定位器（URL）用于定位万维网上的文档（或其他数据）。

网址，比如 [http://www.w3school.com.cn/html/index.asp](http://www.w3school.com.cn/html/index.asp)，遵守以下的语法规则：



```text
scheme://host.domain:port/path/filename
```

解释：

- scheme - 定义因特网服务的类型。最常见的类型是 http
- host - 定义域主机（http 的默认主机是 www）
- domain - 定义因特网域名，比如 [w3school.com.cn](http://w3school.com.cn)
- :port - 定义主机上的端口号（http 的默认端口号是 80）
- path - 定义服务器上的路径（如果省略，则文档必须位于网站的根目录中）。
- filename - 定义文档/资源的名称

编者注：URL 的英文全称是 Uniform Resource Locator，中文也译为“统一资源定位符”。

## URL Schemes

![](https://secure2.wostatic.cn/static/xxePdPwtFYJof7FWTFPSSR/image.png)

# HTML 框架

**通过使用框架，你可以在同一个浏览器窗口中显示不止一个页面。**

## 框架

通过使用框架，你可以在同一个浏览器窗口中显示不止一个页面。每份HTML文档称为一个框架，并且每个框架都独立于其他的框架。

使用框架的坏处：

- 开发人员必须同时跟踪更多的HTML文档
- 很难打印整张页面

框架结构标签（<frameset>）

- 框架结构标签（<frameset>）定义如何将窗口分割为框架
- 每个 frameset 定义了一系列行_或_列
- rows/columns 的值规定了每行或每列占据屏幕的面积

编者注：frameset 标签也被某些文章和书籍译为框架集。

## 框架标签（Frame）

Frame 标签定义了放置在每个框架中的 HTML 文档。

在下面的这个例子中，我们设置了一个两列的框架集。第一列被设置为占据浏览器窗口的 25%。第二列被设置为占据浏览器窗口的 75%。HTML 文档 "frame_a.htm" 被置于第一个列中，而 HTML 文档 "frame_b.htm" 被置于第二个列中：

```text
<frameset cols="25%,75%">
   <frame src="frame_a.htm">
   <frame src="frame_b.htm">
</frameset>
```

## 基本的注意事项 - 有用的提示

假如一个框架有可见边框，用户可以拖动边框来改变它的大小。为了避免这种情况发生，可以在 <frame> 标签中加入：noresize="noresize"。

为不支持框架的浏览器添加 <noframes> 标签。

重要提示：不能将 <body></body> 标签与 <frameset></frameset> 标签同时使用！不过，假如你添加包含一段文本的 <noframes> 标签，就必须将这段文字嵌套于 <body></body> 标签内。（在下面的第一个实例中，可以查看它是如何实现的。）

[导航框架](https://www.w3school.com.cn/tiy/t.asp?f=eg_html_frame_navigation)

本例演示如何制作导航框架。导航框架包含一个将第二个框架作为目标的链接列表。名为 "contents.htm" 的文件包含三个链接。

# HTML 背景

## 背景（Backgrounds）

<body> 拥有两个配置背景的标签。背景可以是颜色或者图像。

### 背景颜色（Bgcolor）

背景颜色属性将背景设置为某种颜色。属性值可以是十六进制数、RGB 值或颜色名。

```text
<body bgcolor="#000000">
<body bgcolor="rgb(0,0,0)">
<body bgcolor="black">
```

以上的代码均将背景颜色设置为黑色。

### 背景（Background）

背景属性将背景设置为图像。属性值为图像的URL。如果图像尺寸小于浏览器窗口，那么图像将在整个浏览器窗口进行复制。

<body background="clouds.gif">
<body background="[http://www.w3school.com.cn/clouds.gif](http://www.w3school.com.cn/clouds.gif)">

URL可以是相对地址，如第一行代码。也可以使绝对地址，如第二行代码。

提示：如果你打算使用背景图片，你需要紧记一下几点：

- 背景图像是否增加了页面的加载时间。小贴士：**图像文件不应超过 10k。**
- 背景图像是否与页面中的其他图象搭配良好。
- 背景图像是否与页面中的文字颜色搭配良好。
- 图像在页面中平铺后，看上去还可以吗？
- 对文字的注意力被背景图像喧宾夺主了吗？

## 基本的注意事项 - 有用的提示：

<body> 标签中的背景颜色（bgcolor）、背景（background）和文本（text）属性在最新的 HTML 标准（HTML4 和 XHTML）中已被废弃。W3C 在他们的推荐标准中已删除这些属性。

应该使用层叠样式表（CSS）来定义 HTML 元素的布局和显示属性。

# HTML <!DOCTYPE>

**<!DOCTYPE> 声明帮助浏览器正确地显示网页。**

## <!DOCTYPE> 声明

Web 世界中存在许多不同的文档。只有了解文档的类型，浏览器才能正确地显示文档。

HTML 也有多个不同的版本，只有完全明白页面中使用的确切 HTML 版本，浏览器才能完全正确地显示出 HTML 页面。这就是 <!DOCTYPE> 的用处。

<!DOCTYPE> 不是 HTML 标签。它为浏览器提供一项信息（声明），即 HTML 是用什么版本编写的。

提示：W3School 即将升级为最新的 HTML5 文档类型。

![](https://secure2.wostatic.cn/static/9Mz9nPg6ErP7sXMJU2bVEX/image.png)

