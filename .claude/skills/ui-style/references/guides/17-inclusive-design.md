# #17 Inclusive Design (包容性設計)

- **分類**: General
- **檔案**: examples/17-inclusive-design.html
- **一句話**: 為所有人設計 — 高對比、色盲友善、完整鍵盤與螢幕閱讀器支援的通用無障礙介面。

## 字型
- 全站: `Atkinson Hyperlegible` (400/700) — 美國盲人基金會專為低視力者設計的高辨識度字型

## 配色 (取自實際 HTML)
| 用途 | 色值 |
|---|---|
| 背景 | 白 / gray-100 |
| 主色 (深藍) | #003366 |
| 連結 / focus | #0066CC |
| 成功 | #006644 |
| 錯誤 | #B91C1C |
| 文字 | gray-900 (高對比) |

## 招牌技法
- 全域 focus 樣式: `:focus { outline: 4px solid #0066CC; outline-offset: 4px; }` 永遠看得見焦點
- Skip link: `.skip-link` 預設藏於 `top: -100px`,`:focus` 時滑入 `top: 16px`
- 尊重動效偏好: `@media (prefers-reduced-motion: reduce) { * { animation: none !important; transition: none !important; } }`
- 語意化 HTML + ARIA: `role`、`aria-label`、`aria-labelledby`、`aria-describedby`、`aria-required`、`.sr-only`
- 觸控目標最小 44×44px (`min-w-[44px] min-h-[44px]`),按鈕 `focus:ring-4`
- 不靠顏色傳意: 色盲示意用 `repeating-linear-gradient` 條紋 + 文字標籤雙重指示

## 關鍵程式片段
```html
<style>
  :focus { outline: 4px solid #0066CC; outline-offset: 4px; }
  .skip-link { position: absolute; top: -100px; left: 50%; transform: translateX(-50%);
    background: #000; color: #fff; padding: 16px 24px; }
  .skip-link:focus { top: 16px; }
  @media (prefers-reduced-motion: reduce) {
    * { animation: none !important; transition: none !important; }
  }
</style>
<a href="#main" class="skip-link">Skip to main content</a>
<main id="main" role="main">...</main>
```

## Do / Don't
- ✅ 適合公共服務、政府網站、教育、醫療、金融等高無障礙需求場景
- ✅ 維持 WCAG AAA 對比 (≥7:1),所有互動元件可純鍵盤操作且焦點可見
- ✅ 必填欄位以符號 + `sr-only` 文字 + `aria-required` 三重標示
- ❌ 不要僅用顏色區分狀態 (需搭配圖案、圖示或文字)
- ❌ 不要移除或隱藏 focus outline,會讓鍵盤使用者迷失
