---
layout: post
title:  "两列固定宽度居中"
category: css
tags: [div, css]
---


```

<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        #layout{
            margin:0 auto;
            width:408px;
        }
        #left{
            background-color: #cccccc;
            border:2px solid #333333;
            width: 200px;
            height: 300px;
            float: left;
        }
        #right{
            background-color: #cccccc;
            border:2px solid #333333;
            width:200px;
            height: 300px;
            float: left;
        }
    </style>
</head>
<body>
<div id="layout">
    <div id="left">左列</div>
    <div id="right">右列</div>
</div>
</body>
</html>
```


