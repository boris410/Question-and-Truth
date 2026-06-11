# #04 Brutalism

- **分類**: General
- **檔案**: examples/04-brutalism.html
- **一句話**: 原始、粗野、誠實——粗黑邊框、原色塊、超粗字體與零過渡的直白設計。

## 字型
- Inter(字重 400 / 700 / 900,標題用 `font-black`)+ Space Mono(等寬,`.mono` 用於標籤與內文)。

## 配色 (取自實際 HTML)
| 用途 | 色值 |
|---|---|
| 背景 | #FFFF00（`bg-yellow-400`) |
| 邊框/區塊 | #000000（`border-4 border-black`、`bg-black`) |
| 原色強調 | #0000FF（`bg-blue-600`)、#FF0000（`bg-red-500`) |
| 卡片底 | #FFFFFF（`bg-white`) |
| 文字 | 黑 / 白(反白於深色塊) |

## 招牌技法
- 一律 `border-4 border-black` 粗黑外框,結構完全外露。
- `transition-none` 移除所有過渡動畫,hover 直接硬切換色彩 (`hover:bg-black hover:text-white`)。
- 超大超粗標題 `text-8xl font-black leading-none`,全大寫排版。
- 原色塊撞色排版(黃底配藍、紅、白塊),不用漸層、不用陰影。

## 關鍵程式片段
```html
<section class="pt-24 pb-12 px-4">
  <div class="max-w-5xl mx-auto">
    <div class="bg-white border-4 border-black p-8">
      <h1 class="text-8xl font-black leading-none mb-4">RAW.<br/>BOLD.<br/>HONEST.</h1>
      <p class="text-xl mono">No polish. No pretense. Just pure, unfiltered design.</p>
    </div>
  </div>
</section>
```

## Do / Don't
- ✅ 用粗黑邊框與原色製造高衝擊;字體越粗越大越好。
- ✅ 保留 `transition-none` 的生硬感,這就是風格的一部分。
- ✅ 等寬字(Space Mono)用於標籤,強化「機械、未修飾」氛圍。
- ❌ 不要加圓角、陰影或柔和漸層,會破壞粗野感。
- ❌ 不要用低飽和的中性色調,失去衝突張力。
