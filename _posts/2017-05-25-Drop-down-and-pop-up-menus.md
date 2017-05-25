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
        padding: 0;
        margin:0;
        list-style: none;
    }
    li{
        float: left;
        width:160px;
    }
        li ul{
            display: none;
        }
        li:hover ul{
            display: block;

        }
        ul li a{
            display: block;
            font-size: 12px;
            border:1px solid #ccc;
            padding:3px;
            text-decoration: none;
            color:#777;
        }
ul li a:hover{
    background-color: #f4f4f4;    
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