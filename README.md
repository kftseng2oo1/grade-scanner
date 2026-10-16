# 成績掃描記錄系統

拍考卷，AI 自動辨識學號與分數，對應到班級名冊並記錄成績，最後匯出 Excel。

**線上使用**：https://kftseng2oo1.github.io/grade-scanner/

## 主要功能
- **班級名冊**：多班級管理，手動新增或從 Excel（需有「學號」「姓名」欄）匯入學生
- **📷 掃描辨識**：批次上傳考卷照片，由 Claude 辨識學號與分數；學號辨識有誤時用模糊比對推薦最接近的學生
- 考試類別：平時考核、期中考試、期末考試
- 也可手動輸入成績（輸入學號尾數即可快速選人）
- **📊 成績總覽**：排序、等第標示、匯出 Excel
- 亮色／暗色主題

## 技術與依賴
- 單檔 HTML PWA（`index.html` 內含全部 HTML/CSS/JS），`manifest.json` + `sw.js` 提供安裝到主畫面與離線快取。
- AI 辨識：`claude-sonnet-4-20250514`，經 `arcar.kftseng2oo1.workers.dev` 代理
- Excel 讀寫使用 cdnjs 上的 SheetJS
- 資料存在瀏覽器 localStorage

## 備註
- repo 內另有 `grade-scanner-pwa.html`，與 `index.html` 內容略有差異，應為舊版；目前缺少 `manifest.json` 與 `sw.js`，所以還不能安裝成 App。
