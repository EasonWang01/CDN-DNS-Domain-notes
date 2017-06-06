[https://www.mailgun.com/](https://www.mailgun.com/)

其服務也是很優惠，到網站照著步驟加入MX與TXT然後按下下圖按鈕即可認證

![](/assets/52.png)

最下面cname部分之前試都無法認證，還需要研究一下，但不影響發送郵件

\#避免垃圾郵件

1.domain跟發送郵件的from要相同

2.郵件內容跟主題要有內容

3.提供unsubscribe按鈕

4.確認有加入DKIM與SPF



# \#接收郵件

先點選Route，然後設定要將你的domain接收的郵件導向哪個信箱\(這邊導向jason40115@hotmail.com為例子\)

![](/assets/2.png)

然後設定

![](/assets/3.png)之後寫信給\`admin@rent.sakatu.com\`隔一下子就可以在jason40115@hotmail.com收到

