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
  <link rel="stylesheet" href="css/style.css">
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

再HTML檔案旁創建一個css資料夾，裡面再創兩個檔案，reset.css與style.css


我們開啟style.css先在body上加入
```
body {
  width: 100%;
  margin: 0;
  padding: 0;
  line-height: 1.5em;
}
```
再幫header加入
```
header {
  text-align: center;
  background-color:#1affff;
}
```
再幫nav加入
```
nav {
  background-color:#ffffcc;
}
```
```
nav ul li {
  display: block;
  width: 100%;
  text-align: center;
  line-height: 2.0em;
  color:black;
  border-bottom: 1px solid #fff;
}
```
幫content加入
```
#contents {
  width: 80%;
  margin: 1em auto 1em;
}
#contents h1{
  font-weight: bold;
}
```
讓section產生空白邊框的感覺
```

section {
  margin: 0 0 1em 0;
}
```
分別設定兩個區域的section
```
aside > section{
  height:130px;
  background-color: #00ccff;
  padding: 15px 0 0 20px;
}
article > section{
  border-bottom: 1px solid #ccc;
}
```
最後在尾端footer加上
```
footer {
  width: 100%;
  text-align: center;
}
```

完成後長這樣

style.css
```

.cf { zoom: 1; }
.cf:before, .cf:after { content: ""; display: table; }
.cf:after { clear: both; }


body {
  width: 100%;
  margin: 0;
  padding: 0;
  line-height: 1.5em;
}
header {
  text-align: center;
  background-color: #1affff;
}
nav {
  background-color: #ffffcc;
}
nav ul li {
  display: block;
  width: 100%;
  text-align: center;
  line-height: 2.0em;
  color:black;
  border-bottom: 1px solid #fff;
}
#contents {
  width: 80%;
  margin: 1em auto 1em;
}
#contents h1{
  font-weight: bold;
}

section {
  margin: 0 0 1em 0;
}
aside > section{
  height:130px;
  background-color: #00ccff;
  padding: 15px 0 0 20px;
}
article > section{
  border-bottom: 1px solid #ccc;
}
footer {
  width: 100%;
  text-align: center;
}
```
#RWD網頁通常會從手機頁面開始做，以下我們開始做給平板跟給電腦螢幕的


/* 平板：481px ～ 768px */

##在下面加上
```
@media only screen and (min-width: 481px) {

}
```
#如何測試?
```
@media only screen and (min-width: 481px) {
body{
background:black;
}
```
調整瀏覽器視窗大小，當到達時會變色

1.讓nav成水平排列

```
 nav ul li {
  float:left;
  width: 100px;
  text-align: center;
  line-height: 3.0em;
  border-left: 1px solid #fff;
  border-right: 1px solid #ccc;  
 }
```
2.讓上面兩個方框變水平
```
  #contents_menu1 {
   width: 45%;
   float: left;
 }
  #contents_menu2 {
   width: 45%;
   float: right;
 }
```

#For電腦
/*  電腦：769px～960px */
```
@media only screen and (min-width: 769px) {

}
```
一樣先加上顏色測試
```
@media only screen and (min-width: 769px) {
 background:black;
}
```

將主畫面的右邊設為

```
 article.main {
   width: 65%;
   float: right;
 }
  aside.contents_menu {
   width: 30%;
   float: left;
 }
```
將主畫面左邊設為
```
 #contents_menu1,
 #contents_menu2 {
   width: 95%;
   float: none;
 }
```