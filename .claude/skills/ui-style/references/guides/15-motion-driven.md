# #15 Motion-Driven (動效驅動)

- **分類**: General
- **檔案**: examples/15-motion-driven.html
- **一句話**: 動畫優先 (Animation First) — 用進場、捲動、懸停與載入動效讓介面活起來。

## 字型
- 全站: `Inter` (300/400/500/600/700/800)

## 配色 (取自實際 HTML)
| 用途 | 色值 |
|---|---|
| 背景 | slate-900 |
| 卡片 / 區塊 | slate-800,邊框 slate-700 |
| 強調漸層 | blue-400 → purple-400 → pink-400 (bg-clip-text) |
| 重點色 | blue-500 / purple-500 / pink-500 / green-500 |
| 文字 | 白 + slate-400/slate-500 |

## 招牌技法
- 進場動畫家族: `fade-in` (0.8s)、`slide-up` (translateY 40px→0, 0.8s)、`scale-in` (scale 0.8→1, 0.6s),皆 `ease-out forwards`
- 交錯延遲: `.stagger-1`~`.stagger-4` 以 `animation-delay: 0.1s~0.4s` 製造瀑布式進場
- 懸停抬升 `.hover-lift`: `transform: translateY(-8px)` + `box-shadow: 0 20px 40px rgba(0,0,0,0.15)`
- 漂浮 `float` (translateY ±10px) 與 `pulse-ring` (scale 1→1.5, opacity 漸隱) 環形脈衝
- 內建 Tailwind 動畫: `animate-bounce / animate-pulse / animate-spin / animate-ping` 做載入態
- 漸層文字標題: `bg-gradient-to-r ... bg-clip-text text-transparent`

## 關鍵程式片段
```html
<style>
  .slide-up { animation: slideUp 0.8s ease-out forwards; opacity: 0; transform: translateY(40px); }
  @keyframes slideUp { to { opacity: 1; transform: translateY(0); } }
  .stagger-1 { animation-delay: 0.1s; }
  .hover-lift { transition: transform 0.3s ease, box-shadow 0.3s ease; }
  .hover-lift:hover { transform: translateY(-8px); box-shadow: 0 20px 40px rgba(0,0,0,0.15); }
</style>
<h1 class="slide-up"><span class="bg-gradient-to-r from-blue-400 via-purple-400 to-pink-400 bg-clip-text text-transparent">Animation First</span></h1>
<p class="slide-up stagger-1">Scroll effects, page transitions, microinteractions...</p>
```

## Do / Don't
- ✅ 適合作品集、敘事平台、互動體驗與創意 SaaS (建議搭 GSAP / Framer Motion)
- ✅ 用 `stagger` 延遲讓群組元素依序進場,比同時出現更有節奏感
- ✅ 配合 `prefers-reduced-motion` 提供降級 (此檔在資訊區明列為無障礙要點)
- ❌ 不要讓所有元素都動 — 過度動效會干擾閱讀並拖累效能
- ❌ 動畫時長不要過長 (參考此檔多在 0.3–0.8s),否則感覺遲鈍
