# #50 Swiss Modernism 2.0

- **分類**: Modern
- **檔案**: examples/50-swiss-modernism.html
- **一句話**: 嚴格網格、無襯線排版與原色撞黑白,把 1950 年代瑞士國際主義的客觀清晰更新到數位時代。

## 字型
- **Inter** (400/500/600/700) 為主,fallback 含 -apple-system、Helvetica Neue 等系統無襯線 (`* { font-family: 'Inter', ... }`)

## 配色 (取自實際 HTML)
| 用途 | 色值 |
|---|---|
| 背景 | bg-white |
| 主色/文字 | bg-black / text-black |
| 強調紅 | bg-red-600 / border-red-600 / text-red-600 |
| 原色藍 | bg-blue-600 |
| 原色黃 | bg-yellow-400 |
| 次文字 | text-gray-600 / text-gray-500 / text-gray-400 |

## 招牌技法
- 12 欄數學網格:`grid-cols-12 gap-4/gap-8`,內容對齊不可見格線,並用 `col-span-3` / `col-span-9` 分配。
- 黑線分隔:section 一律 `border-b border-black`,導覽 `border-b border-black` 強調結構。
- 巨型粗體標題:`text-[8rem]` / `text-[6rem] font-bold leading-none tracking-tighter`。
- 編號小標 `text-sm font-bold uppercase tracking-widest`(如 "01 — Grid"),原則卡用 `border-t-4 border-black/red-600`。
- 原色色塊網格:黑/白/紅/藍/黃 `aspect-square`,白塊以 `border-2 border-black` 界定。

## 關鍵程式片段
```html
<section class="px-6 py-24 border-b border-black">
    <div class="grid grid-cols-12 gap-8">
        <div class="col-span-8">
            <h1 class="text-[8rem] font-bold leading-none tracking-tighter text-black">Helvetica<br/>Never Dies</h1>
        </div>
        <div class="col-span-4 flex flex-col justify-end">
            <p class="text-lg text-gray-600 mb-6">The timeless principles of Swiss design…</p>
        </div>
    </div>
</section>
```

## Do / Don't
- ✅ 嚴格依 12 欄網格對齊,用不對稱 col-span 分配製造張力。
- ✅ 配色限縮在黑白 + 紅藍黃原色,排版用無襯線傳達客觀清晰。
- ❌ 不要加漸層、陰影或裝飾紋理,違背「form follows function」。
- ❌ 避免置中對稱的安全版面;瑞士風偏好不對稱的網格佈局。
