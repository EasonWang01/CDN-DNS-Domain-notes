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

{% embed url="https://css-tricks.com/solving-sticky-hover-states-with-media-hover-hover/" %}

## 5.  linear-gradient 產生效果

讓 顏色後面接續著 transparent 並且在同個 % 可產生以下效果

![](<../.gitbook/assets/截圖 2022-10-28 上午10.54.05.png>)

![](<../.gitbook/assets/截圖 2022-10-28 上午10.57.45.png>)

或是更進階的三層

![](<../.gitbook/assets/截圖 2022-10-28 上午11.30.43.png>)

```css
background: 
linear-gradient(#ffffff, #ffffff) 50% 50%/calc(100% - 20px) calc(100% - 0px) no-repeat, 
linear-gradient(#ffffff, #ffffff) 50% 50%/calc(100% - 10px) calc(100% - 10px) no-repeat, 
linear-gradient(90deg, #48abe0 5%, transparent 5%, transparent 95%, #48abe0 5%)
```

## 6. 網格狀背景

![](<../.gitbook/assets/截圖 2022-10-28 上午11.39.37.png>)

[https://stackoverflow.com/a/32861765/4622645](https://stackoverflow.com/a/32861765/4622645)
