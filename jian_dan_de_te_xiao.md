# 簡單的特效

###改變字型

在這之前，介紹一個字型的網站
https://www.google.com/fonts/

>如何使用?

1.加入`<link href='字型網址' rel='stylesheet' type='text/css'>`

2.`font-family: '字型名稱`


##簡單效果

1.淡入

新增一個HTML檔案，加入

```

<!DOCTYPE html>
<html>
<head>
    
    <link href='http://fonts.googleapis.com/css?family=Lato:900' rel='stylesheet' type='text/css'>
    
    <style type="text/css">
        
        body > div
        {
            
            margin:121px 149px;
            
            width:483px;
            height:298px;
            
            background:#676470;
            color:#fff;
            
            font-family:Lato;
            font-weight:900;
            font-size:3.4em;
            
            text-align:center;
            line-height:298px;
            
            transition:all 0.3s;
            
        }
        
        .fade
        {
            opacity:0.5;
        }
        .fade:hover
        {
            opacity:1;
        }
        
    </style>
</head>
<body>
    
    <div class="fade">Fade in</div>
    
</body>
</html>
```
2.淡出

```
        .fade
        {
            opacity:1;
        }
        .fade:hover
        {
            opacity:0.5;
        }
        
```

3.滑鼠滑入時更改顏色

```

<!DOCTYPE html>
<html>
<head>
    
    <link href='http://fonts.googleapis.com/css?family=Lato:900' rel='stylesheet' type='text/css'>
    
    <style type="text/css">
        
        body > div
        {
            
            margin:121px 149px;
            
            width:483px;
            height:298px;
            
            background:#676470;
            color:#fff;
            
            font-family:Lato;
            font-weight:900;
            font-size:3.4em;
            
            text-align:center;
            line-height:298px;
            
            transition:all 0.3s ease;
            
        }
        
        .color:hover
        {
            background:#53a7ea;
        }
        
    </style>
</head>
<body>
    
    <div class="color">Change Color</div>

</body>
</html>
```
4.放大

```
 .color:hover
        {
            transform: scale(1.3);
            background:#53a7ea;
        }

```
5.縮小
```
       .color:hover
        {
            transform: scale(0.3);
            background:#53a7ea;
        }
```
6.旋轉縮小
```
        .color:hover
        {

            transform: scale(0.3) rotateZ(-30deg);
            background:#53a7ea;
        }
```
7.變換外框形狀
```
        .color:hover
        {

            border-radius:50%;
            background:#53a7ea;
        }
        
```