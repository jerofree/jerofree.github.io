---
layout: post
title:  "下拉及多级弹出式菜单"
category: css
tags: [div, css]
---


```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        ul{
            margin: 0;
            padding: 0;
            list-style: none;
            width:130px;
            border-bottom: 1px solid #ccc;
            font-size:12px;
        }
        ul li{        /*所有ul下的所有li*/
            position:relative;
        }
        li ul{        /*所有li下的所有的ul*/
            position: absolute;
            left: 529px;
            top:0;
            display: none;
        }
        ul li a {
            display: block;
            text-decoration: none;
            color:#777;
            background-color: #fff;
            padding:5px;
            border:1px solid #ccc;
            border-bottom: 0;
        }
        li:hover ul{
            display: block;
        }
    </style>


</head>
<body>
    <ul class="nav">
        <li><a href="">文章</a>
        <ul>
            <li><a href="">CSS教程</a></li>
            <li><a href="">DOM教程</a></li>
            <li><a href="">XML教程</a></li>
            <li><a href="">Flash教程</a></li>
        </ul>
        </li>
        <li><a href="">参考</a>
        <ul>
            <li><a href="">XHTML</a></li>
            <li><a href="">XML</a></li>
            <li><a href="">CSS</a></li>
        </ul>
        </li>
        <li><a href="">Blog</a>
            <ul>
                <li><a href="">全部</a></li>
                <li><a href="">网页技术</a></li>
                <li><a href="">UI技术</a></li>
                <li><a href="">FLASH技术</a></li>
            </ul>
        </li>
    </ul>
</body>
</html>
```































```