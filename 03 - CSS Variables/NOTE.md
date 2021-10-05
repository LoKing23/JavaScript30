# [JS30 筆記] Day3 - CSS Variables
## 練習目標
今天主要練習的就是CSS3變數，還有一個重要的觀念就是對於「資料」與「畫面」的處理，這次的JS code很少，主要的更動是「資料」而不是「畫面」，Wesbos故意將標題的JS字串也使用CSS3變數，導致若是我們更動畫面就必須針對每個DOM做改變
## 心得
今天不難但還是收穫滿滿，有許多意外收穫，了解到Sass變數與CSS3變數的差異，有找到CSS3變數的不可取代性，以及`:root` === `html` === documentElement這件事，大開眼界R，揭開傳說中的偽類`:root`不為我知的那面;還有許久沒用的`this`，感覺今天還是可以用event參數來改變，這次作業兩個方法都有寫，意外發現箭頭函式會影響到this的運作。順便加深一些印象，像是三元運算子及||賦值。
比較意外的一點是`mousemove`觸發顏色改變一開始讓我有點混亂，原本以為`mousemove`應該是要滑鼠在`input`上就要改變顏色，測試之後才想起來滑鼠在上面滑根本不會變，因為`input`的value根本沒有改變R
今天綁事件莫名沒觸發，debug老半天、重新整理網頁好幾遍，後來發現關掉瀏覽器再重開就正常了...
## 知識點紀錄
1. [`:root` == `html`標籤 == documentElement](#:root真面目)
2. [style賦值方法](#style賦值方式)
3. [三元運算子與||賦值](#三元運算子與||賦值)
4. [`this`運用](#`this`運用)
### :root真面目
這三個都是抓一樣的東西 <br>
`document.querySelector(':root')` == `document.querySelector('html')` == `document.documentElement`


### style賦值方式
    - 變數賦值：`document.documentElement.style[名稱] = 值` ->但有--會失敗
    - 函式賦值：`document.documentElement.style.setProperty`(名稱,值)` ->可以用--
### 三元運算式及||賦值
- 三元運算子，精簡版的if...else
```javascript
let a = 3;
console.log("true:" + (a===3?20:10)); //true: 20
console.log("false:" + (a===4?20:10)) //false: 10
```
- ||賦值 <br>
也是超方便，尤其是在賦一些很常undefined、null這種的 

感覺&&也可以拿來用，但還沒研究時機
### `this`的運用
this指向敲好用，也容易出事，像是箭頭函式會影響到this的使用，未來要好好來研究一下，maybe明天。
[this好文 - PJChen](https://pjchender.dev/javascript/js-arrow-function/)、[this好文 - 前端30](https://medium.com/schaoss-blog/%E5%89%8D%E7%AB%AF%E4%B8%89%E5%8D%81-10-js-%E4%B8%80%E8%88%AC%E5%87%BD%E5%BC%8F%E8%88%87%E7%AE%AD%E9%A0%AD%E5%87%BD%E5%BC%8F%E7%9A%84%E5%B7%AE%E7%95%B0-32ce9455ff1a)
