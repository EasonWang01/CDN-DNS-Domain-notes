# CSS Tricks

## 1. 圖片與圖片的上下邊界會有 8px 的距離

## 2.讓文字顯示在背景圖片上的正中間

```markup
      <div
        style={{
          backgroundImage: `url(${board_bg})`,
          backgroundRepeat: "no-repeat",
          backgroundSize: "cover",
          backgroundColor: " rgb(11, 13, 15)",
          backgroundPosition: "50% 50%",
          width: "100vw",
          alignItems: "center",
          justifyContent: "center",
        }}
      >
      ....
```

## 3.Noise Animation

{% embed url="https://css-tricks.com/snippets/css/animated-grainy-texture/" %}

## 4. 移除 Mobile 的 hover 效果

hover 於手機頁面顯示時偶爾會出現上一個選擇的元素也觸發 hover 效果的 bug，可以使用如下

```javascript
  @media (hover: hover) { // Disable hover effect on mobile
    :hover {
      color: #1890ff;
    }
  }
```

[https://css-tricks.com/solving-sticky-hover-states-with-media-hover-hover/](https://css-tricks.com/solving-sticky-hover-states-with-media-hover-hover/)
