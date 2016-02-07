# CSS basic

**如何使用**

1.直接在HTML內加入

```<style> </style>  ```

2.外部檔案

```<link rel="stylesheet" type="text/css" href="mystyle.css">```





**
CSS選取**

只有```<p>```且class為center會被影響
```
p.center {
    text-align: center;
    color: red;
}
```


選擇h1和h2及p用逗號分隔

```
h1, h2, p {
    text-align: center;
    color: red;
}
```