# 引入CSS样式表

## 内部样式表    
```javascript
写在html文档的head标签中title标签之后且用style标签定义
<style type="text/css"></style>
```
## 行内式（内联样式）
```javascript
只对所在标签及嵌套在其中的子标签起作用
<标签名 style="属性1:属性值1;属性2:属性值2;"> 内容 </标签名>
```
## 外部样式表 （外链式） 
```javascript
通过link标签将外部样式表链接到html中link标签放在head头部标签中
<link href="外部样式表文件的URL" type="text/css" rel="stylesheet" />
```
# 选择器

## 标签选择器（元素选择器）
```javascript
能快速为页面中同类型的标签统一样式
标签名（元素名） {
	属性1:属性值1;
	属性2:属性值2;
	属性3:属性值3;
}
```
## 类选择器（调用时用class=“类名”）
```javascript
类选择器使用“.”（英文点号）进行标识，后面紧跟类名
.类名 {
	属性1:属性值1; 
	属性2:属性值2; 
	属性3:属性值3;
 }
```
## 多类名选择器
```javascript
指给一个标签起多个类名，各个类名之间用空格隔开
```
## id选择器
```javascript
id选择器使用"#"进行标识，后面紧跟id名   
同一页面内不允许有相同名字的id名
id名 {
	属性1:属性值1; 
	属性2:属性值2; 
	属性3:属性值3;
 }
```
## 通配符选择器
```javascript
通配符选择器用“*”号表示，他是所有选择器中作用范围最广的，能匹配页面中所有的元素
* {
	属性1:属性值1; 
	属性2:属性值2; 
	属性3:属性值3;
 }
```
# css字体样式属性
```javascript
选择器 {
	font-size(字号大小): number px|em|pt等;
	font-family(字体): "宋体|微软雅黑|黑体等";
	font-weight(字体粗细): normal|bold|bolder|lighter|100~900(100的整数倍);
	font-style(字体风格): normal|italic(斜体)|oblique(斜体);
	font: font-style font-weight font-size/line-height font-family;
}
```
# css外观属性
```javascript 
选择器 {
	color: 预定义颜色值(red、blue等)|十六进制|rgb(0,0,0);
	line-height(行间距): number px|em|%;
	text-align(水平对齐方式): left(左对齐)|right(右对齐)|center(居中对齐);
	text-indent(首行缩进): number(不同单位的数值、em字符宽度的倍数、或相对于浏览器窗口宽度的百分比%，允许使用负值, 建议使用em作为设置单位);
	text-decoration(文本的装饰): none|underline(下划线)|overline(文本上的一条线)|line-through(穿过文本下的一条线);
}
```
# css复合选择器
## 交集选择器
```javascript
交集选择器由两个选择器构成，其中第一个为标签选择器，第二个为class选择器，两个选择器之间不能有空格。如：h3.special {}。
```
## 并集选择器
```javascript
并集选择器（CSS选择器分组）是各个选择器通过逗号连接而成的，任何形式的选择器（包括标签选择器、class类选择器id选择器等），都可以作为并集选择器的一部分。
如：.one,p {}。
```
## 后代选择器
```javascript
后代选择器又称为包含选择器，用来选择元素或元素组的后代，其写法就是把外层标签写在前面，内层标签写在后面，中间用空格分隔。如：.class h3 {}。
```
## 子元素选择器
```javascript
子元素选择器只能选择作为某元素子元素的元素。其写法就是把父级标签写在前面，子级标签写在后面，中间跟一个">"进行连接，注意，符号左右两侧各保留一个空格。如：.classs > h3 {}。
```
## 伪类选择器
```javascript
伪类选择器用于向某些选择器添加特殊的效果。如：:link {}、:hover {}。
```
# 块级元素
```javascript
每个块元素通常都会独自占据一整行或多整行，可以对其设置宽度、高度、对齐等属性，常用于网页布局和网页结构的搭建。
常见的块元素有<h1>~<h6>、<p>、<div>、<ul>、<ol>、<li>等，其中<div>标签是最典型的块元素。
块级元素的特点：
（1）总是从新行开始
（2）高度，行高、外边距以及内边距都可以控制。
（3）宽度默认是容器的100%
（4）可以容纳内联元素和其他块元素。
```
# 行内元素（inline-level）
```javascript
行内元素（内联元素）不占有独立的区域，仅仅靠自身的字体大小和图像尺寸来支撑结构，一般不可以设置宽度、高度、对齐等属性，常用于控制页面中文本的样式。
常见的行内元素有<a>、<strong>、<b>、<em>、<i>、<del>、<s>、<ins>、<u>、<span>等，其中<span>标签最典型的行内元素。
行内元素的特点：
（1）和相邻行内元素在一行上。
（2）高、宽无效，但水平方向的padding和margin可以设置，垂直方向的无效。
（3）默认宽度就是它本身内容的宽度。
（4）行内元素只能容纳文本或则其他行内元素。（a特殊）
```
```javascript
只有 文字才 能组成段落 因此 p 里面不能放块级元素，同理还有这些标签h1,h2,h3,h4,h5,h6,dt，他们都是文字类块级标签，里面不能放其他块级元素。
```
# 行内块元素（inline-block）
```javascript
行内块元素的特点：
（1）和相邻行内元素（行内块）在一行上,但是之间会有空白缝隙。
（2）默认宽度就是它本身内容的宽度。
（3）高度，行高、外边距以及内边距都可以控制。
```
# 标签显示模式转换--display
```javascript
块转行内：display:inline;
行内转块：display:block;
块、行内元素转换为行内块： display: inline-block;
```
# css背景（backgroung）
```javascript
background:背景颜色 背景图片地址 背景平铺 背景滚动 背景位置
选择器 {
	background: background-clolor background-image background-repeat background-attachment background-position;
	background-image(背景图片): none|url(url);
	background-repeat(背景平铺): repeat|no-repeat(不平铺)|repeat-x(在横向上平铺)|repeat-y(在纵向平铺);
	background-position(背景位置): length||lenght(百分数)|position||position(top|center| bottom|left|center|right);
}
	background-attachment(背景附着): scroll(背景图像是随对象内容滚动)|fixed(背景图像固定);
	background-color(背景透明): rgba(0,0,0,0.3); 
}
```
# css盒子
1、 border
```javascript
选择器 {
	border: border-width border-style(solid(单实线)|dashed(虚线)|dotted(点线)|double(双实线)) border-color;
}
```
2、table
```javascript
table {
	border-collapse(细线边框): collapse;//边框合并在一起。
	border-radius(圆角边框): 左上角 右上角 右下角 左下角;
}
```
3、 内边距
```javascript 
选择器 {
	padding: padding-top(上内边距) padding-right(右内边距) padding-bottom(下内边距) padding-left(左内边距);
}
```
4、 外边距
```javascript 
选择器 {
	margin: margin-top(上外边距) margin-right(右外边距) margin-bottom(下外边距) margin-left(左外边距);
}
```
5、盒子阴影
```javascript
1.前两个属性是必须写的。其余的可以省略。
2.外阴影 (outset) 但是不能写 默认 想要内阴影 inset。
选择器 {
	box-shadow: 水平阴影 垂直阴影 模糊距离 阴影尺寸 阴影颜色 内/外阴影;
}
```
6、浮动
```javascript 
选择器 {
	float: left(左浮动)|right(右浮动)|none;
}
```
7、清除浮动
```javascript 
选择器 {
	clear:left(不允许左侧有浮动元素（清除左侧浮动的影响）)|
		right(不允许右侧有浮动元素（清除右侧浮动的影响）)|
		both(同时清除左右两侧浮动的影响);
}
.clear:after {
	content: ".";
	display: block;
	clear: both;
}
.clearfix {zoom: 1;} //IE6、7专有 
```
# 定位
```javascript
元素的定位属性主要包括定位模式和边偏移两部分。
1、边偏移
	top	顶端偏移量，定义元素相对于其父元素上边线的距离
	bottom 底部偏移量，定义元素相对于其父元素下边线的距离
	left 左侧偏移量，定义元素相对于其父元素左边线的距离
	right 右侧偏移量，定义元素相对于其父元素右边线的距离
如：top: 100px; left: 100px;等。
2、定位模式
选择器 {
	position: static|relative|absolute|fixed;
}
	static 自动定位（默认定位方式） 
	relative 相对定位，相对于其原文档流的位置进行定位
	absolute 绝对定位，相对于其上一个已经定位的父元素进行定位
	fixed 固定定位，相对于浏览器窗口进行定位
```
## 静态定位
```javascript 
	静态定位是所有元素的默认定位方式，当position属性的取值为static时，可以将元素定位于静态位置。 所谓静态位置就是各个元素在HTML文档流中默认的位置。
	用处：取消定位。 position: static;
```
## 相对定位
```javascript 
	相对定位是将元素相对于它在标准流中的位置进行定位，当position属性的取值为relative时，可以将元素定位于相对位置。
	对元素设置相对定位后，可以通过边偏移属性改变元素的位置，但是它在文档流中的位置仍然保留。
```
```javascript 
注意：   
	1. 相对定位最重要的一点是，它可以通过边偏移移动位置，但是原来的所占的位置，继续占有。
	2. 其次，每次移动的位置，是以自己的左上角为基点移动（相对于自己来移动位置）
```
## 绝对定位
```javascript 
	当position属性的取值为absolute时，可以将元素的定位模式设置为绝对定位。
```
```javascript
	注：绝对定位最重要的一点是，它可以通过边偏移移动位置，但是它完全脱标，完全不占位置。
```
```javascript
1、父级没有定位
	若所有父元素都没有定位，以浏览器当前屏幕为准对齐(document文档)。
2、父级有定位
	绝对定位是将元素依据最近的已经定位（绝对、固定或相对定位）的父元素（祖先）进行定位。 
3、子绝父相
	子级是绝对定位的话， 父级要用相对定位。
4、绝对定位的盒子水平/垂直居中
	普通的盒子是左右margin 改为 auto就可， 但是对于绝对定位就无效了
	定位的盒子也可以水平或者垂直居中，有一个算法。
	1. 首先left50% 父盒子的一半大小
	2. 然后走自己外边距负的一半值就可以了 margin-left。
```
## 固定定位
```javascript 
	它以浏览器窗口作为参照物来定义网页元素。当position属性的取值为fixed时，即可将元素的定位模式设置为固定定位。
	当对元素设置固定定位后，它将脱离标准文档流的控制，始终依据浏览器窗口来定义自己的显示位置。不管浏览器滚动条如何滚动也不管浏览器窗口的大小如何变化，该元素都会始终显示在浏览器窗口的固定位置。
```
```javascript 
固定定位有两点：
	1. 固定定位的元素跟父亲没有任何关系，只认浏览器。
	2. 固定定位完全脱标，不占有位置，不随着滚动条滚动。
```
## 叠放次序
```javascript 
	当对多个元素同时设置定位时，定位元素之间有可能会发生重叠。
	在CSS中，要想调整重叠定位元素的堆叠顺序，可以对定位元素应用z-index层叠等级属性，其取值可为正整数、负整数和0。
选择器 {
	z-index: number(正值、负值、零);
}
```
```javascript 
注意：
	1. z-index的默认属性值是0，取值越大，定位元素在层叠元素中越居上。
	2. 如果取值相同，则根据书写顺序，后来居上。
	3. 后面数字一定不能加单位。
	4. 只有相对定位，绝对定位，固定定位有此属性，其余标准流，浮动，静态定位都无此属性，亦不可指定此属性。
```
# 元素显示与隐藏
```javascript 
	在CSS中有三个显示和隐藏的单词比较常见，我们要区分开，他们分别是 display visibility 和 overflow。他们的主要目的是让一个元素在页面中消失，但是不在文档源码中删除。
```
## display显示
```javascript
	display : none 隐藏对象 与它相反的是 display:block 除了转换为块级元素之外，同时还有显示元素的意思。
	特点： 隐藏之后，不再保留位置。
```
## visibility可见性
```javascript
设置或检索是否显示对象。
	visible:对象可视
	hidden:对象隐藏
特点：隐藏之后，继续保留原有位置。
```
## overflow溢出
```javascript
检索或设置当对象的内容超过其指定高度及宽度时如何管理内容。
	visible:不剪切内容也不添加滚动条。
	auto:超出自动显示滚动条，不超出不显示滚动条
	hidden:不显示超过对象尺寸的内容，超出的部分隐藏掉
	scroll:不管超出内容否，总是显示滚动条
```
# css高级技巧
## 鼠标样式(cursor)
```javascript
设置或检索在对象上移动的鼠标指针采用何种系统预定义的光标形状。
选择器 {
	cursor: default(小白)|pointer(小手)|move(移动)|text(文本);
}
```
## 轮廓(outline)
``` javascript
是绘制于元素周围的一条线，位于边框边缘的外围，可起到突出元素的作用。
选择器 {
	outline: outline-color outline-style outline-width;
}
	最直接的写法是:outline: 0;或者outline: none;
```
## 防止拖拽文本域(resize)
```javascript
	resize：none;这个单词可以防止火狐、谷歌等浏览器随意的拖动文本域。
```
## 垂直对齐(vertical-align )
```javascript
设置或检索对象内容的垂直对其方式。
选择器 {
	vertical-align: baseline(基线对齐)|top(顶部对齐)|middle(垂直居中)|bottom(底部对齐); 
}
	vertical-align不影响块级元素中的内容对齐，它只针对于行内元素或者行内块元素,特别是行内块元素，通常用来控制图片/表单与文字的对齐。
```
## 溢出的文字隐藏
```javascript
1、word-break:自动换行---主要处理英文单词
	normal 使用浏览器默认的换行规则。
	break-all 允许在单词内换行。
	keep-all 只能在半角空格或连字符处换行。
2、white-space---可以处理中文
white-space设置或检索对象内文本显示方式。通常我们使用于强制一行显示内容
	normal:默认处理方式 nowrap; //强制在同一行内显示所有文本，直到文本结束或者遭遇br标签对象才换行。
3、text-overflow 文字溢出
设置或检索是否使用一个省略标记（...）标示对象内文本的溢出
	text-overflow : clip | ellipsis
	clip:不显示省略标记（...），而是简单的裁切
	ellipsis:当对象内文本溢出时显示省略标记（...）
注意一定要首先强制一行内显示，再次和overflow属性 搭配使用
```
# 引入ico图标
```javascript
	<link rel="shortcut icon" href="favicon.ico" (可省略:type="image/x-icon")/>   
```
# html5标签
```javascript
	<header> 语义 :定义页面的头部  页眉</header>
	<nav>  语义 :定义导航栏 </nav> 
	<footer> 语义: 定义 页面底部 页脚</footer>
	<article> 语义:  定义文章</article>
	<section> 语义： 定义区域</section>
	<aside> 语义： 定义其所处内容之外的内容 侧边</aside>
```
1、datalist   标签定义选项列表
```javascript
请与 input 元素配合使用该元素
	<input type="text" value="输入明星" list="star"/> //input里面用 list
	<datalist id="star"> //datalist 里面用 id  来实现和 input 链接 
		<option>刘德华</option>
		<option>刘若英</option>
		<option>刘晓庆</option>
	 </datalist>
```
2、fieldset 元素可将表单内的相关元素分组，打包legend 搭配使用
```javascript
	<fieldset>
		<legend>用户登录</legend>  标题
		用户名: <input type="text"><br /><br />
		密　码: <input type="password">
 	 </fieldset>
```
3、 新增的input type属性值：
```javascript
类型			使用示例				含义
email		<input type="email">	输入邮箱格式
tel			<input type="tel"> 		输入手机号码格式
url			<input type="url">		输入url格式（地址）
number		<input type="number"> 	输入数字格式
search		<input type="search">	搜索框（体现语义化）
range		<input type="range"> 	自由拖动滑块
time		<input type="time">		小时分钟  
date		<input type="date">		年月日 
datetime	<input type="datetime">	时间    
month		<input type="month">	年月
week		<input type="week">		星期 年
```
4、Input常用新属性
```javascript
placeholder	<input type="text" placeholder="请输入用户名">	
	占位符  当用户输入的时候 里面的文字消失  删除所有文字，自动返回
autofocus	<input type="text" autofocus>	
	规定当页面加载时 input 元素应该自动获得焦点
multiple	<input type="file" multiple>	
	多文件上传
autocomplete	<input type="text" autocomplete="off">	
	规定表单是否应该启用自动完成功能有2个值，一个是on 一个是off;on代表记录已经输入的值	1.autocomplete首先需要提交按钮<br/>2.这个表单您必须给他名字
required	<input type="text" required> 	
	必填项内容不能为空
accesskey	<input type="text" accesskey="s">	
	规定激活（使元素获得焦点）元素的快捷键采用 alt + s的形式
```
# 多媒体标签
## 多媒体 (audio)
```javascript
	<audio src="音频路径"></audio>
并且可以通过附加属性可以更友好控制音频的播放，如：
	autoplay 自动播放
	controls 是否显示默认播放控件
	loop 循环播放。如果这个属性不写 默认播放一次(loop或者loop=“loop”表示无限循环)
由于版权等原因，不同的浏览器可支持播放的格式是不一样的
	<source> 标签允许您规定可替换的视频/音频文件供浏览器根据它对媒体类型或者编解码器的支持进行选择
	<audio controls>
		<source src="路径1">
		<source src="路径2">//路径为同一文件的不同格式文件路径
	</audio>
```
## 多媒体(video)
```javascript
	HTML5通过<audio>标签来解决音频播放的问题。同音频播放一样，<video>使用也相当简单，
	<video src="视频路径"></video>
并且可以通过附加属性可以更友好控制视频的播放，如：
	autoplay 自动播放
	controls 是否显示默认播放控件
	loop 循环播放。
	width 设置播放窗口宽度
	height 设置播放窗口的高度
	
由于版权等原因，不同的浏览器可支持播放的格式是不一样的
	<source> 标签允许您规定可替换的视频/音频文件供浏览器根据它对媒体类型或者编解码器的支持进行选择
	<video controls>
		<source src="路径1">
		<source src="路径2">//路径为同一文件的不同格式文件路径
	</video>
```

