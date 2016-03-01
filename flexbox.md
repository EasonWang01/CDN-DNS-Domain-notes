# Flexbox

在包裹容器加入
```
 display: flex;
```

#包裹容器屬性(Parent)
1.排列行或列

http://www.w3schools.com/cssref/tryit.asp?filename=trycss3_flex-direction
```
flex-direction: row | row-reverse | column | column-reverse;
```
2.要不要分行
```
flex-wrap: nowrap | wrap | wrap-reverse;
```
shortcut http://www.w3schools.com/cssref/css3_pr_flex-flow.asp
```
flex-flow: <‘flex-direction’> || <‘flex-wrap’>
```
3.元素間的排列方式

http://www.w3schools.com/cssref/tryit.asp?filename=trycss3_justify-content
```
 justify-content: flex-start | flex-end | center | space-between | space-around;
```
4.元素整體排列方式  (元素間為column)

http://www.w3schools.com/cssref/tryit.asp?filename=trycss3_align-items
```
 align-items: flex-start | flex-end | center | baseline | stretch;
```

5.元素整體排列方式  (元素間為row)
http://www.w3schools.com/cssref/playit.asp?filename=playcss_align-content&preval=stretch
```
align-content: flex-start | flex-end | center | space-between | space-around | stretch;
```
#容器內元素屬性(Children)
1.排列順序order，數字越小越左邊

http://www.w3schools.com/cssref/tryit.asp?filename=trycss3_order
```
order: <integer>;
```
2.元素所占空間比例，數字大空間大

http://www.w3schools.com/cssref/tryit.asp?filename=trycss3_flex-grow


```
  flex-grow: <number>; /* default 0 */
```
3.元素所占空間比例，數字大空間小

http://www.w3schools.com/cssref/tryit.asp?filename=trycss3_flex-shrink
```
flex-shrink: <number>; /* default 1 */
```