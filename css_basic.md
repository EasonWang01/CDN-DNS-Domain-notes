# CSS basic

**如何使用**

1.直接在HTML內加入

`<style> </style>`

2.外部檔案

`<link rel="stylesheet" type="text/css" href="mystyle.css">`

3.直接在標籤內加入

`<h1 style="color:blue;margin-left:30px;">This is a heading.</h1>` \*\*

CSS選取\*\*

1.只選`<p>`

```text
p{
   color: red;
}
```

2.只有`<p>`且class為center的標籤會被影響

```text
p.center {
    text-align: center;
    color: red;
}
```

3..選擇h1和h2及p用逗號分隔

```text
h1, h2, p {
    text-align: center;
    color: red;
}
```

4.選取其下所有子代\(間隔一個空隔\)

```text
div p{
      color: red;
}
```

5.選取所有元素

```text
*{

}
```

6.選取虛擬元素

[http://www.w3schools.com/css/tryit.asp?filename=trycss\_link](http://www.w3schools.com/css/tryit.asp?filename=trycss_link)

更多可參考 [http://www.w3schools.com/cssref/css\_selectors.asp](http://www.w3schools.com/cssref/css_selectors.asp)

 **CSS Properties 屬性**

1.顏色

color:[http://www.w3schools.com/css/tryit.asp?filename=trycss\_colors\_names](http://www.w3schools.com/css/tryit.asp?filename=trycss_colors_names)

opacity:[http://www.w3schools.com/cssref/tryit.asp?filename=trycss3\_opacity](http://www.w3schools.com/cssref/tryit.asp?filename=trycss3_opacity)

2.背景

Backgrounds:[http://www.w3schools.com/css/css\_background.asp](http://www.w3schools.com/css/css_background.asp)

3.邊框

Border:[http://www.w3schools.com/css/tryit.asp?filename=trycss\_border](http://www.w3schools.com/css/tryit.asp?filename=trycss_border)

4.邊緣距離

Margin:[http://www.w3schools.com/css/tryit.asp?filename=trycss\_margin\_sides](http://www.w3schools.com/css/tryit.asp?filename=trycss_margin_sides)

5.大小: [http://www.w3schools.com/css/tryit.asp?filename=trycss\_dim\_height\_width](http://www.w3schools.com/css/tryit.asp?filename=trycss_dim_height_width)

6.字體操作

[http://www.w3schools.com/css/css\_text.asp](http://www.w3schools.com/css/css_text.asp)

[http://www.w3schools.com/css/css\_font.asp](http://www.w3schools.com/css/css_font.asp)

7.表格:

Table:[http://www.w3schools.com/css/css\_table.asp](http://www.w3schools.com/css/css_table.asp)

8.元素顯示方式 [http://www.w3schools.com/css/css\_display\_visibility.asp](http://www.w3schools.com/css/css_display_visibility.asp)

```text
display: none;隱藏消失

visibility: hidden;隱藏但仍占位
```

9.位置屬性

position:[http://www.w3schools.com/css/css\_positioning.asp](http://www.w3schools.com/css/css_positioning.asp)

```text
static:預設屬性

relative:預設屬性加上top, right, bottom, and left

fix:固定住，不受捲動網頁影響

absolute:relative跳出layout
```

