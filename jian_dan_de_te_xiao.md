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
8.重疊陰影效果
```
        .color:hover
        {

                box-shadow:
                10px 10px #53a7ea,
                20px 20px #53a7ea,
                30px 30px #53a7ea;
       
        transform: translateX(-30px);
        }
```
9.震動效果
```
  /* 定義關鍵影格 */
 @keyframes swing
{
    15%
    {
        -webkit-transform: translateX(5px);
        transform: translateX(5px);
    }
    30%
    {
        -webkit-transform: translateX(-5px);
        transform: translateX(-5px);
    }
    50%
    {
        -webkit-transform: translateX(3px);
        transform: translateX(3px);
    }
    65%
    {
        -webkit-transform: translateX(-3px);
        transform: translateX(-3px);
    }
    80%
    {
        -webkit-transform: translateX(2px);
        transform: translateX(2px);
    }
    100%
    {
        -webkit-transform: translateX(0);
        transform: translateX(0);
    }
}

/*套用*/
        .color:hover
        {

      animation: swing 1s ease;
        }

```
10.往內的邊框
```
        .color:hover
        {

  box-shadow: inset 0 0 0 25px #53a7ea;
        }
```
11.視差捲動
```

<!DOCTYPE html>
<html>
<head>

<body>
<style>
   .demo {
    perspective: 1px; padding: 0; height: 800px; height: calc(100vh - 300px); overflow: auto;
}
.box {
    height: 1280px;
    transform-style: preserve-3d;
    position: relative;
}
.iphone {
    position: absolute; left: 50%;
    transform: translate3D(-50%, -120px, -10px) scale(8);
}
</style>
<div class="demo">
    <div class="box">
        <img src="001.jpg" class="iphone">
        <i class="smile"><img style="position:absolute;top:620px;left:320px; "src="0112.png"/></i><i class="flower"></i><i class="music"></i><i class="pdf"></i>
    </div>
</div>
</body>
</html>
```
解說:
http://codepen.io/EasonWang01/pen/VaQYmW

`perspective`為人們看元素的距離(樹字越大越近看)
`translateZ`為Z軸的坐標

(想像坐在車上時觀看窗外月亮，沒有移動，但窗外樹叢卻移動很快，同樣道理)