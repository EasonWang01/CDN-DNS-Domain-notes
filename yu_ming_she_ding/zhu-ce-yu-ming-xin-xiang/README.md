# 註冊域名信箱

## 註冊域名信箱

1.首先要申請一個網域名稱

2.到zoho網站 [https://home.zoho.com/](https://home.zoho.com/) 點選Mail ，之後選擇免費方案然後註冊帳號

之後就會進入他的教學步驟頁面

3.他有三種認證方法，我們使用TXT方法

```text
到你的DNS服務商新增TXT紀錄即可，如果有用godaddy並使用cloudflare DNS等服務則是到他們的服務添加，也就是到最前面的DNS reach點
```

![](../../.gitbook/assets/螢幕快照%202017-03-13%20下午2.24.04.png)

之後即可認證

![](../../.gitbook/assets/asdasdads.png)

然後設定你的信箱使用者

![](../../.gitbook/assets/螢幕快照%202017-03-13%20下午2.20.50.png)

之後要加入兩個 MX 紀錄

![](../../.gitbook/assets/螢幕快照%202017-03-13%20下午2.24.01.png)

完成後類似如下\(這裡使用cloudflare的服務所以用它來示範，但其他服務商也是類似的\)

![](../../.gitbook/assets/螢幕快照%202017-03-13%20下午2.30.01.png)

之後要來設定有關安全性相關的ＳＰＦ與ＤＫＩＭ

![](../../.gitbook/assets/螢幕快照%202017-03-13%20下午2.42.00.png)

### \#SPF照著左側直接新增TXT即可

### \#DKIM要先點下方按鈕`Proceed to Configure DKIM`

詳細可參考此篇 [https://www.zoho.com/mail/help/adminconsole/dkim-configuration.html\#alink3](https://www.zoho.com/mail/help/adminconsole/dkim-configuration.html#alink3)

點選`Proceed to Configure DKIM`按鈕後點`Add selector`之後輸入名稱後會產生一個hash

![](../../.gitbook/assets/螢幕快照%202017-03-13%20下午2.43.47.png)

把他複製後加到TXT，name要設定為類似如下

```text
<selector>._domainkey.<yourdomainname.com>

但有些DNS商會自動縮寫為如下，兩者都可

<selector>._domainkey
```

完成後類似如下圖

![](../../.gitbook/assets/螢幕快照%202017-03-13%20下午2.54.00.png)

之後即可回到剛才點選verify

![](../../.gitbook/assets/螢幕快照%202017-03-13%20下午2.50.29.png)

成功啟用DKIM會出現如下圖之綠燈

![](../../.gitbook/assets/螢幕快照%202017-03-13%20下午2.50.56.png)

之後即可進入主控台，左下方的SPF說還沒configure其實是他們的bug，官方告知大該要等一下才會消失

![](../../.gitbook/assets/螢幕快照%202017-03-13%20下午3.12.21.png)

## 最後即可到以下地址查看信箱與寄信!

[https://mail.zoho.com/zm/\#mail/folder/inbox](https://mail.zoho.com/zm/#mail/folder/inbox)

## 更改顯示的名字

寄送過去後再地址前的名字可更改

點選左上方的`setting`之後拉到下方點選`Send mail as`

![](../../.gitbook/assets/螢幕快照%202017-03-13%20下午3.27.45.png)

之後輸入名稱點選更新即可

> 注意，如果名稱和mail開頭的名稱相同可能會沒改變，所以可改為其他

![](../../.gitbook/assets/螢幕快照%202017-03-13%20下午3.25.14.png)

把上面名稱改為info，之後寄信後即可看到更改了名稱!

![](../../.gitbook/assets/螢幕快照%202017-03-13%20下午3.33.18.png)

新增使用者

[https://mailadmin.zoho.com/cpanel/index.do\#userdetails](https://mailadmin.zoho.com/cpanel/index.do#userdetails)

可參考之中文文章:[https://sofree.cc/zoho-custom-domain-mail/](https://sofree.cc/zoho-custom-domain-mail/)

## 注意事項:

如果使用他的雙因素認證，會發生使用程式寄信時無法驗證問題

