# WebDeveloperHandbook
charset "utf-8"

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
1. 设置父元素line-height来控制间隔，对于过多的子元素，不好控制间隔；要适时选择是否使用line-height。  (并不是说不用，还是要了解了再用)
2. TODO: 设置div元素line-height为58px，内部元素包括span设置display:inline-block，span有一个图标，设置width/height/display:inline-block，此时如果设置这个span的overflow:hidden，页面结构会错乱，类似浮动，需要设置vertical-align:middle保证页面显示垂直居中效果？Why?  




2016.09.19  
1. 移动端设置placeholder样式：input::-webkit-input-placeholder  
2. 使用li:list-item设置类目前方的圆点，原本可以通过控制font-size和color实现原点的颜色和大小。但是这种情况下，圆点会比较小。实际应用中，圆点比较大的情况下，最好还是使用占位元素，设置背景色等等效果实现圆点样式。这样，做时间轴效果的时候，使用li:before与position:absolute也会比较好控制具体的left等的位置。  




2016.09.20  
1. 今天下午看得一片文章，关于网易和淘宝的手机适配的，受益良多
>http://www.cnblogs.com/lyzg/p/4877277.html

我们的布局和网易的很像，不过，还是处于比较初级的阶段：对于字体，我们使用rem的：为什么容器元素的font-size都不用rem，需要额外地对font-size做媒介查询？所谓容器元素是什么，指所有字体还是说只是部分？

图片来自博客：  
>![image](https://github.com/monicaxun/WebDeveloperHandbook/raw/master/img/taobao-fe-ui-collaboration.png)

2. 解读切图@3x文章  
>http://www.25xt.com/appdesign/8034.html?from=androidqq  
>http://www.zhihu.com/question/26195746  
>![image](https://github.com/monicaxun/WebDeveloperHandbook/raw/master/img/iphone_ratio.jpg)


2016.09.27
supermo的nodejs的安装  
1. 先安装nodejs；
2. 然后在目录下，运行，npm install，会出现node_modules文件夹；
3. 之后运行gulp;
4. 新打开一个终端：node app，然后浏览器输入：localhost:9090

问题：   
1. 第三步运行gulp，提醒找不到，于是先运行npm install -g gulp --> 没有权限 --> sudo npm install -g gulp，之后再运行gulp；   
2. 第三部运行gulp，报错，“SyntaxError: Block-scoped declarations (let, const, function, class) not yet supported outside strict mode”，按照说明，添加"use strict"即可;   
3. 添加自己的sponsor.js到webpack.config.js之后，没有实时编译出来js，重新运行了一次gulp   


2016.09.28   

1. position为absolute的话，元素的margin-top设置负值起作用；否则，估计是因为不会超过当前文档流的布局，无法实现想要的margin-top负值效果；

2. 栅格化图层是因为某些矢量位图，图片不会随着伸展压缩而导致清晰度变化；一般使用中，.jpg不需要这种效果，所以才会在拷贝图层之前，首先进行以下栅格化图层，见9.20日的解读切图@3x，也有部分说明。

而转换为智能对象，是指某些图层，比如说，可以点击这个图层，然后链接到AI工具里面去修改编辑。

3. git stash是保存当前本地编辑的内容，然后从服务器版本开始修改，然后提交；需要取出这个本地编辑的版本，只需要git stash pop一下，就可以找到之前修改的文件等，再进行后续开发;   
git status查看哪些文件有改动；   
git log查看提交记录；   
git diff <commitUUID>:<filename> <commitUUID>:<filename>或者<filename>分别对比两个版本的文件修改，本地文件修改


4. Scss语法，若需要写last-Child，在内部&:last-Child即可实现；目前使用变量，还不会div的背景设置等等，如何动态某个不一样的元素。&::after写法

5. select元素不能直接添加伪元素，借用label实现样式更改，从而点击可移动焦点到select选择。

2016.09.29

1. 为什么页面都没有设置min-width，图片却满屏？

2. git diff <commitUUID> master对比相应提交版本与最新版本的全部修改。  
git checkout <commitUUID>，会恢复到那个版本，想恢复到最新版本，只需要git checkout master.   
git checkou，可以实现在这个版本的更改和提交，不影响其他branch的提交，同时可以废弃在这个状态下的提交从而不影响另一个checkout。
使用提示说：   
You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by performing another checkout.      
If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -b with the checkout command again. Example:

  git checkout -b <new-branch-name>      
如是说，git checkout一般用来新建一个branch分支

3. git commit README.md --author "Author Name <authormail>"用来修改提交的author，查看git log的时候显示的author为新author。

4. ssh报错：The authenticity of host 192.168.0.xxx can't be established.   
解决方案：执行ssh  -o StrictHostKeyChecking=no  192.168.0.xxx　就OK



2016.09.30

1. 杜老师说display:inline-block，兼容性不大好，可以后续验证。::TODO。

2. 看进国新增的页面，background-image设置两个值，以逗号分隔。同样background-position设置两个值，以逗号分隔。

3. git whatchanged，查看具体每次提交的文件修改。   
git show <commitUUID>查看某次提交，各文件的修改情况。

4. jade模版引擎，.pug文件格式



2016.10.01

1. line-height与font-size需要深入研究？TODO，参见9/14日总结。

> http://www.zhangxinxu.com/wordpress/2009/11/css%E8%A1%8C%E9%AB%98line-height%E7%9A%84%E4%B8%80%E4%BA%9B%E6%B7%B1%E5%85%A5%E7%90%86%E8%A7%A3%E5%8F%8A%E5%BA%94%E7%94%A8/

> http://www.w3cplus.com/css/fun-line-height.html

> http://www.cnblogs.com/rainman/archive/2011/08/05/2128068.html

2. clearfix为什么需要写那么多   
.clearfix {   
    zoom: 1;   
}   
.clearfix:after {   
    display: block;   
    overflow: hidden;   
    clear: both;   
    height: 0;   
    visibility: hidden;   
    content: ".";   
}   
.clear{   
    height: 1%;   
}   
.clear:after {   
    content: "";   
    display: block;   
    height: 0;   
    clear: both;   
    visibility: hidden;   
}   

3. select样式改写，-wenkit-appearance: none; -moz-appearance: none;设置替换背景图片，对于在IE下面，还需要添加::-ms-expand{display:none}

2016.10.08

1. 命令行跳转到行首：Ctrl+a，跳转到行末：Ctrl+e   
取消本次命令输入：Ctrl+c

2. dpkg -l | grep <lib2xml等软件名>查看软件是否已安装

3. 接入开发者平台   
下载安装微信web开发者工具，可以直接打开页面调试，输入访问页面地址，调试html web页面样式。

4. 微信页面有时候需要清除缓存，否则页面样式不是最新的效果。可以杀掉进程，保险的方法是，使用调试，可以有清除缓存的选项。   
知乎总结说来有三点：   
1).在使用window.location.href跳转页面时，在url后面加上“?datetime=”+new Date().getTime();保证每次浏览的网页是最新的。   
2).js或css更新后，在html引用的地方更新版本号，例如scr="../js/demo.js?v=20160420"。   
3).对于图片url后不建议加时间戳，否则微信的图片缓存机制将失效，严重影响网页浏览速度。  


2016.10.09

1. 微信和手机端浏览器打开的mui设计页面，placeholder无法显示，点击输入，内容无法输入成功：经发现为border: 0设置的原因，有时间可以研究一下。TODO:: 

2. 微信服务器部署：服务器安装web.py: `pip install web.py`

3. jade模版引擎学习，extends /.pug
  - 学习链接http://www.tuicool.com/articles/bUzQVj2

4. `git add -A`, `git commit, git push`

5. `git stash`, `git pull`, `git stash pop`

6. fix conflict, `git commit`，可以`git reset`回退commit

7. `gitk`查看commit历史

2016.10.10

1. 整体技术方向，确定。标准化，反向推动界面设计风格的统一。

2. gitk失败，安装tcl（先安装homebrew）,brew cask install tcl（ruby的语法 ）

3. Flex布局
  - http://www.ruanyifeng.com/blog/2015/07/flex-grammar.html?utm_source=tuicool
  - a(href="http://www.tuicool.com/articles/Fnu6Zr3")不同场景的选择和代码需求
  - 这其中提到autoprefixer，这个工具会自动添加-webkit－等前缀
  - 设为Flex布局以后，子元素的float、clear和vertical-align属性将失效。
  - 不要用flex-wrap，因为这个属性不支持版本号低于28的firefox浏览器。


2016.10.11

1. 动画.scss文件@keyframes

2. height: 100vh; height: 100%;
  - [看，这就是差距，人家12年在研究的，我现在才看到](http://www.zhangxinxu.com/wordpress/2012/09/new-viewport-relative-units-vw-vh-vm-vmin/)