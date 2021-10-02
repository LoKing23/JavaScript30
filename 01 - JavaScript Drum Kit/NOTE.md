# [JS30筆記] Day1 -  JAVASCRIPT DRUM KIT
## 心得
原本以為會了一些基礎的JS事件及DOM的觀念以後前面幾天會很輕鬆，沒想到第一天的知識量還是很充足R，學到很多很讚的知識點，認識了`audio`標籤，它還有自己的方法、屬性、事件;以前控制DOM的屬性都是用 `setAttribute（）`這個方法，以為動態新增、刪除、切換class只能用jQuery來做，沒想到JavaScript有原生的方法可以使用; `transitionend`這個事件也使我大開眼界，原本只會 `click` 、`keydown`、 `change`系列的我超興奮，也不禁想到若是沒學到 `transitionend` 我會怎麼解決Day1的問題，心想該不會只能使用`setInterval`了吧

看了Alex第一天的介紹真的挺有收穫，有發現一些資深的開發者的習慣，像是寫JS前習慣先「關門」，正面表述程式碼，以及對現存語法的比較（querySelector和getElementByxxx）
## 紀錄知識點

1. [audio標籤](#audio標籤)
2. [classList底下的方法](#classList底下的方法)
3. [`transitionend`事件](#transitionend事件)
4. [`target` 及 `currentTarget`的差別](#target及currentTarget的差別)
5. [現成的轉場效果 `transition: ease`](#現成的轉場效果`transition:case`)

### audio標籤
`autio`是HTML5才新增的標籤，`src`屬性可以內嵌**音訊檔**做使用，可以使用`play()`等方法對音訊檔操作，並且其他標籤沒辦法調用這些方法，我有偷偷用`h2`標籤做過，不給我播（氣）<br>
好文介紹：[audio的方法/屬性/事件](http://www.eion.com.tw/Blogger/?Pid=1038)、[MDN - audio](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/audio) <br>
以下列出個人認為比較會使用到的方法/屬性/事件：<br>
**方法** <br>
1. play() 播放
2. pause() 暫停
3. load() 加載

**屬性**
1. controls 設置或返回媒體是否應顯示控件
```html
<audio data-num = "0" controls src="Blackberry K Two - Squadda B.mp3"></audio>
<script>
  const audio = document.querySelector('audio');
  audio.controls; //true
  audio.controls = false;//關閉控件
</script>
```
2. loop 設置或返回完成後媒體是否循環新開始
3. muted 設置或返回媒體是否靜音 `{video.muted = (video.muted) ? !1 : !0;}`
4. paused 返回媒體是否暫停
5. playbackRate 設置或返回媒體播放的速度
6. volume 設置或返回媒體的音量 range[0,1]
7. currentTime 設置或返回媒體中的當前播放位置（以秒 Seconds 為單位） <br>

**事件**就不一一列舉了，剛剛練習的 [pause事件 - github page](https://loking23.github.io/JavaScript30/01%20-%20JavaScript%20Drum%20Kit/%E6%B8%AC%E8%A9%A6audio%E7%9A%84function/audio.html)

### classList底下的方法
[Codepen - classList方法](https://codepen.io/loking23/pen/BaZEYeG) <br>
每個element都有classList這個方法，常用的方法：
- `add()`新增
- `remove()`刪除
- `toggle()`切換
- `contains()` 查找
- length數量

小知識：
1. `add()`、`remove()`可以放多個參數一次多個class運作
2. 元素可以直接抓：`element.classList.add()` <br>
事件在target後：`event.target.classList.add()`

### transitionend事件
搞了我兩小時的東西... <br>
結果是單字拼成`transitioned`，雖然剛看到這個真的以為是過去式...

[Codepen - transitionend練習](https://codepen.io/loking23/pen/qBjwNeQ)

`transitionend`事件顧名思義就是會等到`transition`**結束後**才會觸發，若是還沒跑完是不會觸發該事件 <br>
認真覺得這個Event超強，感覺可以為了觸發這個事件去設置Event，不然真的不知道要怎麼處理Day1這個效果
### target及currentTarget的差別
簡單來說：
- e.currentTarget指的是註冊事件的物件
- e.target指的是「觸發事件」的物件

以todolist為例，假設使用`ul>li`結構做列表，點擊子項目的監聽綁在父層`ul`上，此時點到li觸發事件時`e.target`是`li`，但`e.currentTarget`則是`ul`

### 現成的轉場效果`transition:case`
現成的轉場速率，像是先快後慢等等。

好像越後面越懶了，哈哈