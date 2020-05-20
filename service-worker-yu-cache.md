# Service worker 與 Cache

[https://developers.google.com/web/ilt/pwa/caching-files-with-service-worker](https://developers.google.com/web/ilt/pwa/caching-files-with-service-worker)

使用Service worker來快取頁面時，不會被network 的 disable cache與瀏覽器強制重整影響到，頁面還是會被快取著。

要用如下指令

```javascript
caches.keys().then(function(names) {
    for (let name of names)
    caches.delete(name);
});
```

[https://stackoverflow.com/a/46597656](https://stackoverflow.com/a/46597656)

> 例如create-react-app

