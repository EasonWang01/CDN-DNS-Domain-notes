# 使用Bootstrap

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
##開始使用

1.everything inside container，所有的元素都必須放在這裡面

2.用class定義元素樣式

3.加起來等於12

4.Glyphicons
```
<div class="container">

</div>
```

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