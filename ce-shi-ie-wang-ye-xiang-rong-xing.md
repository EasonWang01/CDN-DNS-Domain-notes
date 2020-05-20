# 測試 IE 網頁相容性

> 使用 Mac

1.安裝VirtualBox

2.下載 win 10

1. 按照如下網頁設定

[https://medium.com/oceanize-geeks/install-windows-10-7-on-mac-using-virtualbox-109be82b6037](https://medium.com/oceanize-geeks/install-windows-10-7-on-mac-using-virtualbox-109be82b6037)

4.在virtualBox 的 localhost IP 為 10.0.2.2

## 如果是自訂網域

> EX: localhost 使用自訂的網域 ccc.com

1.更改 host file: [https://stackoverflow.com/a/22723681](https://stackoverflow.com/a/22723681)

2.引入憑證：

```text
1. 進入主控台(control panel)
2. 網際網路 => 內容 => 憑證 => 受信任的根憑證授權單位
3. 點選匯入，然後選自己簽發的 crt 憑證
```

