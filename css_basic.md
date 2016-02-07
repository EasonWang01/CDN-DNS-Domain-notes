# CSS basic

**如何使用**

1.直接在HTML內加入

```<style> </style>  ```

2.外部檔案

```<link rel="stylesheet" type="text/css" href="mystyle.css">```

3.直接在標籤內加入

```<h1 style="color:blue;margin-left:30px;">This is a heading.</h1> ```
**
CSS選取**

1.只選```<p>```

```
p{
   color: red;
}

```



2.只有```<p>```且class為center的標籤會被影響
```
p.center {
    text-align: center;
    color: red;
}
```


3..選擇h1和h2及p用逗號分隔

```
h1, h2, p {
    text-align: center;
    color: red;
}
```

4.選取其下所有子代(間隔一個空隔)
```
div p{
      color: red;
}
```
5.選取所有元素
```
*{
  
}

```
6.選取虛擬元素

http://www.w3schools.com/css/tryit.asp?filename=trycss_link

更多可參考
http://www.w3schools.com/cssref/css_selectors.asp

**
CSS Properties 屬性**

1.顏色

color:http://www.w3schools.com/css/tryit.asp?filename=trycss_colors_names

opacity:http://www.w3schools.com/cssref/tryit.asp?filename=trycss3_opacity

2.背景

Backgrounds:http://www.w3schools.com/css/css_background.asp

3.邊框

Border:http://www.w3schools.com/css/tryit.asp?filename=trycss_border

4.邊緣距離

Margin:http://www.w3schools.com/css/tryit.asp?filename=trycss_margin_sides

5.大小:
http://www.w3schools.com/css/tryit.asp?filename=trycss_dim_height_width

6.字體操作

http://www.w3schools.com/css/css_text.asp

http://www.w3schools.com/css/css_font.asp


