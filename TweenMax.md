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
|                                | 說明                                                           |
| ------------------------------ | -------------------------------------------------------------- |
| [TweenMax()][A1]               | TweenMax的構造函數，用來構建一個TweenMax對象。                 |
| [TweenMax.to()][A2]            | 此方法用於創建一個從當前屬性到指定目標屬性的TweenMax動畫對象。 |
| [TweenMax.from()][A3]          |                                                                |
| [TweenMax.fromTo()][A4]        |                                                                |
| [TweenMax.staggerTo()][A5]     |                                                                |
| [TweenMax.staggerFrom()][A6]   |                                                                |
| [TweenMax.staggerFromTo()][A7] |                                                                |
| [TweenMax.delayedCall()][A8]   |                                                                |
| [TweenMax.set()][A9]           |                                                                |

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

|                       | 說明 |
| --------------------- | ---- |
| [delay][B1]           |      |
| [ease][B2]            |      |
| [paused][B3]          |      |
| [immediateRender][B4] |      |
| [overwrite][B5]       |      |
| [useFrames][B6]       |      |
| [lazy][B7]            |      |
| [autoCSS][B8]         |      |
| [callbackScope][B9]   |      |
| [repeat][B10]         |      |
| [repeatDelay][B11]    |      |
| [yoyo][B12]           |      |
| [yoyoEase][B13]       |      |
| [startAt][B14]        |      |
| [cycle][B15]          |      |

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

|                               | 說明 |
| ----------------------------- | ---- |
| [onComplete][C1]              |      |
| [onCompleteParams][C2]        |      |
| [onCompleteScope][C3]         |      |
| [onReverseComplete][C4]       |      |
| [onReverseCompleteParams][C5] |      |
| [onReverseCompleteScope][C6]  |      |
| [onStart][C7]                 |      |
| [onStartParams][C8]           |      |
| [onStartScope][C9]            |      |
| [onUpdate][C10]               |      |
| [onUpdateParams][C11]         |      |
| [onUpdateScope][C12]          |      |
| [onOverwrite][C13]            |      |
| [onRepeat][C14]               |      |
| [onRepeatParams][C15]         |      |
| [onRepeatScope][C16]          |      |
| [.eventCallback()][C17]       |      |

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

|                    | 說明 |
| ------------------ | ---- |
| [.play()][D1]      |      |
| [.pause()][D2]     |      |
| [.paused()][D3]    |      |
| [.restart()][D4]   |      |
| [.resume()][D5]    |      |
| [.reverse()][D6]   |      |
| [.reversed()][D7]  |      |
| [.seek()][D8]      |      |
| [.timeScale()][D9] |      |

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

|                        | 說明 |
| ---------------------- | ---- |
| [.duration()][E1]      |      |
| [.totalDuration()][E2] |      |
| [.time()][E3]          |      |
| [.totalTime()][E4]     |      |
| [.progress()][E5]      |      |
| [.totalProgress()][E6] |      |
| [.delay()][E7]         |      |
| [.invalidate()][E8]    |      |
| [.isActive()][E9]      |      |
| [.updateTo()][E10]     |      |
| [.startTime()][E11]    |      |
| [.endTime()][E12]      |      |
| [.repeat()][E13]       |      |
| [.repeatDelay()][E14]  |      |
| [.yoyo()][E15]         |      |

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

|                                  | 說明 |
| -------------------------------- | ---- |
| [.data][F1]                      |      |
| [TweenLite.defaultEase][F2]      |      |
| [TweenLite.defaultOverwrite][F3] |      |
| [TweenLite.onOverwrite][F4]      |      |
| [TweenLite.selector][F5]         |      |
| [.target][F6]                    |      |
| [.timeline][F7]                  |      |
| [.vars][F8]                      |      |
| [TweenMax.ticker][F9]            |      |

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

|                                     | 說明 |
| ----------------------------------- | ---- |
| [TweenMax.getTweensOf()][G1]        |      |
| [TweenMax.getAllTweens()][G2]       |      |
| [.kill()][G3]                       |      |
| [TweenMax.killDelayedCallsTo()][G4] |      |
| [TweenMax.killTweensOf()][G5]       |      |
| [TweenMax.killAll()][G6]            |      |
| [TweenMax.killChildTweensOf()][G7]  |      |
| [TweenLite.render()][G8]            |      |
| [TweenMax.lagSmoothing()][G9]       |      |
| [TweenMax.globalTimeScale()][G10]   |      |
| [TweenMax.isTweening()][G11]        |      |
| [TweenMax.pauseAll()][G12]          |      |
| [TweenMax.resumeAll()][G13]         |      |

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