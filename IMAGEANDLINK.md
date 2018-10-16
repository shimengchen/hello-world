图像

一、关于web图像
格式
Web 上用的最广泛的三种格 式是 GIF、PNG 和 JPEG 
我们的目标是选择 质量最高，同时文件最小的格式 
1.JPEG是一种有损的格式 ，对 JPEG 进行解压缩无法还原图像 先前丢失的细节 
适用于大多数照片，以及其他颜色较多
2.PNG 和 GIF 是无损的格式 ，GIF 只有 256 种颜色，但 PNG 却支持 几百万种颜 
，均支持透明，它们更适用于保存非照片类的 图像 

大小
图像通常应该控制在几百个像素款之内
为了产生视觉冲击，我们可能需要使 用一张达到或超过整个网站内容宽度的大图。 9 这样的图像通常不超过 960 像素宽。 

可缩放矢量图形(SVG) 
对于使用 SVG 图像语言创建的图像， 无论放大还是缩小都不会影响其质量(以 及其他的一些参数)。 

透明度
gif格式中，一个像素要么是透明的，要么是不透明的，这称为索引色透明（index transparency）
PNG 则既支持索引色透明， 又支持 alpha 透明(alpha transparency)。alpha 透明可以控制一个像素透明的程度。也就是 说，一个像素可以部分透明，而非要么透明 要么不透明。 
PNG-8 既支持索引色透明，也支持 alpha 透明 
Photoshop 不支 持 alpha 透明的 PNG-8，但支持 alpha 透明的 PNG-32 
对于透明图像，应使用 PNG-8 或 PNG-32。后者允许使用超过 256 种颜色。 

二、保存图像
1. Adobe Photoshop 
2. 使 用 Photoshop 的 Save for Web 命 令的步骤 
通常，在计算机上创建的图像(包括标志、 图表、图形、线条艺术，以及任何包含由单 色和锐利细节构成的大块区域的图像)应保 存为 PNG-8 格式 
具有连续色调的图像(如照片)应保存 为 JPEG 或 PNG-24 格式。 
应该使用RGB1模式创建图像，而不 提 示 在优化和输出图像时，没有所谓的唯 是 CMYK 2模式(用于印刷)。 

三、为网站添加图标
我们在浏览器选项卡、 历史记录、书签页、收藏夹和地址栏中看到 的(与网站相关)的小图标称为 favicon，这 个词是 favorites icon(收藏夹图标)的简称。 
我们创建的图标至少应该为 16×16 并保存为 ICO 格式，文件名为 favicon.ico 
<link rel="icon" type="image/x-icon" href="img/favicon.ico">
注意href位置


链接

HTML块级链接
HTML5 几乎允许在链接内包含任何类型的元 素或元素组 ，例如段落、列表、 整篇文章和区块 

创建锚并链接到锚
如果要想用户跳至网页的特定 区域，可以创建一个锚，并在链接中引用该锚 
使用id=“anchor-name”创建锚
使用<a href=“#anchor-name”>链接到锚
如果锚位于另个文档，就是使用<a href=“page.html#anchor-name”>
如果锚位于另一台服务器页面<a href=“http://www.site.com/directory/ page.html#anchor-name 
”>

创建其他类型的链接
对于指向万维网上任何文件(包括图像、 ZIP 文件、程序、PDF 及其他等)的链接，输 入 http://www.site.com/dir/file.ext， 其 中 www.site.com 是 主 机 名 称，dir/file.ext 是 目标文件的路径。后者包括了文件目录和文 件名(以及扩展名)。 
对于电子邮件地址，输入 mailto:name@ domain.com(不以 http:// 开头)，其中 name@ domain.com 是电子邮件地址 
对于电话号码，输入 tel:+(不以 http:// 开头)并紧跟着国家代码和电话号码(所 有的号码中都不必包含短横线)。 
具体见link.html
