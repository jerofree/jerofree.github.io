---
layout: post
title:  "三列浮动中间宽度自适应"
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
        #layout{
            position: absolute;
            top:20px;
            left:0px;
        }
        #left{
            background-color: #cccccc;
            border:2px solid #333333;
            width: 100px;
            height: 300px;
            position: absolute;
            top:0px;
            left: 0px;
        }
        #right{
            background-color: #cccccc;
            border:2px solid #333333;
            width:100px;
            height: 300px;
            position: absolute;
            right: 0px;
            top:0px;

        }
        #center{
            background-color: #cccccc;
            border: 2px solid #333333;
            height: 300px;
            margin-left: 104px;
            margin-right: 104px;
        }
        body{
            margin: 0px;
            padding:0px;
        }
    </style>
</head>
<body>
    <div id="left">左列</div>
    <div id="center">中列</div>
    <div id="right">右列</div>
</body>
</html>

```


