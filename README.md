# scrollmagic

## About the Library

ScrollMagic 的開發遵循以下原則：

- 優化性能
- 輕量級（gzip壓縮為6KB）
- 靈活性和可擴展性
- 相容移動裝置
- 事件管理
- 支持響應式網頁設計
- object oriented programming and object chaining
- 可讀，集中的代碼和直觀的開發
- 同時支持x和y方向對齊（即使在一頁上也是如此）
- 支持在div容器內滾動（即使一頁上有多個）
- extensive debugging and logging capabilities
- 詳細文件
- 許多應用實例

## Availability (for npm)

Option 1: CDN

壓縮版本：
```
http://cdnjs.cloudflare.com/ajax/libs/ScrollMagic/2.0.7/ScrollMagic.min.js
```

所有插件和未壓縮版本：
```
http://cdnjs.cloudflare.com/ajax/libs/ScrollMagic/2.0.7/plugins/debug.addIndicators.js

http://cdnjs.cloudflare.com/ajax/libs/ScrollMagic/2.0.7/plugins/debug.addIndicators.min.js
```

Option 2: GitHub

    git clone git://github.com/janpaepke/ScrollMagic.git

Option 3: npm

    npm install scrollmagic

## Installation

```html
<script src="js/scrollmagic/uncompressed/ScrollMagic.js"></script>
```

## Basic Usage

```js
// 初始化controller
var controller = new ScrollMagic.Controller();

// 建立Scene
new ScrollMagic.Scene({
    duration: 100, // Scene持續100px的滾動距離
    offset: 50 // 滾動50px後開始這個Scene
})
    .setPin('#my-sticky-element') // 在Scene的持續時間內，套用效果到指定元素
    .addTo(controller); // 將Scene指派給controller
```