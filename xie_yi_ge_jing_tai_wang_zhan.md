# 寫一個靜態網站


在body放一個div方便選取

```
<!DOCTYPE html>
<html lang="zh">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width">
  <link rel="stylesheet" href="css/reset.css">
  <link rel="stylesheet" href="css/style.css">
  <title>web 基礎班範例</title>
</head>
<body>
<div id="stage">


</div>
</body>
</html>
```
加上header
```
<header id="header">
    <h1>web 基礎班範例</h1>
  </header>
```
加上導航列
```
  <nav id="nav">
    <ul class="cf">
      <li>menu1</li>
      <li>menu2</li>
      <li>menu3</li>
    </ul>
  </nav>
```
加上主內容欄
```

  <div id="contents" class="cf">
  
  
  </div>
```
在主內容欄內加入一個aside內含兩個section
```
<aside class="contents_menu cf">
      <section id="contents_menu1">
        <h1>Contents Menu1</h1>
      </section>
      <section id="contents_menu2">
        <h1>Contents Menu2</h1>
      </section>
</aside>  
```
在主內容欄再加入一個article內含數個section
```
<article class="main">
	      <section id="body_link">
	        <h1>2016.03.14</h1>
	        <p>請輸入文字</p> 
         </section>
         <section id="section_link">
         	<h1>2016.03.12</h1>
         	<p>請輸入文字</p>
        </section>
        <section id="article_link">
         	<h1>2016.02.25</h1>
         	<p>請輸入文字</p>
        </section>
        <section id="aside_link">
         	<h1>2016.02.10</h1>
         	<p>請輸入文字</p>
        </section>
        <section id="nav_link">
         	<h1>2016.02.09</h1>
         	<p>請輸入文字</p>
        </section>          
    </article>
```
最後在最外層div下加入一個footer當底部
```
  <footer id="footer">
    <small>&copy; 2016 BaseTemplate. </small>
  </footer>
```

完成後長這樣子
```
<!DOCTYPE html>
<html lang="zh">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width">
  <link rel="stylesheet" href="css/reset.css">
  <link rel="stylesheet" href="css/sample01.css">
  <title>web 基礎班範例</title>
</head>
<body>
<div id="stage">
  <header id="header">
    <h1>web 基礎班範例</h1>
  </header>

  <nav id="nav">
    <ul class="cf">
      <li>menu1</li>
      <li>menu2</li>
      <li>menu3</li>
    </ul>
  </nav>

  <div id="contents" class="cf">
    <aside class="contents_menu cf">
      <section id="contents_menu1">
        <h1>Contents Menu1</h1>
      </section>
      <section id="contents_menu2">
        <h1>Contents Menu2</h1>
      </section>
    </aside>  
      <article class="main">
	      <section id="body_link">
	        <h1>2016.03.14</h1>
	        <p>請輸入文字</p> 
         </section>
         <section id="section_link">
         	<h1>2016.03.12</h1>
         	<p>請輸入文字</p>
        </section>
        <section id="article_link">
         	<h1>2016.02.25</h1>
         	<p>請輸入文字</p>
        </section>
        <section id="aside_link">
         	<h1>2016.02.10</h1>
         	<p>請輸入文字</p>
        </section>
        <section id="nav_link">
         	<h1>2016.02.09</h1>
         	<p>請輸入文字</p>
        </section>          
    </article>
  </div>

  <footer id="footer">
    <small>&copy; 2016 BaseTemplate. </small>
  </footer>
</div>
</body>
</html>

```

#接下來要幫他穿上衣服，加上CSS

