# #19 Soft UI Evolution (進化版柔軟 UI)

- **分類**: General
- **檔案**: examples/19-soft-ui-evolution.html
- **一句話**: 進化後的 Soft UI / 新擬態 — 保留柔軟陰影與層次,但提升對比與無障礙,更現代耐看。

## 字型
- 全站: `Inter` (300/400/500/600/700)

## 配色 (取自實際 HTML)
| 用途 | 色值 |
|---|---|
| 背景 (柔和漸層) | #e0f2fe → #f0f9ff → #ecfeff |
| 卡片 | rgba(255,255,255,0.9) |
| focus 強調 | #60a5fa (sky/blue) |
| 漸層圖示 | sky-400→blue-500 / pink-400→rose-500 / emerald-400→teal-500 |
| 柔色票 | #87CEEB / #90EE90 / #E6E6FA / #FFB6C1 |
| 文字 | slate-700 / slate-800 + slate-600 |

## 招牌技法
- 柔軟卡片 `.soft-card`: 半透明白底 + 雙層柔影 `0 4px 20px rgba(0,0,0,0.05), 0 1px 3px rgba(0,0,0,0.08)`
- 柔軟按鈕 `.soft-btn`: `linear-gradient(145deg, #ffffff, #f0f0f0)` + hover 上抬 `translateY(-2px)` 加深陰影,active 改 `inset` 內陰影
- 柔軟輸入框 `.soft-input`: `inset` 微凹陰影,focus 時換 `#60a5fa` 邊框 + `0 0 0 3px rgba(96,165,250,0.2)` 聚焦環
- 相較傳統新擬態:強調「更好的對比」(WCAG AA+),陰影柔但不犧牲深度感知
- 大圓角 (`rounded-2xl / rounded-3xl`) + 漸層方塊圖示維持親和柔和調性

## 關鍵程式片段
```html
<style>
  body { background: linear-gradient(135deg, #e0f2fe 0%, #f0f9ff 50%, #ecfeff 100%); }
  .soft-card {
    background: rgba(255,255,255,0.9);
    box-shadow: 0 4px 20px rgba(0,0,0,0.05), 0 1px 3px rgba(0,0,0,0.08);
    border: 1px solid rgba(255,255,255,0.8);
  }
  .soft-btn { background: linear-gradient(145deg, #ffffff, #f0f0f0);
    box-shadow: 0 4px 12px rgba(0,0,0,0.08), 0 1px 3px rgba(0,0,0,0.06); }
  .soft-btn:hover { transform: translateY(-2px); }
  .soft-btn:active { box-shadow: inset 0 2px 4px rgba(0,0,0,0.06); transform: translateY(0); }
</style>
```

## Do / Don't
- ✅ 適合現代 SaaS、儀表板、消費型 App,想要柔和但仍需可讀性的場景
- ✅ 用淺色漸層底搭配半透明白卡,柔影才浮得出層次
- ✅ 互動狀態用 hover 上抬 / active 內凹的對比,提供清楚回饋
- ❌ 不要把陰影做得太淺以致元件與背景難以分辨 (避免傳統新擬態的對比缺陷)
- ❌ 文字不要用過淺灰色,需確保對比達標
