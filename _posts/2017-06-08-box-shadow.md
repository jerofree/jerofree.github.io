---
layout: post
title:  "box-shadow使用!"
category: css3
tags: [css3,box-shadow]
---

### box-shadow: X轴偏移量 Y轴偏移量 [阴影模糊半径] [阴影扩展半径] [阴影颜色] [投影方式];注意：inset 可以写在参数的第一个或最后一个，其它位置是无效的。

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        div{
            width:200px;
            height: 100px;
            background-color: orange;
            box-shadow:40px 80px 20px black,10px 20px 10px #33CC00,
        10px 10px 10px inset;多阴影边框
        }
        p{
            width: 40px;
            height: 40px;
            border-radius: 20px;
            background-color: black;
        }
    </style>
</head>
<body>
<div>
    <P></P>
</div>
</body>
</html>
```

![image](/images/2017-06-08-box-shadow.PNG)