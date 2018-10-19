CSS构造块
￼
样式表中的每条规则都有两个主要部分: 选择器(selector) 和声明块(declaration block)。选择器决定哪些元素受到影响;声 明块由一个或多个属性 - 值对(每个属性 - 值对构成一条声明，declaration)组成，它们 指定应该做什么 

层叠：当规则发生冲突时
CSS 用层叠的原则来考虑特殊性(specificity)、 顺序(order)和重要性(importance) 
特殊性规则指定选择器的具体程度。选 择器越特殊，规则就越强。遇到冲突时，优先应用特殊性强的规则 
特殊性还不足以判断在相互冲 突的规则中应该优先应用哪一个。在这种情 况下，规则的顺序就可以起到决定作用:晚 出现的优先级高 
重要性：可以声明一条特殊的规 则覆盖整个系统中的规则 
可以在某条声 明的末尾加上 !important，比如 p{ color: orange !important; } 

属性的值
1.inherit对于任何属性，如果希望显式地指出该 属性的值与对应元素的父元素对该属性设定 的值相同，就可以使用 inherit 值。 假 设有一个 article 元素，其中包含几个段落。 article 元素设置了一个边框。边框通常不会 被继承，因此 p { border: inherit; } 这条 规则可以让这些段落获得相同的边框样式。
 
2.只有极少数的 CSS 属性接受不带单位的 数字，如 3、0.65。其中最常见的就是 line- height(参见图 7.5.4)、z-index 和 opacity。例如line-height:1.5;是将与字号相乘，得到行高。

3.url有的 CSS 属性允许开发人员指定另一个文 件( 尤 其 是 图 像) 的 URL，background- 
image 就是这样一个属性。在这种情况下，使用url(file.ext),其中file.ext是目标资源的路径和文件名
例如 background:url(bg.png);相对url应该是相对于样式表的位置而不是相对于html文件的位置

4.CSS颜色
预定义颜色关键字、十六进制、RGB、HSL、RGBA、HSLA最后两种格式可以指定具有一定程度alpha透明度的颜色。

5.RGB
可以通过指定红、绿、蓝的量来构建颜色，使用0~255之间的数字来制定三种颜色的值
rgb(89,0,127)

6.RGBA
RGBA在RGB的基础上加了一个代表alpha透明度的A
可以在红、绿、蓝数值后面加上一个用 以指定透明度的 0 到 1 之间的小数 
property:ragb(red,green,blue,alpha transparency);
Alpha设置越接近0，颜色就越透明，如果设置0，就代表完全透明，就像完全没有设置任何颜色，1表示完全不透明。
例如：
/*不透明,和rgb(89,0,127);效果相同*/
background-color：rgba(89,0,127,1);
/*完全透明*/
background-color:rgba(89,0,127,0);
/*透明度25%*/
background-color: rgba(89,0,127,0.75); 

7.HSL和HSLA
HSL代表色相、饱和度和亮度，其中色相的取值范围是0~360
饱和度和亮度的取值均为百分数
HSL语法
property：hsl(hue,saturation,lightness);
HSLA的语法格式
property:hsla(hue,saturation,lightness,alpha transparency);
例如background-color:hsla(95,100%,28%,0.75);



操作样式表

样式的层叠和顺序
嵌入样式表(位于 style 元素内)与任 何链接的外部样式表之间的关系取决于它们在 HTML 中的相对位置。在两者发生冲突时，如果 link 元素在HTML代码中出现得早 ，style 元素 就会覆盖链接的样式表 ;如 果 link 元素出现得晚，其 中的样式及其包含的任何导入样式表就 会覆盖 style 元素的规则。 

使用与媒体相关的样式表
可以指定一个只用于特定输出的样式表， 如只用于打印 ，或只用于在浏览器中查看屏 幕 
a.在link元素中添加media=“output”,其中output可以是print,screen或all
b.也可以在样式表中使用@media规则


为文本添加样式

选择字体系列
font-family:name;其中的name是首选字体名称
对于包含多个单词的字体名称，应该用引号包围起来
虽然font-family属性是继承的，但有几个元素不会继承父元素的字体设置，其 中 有 表 单 的 select、textarea 和 input 元素，可以强制他们继承父元素字体设置
Input,select,textarea{font-family:inherit;}

指定替代字体
字体列表称为字体栈(font stack)。通常， 字体栈至少包含三个字体:希望使用的字体、 一个或几个替代字体，以及一个表示类属的 标准字体，表示“如果其他的字体都不可用， 就用这个” 
Font-family:Geneva,Tahoma,sans-serif;

OS X 和 Windows 上默认都有的字体 是非常有限的，它们仅包括 Arial、Comic Sans MS、Courier New、Georgia、Impact、 Trebuchet MS、Times New Roman 和 Verdana 
系统通常都具有下列表示类属的字体 名 称 对 应 的 字 体:serif、sans-serif、 cursive、fantasy 和 monospace。 因 此,标准的做法是在字体栈的末尾指定上述字体名称 中的一种。 

创建斜体
Font-style:italic;
Font-style是继承性的
想取消斜体的一个可能的原因是，要 在从父元素中继承了斜体格式的段落中对某 些文字进行强调 
取消斜体font-style:normal;

应用粗体格式
Font-weight:bold;
或者输入100~900之间的100的倍数，其中400表示正常粗细，700表示粗体
或者输入bolder表示更粗或者lighter表示更细
取消粗体格式
Font-weight是继承的
Font-weight:normal;

设置字体
直接使用像素指定要使用的特定字号，或使用百分数、em或者 rem 指定相 对于父元素文本的大小 
1. 理解 em 和百分数字体大小 
在 body 元素上建立一个基准，即声明 body { font-size:100%; } ，在大多数系统中是16px,
font- size 是继承性属性 ,要指定的字体大小/父元素的字体大小=em值 
2.rem
以根元素为参照系 设置其他元素的字体大小，而不是父元素， 根元素是 html 元素 
要指定的字体大小/根元素字体大小=rem值  实际上就是 要指定的字体大小/ 16 =值 

设置行高
行高指的是段落的行距，即段落内每行之间的距离 
Line-height:n;
这里n是一个数字，它与元素的字体大小相乘，得出需要的行高
或者输入a,这里的a是以em,像素或磅为单位的值
或者输入p%,这里的p%是字体大小的百分数

同时设置所有字体值
可以使用 font 简写属性同时设置字体样 式、粗细、变体、大小、行高和字体系列， 
使用font属性要至少包含字体样式和字体大小 font: .875em/1.3 “Palatino Linotype”,Palatino,serif;包含了font-size\line-height和font-famliy声明的font简记法，行高跟在字体大小和一个斜杠后面

设置背景
设 置 背 景 有 很 多 属 性 可 以 利 用， 包 括 background-color、background-image、 background-repeat、background-attachment 及 background-position 

background-color的默认值是transparent (透明)，background-image 的默认值是 none(无)， background-repeat 的默认值是 repeat(重复)， 
background-attachment 的默认值是 scroll(滚 动)，background-position的默认值是0 0 (等价于 top left，即左上角) 

Background-attachment:
Fixed;背景图是固定附着在浏览器窗口，及时访问者滚动页面，图像仍会继续显示
scroll;访问者滚动页面时背景图像会移动
local;只有访问者滚动背景图像所在元素，而不是整个页面时们才会移动
浏览器默认设置是scroll

指定元素背景图像的位置 background-position:x y;
其中 x 和 y 可以表示为距离左上角的绝对距离或百分数,如 20px 147px(允 许负值)。也可以用 left(左对齐)、center(居 中)或 right(右对齐)表示 x，用 top(顶 端对齐)、center(居中)或 bottom(底端对齐) 表示 y 

控制间距
Word-spacing:length;字间距
Letter-spacing:length;字偶距
word-spacing 和 letter-spacing 属性 是继承的。 

增加缩进
Text-indent:length;
Text-indent属性是继承的。

对齐文本
Text-align:
left左对齐，right右对齐，center居中对齐，justify两端对齐

修改文本大小写
Text-transform:
Capitalize;让每一个单词的首字母大写
uppercase;让所有字母大写
lowercase;让所有字母小写
none;让文本保持原来的样子

使用小型大写字母
使用 font-variant 调用小型 大写字母变体 
其中一些字母是大写的，但缩小到了小写字 母的大小 
Font-variant:small-caps;使用小型大写字母
Font-variant:none;取消小型大写字母

装饰文本
Text-decoration:
Underline;添加下划线
overline;添加上划线
Line-through;添加删除线
none;取消文本装饰

设置空白属性
默认情况下，HTML 文档里的多个空 格和回车会显示为一个空格，或者被忽略。 如果要让浏览器显示这些额外的空格，可以 使 用 white-space 属 性 
White-space:
Pre;让浏览器显示原文本中 所有的空格和回车 
Nowrap;确保所有空格不断行，也就是文本全部显示在一行
normal;按正常方式处理空格

用CSS进行布局

开始布局的注意事项
1.内容与显示隔离
应始终保持内容(HTML) 与显示(CSS)分离，通过外部样式表来实现
2.布局方法
网站设计主要有两大类：固定布局和响应式
固定(fixed)布局，整个页面和 每一栏都有基于像素的宽度，无论是使用移动电话和平板电脑 等较小的设备查看页面，还是使用桌 面浏览器并对窗口进行缩小，它的宽 度都不会改变。 
响应式布局也叫做流式布局，使用百分数定义宽度，允许页面随显示环境的改变进行放大 或缩小。 

在旧版浏览器中为HTML5元素添加样式
大多数浏览器允许对它 们并不原生支持的元素添加样式。Internet Explorer 8 及以下版本是个例外 

针对全部浏览器为 HTML5 新元素添加样式 
1.将这段代码添加到网站的主样式表文件
article, aside, figcaption, figure, footer, header, main, nav, section { 
display: block; } 
2.有 两 种 方 式 可 以 实 现 在 Internet Explorer 9 之前的 IE 中为新的 HTML5 元素设 置样式。 
它们都使用了 HTML5 shiv 这个 JavaScript 文 件 
A.在head元素中添加
<script src="http://html5shiv. ➝ googlecode.com/svn/trunk/ ➝ html5.js"></script> 
B.更好的方式是将该 JavaScript 文件放在你 自己的网站上 
,可以通过 https://github. com/aFarkas/html5shiv/ 下 载 HTML5 shiv 的 ZIP 文件 
只需要关注dist 这个文件夹，其中包含了将要用到的 html5shiv. 5 js。将该文件复制到你的网站的某个子目录(如名为 js 的目录)里面。 
然后引用该文件<script src="js/html5shiv.js"> </script> 

 盒模型
Css处理网页时，它认为每个元素都包含在一个不可见的盒子里，这就是盒模型。这个盒子有内容区域、内边距、边框和外边距组成
1.宽度、高度和盒模型
CSS的width属性对元素所显示宽度的影响，有两种处理方式
默认盒模型：css中的宽度指示的是内边距里内容区域的宽度，而元素早浏览器中显示款速则是内容宽度、左右内边距和左右边框的总和
￼
border-box盒模型，元素的显示宽度就等于width属性的值，内容宽度、内边距和边框都包含在里面，要使用这种模式，仅需对元素设置box-sizing:border-box;
￼
￼
控制元素的显示类型和可见性
display:
block;元素显示为块级元素
inline;元素显示为行内元素
Inline-block;元素显示为行内元素，同时具有块级元素的特征，即可以为元素设置四条边的width,height,padding,border,margin
None;隐藏元素，将其从文档流中完全移除

控制元素的可见性
Visibility:
Hidden;让元素不可见，但会在文档流中保留，空出一片区域
visible;让元素显示出来

设置元素的高度和宽度	
*{
-webkit-box-sizing:border-box;
-moz-box-sizing:border-box;
Box-sizing:border-box;
}
可以使用 * 通配符对所有元素应用 border-box 的规则。当然，也可以单独对元素应用 该规则(用你需要的选择器替换 * 即可)。带有 -webkit- 和 -moz- 这些奇怪前缀的属性可以让这些 规则在旧的 Android 和 iOS 设备上起作用，同时在 Firefox 上也能正常工作。 

为什么min-height通常比height更适用
除非你确定元素的内容不会变得更高， 最好避免在样式表中指定高度。在大多数 情况下，可以让内容和浏览器自动控制高 度。这可以让内容在浏览器和设备中根据 需要进行流动。 
如果希望元素至少具有某一特 定高度，可以设置 min-height。如果内容 日后变多，元素的高度会自动按需增长。 

在元素周围添加内边距
如果为padding设置四个值，那么它们分别表示上、右、下、左（按时钟顺序）
如果不设置内边距，元素的内容就会贴着边界

在元素中设置边框
定义边框风格	
Border-style:type,其中type可以是none,dotted(点线)，dashed(虚线)、
solid(实线)，double(双线)、groove(槽线)、 ridge(脊线)、inset(凹边)或 outset(凸边)。 
要让边框显示出来，至少必须定义边框样式，如果没有定义样式，就不会显示边框，边框样式的默认值是border-style:none;																	如border或 border-left 等，则未提供的属性将显示其 默认值。因此，border: 1px black; 相当于 border: 1px black none;，这意味着不会显 示边框(即便在之前使用 border-style 指定 了边框样式)。 

在元素中设置外边距	
如果元素位于另一个元素的上面，对于相互接触的两个 margin(即元素相互接触 的下外边距和上外边距)，仅使用其中较大 的一个，另一个外边距会被叠加。左右外边距不叠加。 
当 em 值用于内边距和外边距时，它的值是相对于元素的字体大小的，而不是相对于父 元素的字体大小的

使元素浮动
float:
left，让元素浮动到左边，其他 内容围绕在它右边 
right，让元素浮动到右边，其 他内容围绕在它左边 
none，让元素完全不浮动,是默认值，因此只有在特定情况下需要覆盖 某个浮动元素的样式规则时才需要用到它 
使用 width 属性显式地设置元素的宽 度，以便有空间放置围绕它 
的内容。 

控制元素浮动位置
浮动元素不会影响父元素的高度
使用clear:left/right/both来清除浮动效果
Clear:none;允许元素浮动在该元素的左右两边

让浮动元素的父元素“自清除” 
如果要让浮动元素的祖先元素在高度上包含浮动元素，并清除浮动，可以使用clearfix方法
.clearfix:before, .clearfix:after { 
content: " "; 
display: table; } 
.clearfix:after { clear: both; 
} 
.clearfix { *zoom: 1; }
为父元素添加clearfix类，让父元素容器的高度等于两列中较高的那一个的高度 

对元素进行相对定位
每个元素在页面的文档流中都有一个自 然位置 。相对 于这个原始位置对元素进行移动就称为相对 定位 
周 围的元素完全不受此影响 ，原来的位置留下空白
position: relative; 
输入top,right,bottom,left在偏移的位置，可以是绝对值，相对值em或者百分数
其他元素不会受到偏移的影响，仍然 按照这个元素原来的盒子进行排列。 
使用相对定位、绝对定位或固定定 位时，对于相互重叠的元素，可以用 z-index 属性指定它们的叠放次序。 
对元素设置 position: static，可以 覆 盖 position: relative 设 置。 

对元素进行绝对定位
通过对元素进行绝对定位，即指定它们 相对于 body ,或最近的已定位祖先元素,的精确位置，可以让元素脱离正 常的文档流。 其他内容不知 道它的存在，它也不知道其他内容的存在。 

Position:absolute;
根据需要，输入 top、right、bottom 或 left。 
再输入 :d，这里的 d 是希望元素相对于 其祖先元素偏移的距离 
根据需要，对希望成为绝对定位参照 体的祖先元素添加 position: relative; 如果跳过这 一步 
，将对元素相对于 body 计算偏移量 

固定定位
固定定位。 当访问者滚动浏览器窗口时，页面内容通常 随之上下移动。如果对元素设置 position: fixed;，它就会固定在浏览器窗口中。当访 问者上下滚动浏览器窗口时，该元素不会随 之移动，页面的其余部分仍照常滚动。 固定定位在很多移动浏览器中效果不佳， 因此如果你希望自己的网页能很好地适应移 动设备，最好不要使用固定定位。 

在栈中定位元素
输入z-index:n;n表示元素在定位过的对象堆中的层级的数字
n越大，元素在堆中越高
z-index 属性仅对定位过的元素(即 设为绝对定位、相对定位或固定定位的元 素) 

处理溢出
元素并不总是包含在它们自己的盒子里。 这可能是因为盒子不够大，例如，图像比它 的容器更宽就会溢出;也可能是因为使用负 的外边距或绝对定位让内容处于盒子的外面; 还有可能你对元素设置了显式高度，它的内 容太高而无法装入盒子内部。无论是哪种情 况，都可以使用 overflow 属性控制元素在盒 子外面的部分 
决定浏览器如何处理溢出的步骤
(1) 输入 overflow:。 
(2) 输入 visible，让元素盒子中的所有 内容可见，这是默认项; 
或者输入 hidden，隐藏元素盒子容纳不 了的内容; 
或者输入 scroll，无论元素是否需要， 都在元素上添加滚动条; 
或者输入 auto，让滚动条仅在访问者访 问溢出内容时出现。 

可以使用min-height
容器会随内容增大而变大
overflow 属性不是继承的。 




																									

 







