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






