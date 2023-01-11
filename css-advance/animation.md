# Animation

## Animation

## 1.Transition

> \(簡單版的動畫\)

用途:如果有hover或click改變某元素style屬性時，可加上

```text
transition: width 2s, height 2s, transform 2s,background 2s;
```

來讓元素在改變style時加上transition效果

### 如何使用:

short-cut

```text
transition: width      2s           linear       1s;
           元素屬性  幾秒鐘的動畫   如何進行動畫  延遲幾秒開始
```

或是個別指定

```text
  background: #2db34a;
  transition-property: background;
  transition-duration: 1s;
  transition-timing-function: linear;
```

## 2.Animation

> \(複雜版的動畫\)

### 1.指定keyframe

\(下面這個只可指定開始與結束\)

```text
@keyframes mymove {
    from {left: 0px;}
    to {left: 200px;}
}
```

或是\(下面的方法可指定許多關鍵影格\)

```text
@keyframes mymove {
    0% {left: 0px;}
    100% {left: 200px;}
}
```

### 2.設定animation

```text
animation: test  1s 2s 3 alternate 
        //keyframe名稱、持續時間、delay、重複次數、動畫作用方向
```

可參考:[http://www.openfoundry.org/tw/tech-column/9233-css3-animation](http://www.openfoundry.org/tw/tech-column/9233-css3-animation)

