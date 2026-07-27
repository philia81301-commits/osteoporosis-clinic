# 骨質疏鬆門診工具

**製作：潘湘如醫師｜家醫科**　·　版本 v1.0（2026-07-28）

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

本 repo 是工具的唯一位置。沒有 git 的電腦（例如院內電腦）：直接在 GitHub 網頁上編輯檔案並 commit，Pages 同樣會自動重建；要用工具則直接開線上版網址即可。

Google Drive 只保留「專案總覽」Google Doc 當專案基地；原本三個子資料夾內的 HTML 快照已於 2026-07-28 刪除，避免有人下載到過時版本。

改動內容時記得同步更新四個頁面頁尾的**版本號與日期**，那是使用者判斷手上是不是最新版的唯一依據。

## 回報問題

用本 repo 的 [Issues](https://github.com/philia81301-commits/osteoporosis-clinic/issues) 回報錯誤或建議。

## 授權與製作

© 2026 潘湘如醫師．本專案採 [CC BY-NC-ND 4.0](https://creativecommons.org/licenses/by-nc-nd/4.0/deed.zh-hant) 授權：
可自由轉貼分享（含印給病人、教學展示），須署名原作者，禁止商業使用與改作。詳見 [LICENSE](LICENSE)。

臨床內容（風險分層邏輯、選藥決策規則、衛教文案）由潘湘如醫師企劃、撰寫並審定；介面與程式實作由 Claude（Claude Code）協助。
