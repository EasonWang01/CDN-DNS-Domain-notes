# 域名設定

## 1.以下用AWS EC2 與Goddy為例

致電godaddy後他們的客服都不太能解決問題，一開始我看網路上教導說使用AWS Route53服務，但注意，此不包含在Free tire 需另外收費，但還是稍微講解route53的dns設定，當初參考此篇[https://www.quora.com/How-do-I-route-my-GoDaddy-domain-name-to-my-Amazon-EC2-web-server的第一個回答，但他的回答還少了兩點，就是還要再route53加上兩筆A](https://www.quora.com/How-do-I-route-my-GoDaddy-domain-name-to-my-Amazon-EC2-web-server的第一個回答，但他的回答還少了兩點，就是還要再route53加上兩筆A) record 指向你的example.com和www.example.com，才算完成．

> 但要如何用免費的EC2不用route53指向我們在godaddy買的網域呢？

因為一開始EC2給你的都是浮動的IP也就是你把機器重開後IP位置就會改變，所以我們要先申請Elastic IP，一樣在EC2的console那可申請，之後你的EC2的ssh與public ip會自動改為你新申請好的Elastic IP之後再到Godaddy點選域名伺服器，但注意要選`使用預設名稱伺服器`，之後會發現上面多出一個框框  
![](螢幕快照 2016-11-28 下午12.06.26.png)

之前一直很納悶為什麼都沒有出現這個，直到我把`域名伺服器`選項從自訂改為預設後才出現，之後就把A記錄改為你的EC2 IP 然後再把CNAME 的 WWW改為 你的域名即可，  
即為`@`

有時找不到設定的頁面，因為你的域名伺服器改過，這時要聯繫客服

\(2017/2/14\)  
先點擊右上帳號的我的產品=&gt;往下拉到網域部分，點擊管理，然後點擊網域名稱

![](/assets/螢幕快照 2017-02-14 上午11.58.57.png)

之後點擊DNS區域檔案\(如果沒出現請聯繫客服\)

![](/assets/螢幕快照 2017-02-14 上午11.58.35.png)

接著新增把A紀錄的IP更改為EC2的即可

域名伺服器不用更改

# 子網域\(subDomain\)

類似 info.sakatu.com

在域名前加上其他名字

可設定類似如下

```
類型    名稱    值    TTL    動作
A    @    52.193.84.195    1 小時    
A    info    52.198.155.128    1 小時
```

雖然有些教學網站說要設CNAME但在此設定一個A紀錄即可  
因為cname是給轉址ＤＮＳ\(http....\)之類的非ip使用

[https://tw.godaddy.com/help/ip-4080](https://tw.godaddy.com/help/ip-4080)

# 使用GITHUB pages 搭配子網域

讓使用者輸入class.sakatu.com 可轉址到easonwang01.github.io

在DNS provider\(ex:godaddy\) 設定

```
類型    名稱    值    TTL

CNAME    class    easonwang01.github.io    1 小時
```

接著記得到你的github pages設定轉址位址

![](/assets/螢幕快照 2017-07-14 下午10.06.51.png)

> 如果在&lt;Username.github.io&gt;的repo下設定網域一般來說後面加上/repo就會跑到那個repo page，但如果你的那個repo也有設好custom domain則它會自動幫你轉換url

如果想要使用自訂的subdomain加上https服務呢

```
可使用cloudflare的服務，原理為在進入該網站前先進入cloudflare的proxy
```

> 注意:如果想把gh-page之pages對應不同domain或subdomain比較不可行

因為CNAME的設定只可以放domain不可加上`/`但gh-pages對應到domain後一定會自動加上`/`，所以造成找不到頁面

而只在和對應使用者名稱的github pages加上domain名稱的話其他gh-pages repo會自動讓轉址後的domain對應`/` ex:sakatu.com/class

#### 瀏覽器redirect快取移除

1.開啟devtool disable cache 然後開著devtool再到該網站即可

2.在網址後加上`//`即可

ex:

```
https://easonwang01.github.io/classPPT

改為

https://easonwang01.github.io/classPPT//
```



