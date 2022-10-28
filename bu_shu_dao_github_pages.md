# 部屬到github pages

## 部屬到github pages

```
分為使用者網站和專案網站

使用者網站一個使用者只能有一個，Repo名稱必須取為<username>.github.io
專案網站可以有多個，Repo名稱可以隨意，但必須部屬在gh-pages branch下
```

1.下載git

2.申請github帳號

3.開新的repo，名稱打上 username.github.io

4.在你的網頁資料夾點右鍵 git bash here

5.git init

6.git remote add origin + 你的repo位置

7.git add .

8.git commit -m "first commit"

9.git push origin master 或是 git push remote origin +master

10.前往[http://username.github.io/](http://username.github.io/)

> P.S. 入口文件名稱為index.html
>
> 如果輸入[http://username.github.io/](http://username.github.io/)之後沒有到網站的話改為：[http://username.github.io/](http://username.github.io/)index.html
>
> 如果不想加/index.html的話可以刪除repo，然後重建後先用theme的方式創建github page，之後再把內容強制push即可。
>
> 因為有時會有bug，造成一定要加/index.html

## 如果想要部屬多個網站呢

新開一個repo，在push時push到gh-pages branch.

其他與上面相同。

```
git branch gh-pages
```

```
git push origin gh-pages
```

之後前往網址username.github.io/repo-name

### 如仍然沒顯示

可進入github project內點選setting，在option選項下方點選automatic generator

## 如何切換帳號部署

（例如我們想新開一個帳號放網頁，但是在cmd沒辦法push，因為ssh key不同的關係）

解決方法:

1.通常push會找預設的ssh key所以我們要新增一個ssh key

2.記得remote add 的是ssh的url不是https

> 記得要先啟動ssh agent => eval "$(ssh-agent -s)

[https://gist.github.com/jexchan/2351996](https://gist.github.com/jexchan/2351996)

[https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/)

3.最後把key加入帳號的setting裡的ssh key即可push

#### 或是

直接把密碼寫進git url

```
git remote set-url origin https://使用者名稱:密碼@github.com/使用者名稱/專案
```

## 將同帳號多個Repo加上cloudflare

cloudflare

```
cname  subdomain1  username.github.io
cname  subdomain2  username.github.io
```

然後再Repo裡面點選setting

然後下拉選擇Custom domain

輸入你的subdomain.domain即可

## 使用Create react app部屬

[https://github.com/facebook/create-react-app/blob/master/packages/react-scripts/template/README.md#github-pages](https://github.com/facebook/create-react-app/blob/master/packages/react-scripts/template/README.md#github-pages)

> 記得要先git init 並且 設定好remote url
>
> 建議加上帳號密碼
>
> e.g.
>
> ```
> git remote set-url origin https://username:password@github.com/<username>/<reponame>
> ```

1.安裝gh-pages模組`yarn add gh-pages`

2.package.json加上

> 以下如果是部屬到專案網站( gh-pages branch )而非使用者網站(username.github.io)的話，不用加`-b master`

```
  "scripts": {
    "predeploy": "npm run build",
    "deploy": "gh-pages -b master -d build",
    ....
  }
```

3.設定homepage

e.g.

```
"homepage": "http://使用者名稱.github.io/專案名稱"
```

> 如果是使用者頁面則github.io後面不用加專案名稱35 \`npm run bu

4.npm run deploy

> 記得先npm run build
>
> 如果出現gh-pages branch 或 master branch already exist錯誤的話，刪除`node_module/gh-pages/.caches` 即可
>
> 記得depoly後要重新到github setting設定自訂網域。

[https://github.com/gitname/react-gh-pages](https://github.com/gitname/react-gh-pages)

### 如果包含 react-router

重新整理後通常會變 404 可以參考

{% embed url="https://github.com/rafgraph/spa-github-pages" %}

1. 新增一個 404.html 到 public 目錄

```markup
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Single Page Apps for GitHub Pages</title>
    <script type="text/javascript">
      // Single Page Apps for GitHub Pages
      // MIT License
      // https://github.com/rafgraph/spa-github-pages
      // This script takes the current url and converts the path and query
      // string into just a query string, and then redirects the browser
      // to the new url with only a query string and hash fragment,
      // e.g. https://www.foo.tld/one/two?a=b&c=d#qwe, becomes
      // https://www.foo.tld/?/one/two&a=b~and~c=d#qwe
      // Note: this 404.html file must be at least 512 bytes for it to work
      // with Internet Explorer (it is currently > 512 bytes)

      // If you're creating a Project Pages site and NOT using a custom domain,
      // then set pathSegmentsToKeep to 1 (enterprise users may need to set it to > 1).
      // This way the code will only replace the route part of the path, and not
      // the real directory in which the app resides, for example:
      // https://username.github.io/repo-name/one/two?a=b&c=d#qwe becomes
      // https://username.github.io/repo-name/?/one/two&a=b~and~c=d#qwe
      // Otherwise, leave pathSegmentsToKeep as 0.
      var pathSegmentsToKeep = 0;

      var l = window.location;
      l.replace(
        l.protocol + '//' + l.hostname + (l.port ? ':' + l.port : '') +
        l.pathname.split('/').slice(0, 1 + pathSegmentsToKeep).join('/') + '/?/' +
        l.pathname.slice(1).split('/').slice(pathSegmentsToKeep).join('/').replace(/&/g, '~and~') +
        (l.search ? '&' + l.search.slice(1).replace(/&/g, '~and~') : '') +
        l.hash
      );

    </script>
  </head>
  <body>
  </body>
</html>
```

2\. 新增以下 script 到 index.html 的 \<head> 裡面

```javascript
    <script type="text/javascript">
      // Single Page Apps for GitHub Pages
      // MIT License
      // https://github.com/rafgraph/spa-github-pages
      // This script checks to see if a redirect is present in the query string,
      // converts it back into the correct url and adds it to the
      // browser's history using window.history.replaceState(...),
      // which won't cause the browser to attempt to load the new url.
      // When the single page app is loaded further down in this file,
      // the correct url will be waiting in the browser's history for
      // the single page app to route accordingly.
      (function(l) {
        if (l.search[1] === '/' ) {
          var decoded = l.search.slice(1).split('&').map(function(s) { 
            return s.replace(/~and~/g, '&')
          }).join('?');
          window.history.replaceState(null, null,
              l.pathname.slice(0, -1) + decoded + l.hash
          );
        }
      }(window.location))
    </script>
```

之後 yarn build 後 cd build && serve 即可測試，重新整理後不會找不到路徑了

## github.io/<路徑> 下的路徑

[https://github.com/facebook/create-react-app/issues/1765](https://github.com/facebook/create-react-app/issues/1765)
