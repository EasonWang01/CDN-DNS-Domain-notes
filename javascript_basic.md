# Javascript basic



# **如何使用**



1.直接在HTML內加入

```<script> </script>  ```

2.外部檔案

```<script src=""> </script>```





# **選取**





1.選取id
```
document.getElementById("")
```
2.選取tag

```
document.getElementsByTagName("")
```
3.選取class
```
document.getElementsByClassName("")
```


# **型別**




```
var length = 16;                               // Number
var lastName = "Johnson";                      // String
var cars = ["Saab", "Volvo", "BMW"];           // Array
var x = {firstName:"John", lastName:"Doe"};    // Object
```
查詢型別
```
typeof "john"
```
http://www.w3schools.com/js/tryit.asp?filename=tryjs_datatypes_typeof



# 定義物件後可以使用陣列方式存取

http://www.w3schools.com/js/tryit.asp?filename=tryjs_objects_properties_2


# Scope

1.Local

區域變數只存在function內(以var 開頭)

2.Global

在function外宣告均為全域變數，在function內不以var 宣告亦為global


# Array

1.宣告
```
var as=[];

//or

as = new Array()


```
但以下這兩個為不同的意思
```
    e = [3]             // e.length == 1, e[0] == 3
    f = new Array(3),   // f.length == 3, f[0] == undefined

```

2.操作array
http://www.w3schools.com/js/js_array_methods.asp


# 比較與表達

1.比較
http://www.w3schools.com/js/js_comparisons.asp

2.表達

1
```
if () {
    
}
```
2

```
if(){

}else{

}
```

3
```
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
```
//因為第一個if跑完他不會停，而會繼續往下跑其他if找是否有其他符合

ex:上例的time等於5

```

5.

```
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
```
for (i = 0; i < 5; i++) {
    text += "The number is " + i + "<br>";
}
```

7.
```
var person = {fname:"John", lname:"Doe", age:25}; 

var text = "";
var x;
for (x in person) {
    text += person[x];
}
```

8.
```
while (i < 10) {
    text += "The number is " + i;
    i++;
}

```

9.

```


```

