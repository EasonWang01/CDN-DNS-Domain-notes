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

---

# ＃如何切換帳號部署

（例如我們想新開一個帳號放網頁，但是在cmd沒辦法push，因為ssh key不同的關係）

解決方法:

1.通常push會找預設的ssh key所以我們要新增一個ssh key

2.記得remote add 的是ssh的url不是https

> 記得要先啟動ssh agent       =&gt;   eval "$\(ssh-agent -s\)

[https://gist.github.com/jexchan/2351996](https://gist.github.com/jexchan/2351996)

[https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/)

3.最後把key加入帳號的setting裡的ssh key即可push

# 或是

直接把密碼寫進git url

```
git remote set-url origin https://使用者名稱:密碼@github.com/使用者名稱/使用者名稱.github.io.git
```

# 將同帳號多個Repo加上cloudflare

cloudflare

```
cname  subdomain1  username.github.io
cname  subdomain2  username.github.io
```

然後再Repo裡面點選setting

然後下拉選擇Custom domain

輸入你的subdomain.domain即可

