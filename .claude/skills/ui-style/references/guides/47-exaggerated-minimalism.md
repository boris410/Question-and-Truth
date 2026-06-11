# #47 Exaggerated Minimalism

- **分類**: Modern
- **檔案**: examples/47-exaggerated-minimalism.html
- **一句話**: 極端留白搭配巨大細體字,用尺度與空間本身建立層級,大膽的簡約。

## 字型
- **Space Grotesk** (300/400/500/600/700):全站唯一字型 (`* { font-family: 'Space Grotesk' }`),大量使用 `font-light` 細體

## 配色 (取自實際 HTML)
| 用途 | 色值 |
|---|---|
| 背景 | bg-white / bg-gray-50 |
| 反白區塊 | bg-black + text-white |
| 主文字 | text-black |
| 次文字 | text-gray-400 / text-gray-600 |
| 編號淺灰 | text-gray-200 / text-gray-300 |

## 招牌技法
- 超大標題:`text-[12rem]` / `text-[8rem]` 巨型字,搭 `font-light leading-none tracking-tighter`。
- 極端留白:section 用 `py-32` / `py-48`,內容置中 `min-h-screen flex items-center justify-center`。
- 12 欄網格分配:`grid-cols-12`,編號佔 `col-span-4`、內容佔 `col-span-8`。
- 寬字距裝飾:導覽編號 `tracking-[0.3em]` / `tracking-[0.2em]`,小標全大寫。
- 黑白反轉節奏:白 → 黑 (`bg-black text-white`) → 白 → 淺灰交替營造節拍。

## 關鍵程式片段
```html
<style>* { font-family: 'Space Grotesk', sans-serif; }</style>
<section class="py-32">
    <h1 class="text-[12rem] font-light leading-none tracking-tighter text-black mb-8">
        Less.
    </h1>
    <p class="text-2xl text-gray-400 max-w-lg font-light">
        Extreme whitespace. Oversized typography. Bold simplicity.
    </p>
</section>
<div class="col-span-4"><span class="text-[8rem] font-light">01</span></div>
```

## Do / Don't
- ✅ 用 text-[12rem] 等任意值巨型字 + font-light,讓字體成為主視覺。
- ✅ 大膽留白 (py-32/py-48),只保留最必要的元素。
- ❌ 不要塞入裝飾、漸層或多色,違背「去蕪存菁」的精神。
- ❌ 避免粗體與緊湊排版,細字重與空間感才是此風格的張力來源。
