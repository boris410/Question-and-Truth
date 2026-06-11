# #20 Hero-Centric Design (英雄區主導)

- **分類**: Landing
- **檔案**: examples/20-hero-centric.html
- **一句話**: 以滿版 Hero 區為絕對焦點,用大標題、雙 CTA 與產品預覽在第一屏完成價值傳達與轉換。

## 字型
- 全站: `Inter` (400/500/600/700/800)

## 配色 (取自實際 HTML)
| 用途 | 色值 |
|---|---|
| 背景 | 白 / gray-50 |
| Hero 漸層 | indigo-600 → purple-600 → pink-500 |
| 主 CTA | 白底 + indigo-600 文字 |
| 強調點綴 | yellow-300 (標題重點字) |
| 程式碼預覽 | slate-900 / slate-700 + indigo-500 / purple-500 |
| 文字 | 白 + white/80、white/60 階層 |

## 招牌技法
- 滿版 Hero: `min-h-screen flex items-center` + `bg-gradient-to-br from-indigo-600 via-purple-600 to-pink-500`,佔滿首屏
- 背景光暈: `absolute ... w-96 h-96 bg-white rounded-full blur-3xl` 配 `opacity-10`,製造柔光氛圍
- 兩欄式 Hero (`grid grid-cols-2`):左文案 + 雙 CTA、右側產品/程式碼 mock
- CTA 層級對比:實心白底主鈕 `shadow-xl` vs. 外框透明次鈕 `border-2 border-white`
- 信任副本 + 滾動提示: `animate-bounce` 向下箭頭引導往下捲動
- 標籤 pill: `bg-white/20 rounded-full` (如 "New Release 2.0")

## 關鍵程式片段
```html
<section class="min-h-screen flex items-center bg-gradient-to-br from-indigo-600 via-purple-600 to-pink-500 relative overflow-hidden">
  <div class="grid grid-cols-2 gap-12 items-center">
    <div>
      <span class="px-4 py-2 bg-white/20 text-white rounded-full text-sm mb-6">New Release 2.0</span>
      <h1 class="text-6xl font-extrabold text-white leading-tight mb-6">
        Build Something<br/><span class="text-yellow-300">Amazing</span> Today
      </h1>
      <div class="flex gap-4">
        <button class="px-8 py-4 bg-white text-indigo-600 rounded-lg font-bold shadow-xl">Start Free Trial</button>
        <button class="px-8 py-4 border-2 border-white text-white rounded-lg font-bold">Watch Demo</button>
      </div>
    </div>
    <div>...產品預覽 mock...</div>
  </div>
</section>
```

## Do / Don't
- ✅ 適合產品 Landing Page、SaaS 首頁、新品發表,需快速傳達主張並導引轉換
- ✅ 主/次 CTA 對比明確,並附「免信用卡 / 14 天免費」等降低門檻副本
- ✅ Hero 用滿版漸層 + 大字 + 產品 mock,讓焦點集中在單一行動
- ❌ 不要在 Hero 塞太多選項或連結,稀釋主要 CTA
- ❌ 不要讓 Hero 文字壓在低對比漸層上而難以閱讀
