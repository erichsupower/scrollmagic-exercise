# GreenSock

[GreenSock 英文官網](https://greensock.com/)

[對岸中文參考網站](https://www.tweenmax.com.cn/)

<!-- toc -->

- [GreenSock](#greensock)
  - [TweenMax 中文手冊章節劃分](#tweenmax-%e4%b8%ad%e6%96%87%e6%89%8b%e5%86%8a%e7%ab%a0%e7%af%80%e5%8a%83%e5%88%86)

<!-- tocstop -->

TweenLite / TweenMax 是 GreenSock 的核心動畫工具。

基本的動畫包含四個要素：動畫目標，啟點狀態，終點狀態，補間效果。
例如將一個 div 從 opacity：1 經過 5 秒鐘降低至 opacity：0

```js
TweenLite.fromTo('div', 5, {opacity:1}, {opacity:0});
//動畫目標：div
//補間：5秒完成狀態改變
//起點狀態：opacity:1
//終點狀態：opacity:0
```

起點狀態經常可以省略，例如div以當前位置為起點，向右移動300px：

```js
TweenLite.to('div', 5, {x:300});
```

**TweenMax.min.js** 已經包含 CSS 屬性動畫的支援插件(CSSPlugin)。如果使用 **TweenLite.min.js**，需要另外加載**CSSPlugin.min.js**。

## TweenMax 中文手冊章節劃分

- 01節-動畫結構：
設置動畫目標和起點，終點狀態的動畫的結構化方法
- 02節-動畫初始設置：
對動畫進行一些初始化設置，如重複次數（repeat）緩動方式（ease）等
- 03節-介紹動畫事件函數：
如開始事件（onStart），結束事件（onComplete），返回事件（onReverseComplete）等
- 04節-動畫播放組件：
動畫控制組件如播放（play），暫停（pause），重新播放（restart）等
- 05節-動畫屬性調整：
可以獲取到的動畫屬性以及調整他們的方法，如動畫時長（time），播放進度（progress）
- 06節-實例屬性：
介紹了 TweenLite / TweenMax 實例的屬性設置，如設置選擇器，讀取時間軸等
- 07節-實例方法：
介紹 TweenLite / TweenMax 實例的函數方法，如刪除動畫，動畫渲染