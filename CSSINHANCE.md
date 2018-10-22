使用CSS3进行增强

理解厂商前缀
例如
div { 
-webkit-border-radius: 10px; 
border-radius: 10px; 
}
CSS3 规范要达到 W3C 的推荐标准(即 定稿)状态要经过数年。浏览器则通常在 W3C 开发标准的过程中就会提前实现这些特 性。这样，标准在最终敲定之前就能知道哪 些地方还能进一步改进。 
在包含某个特性的初始阶段，浏览器 通常会使用厂商前缀实现这类特性 
.每个主流浏览器都有其自身的前缀: -webkit-(Webkit/Safari/ 旧版本的 Chrome)、 -moz-(Firefox)、-ms-(Internet Explorer)、 -o-(Opera)。应该将前缀放在 CSS 属性名 的前面 

为元素创建圆角
为元素创建四个相同的圆角 
1.可选，-webkit-border-radius:r; r是圆角半径单位是em px 或者百分数
2。border-radius:r;是圆角的半径大小 

为元素创建一个圆角 
1.可选-webkit-border- top-left-radius: r 
2.border-top-left-radius: r 
也可以是top-right,bottom-right,bottom-left

创建椭圆形圆角
1.可选，输入-webkit-border- radius: x/y，其中 x 是圆角在水平方向上的 14 半径大小，y 是圆角在垂直方向上的半径大小， 均表示为长度(带单位)。 
2.border-radius:x/y;

创建圆形
1.输入-webkit-border-radius:r;这 里的 r 是元素的半径大小(带长度单位)。 要创建圆形，可以使用短形式的语法，r 的值 应该等于元素高度或宽度的一半。 
2.输入 border-radius: r 

为文本添加阴影
(1) 输入 text-shadow:。 (2) 分别输入表示 x-offset(水平偏移 
量)、y-offset(垂直偏移量)、blur-radius(模 糊半径)和 color 的值(前三个值带长度单位 
四个值之间不用逗号分隔) 
Text-shadow属性不需要厂商前缀
将text-shadow改回默认值 text-shadow:none;

为其他元素添加阴影
使用 box-shadow 属性则可以为 元素本身添加阴影 
box- shadow 需要加上 -webkit- 厂商前缀 
box-shadow 属性接受六个值:带长度单位的 x-offset 和 y-offset、可选的带长度单 
位的 blur-radius、可选的 inset 关键字、可 选的带长度单位的 spread（用于收缩和扩张阴影） 值及 color 值。如 果不指定 blur-radius 和 spread 的值，则设 为 0。 

使用多重背景
不需要厂商前缀，可以使用标准的短形式语法
输入background-color: b，这里的 b 是希望为元素应用的备用背景颜色 
例如：
.night-sky{
/*备用颜色和图像*/
Background:navy url(ufo.png) no-repeat center bottom;

background:
url(ufo.png) no-repeat 50% 102%,
url(stars.png) no-repeat 100% -150px,
url(stars.png) no-repeat 0 -150px,
url(sky.png) repeat-x 50% 100%;
}

使用渐变背景
Background:linear-gradient(  );
Background:radial-gradient(  );

为元素设置不透明度
使用 opacity 属性可以修改元素(包括图 像)的透明度 
例如：opacity:0.5;
opacity的默认值为1,该属性值可以使用 0.00(完全透明)至 1.00 (完全不透明)之间的两位小数 
通过使用 opacity 属性和 :hover 伪 属性，可以产生一些有趣且实用的效果。例 如，img { opacity: .75; } 默认情况下可以 将图像设置为75%的不透明度，img:hover { opacity: 1; } 可导致用户鼠标停留在元素上 时元素变为不透明。在将缩略图链接到全尺 寸版本时经常看到这种效果。对于访问者来 说，悬浮可增强图像的动感。 

opacity 影响的是整个元素(包括其内容)，而 background-color: rgba(128,0,64,.6); 这 样 的设置仅影响背景的透明度。 
opacity 属 性并不是继承的。opacity 的值小于 1 的元 素的子元素也会受到影响，但这些子元素的 opacity 值仍为 1。 

生成内容的效果
content:” “;

使用sprite拼合图像

