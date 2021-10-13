# [JS30 筆記]Day7 - Array Cardio Day 2
## 練習項目
JavaScript的各式陣列練習
- `some()`,`every()`
- `find()`,`findIndex()`
- `splice()`,`slice()`
## 心得
有些平常比較少用到的陣列方法 `some()`、`slice()`，`some()`看陣列有沒有特定值，以前是用 `findIndex()`，感覺就可以完全取代了吧，除非一定要boolean值 <br>
`splice`及`slice`反而是比較需要注意的點，看了Alex講解，有些開發應該要注意的事情蠻值得記下的
> sever原始的資料不會想改動裡面的內容 --By 新店宋承憲 a.k.a Alex

蠻認同的，而且以前沒有注意這點，所以這次最後一題寫了兩個解，一個直接切原陣列（in-place），一個透過 `slice()` 回傳新的陣列
## 紀錄知識點
這次都大同小異，所有函式都是陣列方法三劍客配一個迭代用的變數

- 隨便舉一個`some()`
```javascript
Array.some((item, index, array) => {
  return item === xxx;
},迭代用的東東（選配）)
```

- `slice(x,y)`需要注意的點<br>
  1. 淺拷貝
  2. 回傳值不包含到`y` 

  `slice(x,y)`，`slice()` 會回傳`x`到`y`這段陣列（但不包含y !!），需要回傳`x`到後面的所有陣列內容就不需要第二個參數
    - slice(x) 回傳`x`後的所有陣列資料

- `find()`與`filter()` <br>
`find()`找到第一個就停，並返回該值 <br>
`filter()` 會回傳所有符合的值，並組成陣列