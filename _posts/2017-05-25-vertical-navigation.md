---
layout: post
title:  "纵向导航"
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
    #category{
        width: 100px;
        border-right: 1px solid #c5c6c4;
        border-bottom: 1px solid #c5c6c4;
        border-left: 1px solid #c5c6c4;
    }
        #category h1{
            margin: 0px;
            padding: 4px;
            font-size: 12px;
            font-weight: bold;
            border-top:1px solid #c5c6c4;
            background-color: #f4f4f4;

        }
        #category h2{
            margin:0px;
            padding:4px;
            font-size:12px;
            font-weight: normal;
        }
    </style>
</head>
<body>
<div id="category">
    <h1>CSS</h1>
        <h2>CSS入门</h2>
        <h2>CSS进阶</h2>
        <h2>CSS高级技巧</h2>
    <h1>WebUI</h1>
        <h2>理论知识</h2>
        <h2>实战应用</h2>
        <h2>高级技巧</h2>
    <h1>DOM</h1>
        <h2>DOM入门</h2>
        <h2>DOM应用</h2>
        <h2>DOM与浏览器</h2>
    <h1>XHTML</h1>
        <h2>XHTML参考手册</h2>
        <h2>XHTML论坛</h2>
</div>

</body>
</html>
```