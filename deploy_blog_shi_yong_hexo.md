# Deploy Blog 使用 Hexo

Hexo 是一個快速產生Blog的模板

藉著terminal的指令快速部署

下面為Hexo部署到github pages範例


#1.首先照著如下安裝

https://hexo.io/zh-tw/

#2.之後成功可在本機跑起來後即可試著部署到github

#3.開啟一個repo 點選 setting 之後建立 github pages 

#4.到hexo 專案根目錄 `_config.yml` 加入部署指令

```
deploy:
  type: git
  repo: https://github.com/EasonWang01/blog.git
  branch: gh-pages
```

#5.注意：如果是使用github.io後面附帶repo name的(也就是gh-pages)
需加入如下在config

url及root需更改

```
# URL
## If your site is put in a subdirectory, set url as 'http://yoursite.com/child' and root as '/child/'
url: http://yoursite.com/blog
root: /blog
```
即可輸入
```
hexo deploy
```
部署

#6.重新部署

```
先刪除.deploy_git 目錄與  public 目錄
```
之後輸入
```
hexo deploy
```

#7.在別的地方develop
先把原本hexo init push到一個repo，之後把他拉下來即可