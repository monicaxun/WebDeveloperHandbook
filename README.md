# WebDeveloperHandbook

7/1到现在，进入项目组快靠近两个月了，开始总结工作！

这边的前端工作，还是偏向原生的较多。过多的炫酷的效果目前还是没有添加进来。
想想自己缺少的还是前端的经验，比如说，看到的网站，哪些实现会比较多，哪些实现会感觉反人类。平时要有方向地多多研究！

1. 搭建网页，主要是元素的构成，先内容插入；
2. 再是，按照设计师给出的设计稿，修改基础的样式：不要害怕修改第一步的元素，不然将来会有更多的修改和时间花在原先不合理的元素上；
3. 最后再是完成页面的动作，交互等的设计；
4. 先是html元素构建内容；然后大体上上下左右布局；定位后调试细节。

这边由于主要是静态页面，所以，目前暂时就好好地锻炼自己的css能力，不焦躁。慢慢练习，找出手感。

来这边之后，比如知道了：  
1. border-radius，照片可以是方的，设置border-radius大于等于50%即可展示为圆形。  
I. 正如原点的实现，可以通过设置长宽为0，然后设置border宽度，同时设置border-radius为大于等于border的宽度即可  
II. 或者，直接设置元素的宽度和高度，如18px，然后设置border-radius为50%；异曲同工  
2. 设计网站的时候，需要考虑很多因素：  
I. 表格考虑没有结果搜索出来的样式；  
II. 字段太长（hover和省略号样式）  
III. 图片元素的高度（设计稿和最终开发呈现的会出现差异）  
V. 输入框等的错误提示信息和样式  
3. 主层父元素居中，通过设置：width:1200px; margin: 0 auto;  
4. ul/li，设置好li为display:inline-block的时候，元素之间依然会有空隙；（http://www.cnblogs.com/2050/archive/2012/05/16/2504081.html），设置ul的font-size为0是最优。设置float为left一样可以清除间隙。


2016.09.01  
还是要实时纪录呀；<br/>
<b>Canvas用法纪录</b><br/>
1. canvas的width和height使用css样式不起作用，应该直接设置width和height属性；<br/>
2. 了解关于canvas实现的原理，比如按照像素分布等等。<br/><br/><br/>


<b>移动端开发领取奖励</b><br/>
1. 使用mui框架；<br/> 
2. 手机端的select元素，表现与浏览器模拟出来的不一致：分别为<br/>
&nbsp;&nbsp;a) 安卓：屏幕中央弹出一个蒙层框，选择选项；<br/>
&nbsp;&nbsp;a) iOS：底部弹出蒙层框，选择选项；<br/>

2016.09.08
#######
1. -webkit-font-smoothing: antialiased;-moz-osx-font-smoothing: grayscale;
   设置字体平滑度（深层理解阅读：http://szafranek.net/works/articles/font-smoothing-explained/）

2. css content结合before/after伪元素使用，设置前后内容
>content使用的unicode编码：https://en.wikipedia.org/wiki/List_of_Unicode_characters

3. 研究学习vue.js，类似Angular.js的MVVM框架

4. PS保存图片，选择保存为WEB所用格式（Command/Ctrl+Alt+Shift+S），图片保存大小与预览大小不一致：
   右侧选择“元数据”为无
   图片保存线条比原先粗：
   选择保存为PNG24位图

5. box-shadow用法：
box-shadow: 0px 5px 15px -5px rgba(3,0,0,0.15);
box-shadow: 横向偏移 竖直偏移 阴影宽度 阴影扩散值 阴影色值 inset/outset

6. css线性:line-gradient
设置为90度，颜色到transparent的过渡，有金属光泽立体感
>学习参考http://www.cnblogs.com/lhb25/archive/2013/01/30/css3-linear-gradient.html

7. (function($) {…})(jQuery);形成闭包，在此范围内定义的变量至此不可引用  
$(function(){…});  
jQuery(function($) {…});  
$(document).ready(function(){…})作用类似，文档加载完成后执行js


2016.09.12  
1. 使用toggle收缩：  

$("#togglt_btn").toggle(function(){  
	$(".to_expand_item").animate({height: 'toggle', opacity: 'toggle'}, "slow");  
	$(this).addClass("expand"); //按钮样式更改  
	return false;  
},function(){  
	$(this).parent().next(".to_expand_item").animate({height: 'toggle', opacity: 'toggle'}, "slow");  
	$(this).removeClass("expand");  
	return false;  
});  

2. 收缩闪一下，由于元素之间的margin值坍塌，最好的方法是处理css时候，不要同时使用margin-top/margin-bottom，只需要设置一个值就ok。



2016.09.14  
1. 设置父元素line-height来控制间隔，对于过多的子元素，不好控制间隔；要适时选择是否使用line-height。

2. TODO: 设置div元素line-height为58px，内部元素包括span设置display:inline-block，span有一个图标，设置width/height/display:inline-block，此时如果设置这个span的overflow:hidden，页面结构会错乱，类似浮动，需要设置vertical-align:middle保证页面显示垂直居中效果？Why?



2016.09.19  
1. 移动端设置placeholder样式：input::-webkit-input-placeholder

2. 使用li:list-item设置类目前方的圆点，原本可以通过控制font-size和color实现原点的颜色和大小。但是这种情况下，圆点会比较小。实际应用中，圆点比较大的情况下，最好还是使用占位元素，设置背景色等等效果实现圆点样式。
这样，做时间轴效果的时候，使用li:before与position:absolute也会比较好控制具体的left等的位置。



2016.09.20
1. 今天下午看得一片文章，关于网易和淘宝的手机适配的，受益良多
>http://www.cnblogs.com/lyzg/p/4877277.html

我们的布局和网易的很像，不过，还是处于比较初级的阶段：对于字体，我们使用rem的：为什么容器元素的font-size都不用rem，需要额外地对font-size做媒介查询？所谓容器元素是什么，指所有字体还是说只是部分？

图片来自博客：  
>![image](https://github.com/monicaxun/WebDeveloperHandbook/raw/master/img/taobao-fe-ui-collaboration.png)

******2. 解读切图@3x文章
>http://www.25xt.com/appdesign/8034.html?from=androidqq
>http://www.zhihu.com/question/26195746
>![image](https://github.com/monicaxun/WebDeveloperHandbook/raw/master/img/iphone_ratio.jpg)
