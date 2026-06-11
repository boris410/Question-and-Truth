# #53 Bento Grids

- **分類**: Modern
- **檔案**: examples/53-bento-grids.html
- **一句話**: 受日式便當盒啟發的非對稱大圓角網格,深色底襯托彩色漸層卡片打造模組化資訊牆。

## 字型
- Inter (400/500/600/700) — 全站(`* { font-family: 'Inter', sans-serif; }`)

## 配色 (取自實際 HTML,Tailwind 色票)
| 用途 | 色值 |
|---|---|
| 背景 | `bg-neutral-950` / 卡片 `bg-neutral-900` |
| 邊框 | `border-neutral-800` |
| 主色漸層 | `from-violet-600 to-indigo-600`、`from-pink-500 to-violet-500` |
| 強調色塊 | `emerald`/`amber`/`cyan`/`rose`/`orange`(皆以 `/20`、`/30` 半透明) |
| 文字 | `text-white` / `text-neutral-400`(次要) |

## 招牌技法
- CSS Grid 跨欄跨列佈局:`grid-cols-4 grid-rows-2` 搭配 `col-span-2 row-span-2` 製造大小錯落。
- 統一大圓角 `rounded-3xl` + 一致 `gap-4` 是便當盒視覺核心。
- 卡片用半透明色票漸層底(如 `from-cyan-500/20 to-blue-500/20`)配同色系細邊框 `border-cyan-500/30`。
- 漸層裁字標題:`bg-gradient-to-r ... bg-clip-text text-transparent` 做數字焦點。
- 圖示容器小圓角方塊 `w-12 h-12 ... rounded-2xl` 內嵌 SVG,語意色 `/20` 底。

## 關鍵程式片段
```html
<section class="grid grid-cols-4 grid-rows-2 gap-4" style="height: 500px;">
  <div class="col-span-2 row-span-2 bg-gradient-to-br from-violet-600 to-indigo-600
              rounded-3xl p-8 flex flex-col justify-between">
    <h1 class="text-4xl font-bold mt-4">Bento Grid Layout</h1>
  </div>
  <div class="col-span-2 bg-neutral-900 rounded-3xl p-6 border border-neutral-800">
    <div class="text-5xl font-bold bg-gradient-to-r from-pink-500 to-violet-500
                bg-clip-text text-transparent">57+</div>
  </div>
</section>
```

## Do / Don't
- ✅ 用 span 製造大小不一的格子,避免每格等大。
- ✅ 固定統一的圓角與間距讓網格有節奏感。
- ✅ 深色中性底搭配少量飽和漸層做焦點。
- ❌ 不要每張卡都用滿版鮮豔漸層,會失去層次。
- ❌ 不要混用不同圓角半徑破壞一致性。
