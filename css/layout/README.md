# CSS Session 第二波 --- 夺取圣杯
---
CSS所要解决的最重要的问题就是布局问题，上一讲中介绍了盒模型与position属性，这一讲中讲主要介绍float以及margin属性，以及他们在布局中的综合使用，找到一个三栏布局的最佳实践，同时也是其他布局很好的参考。

暂时还没有参加Session的同学可以通过本说明配合ppt进行练习。如果练习过程中希望查看答案，请查找ppt中对应练习的css代码。
## Session 目标
1. 了解float的用法，以及清除float
2. 了解三栏布局的各种方式以及最佳实践
3. 进一步了解margin的计算，包括margin对于float元素的计算，以及margin的负值作用

## Session 材料
* [PPT](http://zation.github.com/session/css/layout/)
* [Session练习代码](https://github.com/zation/session/tree/gh-pages/css/layout/session)
* [所有使用到的code](https://github.com/zation/session/tree/gh-pages/css/layout)

## Session 内容
1. 欣赏当前一些好的三栏布局博客。
2. 了解float的基本定义，如果希望深入了解float属性以及如何清除float请[点此](http://www.qianduan.net/about-float.html)。
3. 完成练习的基础准备。
4. 使用section-1.html/css开始第一个练习：完成一个简单的三栏布局，要求：
	* center宽度300px
	* left宽度100px
	* right宽度150px
	
	这个练习没有什么难度，唯一需要注意的是使用float后记住清除，否则footer会跑到页面上方。
5. 使用section-2.html/css开始第二个练习：完成一个宽度自适应的三栏布局，要求：
	* center自动填充除去left以及right剩下的空间
	
	这里需要用到float的特性之一：float元素会使其后的元素围绕自己排列。所以我们把center放在最后，然后使用margin-left, margin-right使其居中。
	
	还有一点需要注意：center会比left和right高出一些，这是由于margin的算法，对于float元素，margin实际值为相邻两个元素的累加；对于非float元素，margin实际值为相邻两个元素的最大值。详细解释请[点此](http://w3help.org/zh-cn/kb/006/#header_3)
6. 使用section-3.html/css开始第三个练习：我们希望页面中重要的内容可以优先加载，提高用户体验，所以追加如下要求：
	* center在html中应该位于left, right之前
7. 第三个练习比较困难，在一定的尝试后，我们开始跟随最佳实践一步一步的完成圣杯布局，使用section-4.html/css：
	1. 在center, left, right之外加上一个容器：`<div class="content"></div>`，并且设置content的css为`padding-left: 140px; padding-right: 230px;`
	
		给center, left, right的class加上column，设置column的css为`float: left`
		
		设置center的css为`width: 100%`
	2. 下面需要把left, right移动到顶部，这里需要用到margin的负值。当一个float元素margin负值的绝对值，大于它本身padding, width的总和时，他所占据的实际宽度就会变成0，使其不占空而浮动到容器的顶部，详细解释请[点此](http://coding.smashingmagazine.com/2009/07/27/the-definitive-guide-to-using-negative-margins/)。
	
		给left加上`margin-left: -100%;`，给right加上`margin-right: -100%;`
	3. 现在right已经位于正确的位置了，但是left还覆盖在center之上，我们只需要利用position把他移动到正确的位置就大功告成啦。
	
		给column加上`position: relative;`，并且给left加上`right: 170px;`

## Session 问题
本次session中有不少问题没有当场回答，这些问题一部分是对于一些内容的延伸，一些是对于我们所使用的css技巧的原理不理解，总结如下（若还有不明白的地方请在mythoughtworks上跟帖，或者在github上留issue）：

* 父元素float以后对于子元素有何影响？子元素不会继承父元素的float属性，所以基本没有影响。
* 为什么`margin-left: -100%;`会使left元素跑到content的顶部？首先这里的100%是相对于left的容器宽度的100%，left的容器宽度肯定是大于left的宽度，对于float元素margin负值会使其实际宽度0，也就是不占空，所以他就跑到容器顶部了。详细解释请[点此](http://coding.smashingmagazine.com/2009/07/27/the-definitive-guide-to-using-negative-margins/)。

下面的几个是课后思考：

* 怎样设置left, right, center为等高
* 是否可以移除content
* 是否可以移除`position: relative; right: 170px;`

	
	