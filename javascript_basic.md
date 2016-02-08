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




