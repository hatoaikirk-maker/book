# 北港義民廟 電子書（真實翻頁書）

一個「跟真的書一樣」的翻頁電子書：手機單頁＋真實捲頁翻動、電腦跨兩頁像翻開的書。
用的是 StPageFlip 翻頁引擎，**已下載到 lib/ 資料夾（不走 CDN）**，可直接放上 GitHub Pages。

## 📁 檔案結構（上傳時整包都要）
```
義民廟電子書/
├── index.html                 ← 電子書程式
├── lib/
│   ├── page-flip.browser.js   ← 翻頁引擎（必須一起上傳）
│   └── stPageFlip.css
├── images/                    ← 把每一頁圖片放這裡
│   ├── page-01.jpg
│   ├── page-02.jpg
│   └── ...
└── README.md
```

## 🖼️ 放入你的書頁
1. 每頁存成圖片，丟進 `images/`，命名 `page-01.jpg`、`page-02.jpg`…（兩位數，順序才對）。
2. 打開 `index.html` 改最上面 CONFIG：`TITLE` 書名、`EXT` 副檔名、`TOTAL` 總頁數。
   > 圖還沒放時，會顯示「第 N 頁」示意頁；放圖後自動替換。
3. 建議所有頁圖片用**同一個長寬比**（例如都直式），翻起來最整齊；程式會用第 1 頁的比例決定書的比例。

## 🚀 上架到 GitHub Pages
1. GitHub 建 repo，把整個資料夾內容上傳（**index.html、lib/、images/ 都要**）。
2. repo → Settings → Pages → Source 選「Deploy from a branch」→ Branch 選 main、資料夾 /(root) → Save。
3. 等一兩分鐘，得到網址 `https://你的帳號.github.io/repo名/`。

## 🎮 操作方式
- **手機（90% 使用者）**：單頁顯示，手指拖曳書頁邊緣即可真實翻頁；也可點下方 ‹ › 。
- **電腦**：跨兩頁像翻開的書，滑鼠拖頁角或點邊緣翻頁、← → 鍵、空白鍵、⛶ 全螢幕。
- 閒置 3 秒工具列自動隱藏。

## 🔒 安全性
- 翻頁引擎已下載到本機 lib/，**不引用任何 CDN**，無供應鏈風險。
- 不使用 eval、不用 innerHTML 塞外部資料，頁碼用 textContent 輸出。
- 純靜態、無後端、無使用者輸入。
