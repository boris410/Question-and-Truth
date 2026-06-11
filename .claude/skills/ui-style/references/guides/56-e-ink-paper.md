# #56 E-Ink / Paper

- **分類**: Modern
- **檔案**: examples/56-e-ink-paper.html
- **一句話**: 模擬電子閱讀器與報紙的高對比黑白排版,以襯線字與留白打造無干擾閱讀體驗。

## 字型
- Newsreader (400/500/600,含義式 400) — 正文與標題襯線(`body` 預設)
- JetBrains Mono (400/500) — 標籤、日期、編號(`.font-mono`)

## 配色 (取自實際 HTML)
| 用途 | 色值 |
|---|---|
| 背景(紙白) | `#f5f1eb` |
| 墨黑(主) | `#1a1a1a` |
| 正文灰 | `#333` / `#444` |
| 次要灰 | `#666` |
| 細線淺灰 | `#ddd` |

## 招牌技法
- 紙張噪點材質 `.paper-texture`:內嵌 SVG `feTurbulence` 分形雜訊 + `background-blend-mode: multiply`,以 `opacity-5` 極淡覆蓋。
- 細墨線邊框 `.ink-border` / `border border-[#1a1a1a]`:1px、無圓角、無陰影。
- 深色模式自適應 `@media (prefers-color-scheme: dark)` 用 `filter: invert(1)` 反相成黑底白字(電子紙觀感)。
- 襯線正文 + 等寬字 meta(日期、編號 `01.`),呼應報紙排版。
- hover 反白互動:`hover:bg-[#1a1a1a] hover:text-[#f5f1eb]`,無漸層無陰影。

## 關鍵程式片段
```html
<style>
  body { font-family: 'Newsreader', Georgia, serif; }
  .paper-texture {
    background-image: url("data:image/svg+xml,%3Csvg ...%3E%3Cfilter id='noiseFilter'%3E
      %3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4'/%3E ... ");
    background-blend-mode: multiply;
  }
  @media (prefers-color-scheme: dark) { .e-ink-adaptive { filter: invert(1); } }
</style>
<blockquote class="border-l-2 border-[#1a1a1a] pl-6 my-8 italic text-xl">
  "The absence of color is not a limitation—it's a liberation."
</blockquote>
```

## Do / Don't
- ✅ 只用黑白與少量灰階,讓字型與留白主導。
- ✅ 邊框維持 1px 細墨線、無陰影無圓角。
- ✅ 大量 `leading-relaxed` 行距與寬鬆 padding 助閱讀。
- ❌ 不要加彩色、漸層或柔和陰影。
- ❌ 不要塞滿版面,留白即是設計。
