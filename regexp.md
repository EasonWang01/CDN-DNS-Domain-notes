# Regexp

有時會看到`/<%([\s\S]+?)%>/g;`

大寫S [http://www.w3schools.com/jsref/jsref\_regexp\_whitespace\_non.asp](http://www.w3schools.com/jsref/jsref_regexp_whitespace_non.asp)

小寫S [http://www.w3schools.com/jsref/jsref\_regexp\_whitespace.asp](http://www.w3schools.com/jsref/jsref_regexp_whitespace.asp)

搜尋中文與英文字母

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

## test

