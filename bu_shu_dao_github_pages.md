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

10.前往http://username.github.io/

ps:入口文件名稱為index.html

#如果想要部屬多個網站呢

新開一個repo，在push時push到gh-pages branch.

之後前往網址username.github.io/<repo-name>