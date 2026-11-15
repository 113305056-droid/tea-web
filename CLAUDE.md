# CLAUDE.md - Tea Collection Project Rules

## 1. 專案目的 (Project Purpose)
- 本專案是一個個人化的「茶葉收藏圖鑑網站」(Tea Collection)，用來記錄與展示不同種類的茶葉及其最佳沖泡參數。
- 本文件的目的是提供明確的結構與開發規範，讓 AI 在未來新增茶葉品項或擴充頁面時，能夠維持完全一致的視覺風格與資料格式。

## 2. 網頁風格與設計規範 (Design & Style Guidelines)
- **整體氛圍**: 溫潤、自然、簡約的茶道與咖啡館風格（Botanical & Minimalist）。
- **UI 框架**: 使用 Tailwind CSS (CDN 引入)。
- **色彩配置**:
  - 背景色：米白色 / 暖灰 (`bg-stone-50`)
  - 卡片背景：純白 (`bg-white`) 搭配細邊框 (`border-stone-200`) 與圓角 (`rounded-2xl`)
  - 主色調：茶綠色 / 橄欖綠 (`emerald-700` / `stone-800`)
  - 茶類標籤色彩規範：
    - 烏龍茶 (Oolong)：琥珀色系 (`bg-amber-50 text-amber-800 border-amber-200`)
    - 紅茶 (Black Tea)：赤褐色系 (`bg-rose-50 text-rose-800 border-rose-200`)
    - 綠茶 (Green Tea)：翠綠色系 (`bg-emerald-50 text-emerald-800 border-emerald-200`)
- **響應式設計 (Responsive)**: 支援手機單欄、平板雙欄、電腦三欄 (`grid-cols-1 md:grid-cols-2 lg:grid-cols-3`) 排列。

## 3. 頁面結構與檔案命名 (Page Structure & Naming)
- `/index.html`: 網站主頁，包含頁首標題、簡介區塊、茶葉種類篩選標籤，以及茶葉收藏卡片網格 (Grid)。
- `/CLAUDE.md`: 本專案的開發與擴充規範文件。

## 4. 新增茶葉卡片的資料結構與規則 (Rules for Adding New Tea Items)
當 AI 收到「新增一款茶葉」的指令時，必須在 `index.html` 的 `<div id="tea-grid">` 區塊內，按照以下固定的 7 項欄位結構新增一張 `<article class="tea-card">` 卡片：

1. **茶葉名稱 (Name)**: 卡片主標題 (`<h3>`)
2. **茶葉類型 (Type)**: 顯示於右上角的膠囊標籤（並套用對應的茶類色彩規範）
3. **產地 (Origin)**: 標示產區或國家
4. **風味特徵 (Flavor Profile)**: 簡述香氣與口感層次（2~3 句話）
5. **沖泡方式與水溫 (Brewing Method & Temp)**: 例如「熱泡 / 95°C」
6. **浸泡時間 (Steeping Time)**: 例如「60 秒」或「3 分鐘」
7. **建議水量 (Water Volume)**: 例如「200 ml」或「300 ml」

### AI 修改限制 (Constraints for AI)
- 不可隨意更動現有的 Tailwind CSS 網格系統與卡片圓角、陰影樣式。
- 沖泡參數（水溫、時間、水量）必須使用三欄式數據區塊 (`grid-cols-3`) 整齊呈現，確保使用者能一眼讀取沖泡比例。
- 語言以繁體中文為主，可適度保留茶葉原產地或專有名詞（如日文、法文或英文名稱）。
