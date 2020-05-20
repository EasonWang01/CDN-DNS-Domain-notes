# Flexbox教學

## Flexbox教學

在包裹容器加入

```text
 display: flex;
```

## 包裹容器屬性\(Parent\)

### flex-direction

1.排列行或列

[http://www.w3schools.com/cssref/tryit.asp?filename=trycss3\_flex-direction](http://www.w3schools.com/cssref/tryit.asp?filename=trycss3_flex-direction)

```text
flex-direction: row | row-reverse | column | column-reverse;
```

### flex-wrap

2.要不要分行

```text
flex-wrap: nowrap | wrap | wrap-reverse;
```

### flex-flow

shortcut [http://www.w3schools.com/cssref/css3\_pr\_flex-flow.asp](http://www.w3schools.com/cssref/css3_pr_flex-flow.asp)

```text
flex-flow: <‘flex-direction’> || <‘flex-wrap’>
```

### justify-content

3.元素間的排列方式

[http://www.w3schools.com/cssref/tryit.asp?filename=trycss3\_justify-content](http://www.w3schools.com/cssref/tryit.asp?filename=trycss3_justify-content)

```text
 justify-content: flex-start | flex-end | center | space-between | space-around;
```

### align-items

4.元素整體排列方式 \(元素間為column\)

[http://www.w3schools.com/cssref/tryit.asp?filename=trycss3\_align-items](http://www.w3schools.com/cssref/tryit.asp?filename=trycss3_align-items)

```text
 align-items: flex-start | flex-end | center | baseline | stretch;
```

### align-content

5.元素整體排列方式 \(元素間為row\)  
[http://www.w3schools.com/cssref/playit.asp?filename=playcss\_align-content&preval=stretch](http://www.w3schools.com/cssref/playit.asp?filename=playcss_align-content&preval=stretch)

```text
align-content: flex-start | flex-end | center | space-between | space-around | stretch;
```

## 容器內元素屬性\(Children\)

### order

1.排列順序order，數字越小越左邊

[http://www.w3schools.com/cssref/tryit.asp?filename=trycss3\_order](http://www.w3schools.com/cssref/tryit.asp?filename=trycss3_order)

```text
order: <integer>;
```

### flex-grow

2.元素所占空間比例，數字大空間大

[http://www.w3schools.com/cssref/tryit.asp?filename=trycss3\_flex-grow](http://www.w3schools.com/cssref/tryit.asp?filename=trycss3_flex-grow)

```text
  flex-grow: <number>; /* default 0 */
```

### flex-shrink

3.元素所占空間比例，數字大空間小

[http://www.w3schools.com/cssref/tryit.asp?filename=trycss3\_flex-shrink](http://www.w3schools.com/cssref/tryit.asp?filename=trycss3_flex-shrink)

```text
flex-shrink: <number>; /* default 1 */
```

### flex-basis

4.強制讓元素固定大小\(會蓋過width\)

[http://www.w3schools.com/cssref/tryit.asp?filename=trycss3\_flex-basis](http://www.w3schools.com/cssref/tryit.asp?filename=trycss3_flex-basis)

[https://www.w3.org/TR/css3-flexbox/images/rel-vs-abs-flex.svg](https://www.w3.org/TR/css3-flexbox/images/rel-vs-abs-flex.svg)

```text
flex-basis: <length> | auto; /* default auto */
```

### flex

5.上面三個可縮寫

[http://codepen.io/HugoGiraudel/pen/95aeaf737efab9c2c1c90ea157c091c6](http://codepen.io/HugoGiraudel/pen/95aeaf737efab9c2c1c90ea157c091c6)

```text
flex: none | [ <'flex-grow'> <'flex-shrink'>? || <'flex-basis'> ]
```

```text
flex: 1 1 20em (shorthand for flex-grow: 1, flex-shrink: 1, flex-basis: 20em)
```

### align-self

6.元素的位置類似於align-item但為單個元素

```text
align-self: auto | flex-start | flex-end | center | baseline | stretch;
```

