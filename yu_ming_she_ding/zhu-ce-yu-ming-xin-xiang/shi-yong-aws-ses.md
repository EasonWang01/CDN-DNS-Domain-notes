# 使用AWS SES

## \#進入SES的頁面先註冊一個domain

![](../../.gitbook/assets/01.png)

然後點domain然後下載CSV

![](../../.gitbook/assets/02.png)

## 之後填入cloudflare或其他網域供應商

![](../../.gitbook/assets/23.png)

## 之後要記得跟AWS support  申請改為SES production模式

然後他回覆你完成

![](../../.gitbook/assets/32.png)

最後就可以試著寄送mail\(這邊的@之前使用者\)打什麼都可以，不像ZOHO要先註冊使用者

![](../../.gitbook/assets/42.png)

## \#有關mail from domain

[https://aws.amazon.com/blogs/ses/amazon-ses-now-supports-custom-mail-from-domains/](https://aws.amazon.com/blogs/ses/amazon-ses-now-supports-custom-mail-from-domains/)

需要注意的是，以上這樣雖然可以從test按鈕發送信件，但使用nodemail或aws-sdk還是可能會跑到垃圾郵件

