# 骨質疏鬆門診工具（專案藍圖）

> 本檔為跨 Agent 通用的專案藍圖（AGENTS.md 開放標準）。任何 Agent 的每個 session 都應先讀本檔＋`handoff.md`。

## 專案簡介

建立一套完整的骨質疏鬆症門診工具，涵蓋三個環節：**風險評估**（找出高風險病人、量化骨折風險）、**衛教**（讓病人聽得懂、願意配合）、**藥物選擇**（依病人狀況選對藥、講清楚用法與注意事項）。三個工具都是自帶樣式的單頁 HTML，純原生 JavaScript、無任何外部相依，可離線使用，並以公開網址供院內外同事直接開啟。

負責人／著作權人：**潘湘如醫師**（家醫科；本人亦負責減重門診）。建立日期：2026-07-27。

## 關鍵時程

<!-- 目前沒有明定的對外時程；門診試用回饋後再排修正版 -->

## 目標與路線圖

- [x] 階段一：建立專案工作區與資料夾結構（2026-07-27）
- [x] 階段二：01 骨折風險評估工具（骨折史 / DXA / FRAX → 風險分層、治療強度、次發性骨鬆 workup）
- [x] 階段三：02 病人衛教單張（含互動式鈣質攝取計算）
- [x] 階段四：03 藥物選擇工具（選藥決策、藥物比較表、用藥衛教口語稿、停藥與銜接）
- [x] 階段五：整套上線 GitHub Pages，取得可分享的公開網址（2026-07-27）
- [x] 階段六：專案初始化至第三層級（2026-07-28）
- [x] 階段七：署名、授權與位置整理（2026-07-28）—— 頁尾署名＋版本號、CC BY-NC-ND 4.0＋LICENSE、Drive 快照刪除、工作副本搬離 OneDrive
- [ ] 階段八：門診實際試用後的回饋修正
- [ ] 階段九：決定是否加入固定的院內版健保給付欄（需提供目前依循的版本）
- [ ] 階段十：產出給 OpenCode 學習的交接包（AGENTS.md + 成果副本，重點寫決策理由與踩過的坑）
- [ ] 階段十一：把可複用的部分做成「醫療工具專案模板」（頁尾／授權／臨床守則），供肌少症等新專案套用

## 資料夾結構

```
<工作副本路徑>\osteoporosis-clinic\   ← 每台電腦各自 clone；GitHub 才是 canonical
   家用電腦：C:\projects\osteoporosis-clinic\（2026-07-28 從 OneDrive 搬出）
   醫院電腦：自行 clone，路徑同樣放在 OneDrive 以外
├── agents.md                  本檔（專案藍圖）
├── handoff.md                 交接檔（開工必讀、收工必更新）
├── README.md                  repo 說明與更新流程
├── index.html                 入口頁（三張卡片連到三個工具）
├── fracture-risk.html         骨折風險評估工具（醫療人員）
├── drug-selection.html        藥物選擇工具（醫療人員）
└── patient-education.html     病人衛教單張（給病人）
```

**Google Drive**：`我的雲端硬碟\osteoporosis\`
- `專案總覽 — 骨質疏鬆風險評估、衛教及藥物選擇`（Google Doc，**專案基地**，進度與待辦寫在那裡）
- `01_風險評估`／`02_衛教素材`／`03_藥物選擇` 三個資料夾內的 HTML 為 2026-07-27 快照，**已停止維護**

## 同步層級（本專案初始化至第三層級）

| 層級 | 平台 | 位置 | 讀取時機 |
|------|------|------|---------|
| L1 | 本地（各電腦的 clone，**不放 OneDrive**） | `agents.md`＋`handoff.md` | 每個 session |
| L2 | GitHub | [philia81301-commits/osteoporosis-clinic](https://github.com/philia81301-commits/osteoporosis-clinic)（**公開**，供 GitHub Pages） | 指定時 |
| L3 | Obsidian | `osteoporosis/專案工作流程.md` | 有需要時 |

**線上版（門診與分享用，免登入）**：https://philia81301-commits.github.io/osteoporosis-clinic/

## 更新流程

兩台電腦流程相同（都有 Claude Code 與 git）：

1. **開工先 `git pull`**
2. 改 HTML
3. `git commit` + `git push` → GitHub Pages 約 1–2 分鐘自動重建
4. **收工更新 `handoff.md` 並 push**

**就這樣。**（2026-07-28 起已停止維護 Drive 的 HTML 鏡像，見下方說明）

- 家用電腦（DESKTOP-LVSV9Q5）：工作副本在 `C:\projects\osteoporosis-clinic\`
- 醫院電腦：有 Claude Code 與 GitHub，但**無法安裝 Google Drive 桌面版**（沒有 `G:\`，已不依賴）

首次設定——**clone 一份自己的工作副本，路徑要在 OneDrive 以外**（例如 `C:\projects\`）：

```bash
git clone https://github.com/philia81301-commits/osteoporosis-clinic.git
```

⚠️ 兩台電腦都有 OneDrive 桌面版，但**不要用 OneDrive 同步這個 repo**。
理由：OneDrive 同步 `.git` 會造成 `index.lock` 衝突與衝突複本（連 `.git` 內部檔案都可能被複製成
「檔案 (DESKTOP-XXX)」版本，很難修），而且少了 pull／push 這道關卡，無法確認改動是否真的落地。
**跨電腦一律靠 git，不靠 OneDrive。** 家用那份原本在 `OneDrive\文件\osteoporosis\`，已於 2026-07-28
搬到 `C:\projects\osteoporosis-clinic\`，兩台的狀況因此一致（都是 clone 來的、都在 OneDrive 外）。

`agents.md` 與 `handoff.md` 都在 repo 裡，所以交接資訊會跟著 git 一起同步。

備援（連 git 都不方便時）：在 github.com 網頁上直接編輯檔案並 commit，Pages 同樣會自動重建；要用工具就直接開線上版網址。
要看專案總覽 Doc 用 `drive.google.com` 網頁版。

> 因此：`G:\` 相關的一切只適用於家用電腦，且本專案已不需要（Drive 鏡像已停止維護）。

### Drive 的角色（2026-07-28 起）

**已停止維護 Drive 上的三個 HTML 鏡像。** 工具以 GitHub repo 為唯一位置、以 GitHub Pages 為唯一發布通道。
理由：Drive 連結本來就開不動互動工具（預覽器不執行 JS），鏡像的唯一功能是離線備份，但 GitHub 已經是雲端備份；
而且醫院電腦沒有 `G:\`，維持鏡像會讓同步流程在兩台電腦上不一致。

Drive 保留的東西只有**「專案總覽 — 骨質疏鬆風險評估、衛教及藥物選擇」Google Doc**（專案基地，進度與待辦寫在那裡）。
三個子資料夾內的 HTML 快照已於 2026-07-28 刪除（在 Drive 垃圾桶，30 天內可還原），避免有人下載到過時版本。

## 署名與授權

- 四個頁面頁尾統一標示：製作 潘湘如醫師｜家醫科、版本號與日期、GitHub Issues 回報連結、© 與授權、AI 協助實作說明
- 授權：[CC BY-NC-ND 4.0](https://creativecommons.org/licenses/by-nc-nd/4.0/deed.zh-hant)（可轉貼分享，須署名，禁商用、禁改作），全文在 `LICENSE`
- 著作權人是潘湘如醫師本人；AI 不具著作權，`LICENSE` 與頁尾以「協助實作」的方式誠實揭露

## 工作約定

- 任何 Agent、任何電腦：**開工先讀 `handoff.md`，收工必更新 `handoff.md`**
- 修改共用檔案前先讀最新內容，避免覆蓋其他 Agent 的變更
- 所有回應與文件使用繁體中文
- 修改前先確認計畫，優先保留原有資料結構

### 本專案特有守則（踩過坑換來的）

- **這是公開 repo**。院內給付條文、任何病人資料都不可放進來；每次 push 前確認新增內容適合公開。
- **跨電腦只用 git，不用 OneDrive 同步 repo**。兩台電腦各自 clone 工作副本，路徑都在 OneDrive 以外（家用：`C:\projects\osteoporosis-clinic\`）。讓 OneDrive 同步 `.git` 會產生 lock 衝突與衝突複本。**新專案一開始就建在 `C:\projects\`，不要放 OneDrive。**
- **臨床工具的表單必須在載入時強制清空**（`autocomplete="off"` + `load` 後再 reset），否則瀏覽器會復原上一位病人的勾選。
- **藥名一律同時標學名與常見商品名**（Evenity、Prolia、Forteo、Aclasta、Fosamax、Evista），只寫學名門診找不到藥。
- **健保給付條文不寫死**（門檻、療程年限、換藥規定會修訂），只註明「請核對當期公告」。
- **不要用分享 Drive 連結的方式給人用工具**：Drive 預覽器不執行 JavaScript，對方只會看到程式碼。要分享就給 GitHub Pages 網址。
- **四個頁面的頁尾有署名、版本號與授權**（製作：潘湘如醫師｜家醫科；CC BY-NC-ND 4.0；GitHub Issues 當回報管道）。改動內容時**版本號與日期要一起更新**，那是使用者判斷手上是不是最新版的唯一依據；署名與授權不要拿掉。
- **對外掛機構名稱前先確認權利歸屬**：目前刻意只署個人名、不掛醫院名，避免職務著作與機構形象的問題。
- 若哪天真的需要丟大檔到 Drive：走 `G:\` 掛載 `Copy-Item`（同名覆蓋沿用同一 file id），不要用 Drive MCP 的 `create_file`（需貼完整內容）。**但 `G:\` 只有家用電腦有**——醫院電腦無法安裝 Google Drive 桌面版，那裡走 `drive.google.com` 網頁版。
- **檔案分工**：程式碼與純文字專案走 git；Excel／PPT／Word／掃描檔、分析產出、Obsidian vault 走 OneDrive。OneDrive 唯一不該做的事就是同步 `.git`。
