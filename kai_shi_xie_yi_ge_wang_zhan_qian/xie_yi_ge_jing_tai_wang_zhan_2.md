# 寫一個靜態網站2

## 寫一個靜態網站2

[https://github.com/EasonWang01/web-basic-template1](https://github.com/EasonWang01/web-basic-template1)

下載好後，我們先把html和css檔案清空，重新寫一次

```
<!DOCTYPE html>
<html lang="ja">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width">
<link rel="stylesheet" href="css/reset.css">
<link rel="stylesheet" href="css/base02.css">
<title>web example by yicheng</title>

<!--[if lt IE 9]>
<script src="js/html5shiv.js"></script>
<![endif]-->

<!--[if lt IE 9]>
<script src="js/css3-mediaqueries.js"></script>
<![endif]-->


</head>

<body>
<div id="stage"> 
<!-- header -->
  <header id="header">
    <h1 id="top"><p> web example by yicheng</p></h1>

    <ul id="s_nav" class="cf">
     <img id="img1" src="images/icn_contact.jpg" />
      <li class="contact"><a href="#">contact</a></li>
      <img src="images/icn_news.jpg" />
      <li class="news"><a href="#">news</a></li>
      <img src="images/icn_sitemap.jpg" />
      <li class="sitemap"><a href="#">sitemap</a></li>
    </ul>
    <p><img src="images/topImage.jpg" alt="Make a Responsivesite"></p>
  </header>

<!-- global navigation -->
  <nav id="nav">
    <ul class="cf">
      <li class="home"><a href="#"><img src="images/nav_home.jpg" width="51" height="48" alt="home"></a></li>
      <li><a href="#"><img src="images/nav_service.jpg" width="63" height="48" alt="service"></a></li>
      <li><a href="#"><img src="images/nav_works.jpg" width="50" height="48" alt="works"></a></li>
      <li><a href="#"><img src="images/nav_company.jpg" width="88" height="48" alt="company"></a></li>
      <li><a href="#"><img src="images/nav_recruit.jpg" width="59" height="48" alt="recruit"></a></li>
      <li class="contact"><a href="#"><img src="images/nav_contact.jpg" width="74" height="48" alt="contact"></a></li>
    </ul>
  </nav>

<!-- content area -->
  <div id="contents" class="cf"> 
    <section id="work" class="cf">

      <article>
       <a href="#"> <img src="images/1.png" width="184" height="160" alt="work1"></a>

        <h2>你好</h2>
      </article>
      <article>
      <a href="#">  <img src="images/2.png" width="184" height="160" alt="work1"></a>

        <h2>歡迎</h2>
      </article>
      <article>
        <a href="#">  <img src="images/3.png" width="184" height="160" alt="work1"></a>

        <h2>來到</h2>
      </article>
      <article>
       <a href="#">   <img src="images/4.png" width="184" height="160" alt="work1"></a>

        <h2>web</h2>
      </article>
      <article>
       <a href="#">   <img src="images/5.png" width="184" height="160" alt="work1"></a>

        <h2>基礎班</h2>
      </article>
    </section>

    <section id="news">
      <h2>NEWS</h2>
      <article>
        <h3>2016.02.03</h3>
        <p><a href="http://www.google.com">我是google</a></p>
      </article>
      <article>
        <h3>2016.02.02</h3>
        <p><a href="http://www.facebook.com">我是facebook</a></p>
      </article>
      <article>
        <h3>2016.02.01</h3>
        <p><a href="http://www.youtube.com.tw">我是youtube</a></p>
      </article>
    </section>

    <section id="information">
      <h2>INFORMATION</h2>
      <ul>
        <li><a href="#"><img src="images/bnr_recuruit.jpg" alt="recruit"></a></li>
        <li><a href="#"><img src="images/bnr_service.jpg" alt="our services"></a></li>
      </ul>
    </section>
  </div>

<!-- page top button -->
  <a id="pagetopBtn" href="#top"><img src="images/icn_pagetop.jpg" width="40" height="60" alt="pagetop"></a>
  <!-- href="#top 帶你到頁面帶有id="top"的地方  -->
<!-- footer -->
  <footer id="footer">
    <div>
      <p>web example by yicheng</p>

      <p><small id="small">Copyright &copy; 2016 Responsive corporation. All Rights Reserved.</small></p>
    </div>
  </footer>

</div>
</body>
</html>
```

css

1\.

```
/* 把連結的字變黑色，底線去掉 */
a {
  color:#000;
  text-decoration:none;
}
```

2.header置中

```
header {
  text-align:center;
}
```

3

```
/* 把header往下拉一點 */
header h1 {
  padding:25px  ; 
}
```

4\.

```
/* 設定圖案 */

p img{
width:100%;
}
```

5\.

```
nav{
text-align:center;
}
```

6\.

```
#contents{
text-align:center;
}
```

7\.

```
article h3 {
padding:20px;
}
```

8\.

```
#information{
padding:20px;
}
```

9\.

```
#information img{
width:100%;
}
```

10

```
#pagetopBtn{
position:fixed;
bottom:0px;
right:0px;
}
```

11

```
#footer p,small{
text-align:center;
font-size:5px;
}
```

接著做給平板用的版型

```
/* For 平板 */
@media only screen and (min-width:481px){


}
```

一樣先放black做測試大小

```
body{

background:black;
}
```

刪掉BODY後，先調nav

```
@media only screen and (min-width:481px){

nav ul li {
  float: left;
  width: 49%;   /*調到50%發現又變回來 ，因為我們上面nav li 設定了一個右側的border 1px*/
  border-bottom: 2px solid #000;
}





}
```

再來設定下面

```
#work article{
float:left;
width:50%;
}
```

### For 電腦螢幕

```
/* For 電腦螢幕 */
@media only screen and (min-width:961px){
nav ul li {
  width: calc(98%/6); 
}
}
```

調整最上方

```
header h1{
float:left;
}
header img{
float:left;
margin-right:5px;
}
header li{
float:left;
margin-right:5px;
}
```

```
header ul{
float:right;
margin-top:25px;
}
```

```
#work article{
float:left;
width:20%;
}
```

從手機板慢慢拉到電腦版，發現最左上方怪怪的，須點F5，畫面才變正常，原因是ul大小在畫面拉大時沒跟著變，所以要幫他變大，才塞的下東西

```
header ul{
width:30%;
margin-right:-100px;
}
```

最後

```
#news{
width:40%;
position:absolute;

}
#information{
width:40%;
float:right;
}
```

## 完成後

```
/* 把連結的字變黑色，底線去掉 */
a {
  color:#000;
  text-decoration:none;
}
/* 滑鼠滑入時變色，並增加底線 */
a:hover {
  color:#333;
  text-decoration:underline;
}
header {
  text-align:center;
}
/* 把header往下拉一點 */
header h1 {
  padding:25px  ; 
}
/* 設定圖案 */

p img{
width:100%;
}
nav{
text-align:center;
}
#contents{
text-align:center;
}

article h3 {
padding:20px;
}

#information{
padding:20px;
}

#information img{
width:100%;
}


#pagetopBtn{
position:fixed;
bottom:0px;
right:0px;
}


#footer p,small{
text-align:center;
font-size:5px;
}

nav li{
border: 1px solid black;
}

section{
margin-top:60px;

}
section>h2{
border-bottom:1px solid black;
}


/* For 平板 */
@media only screen and (min-width:481px){

nav ul li {
  float: left;
  width: 49%;   /* 調到50%發現又變回來 ，因為我們上面nav li 設定了一個右側的border 1px*/
  border-bottom: 2px solid #000;
}
#work article{
float:left;
width:50%;
}




}


/* For 電腦螢幕 */
@media only screen and (min-width:961px){
header h1{
float:left;
}
header img{
float:left;
margin-right:5px;
}
header li{
float:left;
margin-right:5px;
}
header ul{
width:30%;
margin-right:-100px;
}

header ul{
float:right;
margin-top:25px;
}

nav ul li {
  width: calc(98%/6); 
}
#work article{
float:left;
width:20%;
}

#news{
width:40%;
position:absolute;

}
#information{
width:40%;
float:right;
}



}
```
