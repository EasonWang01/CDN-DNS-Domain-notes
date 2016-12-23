#介紹

他會幫你在你的網站server前再加一道防護，你可以去你的DNS provider中把ns(name server)改成cloudflare提供的兩個位置即可

#使用

照著官網步驟即可，但注意在搜尋DNS設定時可能有些不會找到，要自己加上去

#設定SSL

https://www.cloudflare.com/a/crypto/sakatu.com#ssl

進入dashboard後點選Crypto之後ssl有三個選項

```
Full

Full(Strict)

Flexible
```
Full:會自動偵測你的主機server內是否有設定SSL證書，如果有他會幫你替換為他們的，如果沒有他也會幫你加上

Full(Strict):必須要有合格的SSL證書才能

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






