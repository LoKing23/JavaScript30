# [JS30 筆記]Day 5 - Flex Panel Gallery
## 練習項目
這次練習主要是與flex、transition與JS事件的配合，兩段式動畫之前有練習過了，一樣是`transitinoend`接在某事件之後
## 心得
昨天剛好在看flex的grow、shrink、basis，今天就剛好用到了，這次的動畫很美，感覺未來可以用在專案上。
## 紀錄知識點
- [`propertyName`與`transitionend`](#`propertyName`與`transitionend`)
- [`transitionend`與`classList.toggle`注意事項](#`transitionend`與`classList.toggle`注意事項)
### `propertyName`與`transitionend`
`propertyName`是`transitionend`事件觸發後返回的參數，可以從style裡的`transition`看，若是`font-size`改變則`properrtName`就是`font-size`<br>
需要注意的是不是每個瀏覽器返回的名字都一樣，Wesbos有特別講到`flex-grow`返回值在safari上是`flex`，在Chrome瀏覽器是`flex-grow`
### `transitionend`與`classList.toggle`注意事項
`transitionend`會在「每一個」動畫後觸發，也就是說若是一個`click`事件觸發了兩次`transition`就會有兩次`transitionend`事件 <br>
這會有什麼問題呢？用在`classList.toggle()`上就會有沒效果的問題，若是每一次動畫都觸發toggle，那觸發偶數次事件就會使toggle抵銷（一次加上class，一次去掉class）<br>
解決辦法：可以判斷某動畫出現才toggle，這樣就可以過濾掉閒雜人等囉·