---
layout: post
title:  "两列固定宽度"
category: css
tags: [css,div]
---

## 一列宽度自适应

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        #left{
            background-color: #cccccc;
            border:2px solid #333333;
            width: 300px;
            height: 300px;
            float: left;
        }
        #right{
            background-color: #cccccc;
            border:2px solid #333333;
            width: 300px;
            height: 300px;
            float: left;
        }
    </style>
</head>
<body>
<div id="left">左列</div>
<div id="right">右列</div>
</body>
</html>
```