# Regexp

有時會看到`/<%([\s\S]+?)%>/g;`

大寫S
http://www.w3schools.com/jsref/jsref_regexp_whitespace_non.asp

小寫S
http://www.w3schools.com/jsref/jsref_regexp_whitespace.asp



搜尋中文與英文字母

```
var re = /\w+|[\u0800-\u9fa5]+/g
```