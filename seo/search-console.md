# search console

用來登記你的網址並追蹤

## \#1.到以下網址新增網域

[https://www.google.com/webmasters/verification/home?hl=en](https://www.google.com/webmasters/verification/home?hl=en)

## \#2.將google給你的html檔案放到server，nginx配置如下

\(記得先把檔案路徑要寫好，try\_files是相對於root路徑\)

```text
  location /google7d69523ad2a54000.html{
    root /home/ubuntu/abc/build;
    try_files /../../googlesearch/google7d69523ad2a54000.html /test.html;
  }
```

## \#3.之後即可點選search console的認證連結

