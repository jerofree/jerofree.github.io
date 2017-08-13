---
layout: post
title:  "垂直外边距合并的问题"
category: css外边距
tags: [css]
---
###	边界叠加是一个相当简单的概念。但是，在实践中对网页进行布局时，它会造成许多混淆。
###	简单地说，当两个垂直边界相遇时，它们将形成一个边界。这个边界的高度等于两个发生叠加的边界的高度中的较大者。
##	子元素设置margin-top改变父元素定位
这个问题发生的原因是根据规范，一个盒子如果没有上补白(padding-top)和上边框(border-top)，那么这个盒子的上边距会和其内部文档流中的第一个子元素的上边距重叠。
 
###	就会不断一层一层的找自己 “领导”(父元素，祖先元素)的麻烦。
###	只要给领导设置个有效的 border或者padding就可以有效的管制这个目无领导的margin防止它越级，假传圣旨，把自己的margin当领导的margin执行。
###	对于垂直外边距合并的解决方案上面已经解释了，为父元素例子中的middle元素增加一个border-top或者padding-top即可解决这个问题。
- - -
```javascript
	补充解决方案：

	1.外层padding

	2.透明边框border:1pxsolidtransparent;

	3.绝对定位postion:absolute:

	4.外层DIVoverflow:hidden;

	5.内层DIV　加float:left;display:inline;

	6.外层DIV有时会用到zoom:1;

```
###	关于绝对定位与相对定位，父盒子使用相对定位，子盒子使用相对定位或者绝对定位都可以，但是子盒子相对定位后，margin-top属性会导致父盒子变化。解决方案上述已经给出。


