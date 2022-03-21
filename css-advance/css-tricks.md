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
