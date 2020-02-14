# TweenMax API

<!-- toc -->

- [TweenMax API](#tweenmax-api)
  - [動畫結構](#%e5%8b%95%e7%95%ab%e7%b5%90%e6%a7%8b)
  - [動畫初始設置](#%e5%8b%95%e7%95%ab%e5%88%9d%e5%a7%8b%e8%a8%ad%e7%bd%ae)
  - [動畫事件](#%e5%8b%95%e7%95%ab%e4%ba%8b%e4%bb%b6)
  - [動畫播放組件](#%e5%8b%95%e7%95%ab%e6%92%ad%e6%94%be%e7%b5%84%e4%bb%b6)
  - [動畫屬性調整](#%e5%8b%95%e7%95%ab%e5%b1%ac%e6%80%a7%e8%aa%bf%e6%95%b4)
  - [實例屬性](#%e5%af%a6%e4%be%8b%e5%b1%ac%e6%80%a7)
  - [實例方法](#%e5%af%a6%e4%be%8b%e6%96%b9%e6%b3%95)

<!-- tocstop -->

## 動畫結構
|                                | 說明                                                                                                                                     |
| ------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------- |
| [TweenMax()][A1]               | TweenMax的構造函數，用來構建一個TweenMax對象。                                                                                           |
| [TweenMax.to()][A2]            | 此方法用於創建一個從當前屬性到指定目標屬性的TweenMax動畫對象。                                                                           |
| [TweenMax.from()][A3]          | 通過設置動畫起始點來初始化一個TweenMax，相當於動畫從設置點開始。                                                                         |
| [TweenMax.fromTo()][A4]        | 通過設置動畫起始點和結束點來初始化一個TweenMax，相當於動畫從設置點到第二個設置點。                                                       |
| [TweenMax.staggerTo()][A5]     | stagger系列方法為多個目標製作一個有間隔的動畫序列，相當於多個TweenMax的數組。 需要設置每個動畫的開始間隔。如不設置則為零，同時開始動畫。 |
| [TweenMax.staggerFrom()][A6]   | 通過設定序列動畫的終點來初始化一組TweenMax。                                                                                             |
| [TweenMax.staggerFromTo()][A7] | 通過設定序列動畫的起點和終點來初始化一個TweenMax。                                                                                       |
| [TweenMax.delayedCall()][A8]   | 提供一種在設定的時間（或幀）後調用函數的簡單方法。                                                                                       |
| [TweenMax.set()][A9]           | 立即設置目標的屬性值而不產生過渡動畫，相當於0的動畫時間。<br>返回TweenMax對象。                                                          |

[A1]: https://www.tweenmax.com.cn/api/tweenmax/TweenMax()
[A2]: https://www.tweenmax.com.cn/api/tweenmax/TweenMax.to()
[A3]: https://www.tweenmax.com.cn/api/tweenmax/TweenMax.from()
[A4]: https://www.tweenmax.com.cn/api/tweenmax/TweenMax.fromTo()
[A5]: https://www.tweenmax.com.cn/api/tweenmax/TweenMax.staggerTo()
[A6]: https://www.tweenmax.com.cn/api/tweenmax/TweenMax.staggerFrom()
[A7]: https://www.tweenmax.com.cn/api/tweenmax/TweenMax.staggerFromTo()
[A8]: https://www.tweenmax.com.cn/api/tweenmax/TweenMax.delayedCall()
[A9]: https://www.tweenmax.com.cn/api/tweenmax/TweenMax.set()

## 動畫初始設置

|                       | 說明                                                                                                                                                                                                                                                                                |
| --------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [delay][B1]           | 動畫開始之前的延遲秒數（以幀為單位時則為幀數）。                                                                                                                                                                                                                                    |
| [ease][B2]            | 過渡效果的速度曲線（緩動效果）。<br>你可以在動畫的參數中設置各種緩動來控制動畫的變化率，賦予其特定的“感覺”。例如`Elastic.easeOut`或 `Strong.easeInOut`。默認是`Power1.easeOut`。                                                                                                    |
| [paused][B3]          | 如果設置為`true`，動畫將在創建時立即暫停。默認`false `                                                                                                                                                                                                                              |
| [immediateRender][B4] | 立即渲染，默認`false`。<br>一般來說，TweenMax的運動對象會在下一個渲染週期前(也就是下一幀)被渲染到場景中，除非你設置了delay。如果想強制立即渲染，可以把這個參數設為true。<br>另外from()方法的運動對像是立即渲染的（默認true），如果你不想該運動對像被渲染，可以把這個參數設為false。 |
| [overwrite][B5]       | 用來控制同一個對象上有多個動畫時的覆蓋之類的情況。                                                                                                                                                                                                                                  |
| [useFrames][B6]       | 當設置為`true`時，對這個TweenMax對象的時間計算方式基於幀而不是秒，一般幀速約為16.66ms（60幀/秒）。                                                                                                                                                                                  |
| [lazy][B7]            | 延遲渲染。<br>當動畫第一次渲染並讀取其起始值時，將默認自動“延遲渲染”該特定瞬間，這意味著它將嘗試延遲渲染（寫入值）直到最後時間點。這可以提高性能，因為它避免了某些瀏覽器所做的讀/寫/讀/寫佈局顛簸。                                                                                 |
| [autoCSS][B8]         | 自動識別CSS屬性，省略css:{}包裝器。默認true。                                                                                                                                                                                                                                       |
| [callbackScope][B9]   | 用於所有回調的範圍（`onStart`，`onUpdate`，`onComplete`等）。範圍是`this`在任何回調中引用的內容。舊的回調特定範圍屬性（`onStartScope`，`onUpdateScope`，`onCompleteScope`，`onReverseComplete`等）已棄用但仍然有效。                                                                |
| [repeat][B10]         | 動畫在第一次完成後應重複的次數。<br>例如，如果repeat為1，則動畫將總共播放兩次（初始播放加1次重複）。<br>要無限期重複，請使用`-1`。 repeat應該始終是一個整數。                                                                                                                       |
| [repeatDelay][B11]    | 每次重複之間的秒數（或幀）。例如，如果repeat是2並且repeatDelay是1，則動畫將首先播放，然後在重複之前等待1秒，然後再次播放，然後再等待1秒再進行最後的重複。                                                                                                                           |
| [yoyo][B12]           | 如果設置yoyo為`true`，那麼重複的動畫將往返進行。默認為`false`。<br>例如當你設置了repeat:2，如果沒設置yoyo，那麼動畫是這樣的123-123-123，如果設置了yoyo，動畫則是123-321-123                                                                                                         |
| [yoyoEase][B13]       | 定義動畫返回時，緩動效果如何，默認false，返回時的緩動效果按照前進時的反轉。<br>例如，動畫前行效果`ease:Power1.easeOut`，迴轉時則變成是`ease:Power1.easeIn`。<br>如果設置為`true`，迴轉時則與前進相同，為`ease:Power1.easeOut`。<br>也可以設置為特定的ease效果，例如Power2.easeOut。 |
| [startAt][B14]        | 設置動畫屬性開始時的值                                                                                                                                                                                                                                                              |
| [cycle][B15]          | 在stagger（錯開）動畫中定義屬性組。<br>雖然stagger定義了動畫目標使用相同的屬性（如x：100，旋轉：90），但您可以使用cycle來設定一個屬性組（如cycle：{x ：[100，-100]，rotation：[30.60.90]}），<br>或使用函數。（如{x：function（）{return Math.random（）* 200; }}）                 |

[B1]: https://www.tweenmax.com.cn/api/tweenmax/delay
[B2]: https://www.tweenmax.com.cn/api/tweenmax/ease
[B3]: https://www.tweenmax.com.cn/api/tweenmax/paused
[B4]: https://www.tweenmax.com.cn/api/tweenmax/immediateRender
[B5]: https://www.tweenmax.com.cn/api/tweenmax/overwrite
[B6]: https://www.tweenmax.com.cn/api/tweenmax/useFrames
[B7]: https://www.tweenmax.com.cn/api/tweenmax/lazy
[B8]: https://www.tweenmax.com.cn/api/tweenmax/autoCSS
[B9]: https://www.tweenmax.com.cn/api/tweenmax/callbackScope
[B10]: https://www.tweenmax.com.cn/api/tweenmax/repeat
[B11]: https://www.tweenmax.com.cn/api/tweenmax/repeatDelay
[B12]: https://www.tweenmax.com.cn/api/tweenmax/yoyo
[B13]: https://www.tweenmax.com.cn/api/tweenmax/yoyoEase
[B14]: https://www.tweenmax.com.cn/api/tweenmax/startAt
[B15]: https://www.tweenmax.com.cn/api/tweenmax/cycle

## 動畫事件

|                               | 說明                                                                                                                                                                            |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [onComplete][C1]              | 在動畫結束時觸發此回調函數。                                                                                                                                                    |
| [onCompleteParams][C2]        | 傳遞給`onComplete`函數的參數數組                                                                                                                                                |
| [onCompleteScope][C3]         | 定義`onComplete`函數的作用域，即函數內`this`的指向。                                                                                                                            |
| [onReverseComplete][C4]       | 反向播放動畫完成時執行此回調函數。                                                                                                                                              |
| [onReverseCompleteParams][C5] | 傳遞給`onReverseComplete`函數的參數數組                                                                                                                                         |
| [onReverseCompleteScope][C6]  | 定義`onReverseComplete`函數的作用域，即函數內`this`的指向。                                                                                                                     |
| [onStart][C7]                 | 當動畫開始渲染時執行此事件函數，有可能會被執行多次，因為動畫是可以重複開始的。                                                                                                  |
| [onStartParams][C8]           | 傳遞給`onStart`事件函數的參數數組                                                                                                                                               |
| [onStartScope][C9]            | 定義`onStart`函數的作用域，即函數內`this`的指向。                                                                                                                               |
| [onUpdate][C10]               | 當動畫發生改變時(動畫進行中的每一幀)不停的觸發此事件。                                                                                                                          |
| [onUpdateParams][C11]         | 傳遞給`onUpdate`事件函數的參數數組                                                                                                                                              |
| [onUpdateScope][C12]          | 定義`onUpdate`函數的作用域，即函數內`this`的指向。                                                                                                                              |
| [onOverwrite][C13]            | 當一個補間動畫被另外一個補間動畫覆蓋時發生的事件。                                                                                                                              |
| [onRepeat][C14]               | 在每次動畫重複時(repeat)執行此事件函數。                                                                                                                                        |
| [onRepeatParams][C15]         | 傳遞給`onRepeat`事件函數的參數數組                                                                                                                                              |
| [onRepeatScope][C16]          | 定義`onRepeat`函數的作用域，即函數內`this`的指向。                                                                                                                              |
| [.eventCallback()][C17]       | 獲取或者設置事件，例如`onComplete`, `onUpdate`, `onStart`, `onReverseComplete` , `onRepeat` (`onRepeat`只應用在 TweenMax 或者 TimelineMax 實例)，以及應傳遞給該回調的任何參數。 |

[C1]: https://www.tweenmax.com.cn/api/tweenmax/onComplete
[C2]: https://www.tweenmax.com.cn/api/tweenmax/onCompleteParams
[C3]: https://www.tweenmax.com.cn/api/tweenmax/onCompleteScope
[C4]: https://www.tweenmax.com.cn/api/tweenmax/onReverseComplete
[C5]: https://www.tweenmax.com.cn/api/tweenmax/onReverseCompleteParams
[C6]: https://www.tweenmax.com.cn/api/tweenmax/onReverseCompleteScope
[C7]: https://www.tweenmax.com.cn/api/tweenmax/onStart
[C8]: https://www.tweenmax.com.cn/api/tweenmax/onStartParams
[C9]: https://www.tweenmax.com.cn/api/tweenmax/onStartScope
[C10]: https://www.tweenmax.com.cn/api/tweenmax/onUpdate
[C11]: https://www.tweenmax.com.cn/api/tweenmax/onUpdateParams
[C12]: https://www.tweenmax.com.cn/api/tweenmax/onUpdateScope
[C13]: https://www.tweenmax.com.cn/api/tweenmax/onOverwrite
[C14]: https://www.tweenmax.com.cn/api/tweenmax/onRepeat
[C15]: https://www.tweenmax.com.cn/api/tweenmax/onRepeatParams
[C16]: https://www.tweenmax.com.cn/api/tweenmax/onRepeatScope
[C17]: https://www.tweenmax.com.cn/api/tweenmax/eventCallback()


## 動畫播放組件

|                    | 說明                                                                                                                                                                                                  |
| ------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [.play()][D1]      | 控制動畫往正方向播放，可設定開始的時間點。<br>如果suppressEvents保持默認狀態並跳到新的時間點，那麼之前在新舊時間點之間設置的回調或函數不會被觸發，相當於跳過了那些時間點。<br>如果想觸發，設為false。 |
| [.pause()][D2]     | 暫停動畫，可選擇跳轉到特定時間。<br>如果suppressEvents保持默認狀態並跳到新的時間點，那麼之前在新舊時間點之間設置的回調或函數不會被觸發，相當於跳過了那些時間點。<br>如果想觸發，設為false。           |
| [.paused()][D3]    | 獲取或設置動畫的暫停狀態，該狀態指示動畫當前是否已暫停。                                                                                                                                              |
| [.restart()][D4]   | 重新開始動畫/重頭開始。                                                                                                                                                                               |
| [.resume()][D5]    | 恢復播放而不改變方向（前進或後退），可選擇首先跳到特定時間。                                                                                                                                          |
| [.reverse()][D6]   | 控制動畫反向播放。動畫的各種表現都會反轉，例如ease。                                                                                                                                                  |
| [.reversed()][D7]  | 獲取或設置動畫的反轉狀態，指示是否應該反向播放動畫。                                                                                                                                                  |
| [.seek()][D8]      | 不改變狀態（播放、暫停、方向）的情況下直接跳轉到某個時間點。                                                                                                                                          |
| [.timeScale()][D9] | 獲取/設定動畫速度，默認為1。<br>例如0.5為慢速，2為快速。<br>如果設置則返回此動畫實例便於鍊式調用，如不設置則返回時間調節比例。                                                                        |

[D1]: https://www.tweenmax.com.cn/api/tweenmax/play()
[D2]: https://www.tweenmax.com.cn/api/tweenmax/pause()
[D3]: https://www.tweenmax.com.cn/api/tweenmax/paused()
[D4]: https://www.tweenmax.com.cn/api/tweenmax/restart()
[D5]: https://www.tweenmax.com.cn/api/tweenmax/resume()
[D6]: https://www.tweenmax.com.cn/api/tweenmax/reverse()
[D7]: https://www.tweenmax.com.cn/api/tweenmax/reversed()
[D8]: https://www.tweenmax.com.cn/api/tweenmax/seek()
[D9]: https://www.tweenmax.com.cn/api/tweenmax/timeScale()

## 動畫屬性調整

|                        | 說明                                                                                                                                                                                                                                                                                                                                                                                                                   |
| ---------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [.duration()][E1]      | 獲取或設置動畫持續的時間。                                                                                                                                                                                                                                                                                                                                                                                             |
| [.totalDuration()][E2] | 獲取或設定全部重複的動畫的持續時間                                                                                                                                                                                                                                                                                                                                                                                     |
| [.time()][E3]          | 獲取或設置當前動畫時間。                                                                                                                                                                                                                                                                                                                                                                                               |
| [.totalTime()][E4]     | 獲取或設置總的動畫時長。                                                                                                                                                                                                                                                                                                                                                                                               |
| [.progress()][E5]      | 獲取或者設置單次動畫的進程（從0到1）                                                                                                                                                                                                                                                                                                                                                                                   |
| [.totalProgress()][E6] | 獲取或者設置總的動畫進程（從0到1）                                                                                                                                                                                                                                                                                                                                                                                     |
| [.delay()][E7]         | 獲取或者設置動畫的開始延遲秒數（幀）。                                                                                                                                                                                                                                                                                                                                                                                 |
| [.invalidate()][E8]    | 刷新任何內部記錄的開始/結束值，如果您想要重新啟動動畫而不恢復到以前記錄的任何起始值，這將非常有用。                                                                                                                                                                                                                                                                                                                    |
| [.isActive()][E9]      | 指示動畫當前是否處於活動狀態（表示該虛擬播放頭在該實例的時間跨度內活動移動，並且沒有暫停，也沒有任何其祖先時間軸）。<br>因此，如果在補間中間，則它處於active狀態，但在補間完成後（或在補間開始前），該補間不活動（返回false）。<br>如果它被暫停或者被放置在暫停的時間軸內（或者其任何祖先時間軸被暫停），isActive() 則將返回 false。<br>如果播放頭直接位於動畫開始時間的頂部（即使播放頭尚未完成渲染），則視為“有效”。 |
| [.updateTo()][E10]     | 更新動畫的值即使動畫正在運行中。<br>`updateTo()`僅適合改變非插件值，因此如果你想改變插件屬性（如CSSPlugin），這個方法不太適用，因為插件的計算方式較為複雜。<br>例如{x:500}無效，需要寫成{css: {x:500}}。                                                                                                                                                                                                               |
| [.startTime()][E11]    | 獲取/設定動畫在其父時間軸上的開始時間。                                                                                                                                                                                                                                                                                                                                                                                |
| [.endTime()][E12]      | 獲取動畫在父時間軸上的結束時間。                                                                                                                                                                                                                                                                                                                                                                                       |
| [.repeat()][E13]       | 獲取或者設定動畫在第一次完成後的重複次數。                                                                                                                                                                                                                                                                                                                                                                             |
| [.repeatDelay()][E14]  | 獲取或者設置每次重複動畫之間的間隔時間（秒）                                                                                                                                                                                                                                                                                                                                                                           |
| [.yoyo()][E15]         | 獲取或設置補間動畫的yoyo的狀態。 如果你要使用yoyo的話，還需要設置repeat（動畫重複次數）                                                                                                                                                                                                                                                                                                                                |

[E1]: https://www.tweenmax.com.cn/api/tweenmax/duration()
[E2]: https://www.tweenmax.com.cn/api/tweenmax/totalDuration()
[E3]: https://www.tweenmax.com.cn/api/tweenmax/time()
[E4]: https://www.tweenmax.com.cn/api/tweenmax/totalTime()
[E5]: https://www.tweenmax.com.cn/api/tweenmax/progress()
[E6]: https://www.tweenmax.com.cn/api/tweenmax/totalProgress()
[E7]: https://www.tweenmax.com.cn/api/tweenmax/delay()
[E8]: https://www.tweenmax.com.cn/api/tweenmax/invalidate()
[E9]: https://www.tweenmax.com.cn/api/tweenmax/isActive()
[E10]: https://www.tweenmax.com.cn/api/tweenmax/updateTo()
[E11]: https://www.tweenmax.com.cn/api/tweenmax/startTime()
[E12]: https://www.tweenmax.com.cn/api/tweenmax/endTime()
[E13]: https://www.tweenmax.com.cn/api/tweenmax/repeat()
[E14]: https://www.tweenmax.com.cn/api/tweenmax/repeatDelay()
[E15]: https://www.tweenmax.com.cn/api/tweenmax/yoyo()

## 實例屬性

|                                  | 說明                                                                                                                                                                                                                                                                                                                         |
| -------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [.data][F1]                      | 可用於存儲你需要的數據。                                                                                                                                                                                                                                                                                                     |
| [TweenLite.defaultEase][F2]      | 用於更改`TweenLite`默認的緩動方式，默認的緩動方式是`Power1.easeOut`。                                                                                                                                                                                                                                                        |
| [TweenLite.defaultOverwrite][F3] | 設置`TweenLite`的默認`overwrite`模式。 可選值包括`auto`, `all`, `none`, `allOnStart`, `concurrent`, `preexisting`。默認是`auto`。                                                                                                                                                                                            |
| [TweenLite.onOverwrite][F4]      | 當一個補間動畫被另外一個補間動畫覆蓋時產生的事件函數。                                                                                                                                                                                                                                                                       |
| [TweenLite.selector][F5]         | 當動畫接收字符串作為其目標時使用的選擇器引擎（如jQuery，但默認為document.querySelectorAll()）。<br>TweenMax的對象選擇器接受dom或者string作為目標，如`#myID`。<br>TweenMax不依賴jQuery，但如果引入了jQuery，TweenMax會優先使用jQuery的選擇器，如`p:first`，否則回退到document.querySelectorAll()及document.getElementById()。 |
| [.target][F6]                    | 獲取動畫的目標對象。                                                                                                                                                                                                                                                                                                         |
| [.timeline][F7]                  | 獲取動畫的父級時間軸對象（只讀）。                                                                                                                                                                                                                                                                                           |
| [.vars][F8]                      | 一個存儲了傳遞給構造器的配置變量的對象。包含動畫選項和回調函數等。例如`delay`、`paused`、`onComplete`。                                                                                                                                                                                                                      |
| [TweenMax.ticker][F9]            | 設置動畫核心引擎，每當引擎update時這個對象將分配tick事件，你可以添加你自己的listener來運行自定義邏輯（非常適合遊戲開發人員） 。                                                                                                                                                                                              |

[F1]: https://www.tweenmax.com.cn/api/tweenmax/data
[F2]: https://www.tweenmax.com.cn/api/tweenmax/TweenLite.defaultEase
[F3]: https://www.tweenmax.com.cn/api/tweenmax/TweenLite.defaultOverwrite
[F4]: https://www.tweenmax.com.cn/api/tweenmax/TweenLite.onOverwrite
[F5]: https://www.tweenmax.com.cn/api/tweenmax/TweenLite.selector
[F6]: https://www.tweenmax.com.cn/api/tweenmax/target
[F7]: https://www.tweenmax.com.cn/api/tweenmax/timeline
[F8]: https://www.tweenmax.com.cn/api/tweenmax/vars
[F9]: https://www.tweenmax.com.cn/api/tweenmax/TweenMax.ticker

## 實例方法

|                                     | 說明                                                                                                                                                                                                                                                                                                                                                 |
| ----------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [TweenMax.getTweensOf()][G1]        | 用來獲取某個物體上的所有TweenLite、TweenMax對象。<br>如果my_mc上使用了不止一個的緩動效果，那麼這裡將返回一個數組，數組中是不同的緩動效果的實例，可以用來對每個緩動進行實時的控制。                                                                                                                                                                   |
| [TweenMax.getAllTweens()][G2]       | 獲取所有動畫實例的數組（或時間軸，不包括根時間軸）。                                                                                                                                                                                                                                                                                                 |
| [.kill()][G3]                       | 消滅整個動畫或部分參數。返回self便於鍊式調用。                                                                                                                                                                                                                                                                                                       |
| [TweenMax.killDelayedCallsTo()][G4] | 立刻殺死所有延遲執行函數。                                                                                                                                                                                                                                                                                                                           |
| [TweenMax.killTweensOf()][G5]       | 移除指定對象的所有動畫（或特定動畫屬性）或移除延遲執行函數。                                                                                                                                                                                                                                                                                         |
| [TweenMax.killAll()][G6]            | 刪除所有補間動畫或延遲執行函數或時間軸，可選擇強制它們先完成。                                                                                                                                                                                                                                                                                       |
| [TweenMax.killChildTweensOf()][G7]  | 刪除/殺死（kill）特定DOM元素的子元素的所有補間動畫，可選擇強制它們首先完成。                                                                                                                                                                                                                                                                         |
| [TweenLite.render()][G8]            | 強制渲染所有活動的補間動畫。<br>這可能會很有用，例如你設置了一堆`from()`補間動畫，然後你需要強制立即渲染（甚至是lazy補間動畫），以避免在渲染之前發生短暫的延遲。                                                                                                                                                                                     |
| [TweenMax.lagSmoothing()][G9]       | 卡頓平滑補償機制，當你的動畫卡住時平分卡頓的時間使其看起來不是很卡。<br>`lagSmoothing()`允許你控制在引擎的兩次tick（update）之間經過太多時間時發生的情況，調整核心計時機制以補償並避免跳幀。<br>lagSmoothing()的默認閾值是500ms，調整幀速是33ms。也就是說，如果你的卡頓超過500ms，那麼你的幀速降至33ms以平分這些卡頓，跳幀完成後幀速恢復為默認幀速。 |
| [TweenMax.globalTimeScale()][G10]   | 用來讀取或設置所有動畫的全局播放速率，例如1為正常速度，0.5為一半速度，2為2倍速度，能取的最小值為0.0001。                                                                                                                                                                                                                                             |
| [TweenMax.isTweening()][G11]        | 判斷一個元素是否處於動畫激活狀態，返回true或false。元素在時間軸上反方向移動或者加/減速時會出現錯判。                                                                                                                                                                                                                                                 |
| [TweenMax.pauseAll()][G12]          | 暫停所有動畫或時間軸或回調函數。                                                                                                                                                                                                                                                                                                                     |
| [TweenMax.resumeAll()][G13]         | 恢復運行所有暫停的動畫或時間軸或回調函數。                                                                                                                                                                                                                                                                                                           |

[G1]: https://www.tweenmax.com.cn/api/tweenmax/TweenMax.getTweensOf()
[G2]: https://www.tweenmax.com.cn/api/tweenmax/TweenMax.getAllTweens()
[G3]: https://www.tweenmax.com.cn/api/tweenmax/kill()
[G4]: https://www.tweenmax.com.cn/api/tweenmax/TweenMax.killDelayedCallsTo()
[G5]: https://www.tweenmax.com.cn/api/tweenmax/TweenMax.killTweensOf()
[G6]: https://www.tweenmax.com.cn/api/tweenmax/TweenMax.killAll()
[G7]: https://www.tweenmax.com.cn/api/tweenmax/TweenMax.killChildTweensOf()
[G8]: https://www.tweenmax.com.cn/api/tweenmax/TweenLite.render()
[G9]: https://www.tweenmax.com.cn/api/tweenmax/TweenMax.lagSmoothing()
[G10]: https://www.tweenmax.com.cn/api/tweenmax/TweenMax.globalTimeScale()
[G11]: https://www.tweenmax.com.cn/api/tweenmax/TweenMax.isTweening()
[G12]: https://www.tweenmax.com.cn/api/tweenmax/TweenMax.pauseAll()
[G13]: https://www.tweenmax.com.cn/api/tweenmax/TweenMax.resumeAll()