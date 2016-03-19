# Less

線上編輯器:
http://winless.org/online-less-compiler


##安裝
NPM
```
npm install less -g
```
新建一個檔案名為test.less
```
@base: #f938ab;

.box-shadow(@style, @c) when (iscolor(@c)) {
  -webkit-box-shadow: @style @c;
  box-shadow:         @style @c;
}
.box-shadow(@style, @alpha: 50%) when (isnumber(@alpha)) {
  .box-shadow(@style, rgba(0, 0, 0, @alpha));
}
.box {
  color: saturate(@base, 5%);
  border-color: lighten(@base, 30%);
  div { .box-shadow(0 0 5px, 30%) }
}
```
進行編譯
```
lessc test.less test.css
```

CDN
```
<script src="//cdnjs.cloudflare.com/ajax/libs/less.js/2.5.3/less.min.js"></script>
```


參考至:

中文:http://less.bootcss.com/features/#features-overview-feature
英文:http://lesscss.org/
