网页的构造块

HTML思想
HTML元素描述的内容是什么，而非看起来是什么样

基本的HTML页面组成
一个网页主要由三部分组成：文本内容、对其他内容的引用和标记
HTML标记由元素、属性和值构成
1.网页的顶部和头部
<!DOCTYPE html>部分(称为DOCTYPE)告诉浏览器这是HTML5页面，应该始终位于页面第一行。
<html>在这里可以为网页指定其他语言
<head>
         <meta charset=“utf-8”/>指明文档的字符编码类型为UTF-8

文件名与文件夹名   
统一使用小写字母，单词间用短横线分隔
例如：https://yoursite.com/20th-century/buckminster-fuller.html

URL
绝对URL和相对URL
绝对URL包含了指向目录或文件的完整信息，包括模式、主机名、路径
相对url:
   1.引用同一目录下的文件，相对url就只是文件名和扩展名
      例如：<a href="history.html">Take me to history. html!</a> 
   2.引用子目录下的文件名
       目标文件在当前目录的子目录下，相对url就是子目录名/文件名.扩展名
      例如：<a href="info/data. html">Data supports my hypothesis</a> 
   3.引用上层目录的文件 
       Url就是../文件名.扩展名，../../上两层，../../../上三层
   4.根相对URL
       例如/img/family/vacation.jpg(假定img文件夹位于网站的根文件夹)
￼

HTML:有含义的标记，语义化
语义化html指的是使用最恰当的HTML元素进行标记内容，而不关心它在浏览器中显示的样式。
无障碍访问，指的是让内容对所有用户可用，不论其能力如何。

为什么语义化很重要？
1. 提升可访问性和互操作性(内容对于借助辅助技术的残障访问者是可访问的， 同时对于台式机、手机、平板电脑及 其他设备上的浏览器都是可访问的)。 
2. 提升搜索引擎优化(SEO)的效果，因为搜索引擎 对特殊方式标记的内容会赋予更高的权重。 
3.  使维护代码和添加样式变得容易。 
4.  (通常)使代码更少，页面加载更快 

处理网页文件

创建页眉
页面中有一块包含一组介绍性或导航性内容的区域，应该用header元素进行标记
一个页面可以有任意数量的header元素
页眉通常包括网站标志、主导航和其他全站链接，甚至是搜索框

标记导航
使用nav来表示主导航链接区域，nav中的链接可以指向页面中的内容，也可以指向其他页面或资源，仅对文档中重要的链接群使用nav
代码见new.html

标记页面主要区域
main元素用来标记页面的主要内容部分，在一个页面中仅使用一次
最好在main开始标签加上role=“main”
代码见new.html

创建文章
article元素表示文档、页面、应用或网站中的一个独立的容器，原则上是可独立分配或可再用的，就像聚合内容中的各部分。
可以是一篇杂志或报纸文章、论坛帖子、博客条目、用户提交的评论、交互性的小部件或小工具，或者任何其他独立的内容项。
article可以嵌套article,一个页面可以有多个article
代码见new.html

定义区块
section元素代表文档或应用的一个一般的区块。section是具有相似主题的一组内容 ，通常包含一个标题
Section的例子包括章节、标签式对话框中的各种标签页、论文中带编号的区块。
与div进行区分，section标记的是页面中的特定区域，而div则不传达任何语义

指定附注栏
aside元素用于页面中有一部分内容与主体内容相关性没有那么强，但可以独立存在的时候
还可以用于重要引述、侧栏、指向相关文章的一组链接、广告等
在aside中可以使用role=“complementary”
对于与内容相关的图像（如图表、图形或带有说明文字的插图），使用figure而非aside

创建页脚
footer最近的祖先是body时，它是整个页面的页脚，通常包括版权说明、指向隐私政策页面的链接，可以使用role=“contentinfo”(用于页面级的footer,一个页面只能使用一次)
还可以使用footer代表附录、索引、版权页、许可协议这样的内容

创建通用容器
在需要为一段内容外围包裹一个容器，为其应用CSS样式或者JS效果时，使用div作为通用容器。
div是块级无语义容器，span是行内无语义容器

使用ARIA改善可访问性
WAI-ARIA(Web Accessibility Initiative’s Accessible Rich Internet Applications， 无 障 碍 网页倡议 – 无障碍的富互联网应用，也简称 ARIA)是一种技术规范 。
无障碍访问的意义是让所有的访问者都 能获取网站的内容。 
地标角色可帮助用户实别页面区域，对这些区域指定role属性就可以
地标角色  如何使用及何时使用 

role="banner"(横幅) 面向全站的内容，通常包含网站标志、网站赞助者标志、 全站搜索工具等。横幅通常显示在页面的顶端，而且通 常横跨整个页面的宽度 
  将其添加到页面级的 header 元素，每个页面只用一次 

role="navigation"(导航) 文档内不同部分或相关文档的导航性元素(通常为链接) 的集合 
  与 nav 元素是对应关系。应将其添加到每个 nav 元素， 或其他包含导航性链接的容器。这个角色可在每个页面 上使用多次，但是同 nav 一样，不要过度使用该属性 

role="main"(主体) 文档的主要内容 
  与 main 元素是对应关系。最好将其添加到 main 元素， 也可以添加到其他表示主体内容的元素(可能是 div)。 在每个页面仅使用一次 

role="complementary"(补充性内容) 文档中作为主体内容补充的支撑部分。它对区分主体内 容是有意义的 
  与 aside 元素是对应关系。应将其添加到 aside 或 div 元 素(前提 是该 div 仅包含补充性内容)。可以在一个页 面里包含多个 complementary 角色，但不要过度使用 

role="contentinfo"(内容信息) 包含关于文档的信息的大块可感知区域这类信息的例子 包括版权声明和指向隐私权声明的链接等 
  将其添加至整个页面的页脚(通常为 footer 元素)。每 个页面仅使用一次 

为元素指定类别或ID名称
使用id属性，唯一的
使用class属性 一个元素可以拥有多个class,如class=“name anothername”

为元素添加title属性
title属性可以为任何部分加上提示标签，可以提升无障碍访问功能
当访问者将鼠标指向加了说明标签的元素时，就会显示title

文本

指明细则
small表示细则一类的旁注(side comment),“通常包括免责声明、注意事项、法律权限、版权信息等。”
例如<p><small>&copy;2013 The Super Store.All Right Reserved</small></p>

标记重要和强调的文本
strong元素表示内容的重要性，而em则表示内容的着重点
浏览器通常将strong文本以粗体显示，em文本以斜体显示
例如：
<p><strong>Warning:Do not approach the zombies <em>under any circumstances</em></strong>.They may <em>look</em> friendly,but that's just because they want to eat your arm.</p>

HTML5 强调，b 和 i 应该是其他元素(如 strong、em、cite 等)都不适用时的最后选择 
HTML5 将 b 重新定义为: 
b 元素表示出于实用目的提醒读者注意的一块文字，不传达任何额外的重要性，也不表 示其他的语态和语气，用于如文档摘要里的关键词、评论中的产品名、基于文本的交互式软 件中指示操作的文字、文章导语等。 
HTML5 将 i 重新定义为: 
i 元素表示一块不同于其他文字的文字，具有不同的语态或语气，或其他不同于常规之处， 用于如分类名称、技术术语、外语里的惯用语、翻译的散文、西方文字中的船舶名称等 

创建图
图可以是图标、照片、图形、插图、代码片段以及其他类似独立内容
使用figure标签，figcaption是figure的标题，可选，可以出现在figure内容的开头或者结尾处
现代浏览器在默认情况下为figure添加40px宽的左右边距
代码见text.html

指明引用或参考
使用cite元素可以指明对某内容源的引用或参考。例如戏剧、脚本、图书标题、歌曲、电影、照片、雕塑的名称、演唱会，规范、报纸或法律文件等

引述文本
blockquote元素表示单独存在的引述，它默认显示在新的一行，有缩进
q元素则用于短的引述，如句子里面的引述，浏览器对q里面的文本自动加上语言引号
两种元素都可以包含cite属性来提供引述文本的位置
代码见text.html

指定时间
使用time元素标记时间、日期或时间段
可以添加datetime属性

解释缩写词
使用abbr元素标记缩写词并使用title属性或者后面跟括号解释其含义

定义术语
dfn用于首次定义术语，会对其添加区别于其他文本的格式，在其后提到该术语时则不再使用特殊格式
术语及其定义位置应相近

创建上标和下标
使用sup和sub来创建上标和下标，常见的上标包括商品标号、指数和脚注编号
常见的下标包括化学符号
上下标会轻微的扰乱行间距，可以使用css修复http://necolas.github.com/ normalize.css/ 

添加作者联系信息
Address是用以定义HTML页面或页面一部分（如一篇报道或新文章）有关作者、相关人士或组着的联系信息，通常位于页面底部或者相关部分内

标记编辑和不再准确的文本
代表添加内容的ins元素和标注已删除内容的del元素，代表已标注的内容不再准确和不再相关的s元素
del 和 ins 是少有的既可以包围短语内 容(HTML5 之前称“行内元素”)又可以包围块 级内容的元素 
用 ins 标记的文本通常会显示一条下 划线 
用 del 标记的文本通常会显示一条删 除线 

标记代码
使用code元素标记代码实例或文件名
如果代码需要显示<>应分别使用&lt;和&gt;

使用预格式化的文本
预格式化文本可以保持固有的换行和空格，它是计算机代码示例的理想元素

突出显示文本
Mark突出显示
主要用于对搜索结果页面或文章中的搜索词进 行突出显示。  
创建换行
要确保使用 br 是最后的选择，因为该元 素将表现样式带入了 HTML，而不是让所有 的呈现样式都交由 CSS 控制。 
实际上，对 于诗歌、街道地址等应该紧挨着出现的短行，都适合用 br 元素。 
代码见text.html section title=“br”

创建span
同 div 一样，span 元素是没有任何语义的，是行内元素。 
由于 span 没有任何语义，因此应将它作 
为最后的选择，仅在没有其他合适的元素时 才使用它。 
例如想对一小块文字指定 不同的语言 
代码见text.html section title=“span”



