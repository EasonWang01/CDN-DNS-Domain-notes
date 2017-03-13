#註冊域名信箱

1.首先要申請一個網域名稱

2.到zoho網站  https://home.zoho.com/ 點選Mail

3.他有三種認證方法，我們使用TXT方法

```
到你的DNS服務商新增TXT紀錄即可，如果有用godaddy並使用cloudflare DNS等服務則是到他們的服務添加，也就是到最前面的DNS reach點
```

![](/assets/螢幕快照 2017-03-13 下午2.24.04.png)


之後即可認證

![](/assets/asdasdads.png)

然後設定你的信箱使用者

![](/assets/螢幕快照 2017-03-13 下午2.20.50.png)

之後要加入兩個 MX 紀錄

![](/assets/螢幕快照 2017-03-13 下午2.24.01.png)

完成後類似如下(這裡使用cloudflare的服務所以用它來示範，但其他服務商也是類似的)

![](/assets/螢幕快照 2017-03-13 下午2.30.01.png)


之後要來設定有關安全性相關的ＳＰＦ與ＤＫＩＭ


![](/assets/螢幕快照 2017-03-13 下午2.42.00.png)

 #### #SPF照著左側直接新增TXT即可

#### #DKIM要先點下方按鈕`Proceed to Configure DKIM`

詳細可參考此篇 https://www.zoho.com/mail/help/adminconsole/dkim-configuration.html#alink3


點選`Proceed to Configure DKIM`按鈕後點`Add selector`之後輸入名稱後會產生一個hash

![](/assets/螢幕快照 2017-03-13 下午2.43.47.png)

把他複製後加到TXT，name要設定為類似如下

```
<selector>._domainkey.<yourdomainname.com>

但有些DNS商會自動縮寫為如下，兩者都可

<selector>._domainkey

```

完成後類似如下圖

![](/assets/螢幕快照 2017-03-13 下午2.54.00.png)


之後即可回到剛才點選verify

![](/assets/螢幕快照 2017-03-13 下午2.50.29.png)

成功啟用DKIM會出現如下圖之綠燈

![](/assets/螢幕快照 2017-03-13 下午2.50.56.png)


之後即可進入主控台，左下方的SPF說還沒configure其實是他們的bug，官方告知大該要等一下才會消失

![](/assets/螢幕快照 2017-03-13 下午3.12.21.png)



#最後即可到以下地址查看信箱與寄信!


https://mail.zoho.com/zm/#mail/folder/inbox