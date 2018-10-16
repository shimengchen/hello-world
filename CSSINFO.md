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

