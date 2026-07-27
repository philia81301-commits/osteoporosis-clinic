# 交接檔（handoff.md）

> 任何 Agent、任何電腦接手前**必讀**；收工時**必更新**。本檔只放交接必需的精簡資訊，詳細脈絡放 Obsidian `osteoporosis/專案工作流程.md`。

## ⏯️ 目前做到哪

專案初始化完成（L1 + L2 + L3），三個工具第一版已上線 GitHub Pages。2026-07-28 追加：刪除 Drive 的 HTML 快照（Drive 只留專案總覽 Doc）、四個頁面加上署名與版本號、授權定為 CC BY-NC-ND 4.0 並新增 LICENSE、**家用工作副本從 OneDrive 搬到 `C:\projects\osteoporosis-clinic\`**（跨電腦改為純 git 同步）。

## 🚦 目前狀態

- **可運行**。線上版四個頁面（入口 + 三工具）皆驗證 HTTP 200，JavaScript 在線上版正常執行。
- 本機 repo 乾淨、與 GitHub 同步。
- 沒有做一半的東西；下一步是等門診試用後的回饋。

## ➡️ 下一步

1. 門診實際試用三個工具，收集要修的點（尤其藥物選擇的選藥順位是否符合實際習慣）
2. 決定要不要加固定的院內版健保給付欄——若要，需先提供目前依循的給付版本
3. 產出給 OpenCode 學習的交接包（獨立資料夾 + AGENTS.md，重點寫決策理由與踩過的坑）

## ⚠️ 注意事項

- **repo 是公開的**（為了 GitHub Pages）。院內給付條文、病人資料一律不可進 repo。
- **改動只要兩步**：改本機 repo → `git push`（Pages 自動重建）。2026-07-28 起**已停止維護 Drive 的 HTML 鏡像**，Drive 只保留「專案總覽」Google Doc；那三個資料夾裡的 HTML 是 07-27 快照，不要當最新版用。
- **改內容時頁尾版本號與日期要一起更新**（目前 v1.0 / 2026-07-28），那是使用者判斷手上是不是最新版的唯一依據；署名與授權區塊不要拿掉。
- **對外掛機構名稱前先確認權利歸屬**：目前刻意只署個人名（潘湘如醫師｜家醫科）、不掛醫院名。
- **兩台電腦都有 Claude Code 與 GitHub，工作副本路徑一致＝`C:\projects\osteoporosis-clinic\`**（家用 DESKTOP-LVSV9Q5、醫院 X108521，2026-07-28 醫院端已 clone 並定位完成）。流程相同：`git pull` → 改檔 → commit → push → 收工更新 handoff.md 再 push。醫院無法安裝 Google Drive 桌面版（沒有 `G:\`，本專案已不依賴）。
- ⚠️ **不要用 OneDrive 同步這個 repo**。OneDrive 同步 `.git` 會造成 lock 衝突與衝突複本；跨電腦一律靠 git。檔案分工：程式碼走 git、Excel／PPT／Word／分析產出／Obsidian vault 走 OneDrive。
- 舊的 OneDrive 工作副本已移到 `C:\projects\_osteoporosis_舊OneDrive副本\`（內容與 GitHub 相同，確認無誤後可自行刪除）。
- Google Doc 的內容無法用 Drive 連接器修改，要改專案總覽得用 claude-in-chrome 開瀏覽器（擴充功能偶爾沒連上，重試即可）。

## 🕐 最後更新

- 時間：2026-07-28 06:10（2026-07-28 醫院端補記工作副本路徑）
- 更新者：阿克（Claude Code, Opus 5）@ DESKTOP-LVSV9Q5 → X108521
- Git push：✅ 已推
