# 介紹

他會幫你在你的網站server前再加一道防護，你可以去你的DNS provider中把ns\(name server\)改成cloudflare提供的兩個位置即可

> 在Cloudflare找到如下的兩個位置的Name Server![](/assets/Screen Shot 2018-08-15 at 5.49.00 PM.png)

Godaddy畫面如下，加入剛才的兩個位置![](/assets/Screen Shot 2018-08-15 at 5.50.05 PM.png)

# 使用

照著官網步驟即可，但注意在搜尋DNS設定時可能有些不會找到，要自己加上去

# 設定SSL

[https://support.cloudflare.com/hc/en-us/articles/200170416-What-do-the-SSL-options-mean-](https://support.cloudflare.com/hc/en-us/articles/200170416-What-do-the-SSL-options-mean-)

進入dashboard後點選Crypto之後ssl有三個選項

```
Full   會自動偵測你的主機server內是否有設定SSL證書,自行簽發的即可

Full(Strict)  必須要有合格機構簽發的SSL證書才能

Flexible  不用證書它會自動幫你上https
```

> 以nginx為例，如果使用Full則必須要加上以下才可以，不然監聽443 port時會無法存取網頁。
>
> 其中pem與key是從Crypto頁下方的`Origin Certificates` 產生。
>
> ```
> ssl on;
> ssl_certificate /usr/test/c.pem;
> ssl_certificate_key /usr/test/c.key;
> ```

如果用Flexible策略則在nginx不用加入以上。

官網說明

```
Flexible SSL: There is an encrypted connection between your website visitors and Cloudflare, but not from Cloudflare to your server.
You do not need an SSL certificate on your server
Visitors will see the SSL lock icon in their browser

Full SSL: Encrypts the connection between your website visitors and Cloudflare, and from Cloudflare to your server. The difference between Full and Full (Strict) is that Full (Strict) checks for a valid certificate on your origin server, whereas Full checks for any certificate.
You will need to have an SSL certificate on your server. However, Cloudflare will not attempt to validate the certificate (certificates may be self-signed)
Visitors will see the SSL lock icon in their browser

Full SSL (strict): Encrypts the connection between your website visitors and Cloudflare, and from Cloudflare to your server.
You will need to have a valid SSL certificate installed on your server signed by a publicly trusted certificate authority which has not expired and contains the domain name for the request (hostname).
Visitors will see the SSL lock icon in their browser
```

> 配置後要等一下才會生效\(可能到幾個小時\)，如果是讓github page 自訂域名後用https，設定要選Flexible

如果用nginx，則在nginx設置好80 port後在https網址即可看到

[https://xblockchain.co](https://xblockchain.co)

```
server {
        listen 80;
        server_name xblockchain.co;
        location / {
          proxy_pass http://localhost:8080;
        }
}
```

# 使用nginx搭配cloudflare配置https\(Origin certificate\)

> 先前是指在browser到cloudflare有加密SSL  這個是在cloudflare到你的server這段也加上SSL

[https://support.cloudflare.com/hc/en-us/articles/217471977](https://blog.cloudflare.com/cloudflare-ca-encryption-origin/)

先到[https://www.cloudflare.com/a/crypto](https://www.cloudflare.com/a/crypto)

然後往下拉點選\`Create certificate\`

![](/assets/螢幕快照 2017-05-30 下午2.29.02.png)

之後會給你pem跟key，複製起來存到主機中

之後加nginx的config加上

![](/assets/螢幕快照 2017-05-30 下午2.24.27.png)

# 目前範例配置

\(上面的A記錄為subdomain\)下面ＣＮＡＭＥ與MX,TXT為mail使用![](/assets/螢幕快照 2017-05-30 下午2.31.08.png)

Origin Certificate是我們想在Server上安裝時需要申請的，而Edge Certificate是cloudflare自動產生的，不用理會。

其中pem與key，pem下次點選網頁上Download按鈕還可以看到，但Key下一次點進來就看不到了。

# 注意:

有時使用Github page設定subdomain域名但還是找不到，換一個subdomain即可。

目前測試如果放兩個subdomain則會無法進入`https://`

E.g.

```
aa.cc.ni.com/
```

# 在Github page加上apex domain

（apex domain就是沒有subdomain的domain\)

> s在cloudflare的A記錄加上Github給的四個A記錄即可

[https://help.github.com/articles/setting-up-an-apex-domain/\#configuring-a-records-with-your-dns-provider](https://help.github.com/articles/setting-up-an-apex-domain/#configuring-a-records-with-your-dns-provider)

