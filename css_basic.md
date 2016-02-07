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