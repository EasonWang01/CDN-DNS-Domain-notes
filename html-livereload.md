# LiveReload

讓code更新後不用手動刷新瀏覽器



# \#使用方法

1.

```
npm install -g livereload
```

2.把以下這段加到html

```js
<script>
  document.write('<script src="http://' + (location.host || 'localhost').split(':')[0] +
  ':35729/livereload.js?snipver=1"></' + 'script>')
</script>
```

3.在command line輸入

```
livereload <html的路徑>
```

4.然後開啟瀏覽器輸入`localhost:35729 `

