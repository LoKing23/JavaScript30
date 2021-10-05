# [JS30 筆記]Day4 - Array Cardio Day
## 今天練習重點
今天練習一些常用的陣列方法，後面還有陣列方法Day2。
主要就是一些簡單的篩選、排序、迴圈方法、累加等等，還有將字串切成陣列
## 心得
半年前剛自學JS的時候也有練習過類似的題目，就是一些常用的陣列方法，那時候花了三天做了一些練習才了解每個方法該怎麼用，這次練習有勾起之前練習的回憶，因為之前看過所以這次學得還算快，但還是有一些需要筆記的地方，像是`sort()`預設轉成Unicode才會比較，所以比較數字等需要自己寫一些條件; `map()`與`forEach()`的差異，`reduce()`的計算方式等
## 知識點
1. [`filter()`篩選](#filter()`篩選)
2. [`map()``forEach()`](#`map()`、`forEach()`)
3. [`sort()`](#`sort()`)
4. [`reduce()`](#`reduce()`)
5. [`split()`](#`split()`)
6. [`console.table()`好用歐](#`cnosole.table()好用歐`)
### `filter()`篩選
`filter()`會返回符合條件的item，函式的參數還是三個老屁股，一樣也是後面兩個隨選
```javascript
filter(function(item,index,array){
  return 符合條件;
})
```
### `map()`、`forEach()`
`map()`與`forEach()`一樣會跑完所有物件，差異是`map()`會回傳一個新的陣列，而`forEach()`不會，並且`forEach()`可能有同步異步的問題存在
### `sort()`
排列，預設轉成Unicode排列，所以數字會有110排在2前面這種情況，可以在函式內重新定義如何排序
```javascript
//a, b各是陣列兩個元素，return<0則a排在b前面，return>0則a排在b後面，return=0則不動排序
//以數字排序為例
arr.sort(function(a,b){
  return a-b;
})
```
### `reduce()`
有「累加器」的方法，這個累加器也是最後會回傳的項目，陣列迭代時可以保持原本的模樣，可以省去一般做遞迴累進時需要另外設定變數的麻煩 <br>
「累加器」可以是數字、陣列、物件等
```javascript
arr.reduce(function(total, element){
  ...
  return 累加器
},累加器)
```
### `split()`
切割字串的方法，可以設置斷點切割成陣列，沒有設定就會將每個字元切成陣列
```javascript
str = '你好6我是LoKing6請多指掉' 
let arr = str.split('6'); //arr['你好','我是LoKing','請多指掉']
```
### `console.table()好用歐`
陣列、物件等使用`console.table()`看超舒服