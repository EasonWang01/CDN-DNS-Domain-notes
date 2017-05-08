# cloudflare設定
![](/assets/螢幕快照 2017-05-08 下午5.39.42.png)

nginx config

![](/assets/螢幕快照 2017-05-08 下午6.01.25.png)

![](/assets/螢幕快照 2017-05-08 下午6.11.30.png)



# 預設domain

這樣子輸入sakatu.com即可另外到一個網站，有時要等一下才會生效，而www則跟上面subdomain設法一樣，但要等一下，有時不行可能是瀏覽器快取，換個瀏覽器試試
![](/assets/螢幕快照 2017-05-08 下午11.29.52.png)

![](/assets/s.png)


如果改完沒反應可先去chrome的設定清空瀏覽資料(時間記得設全部)
`cmd+shift+del`
![](/assets/螢幕快照 2017-05-08 下午11.48.54.png)


如果清完後輸入網址還是無法，可以清空電腦dns

(For mac)
```
sudo killall -HUP mDNSResponder
```
http://osxdaily.com/2008/03/21/how-to-flush-your-dns-cache-in-mac-os-x/