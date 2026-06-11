# #08 Accessible & Ethical

- **分類**: General
- **檔案**: examples/08-accessible.html
- **一句話**: 把無障礙當地基——高對比、語意化 HTML、鍵盤可達與清晰焦點環。

## 字型
- Inter;字重 400 / 500 / 600 / 700,最小 16px 基礎字級,標題清晰分層 (`leading-tight`/`leading-relaxed`)。

## 配色 (取自實際 HTML)
| 用途 | 色值 |
|---|---|
| 背景 | #FFFFFF（`bg-white`)、輔助 `bg-gray-50` |
| 主色/連結 | #0066CC（焦點環色) |
| 連結 hover | #0052A3 |
| 警示/錯誤 | #D32F2F |
| 邊框/文字 | #000000、`text-gray-900` / `text-gray-700` |

## 招牌技法
- 焦點環 `:focus { outline: 3px solid #0066CC; outline-offset: 2px }`,所有互動元素皆可見焦點。
- Skip link `.skip-link`:`position: absolute; top: -40px`,`:focus` 時 `top: 0` 跳出,供鍵盤使用者跳到主內容。
- 語意化結構與 ARIA:`role="navigation"`、`aria-label`、`aria-current="page"`、`aria-labelledby`、`aria-hidden`。
- 7:1 對比比例(AAA),卡片用 `border-2 border-gray-900` 加強邊界辨識。

## 關鍵程式片段
```css
.skip-link {
  position: absolute; top: -40px; left: 0;
  background: #000; color: #fff; padding: 8px; z-index: 100;
}
.skip-link:focus { top: 0; }
:focus { outline: 3px solid #0066CC; outline-offset: 2px; }
```
```html
<a href="#main" class="skip-link">Skip to main content</a>
<nav role="navigation" aria-label="Main navigation"> ... </nav>
<main id="main" role="main"> ... </main>
```

## Do / Don't
- ✅ 保證 7:1 文字對比、最小 16px 字級,提供可見焦點環。
- ✅ 用語意標籤 (`main`/`nav`/`article`) 與 ARIA 屬性,支援螢幕報讀。
- ✅ 提供 Skip link 與完整鍵盤導覽。
- ❌ 不要僅用顏色傳達狀態(需搭配文字/圖示)。
- ❌ 不要移除 outline 或用低對比的細灰字。
