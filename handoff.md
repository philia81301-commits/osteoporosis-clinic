# 交接檔（handoff.md）

> 任何 Agent、任何電腦接手前**必讀**；收工時**必更新**。本檔只放交接必需的精簡資訊，詳細脈絡放 Obsidian `osteoporosis/專案工作流程.md`。

## ⏯️ 目前做到哪

三個工具第一版完成並上線 GitHub Pages；專案初始化至第三層級。2026-07-28 這輪把「對外」與「位置」整理乾淨：
四頁加上署名（潘湘如醫師｜家醫科）＋版本號 v1.0、授權定為 CC BY-NC-ND 4.0 並附 LICENSE、刪掉 Drive 的過時 HTML 快照、
家用工作副本從 OneDrive 搬到 `C:\projects\osteoporosis-clinic\`，跨電腦改為純 git 同步。

## 🚦 目前狀態

- **可運行**。線上版四頁（入口 + 三工具）皆 HTTP 200，署名與授權區塊已在線上驗證。
- 工作副本乾淨、與 GitHub 同步。沒有做一半的東西。
- 藥物選擇工具的「過去骨鬆用藥史」選項已簡化為純藥名（v1.1）；其餘工具內容自 07-27 起未再改動。

## ➡️ 下一步

1. **門診實際試用三個工具**，收集要修的點（重點：藥物選擇的選藥順位是否符合實際習慣）
2. 決定要不要加固定的院內版健保給付欄——若要，需先提供目前依循的給付版本
3. 開新專案「肌少症門診工具」時：說「初始化專案：肌少症門診工具，要公開上 GitHub Pages」，repo 直接建在 `C:\projects\`
4. （選配）把可複用的部分做成醫療工具專案模板；（選配）產出給 OpenCode 學習的交接包

## ⚠️ 注意事項

- **repo 是公開的**（為了 GitHub Pages）。院內給付條文、病人資料一律不可進 repo。
- **流程就四步**：`git pull` → 改檔 → `commit` + `push`（Pages 約 1–2 分重建）→ 收工更新本檔再 push。
- **不要用 OneDrive 同步這個 repo**。每台電腦各自 `git clone`，路徑放在 OneDrive 以外。家用：`C:\projects\osteoporosis-clinic\`。
  檔案分工：程式碼走 git；Office 檔、分析產出、Obsidian vault 走 OneDrive；臨床原始資料集中 Google Drive。
- **醫院電腦**有 Claude Code 與 GitHub，流程與家中相同；但**無法安裝 Google Drive 桌面版**（沒有 `G:\`，本專案已不依賴）。首次要先 clone。
- **改內容時頁尾版本號與日期要一起更新**（藥物選擇工具 v1.1、其餘三頁 v1.0，皆 2026-07-28）；署名與授權區塊不要拿掉。
- 用藥史選項只顯示藥名（bisphosphonate／denosumab／SERM 荷爾蒙／骨生成藥），但**判斷邏輯的語意仍是「denosumab＝目前仍在使用」「骨生成藥＝療程剛結束」**；輸出的提示文字保留完整敘述。
- **對外掛機構名稱前先確認權利歸屬**：目前刻意只署個人名、不掛醫院名。
- Google Doc（專案總覽）無法用 Drive 連接器修改，要改得用 claude-in-chrome 開瀏覽器；在 Docs 裡用座標點擊定位游標容易打偏，輸入前先截圖確認。
- 待清理：`C:\projects\_osteoporosis_舊OneDrive副本\`（舊工作副本，內容與 GitHub 相同，潘醫師確認後可刪）。

## 🕐 最後更新

- 時間：2026-07-28 06:20
- 更新者：阿克（Claude Code, Opus 5）@ DESKTOP-LVSV9Q5
- Git push：✅ 已推
