# ngrok與localtunnel

當我們需要將在NAT後面的Server提供給別人連線時，可以用此種proxy服務

1.ngrok

[https://ngrok.com/](https://ngrok.com/)

> 如果要subdomain要付費，可考慮用localtunnel

2.localtunnel

```text
 npm install -g localtunnel
```

```text
$ lt --port 82 --subdomain haha
your url is: https://haha.localtunnel.me
```

