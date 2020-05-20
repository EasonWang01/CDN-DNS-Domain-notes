# 做一個貪食蛇小遊戲

```text
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

```text
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

## 先讓長寬相等

```text
var x = $("td").width();
$("td").height(x);

$(window).resize(function() {
 var x = $("td").width();
$("td").height(x);
});

for(i=0;i < $("td").length;i++){
    var as = $("td")[i];//as會變為plain HTML   <tr>..</tr>
    $(as).attr('id',i);//所以要再用jquery包起來


};
```

宣告變數

```text
var current = 0;
var direction ="right";//一開始的前進方向
var currentBody=[current];
var score1 = 0;
var snackColor ='black';

var apple = Math.floor((Math.random() * 95) + 1);//產生一個隨機的蘋果
$("#"+(apple)).css('background','red');//
```

設定前進時的方向變數

```text
document.onkeydown = function(key){

if (key.code=='ArrowLeft') { 

    direction ="left";


}else if(key.code=="ArrowRight"){
    direction ="right";

}else if(key.code=="ArrowUp"){
    direction ="up";

}else if(key.code=="ArrowDown"){
    direction ="down";


}


}
```

## 思考方向

1.如何產生會前進的黑色方格

2.黑色方格的id = 蘋果的id時蛇的陣列長度+1

3.再次產生一個紅色方格，但不在蛇的身體上

4.如果蛇撞到邊界或自己身體遊戲結束

```text
for(i=0;i<currentBody.length;i++){//一開始的黑色
$("#"+currentBody[i]).css('background',snackColor)
 };
function start(){
var starts =  setInterval(function(){





 if(direction=="right"){

     if(currentBody[0]!=11&&currentBody[0]!=23&&currentBody[0]!=35&&currentBody[0]!=47&&currentBody[0]!=59&&currentBody[0]!=71&&currentBody[0]!=83&&currentBody[0]!=95){

   current=currentBody[((currentBody.length)-1)];//a[3]為最後一元素但a.length為4，所以減1，current表示蛇陣列的尾巴id，記錄上一輪尾巴的坐標


  var last = currentBody[(currentBody.length)-1];//在移動前記錄尾巴元素 

    for(i=(currentBody.length)-1;i>0;i--){///前進時後一個元素id護變為前一個id
    currentBody[i]=currentBody[i-1]

    };

    cc = currentBody.slice(0);
    delete cc[0];

    cc.push(last);

     currentBody[0]+=1;

   if(($.inArray(currentBody[0],cc))!=-1){
  if(currentBody[0]!=apple){
    clearInterval(starts);
    $('body').html("遊戲結束"+score1);
   };

};




$("#"+(current)).css("background","white");



for(i=0;i<currentBody.length;i++){//蛇的陣列元素是黑色
$("#"+currentBody[i]).css('background',snackColor)
 };

    if(currentBody[0]==apple){

    currentBody.push(apple);
  score1++;
   console.log("aa");
  $('#score').html("你的分數為"+score1);
  for(;;){//如果蘋果產生在蛇身體上，重新產生蘋果直到不在
   apple = Math.floor((Math.random() * 95) + 1);
   if(($.inArray(apple,currentBody))==-1){

    break;
   }
 };
 $("#"+(apple)).css('background','red');//讓蘋果的位置是紅色
};

 }else{
     clearInterval(starts);
    $('body').html("遊戲結束"+score1);

 };
 };


 if(direction=="left"){
     if(currentBody[0]!=0&&currentBody[0]!=12&&currentBody[0]!=24&&currentBody[0]!=36&&currentBody[0]!=48&&currentBody[0]!=60&&currentBody[0]!=72&&currentBody[0]!=84){

   current=currentBody[((currentBody.length)-1)];//a[3]為最後一元素但a.length為4，所以減1，current表示蛇陣列的尾巴id，記錄上一輪尾巴的坐標


  var last = currentBody[(currentBody.length)-1];//在移動前記錄尾巴元素


 for(i=(currentBody.length)-1;i>0;i--){///前進時後一個元素id護變為前一個id
    currentBody[i]=currentBody[i-1]

    };

    cc = currentBody.slice(0);
    delete cc[0];
         //////////看是否撞到身體，使用var last記錄完後，把頭刪掉加上上次的尾巴
    cc.push(last);

     currentBody[0]-=1;

   if(($.inArray(currentBody[0],cc))!=-1){
  if(currentBody[0]!=apple){
    clearInterval(starts);
    $('body').html("遊戲結束"+score1);
   };//////////看是否撞到身體，使用var last記錄完後，把頭刪掉加上上次的尾巴

};




$("#"+(current)).css("background","white");



for(i=0;i<currentBody.length;i++){//蛇的陣列元素是黑色
$("#"+currentBody[i]).css('background',snackColor)
 };

  if(currentBody[0]==apple){
  currentBody.push(apple);
  score1++;
  $('#score').html("你的分數為"+score1);

  for(;;){//如果蘋果產生在蛇身體上，重新產生蘋果直到不在
   apple = Math.floor((Math.random() * 95) + 1);
   if(($.inArray(apple,currentBody))==-1){

    break;
   }
 };

$("#"+(apple)).css('background','red');//讓蘋果的位置是紅色

    };


 }else{
     clearInterval(starts);
    $('body').html("遊戲結束"+score1);

 };
 };
 if(direction=="down"){
     if(currentBody[0]!=84&&currentBody[0]!=85&&currentBody[0]!=86&&currentBody[0]!=87&&currentBody[0]!=88&&currentBody[0]!=89&&currentBody[0]!=90&&currentBody[0]!=91&&currentBody[0]!=92&&currentBody[0]!=93&&currentBody[0]!=94&&currentBody[0]!=95){


   current=currentBody[((currentBody.length)-1)];//a[3]為最後一元素但a.length為4，所以減1，記錄上一輪尾巴的坐標

 var last = currentBody[(currentBody.length)-1];//在移動前記錄尾巴元素 


for(i=(currentBody.length)-1;i>0;i--){///前進時後一個元素id護變為前一個id
    currentBody[i]=currentBody[i-1]

    };


    cc = currentBody.slice(0);
    delete cc[0];

    cc.push(last);

     currentBody[0]+=12;

   if(($.inArray(currentBody[0],cc))!=-1){
  if(currentBody[0]!=apple){
    clearInterval(starts);
    $('body').html("遊戲結束得分為"+score1);
   };

};



$("#"+(current)).css("background","white");



for(i=0;i<currentBody.length;i++){//蛇的陣列元素是黑色
$("#"+currentBody[i]).css('background',snackColor)
 };


  if(currentBody[0]==apple){
  currentBody.push(apple);
  score1++;
  $('#score').html("你的分數為"+score1);

  for(;;){//如果蘋果產生在蛇身體上，重新產生蘋果直到不在
   apple = Math.floor((Math.random() * 95) + 1);
   if(($.inArray(apple,currentBody))==-1){

    break;
   }
 };

$("#"+(apple)).css('background','red');//讓蘋果的位置是紅色

    };

 }else{
     clearInterval(starts);
    $('body').html("遊戲結束"+score1);

 };
 };
 if(direction=="up"){
     if(currentBody[0]!=0&&currentBody[0]!=1&&currentBody[0]!=2&&currentBody[0]!=3&&currentBody[0]!=4&&currentBody[0]!=5&&currentBody[0]!=6&&currentBody[0]!=7&&currentBody[0]!=8&&currentBody[0]!=9&&currentBody[0]!=10&&currentBody[0]!=11){

/////////
   current=currentBody[((currentBody.length)-1)];//a[3]為最後一元素但a.length為4，所以減1，記錄上一輪尾巴的坐標，讓他變白色
////////



 var last = currentBody[(currentBody.length)-1];//在移動前記錄尾巴元素 



for(i=(currentBody.length)-1;i>0;i--){///前進時後一個元素id護變為前一個id
    currentBody[i]=currentBody[i-1]

    };

    cc = currentBody.slice(0);
    delete cc[0];

    cc.push(last);

     currentBody[0]-=12;

   if(($.inArray(currentBody[0],cc))!=-1){
  if(currentBody[0]!=apple){
    clearInterval(starts);
    $('body').html("遊戲結束得分為"+score1);
   };

};


//////    
$("#"+(current)).css("background","white");


//////
for(i=0;i<currentBody.length;i++){//蛇的陣列元素是黑色
$("#"+currentBody[i]).css('background',snackColor)
 };


//////
  if(currentBody[0]==apple){
  currentBody.push(apple);
  score1++;
  $('#score').html("你的分數為"+score1);

  for(;;){//如果蘋果產生在蛇身體上，重新產生蘋果直到不在
   apple = Math.floor((Math.random() * 95) + 1);
   if(($.inArray(apple,currentBody))==-1){

    break;
   }
 };

$("#"+(apple)).css('background','red');//讓蘋果的位置是紅色

    };
//////

 }else{
     clearInterval(starts);
    $('body').html("遊戲結束"+score1);

 };
 };



},300);
};
```

[http://easonwang01.github.io/snake/](http://easonwang01.github.io/snake/)

