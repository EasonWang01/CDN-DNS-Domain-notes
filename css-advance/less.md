# Less

線上編輯器: [http://winless.org/online-less-compiler](http://winless.org/online-less-compiler)

## 安裝

NPM

```text
npm install less -g
```

新建一個檔案名為test.less

```text
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

```text
lessc test.less test.css
```

CDN

```text
<script src="//cdnjs.cloudflare.com/ajax/libs/less.js/2.5.3/less.min.js"></script>
```

開啟線上編繹器進行練習

## 1.定義變數與使用四則運算

```text
@nice-blue: #5B83AD;
@light-blue: @nice-blue * 1.5;

#header {
  color: @light-blue;
}
```

## 2.使用Mixin

\(將 css規則直接塞入其他css規則中\)

```text
.bordered {
  border-top: dotted 1px black;
  border-bottom: solid 2px black;
}

#menu a {
  color: #111;
  .bordered;
}

.post a {
  color: red;
  .bordered;
}
```

## 3.更加清楚的子代規則

\(以下面為例，選取id header內所有 相關class\)

```text
#header {
  color: black;
}
#header .navigation {
  font-size: 12px;
}
#header .logo {
  width: 300px;
}
```

可寫成這樣

```text
#header {
  color: black;
  .navigation {
    font-size: 12px;
  }
  .logo {
    width: 300px;
  }
}
```

虛擬元素記得前面+&

```text
.clearfix {
  display: block;
  zoom: 1;

  &:after {
    content: " ";
    display: block;
    font-size: 0;
    height: 0;
    clear: both;
    visibility: hidden;
  }
}
```

## 4指定選擇器名稱的變數

```text
@mySelector: banner;

.@{mySelector} {
  font-weight: bold;
  line-height: 40px;
  margin: 0 auto;
}
```

參考至:

中文:[http://less.bootcss.com/features/\#features-overview-feature](http://less.bootcss.com/features/#features-overview-feature)

英文:[http://lesscss.org/](http://lesscss.org/)

