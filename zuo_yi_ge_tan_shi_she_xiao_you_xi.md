# 做一個貪食蛇小遊戲


```
<!DOCTYPE html>
<html>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8">
<head>
<script src="https://code.jquery.com/jquery-2.2.1.min.js"></script>
<style>
table {
    width:80%;
}
table, th, td {
    border: 1px solid black;
    border-collapse: collapse;
}
td{
  width:2px;
  
}
</style>
</head>
```
```
<body>
  <button id="btn"style="width:200px;height:50px;position:absolute;" onclick="h()">開始遊戲</button>
  <div id="score"style="position:absolute;bottom:20px"></div>
<div id="main" style="width:100%;height:100%;">  
  <!--不可設為absolute才不會按按鍵滑動移幕 -->


<table>
  <tr>
   <td></td>
    <td></td>		
    <td></td>
     <td></td>
     <td></td>		
    <td></td>
     <td></td>
     <td></td>		
    <td></td>
     <td></td>
     <td></td>		
    <td></td>
  </tr>
  <tr>
     <td></td>
     <td></td>		
    <td></td>
       <td></td>
     <td></td>		
    <td></td>
       <td></td>
     <td></td>		
    <td></td>
       <td></td>
     <td></td>		
    <td></td>
  <tr>
   <td></td>
     <td></td>		
    <td></td>
       <td></td>
     <td></td>		
    <td></td>
       <td></td>
     <td></td>		
    <td></td>
       <td></td>
     <td></td>		
    <td></td>
  </tr>
  <tr>
      <td></td>
     <td></td>		
    <td></td>
       <td></td>
     <td></td>		
    <td></td>
       <td></td>
     <td></td>		
    <td></td>
       <td></td>
     <td></td>		
    <td></td>
  </tr>
</table>


<table>
  <tr>
   <td></td>
     <td></td>		
    <td></td>
       <td></td>
     <td></td>		
    <td></td>
       <td></td>
     <td></td>		
    <td></td>
       <td></td>
     <td></td>		
    <td></td>
  </tr>
  <tr>
     <td></td>
     <td></td>		
    <td></td>
       <td></td>
     <td></td>		
    <td></td>
       <td></td>
     <td></td>		
    <td></td>
       <td></td>
     <td></td>		
    <td></td>
  <tr>
   <td></td>
     <td></td>		
    <td></td>
       <td></td>
     <td></td>		
    <td></td>
       <td></td>
     <td></td>		
    <td></td>
       <td></td>
     <td></td>		
    <td></td>
  </tr>
  <tr>
      <td></td>
     <td></td>		
    <td></td>
       <td></td>
     <td></td>		
    <td></td>
       <td></td>
     <td></td>		
    <td></td>
       <td></td>
     <td></td>		
    <td></td>
  </tr>
</table>
</div>

</body>
</html>
```