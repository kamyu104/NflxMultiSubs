TODO
====
歡迎送 PR！但請保持本套件簡單易用，太複雜的功能可能不會被 merge 哦！



Bugfixes
--------
- [ ] 首次載入 image-based 的第二字幕（如中文、日文）時很慢
    - 因為 image-based subtitles 是個好幾 MB 的 ZIP archive，大概要抓個 30 秒
    - 下載速度慢的原因不明，暫時猜測是我們抓字幕時亂挑 CDN 導致



Features
--------
- [ ] 新增設定介面，在 pop-up 裡可以即時設整並預覽
    - 透過 message port 改 `gRenderOptions` 然後呼叫 `gRendererLoop.setRenderDirty()` 強迫重繪即可即時預覽
    - 考慮到使用者的不同裝置可能需要不同設定，建議使用 `chrome.storage.local` 而非一般推薦的 `chrome.storage.sync` 來存放設定值

- [ ] 移植至 Firefox
    - 同為 WebExtension 架構，整體差異不大
    - 有些地方的 `chrome` 要改用 `browser`，如 `browser.webRequest.xxx`
    - CSS style 如果有 vendor prefix 的也需要留意

- [ ] 更新之後跳個 What's new 頁面給使用者看看


Miscellaneous
-------------
- [ ] 改進效能
    - 目前很硬幹地在 `window.requestAnimationFrame()` 裡跑一堆東西
    - 這個 renderer loop 應該可以少做一點事情（像是不必要的 DOM queries ……）

- [ ] 改進開發環境，目前都還挺土砲的 XD
    - 每次都會重 build 所有東西，也沒有過 linter
    - 打算整合 [webpack](https://webpack.js.org/) 或 [Rollup](https://rollupjs.org/guide/en)

- [ ] 將文件都變成中英雙語？

- [ ] 原始碼重構（好吧，這應該是個永遠不會被打勾的持續項目 XD）
