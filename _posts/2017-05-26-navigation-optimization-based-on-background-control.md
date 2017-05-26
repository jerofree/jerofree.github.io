---
layout: post
title:  "基于背景控制的导航优化"
category: css
tags: [div, css]
---



高亮段落代码

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
   #header{
       width: 802px;
       height: 98px;
       background: url(img/headerbg.gif);
   }
   #nav{
       height: 26px;
       list-style: none;
       float: right;
       margin-top: 72px;
   }
    #nav li a{
        color: #ffffff;
        text-decoration: none;
        padding-top: 7px;
        display: block;
        width: 97px;
        height: 19px;
        text-align: center;
        background: url("img/nav.gif");
        margin-left: 2px;
    }
        #nav li a:hover {
            background: url("img/nav.gif") 0 -26px;
            color: #FFFFFF;
        }
        #nav li a#current{
            background: url(img/nav.gif) 0 -52px;
            color:#000000;
        }
#nav li{
    float: left;
}

    </style>


</head>
<body>
<div id="header">
    <div id="nav">
        <li><a href="#" id="current">首页</a></li>
        <li><a href="#">文章</a></li>
        <li><a href="#">参考</a></li>
        <li><a href="#">Blog</a></li>
        <li><a href="#">论坛</a></li>
        <li><a href="#">联系</a></li>
    </div>
</div>




</body>
</html>
```


