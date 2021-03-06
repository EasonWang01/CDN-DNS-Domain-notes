# Regexp

有時會看到`/<%([\s\S]+?)%>/g;`

大寫S [http://www.w3schools.com/jsref/jsref\_regexp\_whitespace\_non.asp](http://www.w3schools.com/jsref/jsref_regexp_whitespace_non.asp)

小寫S [http://www.w3schools.com/jsref/jsref\_regexp\_whitespace.asp](http://www.w3schools.com/jsref/jsref_regexp_whitespace.asp)

## 搜尋中文與英文字母

```text
var re = /\w+|[\u0800-\u9fa5]+/g
```

## 變數加上表達式

```text
const findPropsReg = new RegExp(`${fileName}.propTypes(.|\n)+.+`, 'g')
```

> 直接寫表達式即可 不用 \

## Match所有字元包含換行

> 如果單純用g，則是會match後繼續往下找，但假設match後要用表達式找下一行則要用如下\n

```text
(.|\n)+
```

## Match 直到某個字

```javascript
(.|\n)+?(?=到某個字)
```

{% embed url="https://stackoverflow.com/questions/7124778/how-to-match-anything-up-until-this-sequence-of-characters-in-a-regular-expres" %}

## exec vs match

1. 用Match 的話就會幫你找出所有匹配的部分並回傳 array，如果用 exec就算加上 g還是要放在loop內
2. exec 如果regexp內有 \(\) 的話 裡面匹配的部分會另外顯示在回傳值第二個參數

```javascript
var myArray = /d(b+)d/g.exec('cdbbdbsbz'); 
// similar to "cdbbdbsbz".match(/d(b+)d/g); however,
    // the latter outputs Array [ "dbbd" ], while 
    // /d(b+)d/g.exec('cdbbdbsbz') outputs Array [ "dbbd", "bb" ].
```

{% embed url="https://stackoverflow.com/questions/9214754/what-is-the-difference-between-regexp-s-exec-function-and-string-s-match-fun" %}

## Invalid regular expression: /\({/: Unterminated group

當我們使用 \({ 之類必須要用 \ 跳脫

但 new Regexp 如果第一個參數是 string 要用兩個 \

```javascript
"ddf vd ({ dd })".match(new RegExp(/\(\{/, 'g'))
// ["({"]
```

以及

```javascript
"ddf vd ({ dd })".match(new RegExp("\\(\\{", 'g'))
```

