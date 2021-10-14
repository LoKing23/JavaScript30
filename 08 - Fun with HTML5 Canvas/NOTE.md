# [JS30 筆記]Day8 - Fun with HTML5 Canvas
## 練習項目
## 心得
## 紀錄知識點
- `mouseout()`與 `mouseleave()` 差異
- `canvas`基本屬性
### `mouseout()`與`mouseleave()`差異
[Codepen測試 - mouseout與mouseleave差異](https://codepen.io/loking23/pen/RwZWWVm) <br>
這兩個都是「移出」元素時會觸發的事件，不一樣的是：
- `mouseout()` 底下的子層也會觸發事件
- `mouseleave()`只有綁定的那一層才會觸發mouseleave事件

### `mouseenter()`與`mouseover()`與`mousemove()`
`mousemove()`比較不一樣，在元素內「移動」就會觸發 <br>
`mouseenter()`與`mouseover()`的關係與上面的關係比較接近，都是滑鼠「移入」元素時觸發，差異是：
- `mouseenter()`只有滑進指定元素時觸發
- `mouseover()`滑進指定元素的底層元素也會觸發

### canvas
- Canvas 2D基礎
抓到Canvas的DOM後，使用`hetContent('2D')`使用Canvas的2D繪圖，使用不同的繪畫方式要輸入不同的參數
```javascript
  const canvas = document.querySelector('#draw');
  let ctx = canvas.getContext('2d');
```
- `ctx.beginPath()` ＆ `ctx.stroke()` <br>
簡單來說就是起始點，但`ctx.stroke()`是專門用來描邊的，若是換成`ctx.fill()`則會將中間的點連線後填滿 <br>
- `ctx.strokeStyle`
邊線的顏色，從前面的stroke知道這是`ctx.stroke()`的顏色，還有另一個可以設定`fill()`的顏色
- `ctx.lineJoin`
設定線的折角要怎麼處理，奇怪的拐角 || 圓形 || 直角<br>
```javascript
ctx.lineJoin = bevel || round || miter;
```
- `ctx.lineCap`
設定線的頂端怎麼處理，畢竟是人家的帽子（cap）<br>
```javascript
ctx.lineCap = bevel || round || miter;
```
- `ctx.lineWidth`
設定線條的寬度多少，不用加上單位
```javascript
ctx.lineWidth = 20;
```
