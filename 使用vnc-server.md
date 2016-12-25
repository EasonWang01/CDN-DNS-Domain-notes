圖形化的SSH介面

```
sudo apt-get install tightvncserver 
```

```
sudo tightvncserver
```

```
輸入n
```

啟動
```
vncserver :1
```
如出現錯誤可把1換成其他數字，如出現locale沒設定等問題可到
```
/etc/default/locale
```
加上
```
LC_ALL=en_US.UTF-8
LANG=en_US.UTF-8
```
即可