# 交接檔（handoff.md）

> 任何 Agent、任何電腦接手前**必讀**；收工時**必更新**。本檔只放交接必需的精簡資訊，詳細脈絡放 Obsidian `osteoporosis/專案工作流程.md`。

## ⏯️ 目前做到哪

專案初始化完成（L1 + L2 + L3）。三個工具的第一版都已完成並上線 GitHub Pages，Drive 鏡像與專案總覽 Doc 的進度也都同步過了。

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
- **改動要同步三處**：本機 repo → git push（Pages 自動重建）→ 複製到 `G:\我的雲端硬碟\osteoporosis\` 對應子資料夾（Drive 用中文檔名，本機用英文檔名，內容相同）。
- **醫院電腦無法安裝 Google Drive 桌面版**，那裡沒有 `G:\`：用工具就開線上版網址、要改就在 github.com 網頁編輯後 commit、要碰 Drive 走網頁版。醫院端改過的東西回家記得 `git pull`。
- repo 位在 OneDrive 內，OneDrive 同步 `.git` 偶爾會鎖檔導致 git 指令失敗；已設 `windows.appendAtomically false`，真的卡住就把 repo 移出 OneDrive。
- Google Doc 的內容無法用 Drive 連接器修改，要改專案總覽得用 claude-in-chrome 開瀏覽器（擴充功能偶爾沒連上，重試即可）。

## 🕐 最後更新

- 時間：2026-07-28 05:24
- 更新者：阿克（Claude Code, Opus 5）@ DESKTOP-LVSV9Q5
- Git push：✅ 已推
