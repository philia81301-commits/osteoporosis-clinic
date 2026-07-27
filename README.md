# 骨質疏鬆門診工具

門診自用的三個單頁工具，純 HTML + CSS + 原生 JavaScript，無外部相依（無 CDN、無外部字型），可離線使用。

**線上版**：https://philia81301-commits.github.io/osteoporosis-clinic/

| 檔案 | 內容 | 對象 |
| --- | --- | --- |
| `index.html` | 入口頁 | — |
| `fracture-risk.html` | 骨折風險評估工具（骨折史 / DXA / FRAX → 風險分層、治療強度、次發性骨鬆 workup） | 醫療人員 |
| `drug-selection.html` | 藥物選擇工具（選藥決策、藥物比較表、用藥衛教口語稿、停藥與銜接） | 醫療人員 |
| `patient-education.html` | 病人衛教單張（含互動式鈣質攝取計算） | 病人 |

## 說明

- 所有計算都在瀏覽器本機完成，不傳送、不儲存任何輸入資料。表單每次載入都會清空，避免殘留前一位病人的資料。
- 風險評估與藥物選擇為**決策輔助與教學用途**，非硬性診斷或處方標準。
- 健保給付條文（門檻、療程年限、換藥規定）刻意未寫死，僅註明需核對當期公告。

## 更新流程

1. 改本資料夾內的 HTML
2. `git commit` 並 push 到 main → GitHub Pages 自動重建（約 1–2 分鐘）
3. 同步一份到 Google Drive `我的雲端硬碟\osteoporosis\` 對應子資料夾（Drive 上沿用中文檔名）

Drive 對應：`01_風險評估`／`02_衛教素材`／`03_藥物選擇`。
