# 使用Bootstrap

## 使用Bootstrap

1.開啟一個新的資料夾，裡面建立css資料夾，以及外面建立index.html

2.到bootstrap官網下載，之後加css資料夾內的bootstrap.css放入你的css資料夾內

index.html

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link rel='stylesheet' type='text/css' href='./css/bootstrap.css' />
    <title>Document</title>
</head>
<body>

</body>
</html>
```

或直接放入

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Bootstrap  Template</title>


    <link href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/css/bootstrap.min.css" rel="stylesheet">
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.1/jquery.min.js"></script>

    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/js/bootstrap.min.js"></script>

  </head>
  <body>
   <div class="container">







</div>
 </body>
</html>
```

### 開始使用

1.everything inside container，所有的元素都必須放在這裡面

2.用class定義元素樣式

3.加起來等於12

4.Glyphicons

```
<div class="container">

</div>
```

將下面放入container內

```
<nav class="navbar navbar-inverse">
  <div class="container-fluid">
    <div class="navbar-header">
      <a class="navbar-brand" href="#">WebSiteName</a>
    </div>
    <ul class="nav navbar-nav">
      <li class="active"><a href="#">Home</a></li>
      <li class="dropdown"><a class="dropdown-toggle" data-toggle="dropdown" href="#">Page 1 <span class="caret"></span></a>
        <ul class="dropdown-menu">
          <li><a href="#">Page 1-1</a></li>
          <li><a href="#">Page 1-2</a></li>
          <li><a href="#">Page 1-3</a></li>
        </ul>
      </li>
      <li><a href="#">Page 2</a></li>
      <li><a href="#">Page 3</a></li>
    </ul>
  </div>
</nav>
```

```
   <div class="jumbotron">
    <h1>我是範例</h1>      
    <p>This is just an example</p>
  </div>
```

## 佈局

```
.col-xs- 小於768px
.col-sm- 768~992
.col-md- 992~1200
.col-lg- 大於1200
```

後面的數字加起來最大12，超過會跑到第二列

如果一個螢幕大小為1200px而div中具有xs和sm則sm會蓋過xs的效果

```
<div class="row">
  <div class="col-xs-12 col-md-8">.col-xs-12 .col-md-8</div>
  <div class="col-xs-6 col-md-4">.col-xs-6 .col-md-4</div>
</div>


<div class="row">
  <div class="col-xs-6 col-md-4">.col-xs-6 .col-md-4</div>
  <div class="col-xs-6 col-md-4">.col-xs-6 .col-md-4</div>
  <div class="col-xs-6 col-md-4">.col-xs-6 .col-md-4</div>
</div>

<div class="row">
  <div class="col-xs-6">.col-xs-6</div>
  <div class="col-xs-6">.col-xs-6</div>
</div>
```

使用offset讓元素往右

```
<div class="row">
  <div class="col-md-6">.col-sm-5 .col-md-6</div>
  <div class=" col-md-6 col-md-offset-0">.col-sm-5 .col-sm-offset-2 .col-md-6 .col-md-offset-0</div>
</div>

<div class="row">
  <div class="col-md-5 ">.col-sm-6 .col-md-5 </div>
  <div class=" col-md-5 col-md-offset-1">.col-sm-6 .col-md-5 .col-md-offset-2 .col-lg-6 .col-lg-offset-0</div>
</div>
```

等於

```
<div class="row">
  <div class="col-md-6">.col-sm-5 .col-md-6</div>
  <div class=" col-md-6 col-md-offset-0">.col-sm-5 .col-sm-offset-2 .col-md-6 .col-md-offset-0</div>
</div>

<div class="row">
  <div class="col-md-6 ">.col-sm-6 .col-md-5 </div>
  <div class=" col-md-5 col-md-offset-0">.col-sm-6 .col-md-5 .col-md-offset-2 .col-lg-6 .col-lg-offset-0</div>
</div>
```

### 使用pull和push的absolute移動

push往左，pull往右

```
<div class="row">
  <div class="col-md-9 col-md-push-3">.col-md-9 .col-md-push-3</div>
  <div class="col-md-3 col-md-pull-9">.col-md-3 .col-md-pull-9</div>
</div>
```

### 文字對齊

```
<p class="text-left">靠左對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。</p>
<p class="text-center">置中對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。</p>
<p class="text-right">靠右對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。</p>
<p class="text-justify">平均對齊文字平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。。</p>
<p class="text-nowrap">不換行文字平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。平均對齊文字。。</p>
```

### blockquote

比原生html多了左邊的直線 [http://www.w3schools.com/tags/tryit.asp?filename=tryhtml\_blockquote\_default\_css](http://www.w3schools.com/tags/tryit.asp?filename=tryhtml\_blockquote\_default\_css)

```
<blockquote>
  <p>人之初</p>
  <footer>今天<cite title="Source Title">買蘋果</cite></footer>
</blockquote>
```

表單

```
<form role="form">
  <div class="form-group">
    <label for="exampleInputEmail1">電子郵件</label>
    <input type="email" class="form-control" id="exampleInputEmail1" placeholder="輸入電子郵件">
  </div>
  <div class="form-group">
    <label for="exampleInputPassword1">密碼</label>
    <input type="密碼" class="form-control" id="exampleInputPassword1" placeholder="Password">
  </div>
  <div class="form-group">
    <label for="exampleInputFile">檔案上傳</label>
    <input type="file" id="exampleInputFile">
    <p class="help-block">在此示範區塊層級輔助說明文字。</p>
  </div>
  <div class="checkbox">
    <label>
      <input type="checkbox"> 勾選我
    </label>
  </div>
  <button type="submit" class="btn btn-default">送出</button>
</form>
```

## 導覽列

```
<nav class="navbar>
```

```
<nav class="navbar navbar-inverse">
  <div class="container-fluid">
    <div class="navbar-header">
      <button type="button" class="navbar-toggle" data-toggle="collapse" data-target="#myNavbar">
        <span class="icon-bar"></span>
        <span class="icon-bar"></span>
        <span class="icon-bar"></span>                        
      </button>
      <a class="navbar-brand" href="#">WebSiteName</a>
    </div>
    <div class="collapse navbar-collapse" id="myNavbar">
      <ul class="nav navbar-nav">
        <li class="active"><a href="#">Home</a></li>
        <li class="dropdown">
          <a class="dropdown-toggle" data-toggle="dropdown" href="#">Page 1 <span class="caret"></span></a>
          <ul class="dropdown-menu">
            <li><a href="#">Page 1-1</a></li>
            <li><a href="#">Page 1-2</a></li>
            <li><a href="#">Page 1-3</a></li>
          </ul>
        </li>
        <li><a href="#">Page 2</a></li>
        <li><a href="#">Page 3</a></li>
      </ul>
      <ul class="nav navbar-nav navbar-right">
        <li><a href="#"><span class="glyphicon glyphicon-user"></span> Sign Up</a></li>
        <li><a href="#"><span class="glyphicon glyphicon-log-in"></span> Login</a></li>
      </ul>
    </div>
  </div>
</nav>
```

使用圖案，到[https://kkbruce.tw/bs3/Components查詢](https://kkbruce.tw/bs3/Components%E6%9F%A5%E8%A9%A2)

```
<button class="btn btn-default" >
  <span class="glyphicon glyphicon-align-left" aria-hidden="true"></span>
</button>

<button  class="btn btn-default ">
  <span class="glyphicon glyphicon-star" aria-hidden="true"></span> 
</button>
```

實際範例

加入導覽列

```
 <div class="navbar navbar-inverse navbar-fixed-top">
      <div class="container">
        <div class="navbar-header">
          <button type="button" class="navbar-toggle" data-toggle="collapse" data-target=".navbar-collapse">
            <span class="icon-bar"></span>
            <span class="icon-bar"></span>
            <span class="icon-bar"></span>
          </button>
          <a class="navbar-brand" href="#">SP<i class="fa fa-circle"></i>T</a>
        </div>
        <div class="navbar-collapse collapse">
          <ul class="nav navbar-nav navbar-right">
            <li class="active"><a href="index.html">HOME</a></li>
            <li><a href="about.html">ABOUT</a></li>
            <li><a href="services.html">SERVICES</a></li>
            <li><a href="works.html">WORKS</a></li>
            <li><a data-toggle="modal" data-target="#myModal" href="#myModal"><i class="fa fa-envelope-o"></i></a></li>
          </ul>
        </div><!--/.nav-collapse -->
      </div>
    </div>
```

加入中間部分

```
    <div style="margin-top:100px;" class="container">
        <div class="row centered">
            <br><br>
            <div class="col-lg-4">
                <i class="fa fa-heart"></i>
                <h4>DESIGN</h4>
                <p>There are many variations of passages of Lorem Ipsum available, but the majority have suffered alteration in some form, by injected humour, or randomised words which don't look even believable.</p>
            </div><!-- col-lg-4 -->

            <div class="col-lg-4">
                <i class="fa fa-laptop"></i>
                <h4>BOOTSTRAP</h4>
                <p>There are many variations of passages of Lorem Ipsum available, but the majority have suffered alteration in some form, by injected humour, or randomised words which don't look even believable.</p>
            </div><!-- col-lg-4 -->

            <div class="col-lg-4">
                <i class="fa fa-trophy"></i>
                <h4>SUPPORT</h4>
                <p>There are many variations of passages of Lorem Ipsum available, but the majority have suffered alteration in some form, by injected humour, or randomised words which don't look even believable.</p>
            </div><!-- col-lg-4 -->
        </div><!-- row -->
        <br>
        <br>
    </div><!-- container -->
```

2\.

```
<div>
        <div class="container">
            <div class="row">
                <h4>LATEST WORKS</h4>
                <br>
                <div class="col-lg-4">
                    <div class="tilt">
                    <a href="#"><img src="https://raw.githubusercontent.com/EasonWang01/EasonWang01.github.io/master/assets/img/p01.png" alt=""></a>
                    </div>
                </div>

                <div class="col-lg-4">
                    <div class="tilt">
                    <a href="#"><img src="https://raw.githubusercontent.com/EasonWang01/EasonWang01.github.io/master/assets/img/p03.png" alt=""></a>
                    </div>
                </div>

                <div class="col-lg-4">
                    <div class="tilt">
                    <a href="#"><img src="https://raw.githubusercontent.com/EasonWang01/EasonWang01.github.io/master/assets/img/p02.png" alt=""></a>
                    </div>
                </div>
            </div><!-- row -->
        </div><!-- container -->
    </div>
```

3\.

```
<div class="container" >
        <div class="row ">
            <br><br>
            <div class="col-lg-8 col-lg-offset-2">
                <h4>WE CREATE FIRST CLASS DESIGN</h4>
                <p>By being true to the brand we represent, we elevate the audiences’ relationship to it. Like becomes love becomes a passion. Passion becomes advocacy. And we see the brand blossom from within, creating a whole story the audience embraces. That’s when the brand can truly flex its muscles.</p>
            <p><br/><br/></p>
            </div>
            <div class="col-lg-2"></div>
            <div class="col-lg-10 col-lg-offset-1">
                <img class="img-responsive" src="https://raw.githubusercontent.com/EasonWang01/EasonWang01.github.io/master/assets/img/munter.png" alt="">
            </div>
        </div><!-- row -->
    </div><!-- container -->
```

4\.

```
    <div>
        <div class="container"style="margin-top:10%">
            <div class="row>
                <div class="col-lg-8 col-lg-offset-2">

                    <p>We believe ideas come from everyone, everywhere. At BlackTie, everyone within our agency walls is a designer in their own right. And there are a few principles we believe—and we believe everyone should believe—about our design craft. These truths drive us, motivate us, and ultimately help us redefine the power of design.</p>
                </div>
            </div><!-- row -->
        </div><!-- container -->
```
