---
name: ui-style
description: >-
  套用 57 種可重複取用的 UI 設計風格樣板，做出風格一致的網頁／HTML 頁面。當使用者要「做一個網頁／著陸頁／儀表板／某某頁面」、要某種設計調性（極簡、毛玻璃、賽博龐克、新粗野主義、便當盒網格、儀表板…），或點名某個風格時使用。涵蓋 General、Landing、BI-Analytics、Modern 四大分類，每種風格都附字型、配色、招牌技法、程式片段與 Do/Don't 規格，以及可直接開啟的 HTML 參考實作。Use when building or designing a web page / HTML UI and you want a consistent, named visual style.
---

# UI Style 樣板庫

這個 skill 是一個**可重複取用的 UI 設計風格樣板庫**：57 種獨立風格，每種都有結構化設計規格（字型、配色、招牌技法、程式片段、Do/Don't）與一份可直接開啟的 HTML 參考實作。目的：做網頁時從這裡挑一個既有風格、套用它的規格，產出風格一致的頁面，而不是每次從零猜設計方向。

## 工作流程（重要）

當使用者要「做一個 XX 頁面／元件」時：

1. **挑風格**：先看下方〈風格速查表〉。依使用者情境或點名挑出 1-3 個候選。情境不明確時，先問使用者想要哪種調性，或直接推薦。
2. **讀規格**：只讀選定那一份 `references/guides/NN-name.md`（**不要一次讀全部 57 份，浪費 context**）。需要更多實作細節時，才開對應的 `examples/NN-name.html` 原始檔當參考。
3. **產頁面**：依規格的字型、配色、招牌技法產出頁面，並**嚴格遵守下方〈技術慣例〉**，讓成品與該風格一致。
4. **回報**：產出後，簡短說明套用了哪個風格（編號＋名稱）與關鍵設計決定。

## 技術慣例（所有產出共用，務必遵守）

- **純靜態單檔 HTML**：無建置流程、無 npm，每個檔案自包含、可直接 `open`。
- **`<html lang="zh-TW">`**，含 `<meta charset="UTF-8">` 與 `<meta name="viewport" content="width=device-width, initial-scale=1.0">`。
- **Tailwind CSS 透過 CDN**：`<script src="https://cdn.tailwindcss.com"></script>`。優先用 Tailwind utility class，風格專屬效果才寫進 `<style>`。
- **字型用 Google Fonts**：在 `<head>` 以 `<link>` 載入，並在 `<style>` 用 `* { font-family: ... }` 套用。字型選擇見各風格規格。
- **風格專屬 CSS**（自訂 class、`@keyframes`、漸層、陰影）集中寫在 `<head>` 的 `<style>` 區塊。
- **響應式**：使用 `max-w-*`、`md:`/`lg:` 斷點，確保桌機與行動皆可用。
- **內容用繁體中文**（範例文案可中英混用，符合各風格調性）。
- **配色與字型請填實際值**：直接沿用規格中列出的色票與字重，不要捏造。

> 註：Tailwind CDN 僅適合開發／展示用途。若要正式上線高流量站，改用 Tailwind CLI 預編譯精簡 CSS。

## 檔案位置

- `references/INDEX.md` — 57 種風格完整速查表（與下方表格同源）。
- `references/guides/NN-name.md` — 各風格的結構化設計規格（**做頁面時讀這個**）。
- `examples/NN-name.html` — 各風格可直接開啟的 HTML 參考實作（需要更多細節時才讀）。

## 風格速查表（57 種）

> 確定要哪一種後，**只讀對應的 `references/guides/NN-name.md`**。使用者只給情境 → 挑 1-3 個候選，必要時詢問；直接點名 → 直接對應編號。

### General（01-19）通用元件與基礎風格

| # | 風格 | 一句話 |
|---|------|--------|
| 01 | Minimalism & Swiss Style | 數學般精準網格、極致留白與高對比黑白，讓內容自己說話 |
| 02 | Neumorphism | 同色系雙向陰影營造柔軟浮凸與內凹的觸覺感 |
| 03 | Glassmorphism | 半透明毛玻璃疊在繽紛漸層上，用模糊與透光營造層次 |
| 04 | Brutalism | 粗黑邊框、原色塊、超粗字體與零過渡的直白設計 |
| 05 | 3D & Hyperrealism | 透視、立體旋轉與多層擬真陰影，打造金屬光澤與空間深度 |
| 06 | Vibrant & Block-based | 黑底撞色螢光大色塊，大膽充滿能量的區塊式排版 |
| 07 | Dark Mode (OLED) | 純黑底配螢光發光強調色，為 OLED 省電而生 |
| 08 | Accessible & Ethical | 高對比、語意化 HTML、鍵盤可達與清晰焦點環 |
| 09 | Claymorphism | 厚實圓潤像黏土玩具的 3D 元件，柔軟又有玩心 |
| 10 | Aurora UI | 極光流動漸層，色彩緩慢呼吸流轉的夢幻氛圍 |
| 11 | Retro-Futurism | 80 年代美學＋未來想像，霓虹輝光與 CRT 掃描線 |
| 12 | Flat Design | 無陰影無漸層，只靠大膽純色與乾淨字型 |
| 13 | Skeuomorphism | 用材質光影模擬實體物件（皮革/木紋/金屬/玻璃） |
| 14 | Liquid Glass | 流動有機形狀、彩虹虹彩與深度模糊玻璃 |
| 15 | Motion-Driven | 動畫優先，用進場/捲動/懸停動效讓介面活起來 |
| 16 | Micro-interactions | 小細節大影響，觸覺回饋與情境動畫帶來愉悅感 |
| 17 | Inclusive Design | 色盲友善、完整鍵盤與螢幕閱讀器支援的通用無障礙 |
| 18 | Zero Interface | 語音優先、手勢與 AI 驅動的隱形控制 |
| 19 | Soft UI Evolution | 進化版新擬態，柔軟陰影＋更高對比與無障礙 |

### Landing（20-27）著陸頁／行銷頁

| # | 風格 | 一句話 |
|---|------|--------|
| 20 | Hero-Centric | 滿版 Hero 主導，大標＋雙 CTA 第一屏完成轉換 |
| 21 | Conversion-Optimized | 緊迫感＋信任訊號＋單一 CTA，最大化註冊轉換 |
| 22 | Feature-Rich Showcase | 深色 Hero 帶多功能網格，展示一站式平台能力 |
| 23 | Minimal & Direct | 大量留白、細字重、單欄敘事，直白傳達單一訊息 |
| 24 | Social Proof-Focused | 評分、頭像牆、客戶 logo 與見證牆堆疊信任 |
| 25 | Interactive Product Demo | 可操作產品預覽放進 Hero，先試再買降低門檻 |
| 26 | Trust & Authority | 襯線標題、認證徽章與莊重配色塑造權威感 |
| 27 | Storytelling-Driven | 一章一章的敘事，用襯線長文帶讀者走完品牌旅程 |

### BI-Analytics（28-37）儀表板／數據分析

| # | 風格 | 一句話 |
|---|------|--------|
| 28 | Data-Dense Dashboard | 深色高密度後台，小間距網格塞進最多 KPI |
| 29 | Heatmap & Density | GitHub 貢獻圖式色階方塊，視覺化密度與強度 |
| 30 | Executive Summary | 淺色留白的高階主管儀表板，關鍵指標一目了然 |
| 31 | Real-Time Monitoring | 暗色機房儀表板，脈動指示燈＋等寬數字 |
| 32 | Drill-Down Analytics | 麵包屑層級＋可點表格，一層層往下鑽探資料 |
| 33 | Comparative Analytics | 本期 vs 去年雙色對照，並排數字與差異進度條 |
| 34 | Predictive Analytics | 暗色 AI 預測儀表板，紫色標記＋信賴區間 |
| 35 | User Behavior Analytics | 漸層藍漏斗圖，視覺化使用者轉換與流失 |
| 36 | Financial Analytics | 深色交易終端風，等寬數字＋翡翠綠盈虧 |
| 37 | Sales Intelligence | 明亮銷售管線儀表板，indigo 行動色＋綠色成交 |

### Modern（38-57）前衛／潮流風格

| # | 風格 | 一句話 |
|---|------|--------|
| 38 | Neubrutalism | 粗黑邊框、硬陰影、飽和糖果色，刻意不修飾 |
| 39 | Bento Box Grid | 日式便當盒非對稱大圓角網格，跨欄跨列建立層級 |
| 40 | Y2K Revival | 千禧年科技樂觀復刻，霓虹漸層＋發光字＋毛玻璃泡泡 |
| 41 | Cyberpunk | 黑底霓虹螢光，發光字、掃描線與 glitch 抖動 |
| 42 | Organic Biophilic | 大地色＋有機不規則圓角，平靜療癒的自然親和 |
| 43 | AI-Native Interface | 對話為核心的 AI 助理介面，聊天泡泡＋打字動畫 |
| 44 | Memphis Revival | 80 年代 Memphis 幾何色塊、粗框、硬陰影與波浪線 |
| 45 | Vaporwave | 粉紫青漸層、捲動網格、鉻金屬字的迷幻數位鄉愁 |
| 46 | Dimensional Layering | 堆疊色塊、偏移陰影與模糊光暈製造三維縱深 |
| 47 | Exaggerated Minimalism | 極端留白＋巨大細體字，用尺度與空間建立層級 |
| 48 | Kinetic Typography | 黑底巨大顯示字＋動態 hover，讓文字會呼吸會移動 |
| 49 | Parallax Storytelling | 全螢幕章節捲動敘事，多層深度與漸進揭露 |
| 50 | Swiss Modernism 2.0 | 嚴格網格、無襯線排版、原色撞黑白的客觀清晰 |
| 51 | HUD / Sci-Fi | 軍事科幻抬頭顯示器，青色發光＋掃描線＋角框 |
| 52 | Pixel Art / Retro Gaming | 致敬 Game Boy 的 8-bit 四色綠調點陣字 |
| 53 | Bento Grids | 日式便當盒非對稱網格，深色底襯彩色漸層卡片 |
| 54 | Neubrutalism v2 | 粗黑邊框、硬位移陰影與衝突鮮豔色塊的升級版 |
| 55 | Spatial UI | Vision Pro 啟發的空間運算，毛玻璃＋景深＋環境光 |
| 56 | E-Ink / Paper | 模擬電子閱讀器與報紙的高對比黑白無干擾排版 |
| 57 | Gen Z Chaos | more is more 混亂美學，旋轉貼紙＋漸層字＋glitch |
