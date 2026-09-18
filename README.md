# CS2 Random

純前端的 CS2 Discord 內戰控制台。

## 分隊與抽圖

- 貼上 10 人以上玩家名單
- 隨機抽出 10 位先發，其餘列為候補
- 平均人數分隊：Team A / Team B 各 5 人
- 不使用戰績、K/D、ADR 或任何實力資料做平衡
- 隨機分配 CT / T
- 可自訂地圖池並隨機抽圖
- 可重新分隊、重抽地圖、交換 CT/T
- 一鍵複製 Discord 格式
- 一鍵複製 `changelevel` 指令

## 戰績紀錄

- 賽後可上傳 CSV
- 支援常見欄位名稱：player/name/玩家、team/隊伍、kills/k/擊殺、assists/a/助攻、deaths/d/死亡、adr、mvp
- 記錄比賽日期、地圖與 Team A / Team B 比分
- 自動彙整玩家場次、勝敗、K/D、平均 ADR、MVP
- 提供 CSV 範本下載
- 可匯出 / 匯入 JSON 備份
- 戰績只做紀錄，不參與分隊

## 資料保存

目前專案使用 GitHub Pages，沒有後端資料庫。

玩家名單、地圖設定與比賽紀錄都存放在瀏覽器的 localStorage。更換瀏覽器、清除網站資料或更換裝置前，請先匯出 JSON 備份。

## GitHub Pages

Repository Settings → Pages → Build and deployment → Deploy from a branch → main / root。

網站主檔案為 `index.html`，不需要建置工具。


## 2026-09 功能更新

- 地圖池加入 `de_cache`
- 新增 BO1 地圖 Ban / Pick：Team A / Team B 輪流 Ban，最後一張自動成為本場地圖
- Ban / Pick 使用目前勾選中的地圖池
- 戰績頁新增「同步 Google Sheet」
- 網站開啟時會嘗試從 Google Apps Script 讀取 Players 總表
- Google Sheet 為主要資料來源，本機 localStorage 僅作快取

### Google Apps Script 讀取 API

Apps Script 除了原本的 `doPost(e)`，還需要加入 `doGet(e)`，讓網站能讀回 Players 資料。
