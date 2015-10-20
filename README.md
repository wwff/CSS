# CSS
CSS的注意事项
1.模块最好不要混用margin-top和margin-bottom，统一使用margin-top或margin-bottom，因为相邻的模块同时使用margin-top和margin-bottom会造成边距的重合，从而带来不必要的麻烦。
2当不同选择符的样式设置有冲突时.会采用权重高的选择符设置样式（html标签的权重：1, class：10, id：100， ）；如果css选择符的全中相同，样式会遵循就近原则即哪个选择符最后定义，就采用这个选择符的样式。
3.为了保证样式容易被覆盖，提高可维护性，css选择符需保证权重尽可能低。
4.a标签的四种状态的排序：lovehate原则即l(link)ov(visited)e h(hover)a(active)te
5.IE的专有属性：hasLayout，触发hasLayout属性的方法：①设置css属性zoom:1(最常用，最安全，成本最低的方式)②设置css属性position:relative(会带来一点副作用，在zoom:1无效的时候使用)
6.
(1)常用的块级元素：div、p、form、ul、li、ol等；常用的行内元素：span、strong、em（行内元素设置width、height属性无效）
(2)块级元素与行内元素的css相关属性是display，其中块级元素对应于display:block,行内元素对应于display:inline；可以通过修改display属性值来切换块级元素和行内元素
(3)display:inline-block,即行内的块级元素，拥有块级元素的特点，可以设置长宽width、height、margin、padding值，但不是独占一行，其宽度不占满父级元素，而是和行内元素一样，和其他行内元素排在同一行。（IE6、7不兼容该属性，可把display:inline-block改为zoom:1）
(4)position:absolute和float会隐式地改变display类型(display:inline-block)；position:relative不会隐式改变display属性值。
7、居中
（1）行内元素的水平居中:text-align:center
（2）确定宽度的块级元素的水平居中：margin-left:auto;margin-right:auto;
（3）不确定宽度的块级元素的水平居中：display:inline;text-align:center;
（4）父元素高度确定的多行文本、图片、块级元素的竖直居中的实现方法：
①当父元素为td、th时：使用vertical-align:middle
②对不支持vertical-align属性的其他块级元素，可设置：display:table-cell;vertical-align:middle;(IE6、7不支持display:table-cell;使用特定格式hack兼容)
8、网格布局：利用子选择器布局嵌套使用：
eg：<div class="content content-lr-001">
	<div class="main"></div>
	<div class="sidebar"></div>
    </div>
    <div class="content content-lr-002">
	<div class="main"></div>
	<div class="sidebar"></div>
    </div>
在给content-xx-xxx的宽度设置时具体单位最好使用百分比这种相对单位，使用百分比可以嵌套使用、提高重用性
