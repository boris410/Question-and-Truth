# #39 Bento Box Grid

- **分類**: Modern
- **檔案**: examples/39-bento-box.html
- **一句話**: 仿日式便當盒的非對稱大圓角網格,用跨欄跨列方塊建立視覺層級。

## 字型
- **Inter** (400/500/600/700),透過 `* { font-family: 'Inter' }` 全域套用

## 配色 (取自實際 HTML)
| 用途 | 色值 |
|---|---|
| 背景 | bg-neutral-100 |
| 卡片 | bg-white / bg-neutral-900(深色卡) |
| 主特色漸層 | from-violet-500 to-purple-600 |
| 點綴色塊 | bg-amber-400 / bg-emerald-500 / bg-rose-500 |
| 文字 | text-neutral-900 / text-neutral-500 / text-neutral-600 |

## 招牌技法
- 核心是 CSS Grid 非對稱排版:`grid grid-cols-4 grid-rows-3 gap-4`,固定 `style="height: 600px;"`
- 大特色卡用 `col-span-2 row-span-2` 占據左上,其餘小卡填補,形成便當格
- 所有方塊統一大圓角 `rounded-3xl`,軟化網格的硬邊
- 主卡用 violet→purple 漸層,其餘以單色塊(amber/emerald/rose)點綴節奏
- 卡片內 `flex flex-col justify-between` / `justify-center` 控制內容對齊
- 用 `col-span` / `row-span` 控制每格大小,大小差異即建立層級

## 關鍵程式片段
```html
<div class="grid grid-cols-4 grid-rows-3 gap-4 mb-8" style="height: 600px;">
    <div class="col-span-2 row-span-2 bg-gradient-to-br from-violet-500 to-purple-600 rounded-3xl p-8 flex flex-col justify-between text-white">
        <div><span class="text-sm opacity-80">Featured</span><h1 class="text-4xl font-bold mt-2">Beautiful Grid Layouts</h1></div>
        <p class="text-lg opacity-90">Organize content in visually appealing asymmetric grids.</p>
    </div>
    <div class="bg-amber-400 rounded-3xl p-6 flex items-center justify-center">...</div>
    <div class="col-span-2 bg-neutral-900 rounded-3xl p-6 flex items-center justify-between text-white">...</div>
</div>
```

## Do / Don't
- ✅ 用 col-span/row-span 製造大小對比,最重要內容占最大格
- ✅ 全部卡片統一 rounded-3xl 與 gap-4,維持便當盒的整齊節奏
- ✅ 多數中性白卡 + 少數彩色卡,色塊用來點睛而非鋪滿
- ❌ 不要讓所有格子一樣大,失去非對稱層級就不是 bento 了
- ❌ 避免圓角大小不一或間距忽寬忽窄,會破壞網格秩序
