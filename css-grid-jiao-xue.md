# \#CSS Grid 教學

[https://css-tricks.com/snippets/css/complete-guide-grid/](https://css-tricks.com/snippets/css/complete-guide-grid/)

一個CSS的layout方法 為2-dimension 的排版方式



以此為範例

https://codepen.io/pen/?editors=1100

步驟1: 寫 grid-template-columns 與 grid-template-rows 用來寫好這個container是如何分割

```css
.grid-container {
  height: 100vh;
  display: grid;
  grid-template-columns: 0.25fr 0.25fr 0.25fr 0.25fr;
  grid-template-areas: "header header header header"
                       "main main . sidebar"
                       "footer footer footer footer";
  grid-column-gap: 100px;
  grid-row-gap: 20px;
}
```

```html
<div class="grid-container">
  <div class="grid-item header">
    <div>我是標題</div>
  </div>
  <div class="grid-item main">
    <div>我是主題</div>
  </div>
  <div class="grid-item sidebar">
    <div>我是左側</div>
  </div>
  <div class="grid-item footer">
    <div>我是底部</div>
  </div>
</div>
```



```css
.grid-container {
  height: 100vh;
  display: grid;
  grid-template-columns: 0.25fr 0.25fr 0.25fr 0.25fr;
  grid-template-areas: "header header header header"
                       "main main . sidebar"
                       "footer footer footer footer";
  grid-column-gap: 100px;
  grid-row-gap: 20px;
}

.grid-item div {
  text-align: center;
}

.header {
  background-color: black;
  grid-area: header;
}

.main {
  background-color: green;
  grid-area: main;
}

.sidebar {
  background-color: orange;
  grid-area: sidebar;
}

.footer {
  background-color: yellow;
  grid-area: footer;
}
```



