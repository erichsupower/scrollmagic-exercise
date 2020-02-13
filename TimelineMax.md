# TimelineMax API

<!-- toc -->

- [TimelineMax API](#timelinemax-api)
  - [時間軸初始化及動畫管理](#%e6%99%82%e9%96%93%e8%bb%b8%e5%88%9d%e5%a7%8b%e5%8c%96%e5%8f%8a%e5%8b%95%e7%95%ab%e7%ae%a1%e7%90%86)
  - [時間軸初始設置](#%e6%99%82%e9%96%93%e8%bb%b8%e5%88%9d%e5%a7%8b%e8%a8%ad%e7%bd%ae)
  - [時間軸事件](#%e6%99%82%e9%96%93%e8%bb%b8%e4%ba%8b%e4%bb%b6)
  - [時間軸播放组件](#%e6%99%82%e9%96%93%e8%bb%b8%e6%92%ad%e6%94%be%e7%bb%84%e4%bb%b6)
  - [時間軸属性调整](#%e6%99%82%e9%96%93%e8%bb%b8%e5%b1%9e%e6%80%a7%e8%b0%83%e6%95%b4)
  - [時間軸对象属性](#%e6%99%82%e9%96%93%e8%bb%b8%e5%af%b9%e8%b1%a1%e5%b1%9e%e6%80%a7)
  - [時間軸对象方法](#%e6%99%82%e9%96%93%e8%bb%b8%e5%af%b9%e8%b1%a1%e6%96%b9%e6%b3%95)

<!-- tocstop -->

## 時間軸初始化及動畫管理
|                         | 說明                                                                                                                                                                                                                      |
| ----------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [TimelineMax()][A1]     | 構建一個TimelineMax實例，創建時間軸。                                                                                                                                                                                     |
| [.add()][A2]            | 向時間軸添加動畫、其他時間軸、回調函數或標籤（或它們的陣列）。                                                                                                                                                            |
| [.addCallback()][A3]    | 在特定位置插入回調函數。                                                                                                                                                                                                  |
| [.addLabel()][A4]       | 在時間軸上添加一個標記，便於標記重要位置/時間。                                                                                                                                                                           |
| [.addPause()][A5]       | 在時間軸上添加一個暫停點。                                                                                                                                                                                                |
| [.remove()][A6]         | 從時間軸上移除一個動畫、時間軸、函數或標籤(或者他們的陣列)。                                                                                                                                                              |
| [.removeCallBack()][A7] | 從特定位置移除回調函數。如果沒有設置時間點或者標記，則移除所有該回調函數。                                                                                                                                                |
| [.removeLabel()][A8]    | 從時間軸中刪除標記。也可以使用remove()方法來移除。                                                                                                                                                                        |
| [.removePause()][A9]    | 刪除透過TimelineMax.addPause() 添加到時間軸的暫停點。                                                                                                                                                                     |
| [.to()][A10]            | 添加一個TweenLite.to()動畫到時間軸，相當於add(TweenLite.to(...))                                                                                                                                                          |
| [.from()][A11]          | 添加一個TweenLite.from()動畫到時間軸，相當於add(TweenLite.from(...))                                                                                                                                                      |
| [.fromTo()][A12]        | 添加一個TweenLite.fromTo()動畫到時間軸，相當於add(TweenLite.fromTo(...))                                                                                                                                                  |
| [.staggerTo()][A13]     | 為一組目標設定相同的終點變化屬性，但是錯開一定的時間，創建成一個間隔均勻的動畫序列。將此動畫序列添加到時間軸。                                                                                                            |
| [.staggerFrom()][A14]   | 為一組目標設定相同的起點變化屬性，但是錯開一定的時間，創建成一個間隔均勻的動畫序列。將此動畫序列添加到時間軸。                                                                                                            |
| [.staggerFromTo()][A15] | 為一組目標設定相同的起點和終點變化屬性，但是錯開一定的時間，創建成一個間隔均勻的動畫序列。                                                                                                                                |
| [.set()][A16]           | 將零持續時間的動畫添加到時間軸的末尾（或使用“位置”參數的其他位置）立即設置值（當虛擬播放頭到達時間軸上的該位置時）。<br>這是一種方便的方法，可以完成同樣類似於 add( TweenLite.to(target, 0, {...}) ) 的事情，但代碼較少。 |

[A1]: https://www.tweenmax.com.cn/api/timelinemax/TimelineMax()
[A2]: https://www.tweenmax.com.cn/api/timelinemax/add()
[A3]: https://www.tweenmax.com.cn/api/timelinemax/addCallback()
[A4]: https://www.tweenmax.com.cn/api/timelinemax/addLabel()
[A5]: https://www.tweenmax.com.cn/api/timelinemax/addPause()
[A6]: https://www.tweenmax.com.cn/api/timelinemax/remove()
[A7]: https://www.tweenmax.com.cn/api/timelinemax/removeCallBack()
[A8]: https://www.tweenmax.com.cn/api/timelinemax/removeLabel()
[A9]: https://www.tweenmax.com.cn/api/timelinemax/removePause()
[A10]: https://www.tweenmax.com.cn/api/timelinemax/to()
[A11]: https://www.tweenmax.com.cn/api/timelinemax/from()
[A12]: https://www.tweenmax.com.cn/api/timelinemax/fromTo()
[A13]: https://www.tweenmax.com.cn/api/timelinemax/staggerTo()
[A14]: https://www.tweenmax.com.cn/api/timelinemax/staggerFrom()
[A15]: https://www.tweenmax.com.cn/api/timelinemax/staggerFromTo()
[A16]: https://www.tweenmax.com.cn/api/timelinemax/set()


## 時間軸初始設置

|                          | 說明                                                                                                                                                                                                                                                                                                       |
| ------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [delay][B1]              | 時間軸動畫開始之前的延遲秒數（或幀數）。 restart()無視delay。                                                                                                                                                                                                                                              |
| [paused][B2]             | 如果設置為true，時間軸將在創建時立即暫停。默認false                                                                                                                                                                                                                                                        |
| [useFrames][B3]          | 當設置為true時，這個時間軸的時間模式基於幀而不是秒，一般幀速約為16.66ms（60幀/秒）。                                                                                                                                                                                                                       |
| [tweens][B4]             | 要將多個動畫一起插入時間軸（TweenLite / TweenMax / TimelineLite / TimelineMax），可使用tweens屬性，<br>這比使用add()要簡潔。你可以將此選項與align 和stagger 屬性結合使用，以使用最少的代碼設置複雜序列。                                                                                                   |
| [stagger][B5]            | 僅與tweens屬性一起使用。它將tweens內的動畫錯開了一定的秒數（或幀），默認值為0。                                                                                                                                                                                                                            |
| [align][B6]              | 僅與tweens屬性一起使用，設置tweens內的動畫的對齊方式，默認為"normal"。align不強制所有tweens/子時間軸保持相對定位，<br>因此，例如你使用"sequence"，然後更改其中一個嵌套動畫的持續時間，它不會強制所有後續動畫更改其在時間軸的位置。<br> align僅影響最初通過vars對象的tweens屬性放入時間軸的動畫的對齊方式。 |
| [autoRemoveChildren][B7] | 如果autoRemoveChildren設置為true，則一旦子動畫/時間軸完成，它們將自動被移除。<br>這通常是不可取的，因為子動畫可以防止時間後退（如果您想要reverse()或將進度設置得更低等等）。<br>但是，它可以提高速度和內存管理。 <br>autoRemoveChildren的默認設置是：false（除了根時間軸）。                               |
| [smoothChildTiming][B8]  | 控制是否自動重新定位子動畫/時間軸（更改其startTime），以便在動態更改屬性時保持平滑播放。<br>這些屬性包括 `reversed`, `timeScale`, `progress`, `totalProgress`, `time`, `totalTime`, `delay`, `pause`, `resume`, `duration`, `totalDuration`。                                                              |
| [repeat][B9]             | 動畫在第一次完成後應重複的次數。<br>例如，如果repeat為1，則動畫將總共播放兩次（初始播放加1次重複）。要無限重複，請使用-1。 repeat應該始終是一個整數。                                                                                                                                                      |
| [repeatDelay][B10]       | 每次repeat之間的秒數（或幀）。<br>例如，如果repeat是2並且repeatDelay是1，則動畫將首先播放，然後在重複之前等待1秒，然後再次播放，然後再等待1秒再進行最後的重複。                                                                                                                                            |
| [yoyo][B11]              | 如果設置yoyo為true，那麼重複的動畫將往返進行。默認為false。<br>例如當你設置了repeat: 2，如果沒設置yoyo，那麼動畫是這樣的123-123-123 如果設置了yoyo，動畫則是123-321-123                                                                                                                                    |
| [callbackScope][B12]     | 用於所有回調的範圍（onStart，onUpdate，onComplete等）。範圍是“this”在任何回調中引用的內容。<br>舊的回調特定範圍屬性（onStartScope，onUpdateScope，onCompleteScope，onReverseComplete等）已棄用但仍然有效。                                                                                                 |

[B1]: https://www.tweenmax.com.cn/api/timelinemax/delay
[B2]: https://www.tweenmax.com.cn/api/timelinemax/paused
[B3]: https://www.tweenmax.com.cn/api/timelinemax/useFrames
[B4]: https://www.tweenmax.com.cn/api/timelinemax/tweens
[B5]: https://www.tweenmax.com.cn/api/timelinemax/stagger
[B6]: https://www.tweenmax.com.cn/api/timelinemax/align
[B7]: https://www.tweenmax.com.cn/api/timelinemax/autoRemoveChildren
[B8]: https://www.tweenmax.com.cn/api/timelinemax/smoothChildTiming
[B9]: https://www.tweenmax.com.cn/api/timelinemax/repeat
[B10]: https://www.tweenmax.com.cn/api/timelinemax/repeatDelay
[B11]: https://www.tweenmax.com.cn/api/timelinemax/yoyo
[B12]: https://www.tweenmax.com.cn/api/timelinemax/callbackScope

## 時間軸事件

|                               | 說明                                                                                                                                |
| ----------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- | --- |
| [onStart][C1]                 | 當時間軸開始時執行的回調函數。<br>當前時間軸設置的delay會影響onStart的執行，但時間軸內的動畫的delay不會影響動畫在時間軸的開始時間。 |     |
| [onStartParams][C2]           | 傳遞給`onStart`回調函數的參數陣列                                                                                                   |     |
| [onStartScope][C3]            | 定義`onStart`函數的作用域，即函數內`this`的指向。                                                                                   |     |
| [onComplete][C4]              | 在時間軸結束時觸發此方法。                                                                                                          |     |
| [onCompleteParams][C5]        | 傳遞給 onComplete 函數的參數陣列。                                                                                                  |     |
| [onCompleteScope][C6]         | 定義`onComplete`函數的作用域，即函數內`this`的指向。                                                                                |     |
| [onReverseComplete][C7]       | 時間軸反向播放完成時執行。                                                                                                          |     |
| [onReverseCompleteParams][C8] | 傳遞給`onReverseComplete`函數的參數陣列。                                                                                           |     |
| [onReverseCompleteScope][C9]  | 定義`onReverseComplete`函數的作用域，即函數內`this`的指向。                                                                         |     |
| [onUpdate][C10]               | 當時間軸變化時(動畫進行中的每一幀)不停的觸發此函數。                                                                                |     |
| [onUpdateParams][C11]         | 傳遞給onUpdate回調函數的參數陣列                                                                                                    |     |
| [onUpdateScope][C12]          | 定义`onUpdate`函数的作用域，即函数内`this`的指向。                                                                                  |     |
| [onRepeat][C13]               | 在每次時間軸重複播放時(repeat)執行。                                                                                                |     |
| [onRepeatParams][C14]         | 傳遞給`onRepeat`回調函數的參數陣列。                                                                                                |     |
| [onRepeatScope][C15]          | 定義`onRepeat`函數的作用域，即函數內`this`的指向。                                                                                  |     |

[C1]: https://www.tweenmax.com.cn/api/timelinemax/onStart
[C2]: https://www.tweenmax.com.cn/api/timelinemax/onStartParams
[C3]: https://www.tweenmax.com.cn/api/timelinemax/onStartScope
[C4]: https://www.tweenmax.com.cn/api/timelinemax/onComplete
[C5]: https://www.tweenmax.com.cn/api/timelinemax/onCompleteParams
[C6]: https://www.tweenmax.com.cn/api/timelinemax/onCompleteScope
[C7]: https://www.tweenmax.com.cn/api/timelinemax/onReverseComplete
[C8]: https://www.tweenmax.com.cn/api/timelinemax/onReverseCompleteParams
[C9]: https://www.tweenmax.com.cn/api/timelinemax/onReverseCompleteScope
[C10]: https://www.tweenmax.com.cn/api/timelinemax/onUpdate
[C11]: https://www.tweenmax.com.cn/api/timelinemax/onUpdateParams
[C12]: https://www.tweenmax.com.cn/api/timelinemax/onUpdateScope
[C13]: https://www.tweenmax.com.cn/api/timelinemax/onRepeat
[C14]: https://www.tweenmax.com.cn/api/timelinemax/onRepeatParams
[C15]: https://www.tweenmax.com.cn/api/timelinemax/onRepeatScope

## 時間軸播放组件

|                       | 說明                                                                                                                                                                                                  |
| --------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [.play()][D1]         | 控制動畫往正方向播放，可設定開始的時間點。<br>如果suppressEvents保持默認狀態並跳到新的時間點，那麼之前在新舊時間點之間設置的回調或函數不會被觸發，相當於跳過了那些時間點。<br>如果想觸發，設為false。 |
| [.pause()][D2]        | 暫停時間軸，可選擇跳轉到特定時間。<br>如果suppressEvents保持默認狀態並跳到新的時間點，那麼之前在新舊時間點之間設置的回調或函數不會被觸發，相當於跳過了那些時間點。<br>如果想觸發，設為false。         |
| [.paused()][D3]       | 獲取或設置動畫的暫停狀態，該狀態指示動畫當前是否已暫停。                                                                                                                                              |
| [.restart()][D4]      | 重新開始動畫/重頭開始。                                                                                                                                                                               |
| [.resume()][D5]       | 恢復播放而不改變方向（前進或後退），可選擇首先跳到特定時間。                                                                                                                                          |
| [.reverse()][D6]      | 控制動畫反向播放。動畫的各種表現都會反轉，例如ease。                                                                                                                                                  |
| [.reversed()][D7]     | 獲取或設置動畫的反轉狀態，指示是否應該反向播放動畫。                                                                                                                                                  |
| [.seek()][D8]         | 不改變狀態（播放、暫停、方向）的情況下直接跳轉到某個時間點。                                                                                                                                          |
| [.timeScale()][D9]    | 獲取/設定動畫速度，默認為1。 例如0.5為慢速，2為快速。<br>如果設置則返回此時間軸便於鍊式調用。如不設置則返回時間調節比例。                                                                             |
| [.tweenTo()][D10]     | 創建一個線性動畫，將時間軸播放到特定時間或標籤，然後停止。                                                                                                                                            |
| [.tweenFromTo()][D11] | 創建一個線性動畫，將時間軸從某時間或標籤播放到指定時間或標籤，然後停止。                                                                                                                              |

[D1]: https://www.tweenmax.com.cn/api/timelinemax/play()
[D2]: https://www.tweenmax.com.cn/api/timelinemax/pause()
[D3]: https://www.tweenmax.com.cn/api/timelinemax/paused()
[D4]: https://www.tweenmax.com.cn/api/timelinemax/restart()
[D5]: https://www.tweenmax.com.cn/api/timelinemax/resume()
[D6]: https://www.tweenmax.com.cn/api/timelinemax/reverse()
[D7]: https://www.tweenmax.com.cn/api/timelinemax/reversed()
[D8]: https://www.tweenmax.com.cn/api/timelinemax/seek()
[D9]: https://www.tweenmax.com.cn/api/timelinemax/timeScale()
[D10]: https://www.tweenmax.com.cn/api/timelinemax/tweenTo()
[D11]: https://www.tweenmax.com.cn/api/timelinemax/tweenFromTo()

## 時間軸属性调整

|                        | 說明                                                                                                                                                                                                                                                                                |
| ---------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [.delay()][E1]         | 獲取或者設置時間軸的開始延遲秒數（幀）。                                                                                                                                                                                                                                            |
| [.repeat()][E2]        | 獲取或設置時間軸在第一次完成後應該重複的次數。<br>例如，如果 repeat 是1，則時間軸將總共播放兩次（初始播放加1次重複）。要無限重複，請使用-1。<br>repeat 應該始終是一個整數。 要使重複在前進和後退之間yoyo 切換，請設置 為 yoyo: true。要在重複之間添加時間間隔，請使用 repeatDelay。 |
| [.repeatDelay()][E3]   | 獲取或設置重複之間的秒數（或基於幀的時間軸的幀）的時間量。例如，如果 repeat 是2並且 repeatDelay 是1，則時間軸將首先播放，然後在重複之前等待1秒，然後再播放，然後等待1秒鐘，然後再進行最後的重複。                                                                                   |
| [.duration()][E4]      | 獲取或設置時間軸的持續時間。                                                                                                                                                                                                                                                        |
| [.totalDuration()][E5] | 獲取或設置總的時間軸持續時間。                                                                                                                                                                                                                                                      |
| [.progress()][E6]      | 獲取或者設置時間軸的進程，返回該時間軸以便鍊式調用。時間軸的進程為開始時是0，到終點時是1。                                                                                                                                                                                          |
| [.totalProgress()][E7] | 獲取或設置總的時間軸進程。                                                                                                                                                                                                                                                          |
| [.time()][E8]          | 獲取或設置當前位置的時間點。                                                                                                                                                                                                                                                        |
| [.totalTime()][E9]     | 獲取或設置當前位置在總的時間軸中的時間。                                                                                                                                                                                                                                            |
| [.endTime()][E10]      | 獲取時間軸的結束時間。                                                                                                                                                                                                                                                              |
| [.startTime()][E11]    | 獲取或設置某個動畫在其父時間軸上的起始時間                                                                                                                                                                                                                                          |
| [.yoyo()][E12]         | 獲取或設置時間軸的yoyo狀態，其中true表示時間軸每次重複時交替來回播放。                                                                                                                                                                                                              |

[E1]: https://www.tweenmax.com.cn/api/timelinemax/delay()
[E2]: https://www.tweenmax.com.cn/api/timelinemax/repeat()
[E3]: https://www.tweenmax.com.cn/api/timelinemax/repeatDelay()
[E4]: https://www.tweenmax.com.cn/api/timelinemax/duration()
[E5]: https://www.tweenmax.com.cn/api/timelinemax/totalDuration()
[E6]: https://www.tweenmax.com.cn/api/timelinemax/progress()
[E7]: https://www.tweenmax.com.cn/api/timelinemax/totalProgress()
[E8]: https://www.tweenmax.com.cn/api/timelinemax/time()
[E9]: https://www.tweenmax.com.cn/api/timelinemax/totalTime()
[E10]: https://www.tweenmax.com.cn/api/timelinemax/endTime()
[E11]: https://www.tweenmax.com.cn/api/timelinemax/startTime()
[E12]: https://www.tweenmax.com.cn/api/timelinemax/yoyo()

## 時間軸对象属性

|                           | 說明                                                                                                                                                                                                                                           |
| ------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [.autoRemoveChildren][F1] | 如果設置為true，則子動畫/時間軸在完成時會被自動移除（默認為false，除了根時間軸）。                                                                                                                                                             |
| [.data][F2]               | 用於儲存或者讀取任何你想要的數據。                                                                                                                                                                                                             |
| [.smoothChildTiming][F3]  | 控制是否自動重新定位子動畫/時間軸（更改其startTime），以便在動態更改屬性時保持平滑播放。<br>這些屬性包括 `reversed`, `timeScale`, `progress`, `totalProgress`, `time`, `totalTime`, `delay`, `pause`, `resume`, `duration`, `totalDuration` 。 |
| [.timeline][F4]           | 獲取父時間軸，所有的動畫都依附於時間軸（默認是根時間軸），並只能有一個父時間軸。                                                                                                                                                               |

[F1]: https://www.tweenmax.com.cn/api/timelinemax/autoRemoveChildren
[F2]: https://www.tweenmax.com.cn/api/timelinemax/data
[F3]: https://www.tweenmax.com.cn/api/timelinemax/smoothChildTiming
[F4]: https://www.tweenmax.com.cn/api/timelinemax/timeline

## 時間軸对象方法

|                          | 說明                                                                                                                                                                                                                               |
| ------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [.call()][G1]            | 在時間軸的末尾（或position位置）增加一個回調函數，作用類似於add( TweenLite.delayedCall(...))                                                                                                                                       |
| [.clear()][G2]           | 清空時間軸的所有動畫，時間軸和回調函數（以及標籤）。不會清除事件回調（如onComplete, onUpdate, onStart等），<br>如果你想清除可使用eventCallback()方法，如myTimeline.eventCallback("onComplete", null);。<br> 返回self便於鍊式調用。 |
| [.currentLabel()][G3]    | 獲取當前時間或之前最接近的label標記，或跳轉到指定的label標記。<br>如跳轉則返回self（便於鍊式調用）。                                                                                                                               |
| [.eventCallback()][G4]   | 獲取或設置一個事件，如`onComplete`，`onUpdate`，`onStart`，`onReverseComplete`或`onRepeat`<br>（`onRepeat`僅適用於TweenMax或TimelineMax）以及應傳遞給該回調事件的任何參數。                                                        |
| [.exportRoot()][G5]      | 將全部動畫、時間軸、函數（可選）從根時間軸導出至新的時間軸便於執行一些高級操作，並且不影響導出後創建的動畫/時間軸。                                                                                                                |
| [.getActive()][G6]       | 返回時間軸中當前處於活動狀態的動畫/時間軸，這意味著時間軸的播放頭位於子動畫/時間軸上，並且子項未暫停。                                                                                                                             |
| [.getChildren()][G7]     | 返回一個陣列，其中包含嵌套在此時間軸中的所有動畫和時間軸。                                                                                                                                                                         |
| [.getLabelAfter()][G8]   | 返回`time`參數後面的下一個標籤（如果有）。 可配合`tweenTo()`使時間軸動畫至該標記。                                                                                                                                                 |
| [.getLabelBefore()][G9]  | 返回在`time`參數之前發生的上一個label標記（如果有）。可配合`tweenTo()`使時間軸動畫至該標記。                                                                                                                                       |
| [.getLabelsArray()][G10] | 返回一個標記對像陣列，按時間軸中出現的順序排列，每個標記對像有“time”和“name”屬性。                                                                                                                                                 |
| [.getLabelTime()][G11]   | 返回特定標記的時間位置。                                                                                                                                                                                                           |
| [.getTweensOf()][G12]    | 返回此時間軸內特定對象的動畫（TweenLite和TweenMax）。                                                                                                                                                                              |
| [.invalidate()][G13]     | 刷新任何內部記錄的開始/結束值，如果您想要重新啟動動畫而不恢復到以前記錄的任何起始值，這將非常有用。                                                                                                                                |
| [.isActive()][G14]       | 指示動畫當前是否處於活動狀態（意味著播放頭在此實例的時間範圍內正在活動，並且未暫停，也不是其任何祖先時間軸）。                                                                                                                     |
| [.kill()][G15]           | 根據參數完全或部分kill時間軸。 返回self便於鍊式調用。                                                                                                                                                                              |
| [.recent()][G16]         | 返回最近添加的子動畫/時間軸/回調函數，無論其在時間軸中的位置如何。                                                                                                                                                                 |
| [.shiftChildren()][G17]  | 將此時間軸的子項的開始時間（startTime）移動一定秒數或幀。當你想在某個點插入動畫，將已存在的動畫後移以騰出位置給新動畫時，可以考慮使用此方法。                                                                                      |
| [.useFrames()][G18]      | 如果為true，則時間線的計時模式是基於幀而不是秒。                                                                                                                                                                                   |

[G1]: https://www.tweenmax.com.cn/api/timelinemax/call()
[G2]: https://www.tweenmax.com.cn/api/timelinemax/clear()
[G3]: https://www.tweenmax.com.cn/api/timelinemax/currentLabel()
[G4]: https://www.tweenmax.com.cn/api/timelinemax/eventCallback()
[G5]: https://www.tweenmax.com.cn/api/timelinemax/exportRoot()
[G6]: https://www.tweenmax.com.cn/api/timelinemax/getActive()
[G7]: https://www.tweenmax.com.cn/api/timelinemax/getChildren()
[G8]: https://www.tweenmax.com.cn/api/timelinemax/getLabelAfter()
[G9]: https://www.tweenmax.com.cn/api/timelinemax/getLabelBefore()
[G10]: https://www.tweenmax.com.cn/api/timelinemax/getLabelsArray()
[G11]: https://www.tweenmax.com.cn/api/timelinemax/getLabelTime()
[G12]: https://www.tweenmax.com.cn/api/timelinemax/getTweensOf()
[G13]: https://www.tweenmax.com.cn/api/timelinemax/invalidate()
[G14]: https://www.tweenmax.com.cn/api/timelinemax/isActive()
[G15]: https://www.tweenmax.com.cn/api/timelinemax/kill()
[G16]: https://www.tweenmax.com.cn/api/timelinemax/recent()
[G17]: https://www.tweenmax.com.cn/api/timelinemax/shiftChildren()
[G18]: https://www.tweenmax.com.cn/api/timelinemax/useFrames()