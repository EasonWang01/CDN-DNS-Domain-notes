#### 1.child absolute 會壓在parent上方，但移除parent z-index 並在child 加上negative zindex後可壓到child上方。

[https://codepen.io/anon/pen/gBdGPN](https://codepen.io/anon/pen/gBdGPN)

> 移除.container1 z-index 試試

#### 2.同層div的順序也會影響，放在前面的div會被壓在下面，但static的position會被壓在最下方。

#### 3.其他同層container 有更大的zindex，就算較小的container zindex下有最大的zindex child還是會被覆蓋。

[https://codepen.io/anon/pen/QZVVbY](https://codepen.io/anon/pen/QZVVbY)

#### 4. opacity小於1 的元素也會讓他成為z-index的stack contexts

#### 不錯的文章：

[https://developer.mozilla.org/en-US/docs/Web/CSS/CSS\_Positioning/Understanding\_z\_index](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Positioning/Understanding_z_index)

[https://philipwalton.com/articles/what-no-one-told-you-about-z-index/](https://philipwalton.com/articles/what-no-one-told-you-about-z-index/)

