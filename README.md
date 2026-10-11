# 憲行法題卡（PWA 手機 App）

司法官・律師第一試 103–115 年「綜合法學（一）」憲法與行政法 695 題的隨機練習 App。放上 GitHub Pages 後，可以在 iPhone 或 Android 加入主畫面，像一般 App 一樣使用，沒有網路也能刷題。

## 檔案說明

| 檔案 | 用途 |
|---|---|
| `index.html` | App 主畫面 |
| `questions.js` | 題庫資料（695 題、答案、解析） |
| `sw.js` | 離線快取；每次更新題庫或頁面時要改裡面的版本號 |
| `manifest.webmanifest` | App 名稱、圖示、主題色 |
| `icons/` | App 圖示 |
| `.nojekyll` | 讓 GitHub Pages 原樣發布檔案（這是隱藏檔，一起上傳即可） |

## 一、放上 GitHub Pages（只需做一次，約 10 分鐘）

1. 登入 <https://github.com>（沒有帳號就先免費註冊）。
2. 右上角 **＋** → **New repository**。
   - Repository name 填英文，例如 `law-quiz`。
   - 選 **Public**。免費方案的 GitHub Pages 只能用公開儲存庫，題目是考選部公開的試題，公開沒有問題。
   - 按 **Create repository**。
3. 在新建立的儲存庫頁面，點 **uploading an existing file** 的連結（或 **Add file → Upload files**）。
4. 把解壓縮後資料夾 **裡面的所有檔案和 `icons` 資料夾** 一起拖進網頁。
   - 要拖的是資料夾的「內容」，不是外層資料夾本身；`index.html` 必須在最上層。
   - `.nojekyll` 是隱藏檔，Mac 可在 Finder 按 `Command + Shift + .` 顯示後一起拖入。漏傳也能運作，只是建議放上。
5. 拉到頁面下方按 **Commit changes**。
6. 到儲存庫的 **Settings → Pages**：
   - Source 選 **Deploy from a branch**
   - Branch 選 **main**，資料夾選 **/ (root)**，按 **Save**。
7. 等 1～2 分鐘，重新整理 Settings → Pages，上方會出現網址，格式為：
   `https://你的帳號.github.io/law-quiz/`

## 二、安裝到手機

**iPhone / iPad**
1. 用 **Safari** 打開上面的網址（Chrome 等其他瀏覽器在 iOS 上不一定能安裝）。
2. 點畫面下方的 **分享** 按鈕（方框加向上箭頭）。
3. 選 **加入主畫面** → **新增**。
4. 之後從主畫面的「憲行法題卡」圖示開啟。

**Android**
1. 用 **Chrome** 打開網址。
2. 頁面上方會出現「安裝 App」按鈕，點它即可；或點右上角 **⋮** → **安裝應用程式**（或「加到主畫面」）。

第一次開啟時要有網路，App 會把題庫下載到手機；之後就能離線使用。

## 三、之後要更新題庫或頁面

1. 在 GitHub 儲存庫按 **Add file → Upload files**，上傳新的 `questions.js` 或 `index.html`（同名會覆蓋）。
2. **同時**打開 `sw.js`，按鉛筆圖示編輯，把第一行的版本號改大，例如 `const VERSION = "v1";` 改成 `"v2"`，再 Commit。
3. 手機下次開啟 App 時會出現「題庫有新版本」，點 **立即更新** 即可。

沒有改版本號的話，手機會一直用舊的快取。

## 注意事項

- **紀錄存在各自的手機上**：成績、錯題本只存在這支手機的這個 App 裡，不會和其他裝置同步。刪除 App 或清除 Safari／Chrome 網站資料會一併清掉。
- **答案以官方公布為準**：題目與答案依考選部公布之試題、標準答案（含更正答案）。標有「⚠️」的解析表示命題後法制或實務已改變，作答依當年官方答案，學習時請留意現行規定。
- **字型**：連網時會載入思源宋體／黑體；離線且尚未快取時改用手機內建中文字型，不影響使用。
