响应式页面

响应式页面的组成
1.灵活的图像和媒体，图像和媒体资源的尺寸是用百分数定义的，从而可以根据环境进行缩放
2.灵活的、基于网格的布局，也就是流 式布局对于响应式网站，所有的 width 属性都用百分数设定，因此所有的布局成分都是相对的。其他水平属 性通常也会使用相对单位(em、百分数和 rem 等)。 
3.媒体查询。使用这项技术，可以根据 媒体特征(如浏览器可视页面区域的 宽度)对设计进行调整。 

创建可伸缩图像
(1) 对任何想做成可伸缩图像的图像，在 HTML 的 img 标签中省略 width 和 height 属 性 
(2) 在样式表中，为每个想做成可伸缩图 像的图像应用 max-width: 100% 

创建弹性布局网格
弹性布局又称为流式布局
1.对于需要某个宽度实现预期布局的元素， 设 置 width: percentage;， 其 中 percentage 表示你希望元素在水平方向上占据容器空间 的比例 
2.作为可选的一步，对包含整个页面内容 的元素设置 max-width: value;，其中 value 表示你希望页面最多可增长到的最大宽度，通常， value 以像素为单位，不过也可以使用百分数、 em 值或其他单位的值。 
在使用公式计算元素的百分数宽度 时 ，容纳它的容器来自它最直接的 祖先(即上下文)。 

对于设置了body { font-size: 100%; } 的页面，对 font-size、margin、padding 和 max-width 使用 em 值还有一个好处——如果 用户更改了浏览器默认字体大小，那么页面 也会跟着变大或变小 

设置相对的 max-width
设 置 .page { max-width: 60em; } 与 使用 960px 是相似的，但它们有一个显著 的不同:前者会根据浏览器默认字体大小 进行缩放。 

理解和实现媒体查询
媒体查询增强了媒体类型方法，允许根据 特定的设备特性定位样式 

媒体查询语法和示例
1.指向外部样式表的链接
<link rel=“stylesheet” media=“logic type and (feature value)” href=“your-stylesheet.css”>
2.位于样式表中的媒体查询
@media logic type and (feature value)
{
/*目标css样式规则写在这里*/
}
例如
@media only screen and (min-width: ➝480px) { 
p{ color: red; 
font-weight: bold; } 
} 
理解为仅 当媒体类型为 screen 且视觉区域最小宽度为 480 像素时，使用下面的样式规则 

理解视觉区域及使用视觉区域meta元素
视觉区域(viewport)指的是浏览器(包括桌面浏览器和移动浏览器)显示页面的区域。 它不包含浏览器地址栏、按钮这样的东西，只是浏览区域。媒体查询的 width 特性对应的是 视觉区域的宽度。不过，device-width 特性不是，它指的是屏幕的宽度。 
解决办法：在页面的 head 部分添加视觉区域 meta 元素即可。 
<meta name=“viewport” content=“width=device-width,intial-scale=1” />

组合使用
理解了可伸缩图像、弹性布局和媒体查 询的知识之后，就可以将它们组合在一起， 创建响应式网页。 
1.创建内容和HTML
在 HTML 页面的 head 元素中，输 入<meta name="viewport" content="width= device-width, initial- scale=1" />  
2.为所有的设备提供基准样式
3.创建适用于所有设备的基准样式(参 见“移动优先方法”)。确保页面中的图像 可伸缩 
4.识别出适合你的内容的断点。创建相 关的媒体查询，让布局适应从小屏幕到大屏 幕的不同可视区域宽度。 
5.如果需要为第 (4) 步中页面的一些内 容指定宽度，使用百分数 
6.选择你希望的旧版 IE 显示页面的方 式 
7. 开始测试 
 

