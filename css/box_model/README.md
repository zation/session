# CSS Session 第一波 --- 一起来画三角形
---
## Session 目标
1. 学习CSS中的盒模型
2. 了解CSS属性Position（主要是absolute、relative）的用法
3. 如何简化CSS书写
4. 如何使CSS样式更易于维护

## Session 材料
* [PPT](http://zation.github.com/session/css/box_model/)
* [Session基础代码](https://github.com/zation/session/blob/gh-pages/css/box_model/basic.html)
* [课后练习基础代码](https://github.com/zation/session/blob/gh-pages/css/box_model/practise.html)
* [所有使用到的code](https://github.com/zation/session/tree/gh-pages/css/box_model)

## Session 内容
1. 展示完成本次Session后大家可以完成的效果，同时也是课后作业
2. 讲解盒模型，特别是border以及content。也许很多人已经了解过盒模型，但是对于其中border和content并没有深入了解。当深入了解以后我们可以做一些很有意思的事情。（深入了解请[点此](http://w3help.org/zh-cn/kb/006/)）
3. 利用CSS中border的特性画一个三角形。这里的几个css属性都可以简写，具体可以参考session.css中#triangle相关样式。
4. 用两种方法画梯形。可以参考session.css中#trapezoid-1和#trapezoid-2的相关样式。
5. 实际操作中了解position属性。可以修改position.css中的属性来查看具体效果，深入了解请[点此](http://w3help.org/zh-cn/kb/009/)。
6. 画一个^符号，主要是用一个三角形遮盖另一个三角形实现。这样实现的样式比较容易维护，当我们要改变颜色、大小的时候只需要调整css属性就可以实现，而调整位置时，只需要调整外层三角形的位置。可以参考#triangle-with-border和#triangle-cover的相关样式。

PS: 第一次做类似workshop的session，也是第一次写成文档，如果有任何欠缺的地方，或者不明白的地方，希望大家可以随时来找我，或者添加评论，发邮件，github上面提issue都可以哦！:)


