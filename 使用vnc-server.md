圖形化的SSH介面

# 安裝
首先我們要在要連線的主機設定server

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

成功會出現如下
```
A VNC server is already running as :1
```

#連線
在來到我們要用來連線的client安裝

https://www.realvnc.com/download/vnc/

ip位置後面記得加上剛才啟動server的`:1`

如果用ＶＰＳ記得要去security group之類開啟port

#錯誤:

```
Xsession: unable to start X session --- no "/home/ubuntu/.xsession" file, no 
"/home/ubuntu/.Xsession" file, no session managers, no window managers, and no 
terminal emulators found; aborting.
```