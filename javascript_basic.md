# Javascript basic

## Javascript basic

## **如何使用**

1.直接在HTML內加入

`<script> </script>`

2.外部檔案

`<script src=""> </script>`

## **選取**

1.選取id

```text
document.getElementById("")
```

2.選取tag

```text
document.getElementsByTagName("")
```

3.選取class

```text
document.getElementsByClassName("")
```

## **型別**

```text
var length = 16;                               // Number
var lastName = "Johnson";                      // String
var cars = ["Saab", "Volvo", "BMW"];           // Array
var x = {firstName:"John", lastName:"Doe"};    // Object
```

查詢型別

```text
typeof "john"
```

[http://www.w3schools.com/js/tryit.asp?filename=tryjs\_datatypes\_typeof](http://www.w3schools.com/js/tryit.asp?filename=tryjs_datatypes_typeof)

## 定義物件後可以使用陣列方式存取

[http://www.w3schools.com/js/tryit.asp?filename=tryjs\_objects\_properties\_2](http://www.w3schools.com/js/tryit.asp?filename=tryjs_objects_properties_2)

## Scope

1.Local

區域變數只存在function內\(以var 開頭\)

2.Global

在function外宣告均為全域變數，在function內不以var 宣告亦為global

## Array

1.宣告

```text
var as=[];

//or

as = new Array()
```

但以下這兩個為不同的意思

```text
    e = [3]             // e.length == 1, e[0] == 3
    f = new Array(3),   // f.length == 3, f[0] == undefined
```

2.操作array [http://www.w3schools.com/js/js\_array\_methods.asp](http://www.w3schools.com/js/js_array_methods.asp)

## 比較與表達

1.比較 [http://www.w3schools.com/js/js\_comparisons.asp](http://www.w3schools.com/js/js_comparisons.asp)

2.表達

1

```text
if () {

}
```

2

```text
if(){

}else{

}
```

3

```text
if (time < 10) {
    greeting = "Good morning";
} else if (time < 20) {
    greeting = "Good day";
} else {
    greeting = "Good evening";
}
```

4

為什麼不放三個if就好?

```text
//因為第一個if跑完他不會停，而會繼續往下跑其他if找是否有其他符合

ex:上例的time等於5
```

5.

```text
switch(expression) {
    case n:
        code block
        break;
    case n:
        code block
        break;
    default: //there is no case match
        default code block
}
```

6.

```text
for (i = 0; i < 5; i++) {
    text += "The number is " + i + "<br>";
}
```

7.

```text
var person = {fname:"John", lname:"Doe", age:25}; 

var text = "";
var x;
for (x in person) {
    text += person[x];
}
```

8.

```text
while (i < 10) {
    text += "The number is " + i;
    i++;
}
```

9.

```text
do {
    code block to be executed
}
while (condition);
```

加上do的差別在於他會先執行一次，再檢查

## Regular Expression

1.用途

When you search for data in a text, you can use this search pattern to describe what you are searching for.

簡言之:搜尋要找的字 RegExp

格式: / /

查找範圍: / /後可加g 或i或m 如/ /g / /gi g為找到一次後會繼續往後找，i為不分大小寫,m為找多行

查找字串 /as/g 每找到as就會印出as

查找字元 /\[as\]/g 找到a或s會印出，一次只找一個字，//g 代表查找所有不是a~z的字

查找特殊的字 /\b/g 查找所有數字，也是以單個字來查找

查找的附帶條件

* * ? 等等，記得是要放在方括號外面，如果有多個附帶條件可用括號刮起來

    ex:/&lt;%\(+\)?%&gt;/g

RegExp為一個object 其擁有的屬性如下

global RegExp 对象是否具有标志 g。 ignoreCase RegExp 对象是否具有标志 i。  
lastIndex 一个整数，标示开始下一次匹配的字符位置。 multiline RegExp 对象是否具有标志 m。  
source 正则表达式的源文本。

RegExp的 方法

compile 编译正则表达式。  
exec 检索字符串中指定的值。返回找到的值，并确定其位置。 test 检索字符串中指定的值。返回 true 或 false。

較常用的為exec，可用console出其反為物件\(在chrome顯示為陣列，但其要使用物件存取\)

ex:

```text
var tpl = '<p>Hello, my name is <%name%>. I\'m <%age%> years old.</p>'

var re = /<%([^%>]+)?%>/g,

match;

var match = re.exec(tpl);

console.log(match);
結果:
["<%name%>", "name", index: 21, input: "<p>Hello, my name is <%name%>. I'm <%age%> years old.</p>"]
```

[http://www.w3schools.com/js/js\_regexp.asp](http://www.w3schools.com/js/js_regexp.asp)

## JSON

[http://www.w3schools.com/js/js\_json.asp](http://www.w3schools.com/js/js_json.asp)

