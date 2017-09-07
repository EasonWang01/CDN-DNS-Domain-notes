# 部屬到github pages

1.下載git

2.申請github帳號

3.開新的repo，名稱打上   username.github.io

4.在你的網頁資料夾點右鍵 git bash here

5.git init

6.git remote add origin + 你的repo位置

7.git add .

8.git commit -m "first commit"

9.git push origin master  或是 git push remote origin +master

10.前往[http://username.github.io/](http://username.github.io/)

ps:入口文件名稱為index.html

# 如果想要部屬多個網站呢

新開一個repo，在push時push到gh-pages branch.

其他與上面相同，

commit後，最後面改為

```
git branch gh-pages
```

```
git push origin gh-pages
```

之後前往網址username.github.io/repo-name

## 如仍然沒顯示

可進入github project內點選setting，在option選項下方點選automatic generator







# 如何切換帳號部署

通常push會找預設的ssh key所以我們要新增一個ssh key

記得remote add 的是ssh的url



