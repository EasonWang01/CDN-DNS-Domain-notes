# 實用CSS 技巧

## 1.使用純CSS做一個Modal，之後點擊外框即可消失

![](../.gitbook/assets/螢幕快照%202017-04-18%20下午3.17.33.png)

html

```text
     <div >
       <input  className="modal-state" id="modal-1" type="checkbox" />  
       <div className="modalbg" style={{width: '100%', height: '100%', background: 'rgba(0,0,0, .6)', position: 'fixed', top: '0', left: '0'}}>
         <div className="modalWhite" style={{zIndex:'100',width: '50%', height: '50%', background: 'white', position: 'fixed', top: '25%', left: '25%'}} ></div> 
         <label className="modal__bg" htmlFor="modal-1"></label>
       </div>     
     </div>
```

css

```text
.modal__bg {
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  cursor: pointer;
}

.modalbg {
  visibility: hidden;
}

.modalWhite {
  visibility: hidden;
}

.modal-state {
  display: none;
}

.modal-state:checked ~ .modalbg > .modalWhite {
  visibility: visible;
}

.modal-state:checked ~ .modalbg {
  visibility: visible;
}
```

之後可使用以下，即可呼叫出Modal

```text
document.getElementById('modal-1').click()
```

## 2.字體大小 RWD

```text
html {
 font-size: 1vw
}
```

讓最外層用 vw，內層元素用rem來相對於最 root 的比例。

```text
div {
  font-size: 1.2rem
}
```

> em是用來相對直接外層元素的大小，rem是相對根元素。

