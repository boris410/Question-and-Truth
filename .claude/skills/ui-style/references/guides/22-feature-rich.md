# #22 Feature-Rich Showcase

- **分類**: Landing
- **檔案**: examples/22-feature-rich.html
- **一句話**: 以深色 Hero 帶出多功能網格,向企業客戶展示「一站式平台」的完整能力。

## 字型
- Google Fonts：Inter，字重 400 / 500 / 600 / 700 / 800（全域 `* { font-family: 'Inter', sans-serif; }`）。

## 配色 (取自實際 HTML)
| 用途 | 色值 (Tailwind token / 對應 hex) |
|---|---|
| 背景 | `bg-slate-50` #f8fafc、Hero 漸層 `from-slate-900` #0f172a → `to-slate-800` #1e293b |
| 主色/強調 | `blue-600` #2563eb（CTA）、`blue-500/20` 半透明標籤、`blue-400` #60a5fa 標籤文字 |
| 文字 | `text-slate-900` #0f172a（主標）、`text-slate-600` #475569（內文）、`text-slate-400` #94a3b8 |
| 圖示底色 | 多彩 pastel：`blue-100` / `green-100` / `purple-100` / `orange-100` / `pink-100` |

## 招牌技法
- 深色漸層 Hero `bg-gradient-to-b from-slate-900 to-slate-800` 製造企業級高級感。
- 導覽列玻璃感 `bg-white/90 backdrop-blur-md border-b border-slate-200`。
- 三欄功能卡片網格 `grid grid-cols-3 gap-6`，卡片 hover `hover:shadow-lg transition-shadow`。
- 每張卡片用彩色方形圖示容器 `w-12 h-12 bg-{color}-100 rounded-lg` 區分功能類別。
- 半透明標籤 `bg-blue-500/20 text-blue-400` 在深底上呈現柔光徽章。

## 關鍵程式片段
```html
<section class="pt-24 pb-16 px-6 bg-gradient-to-b from-slate-900 to-slate-800">
    <div class="max-w-6xl mx-auto text-center">
        <span class="inline-block px-4 py-2 bg-blue-500/20 text-blue-400 rounded-full text-sm font-medium mb-6">Enterprise Platform</span>
        <h1 class="text-5xl font-extrabold text-white mb-6">Everything You Need in One Platform</h1>
    </div>
</section>
<div class="bg-white rounded-xl p-6 border border-slate-200 hover:shadow-lg transition-shadow cursor-pointer">
    <div class="w-12 h-12 bg-blue-100 rounded-lg flex items-center justify-center mb-4">
        <svg class="w-6 h-6 text-blue-600" ...></svg>
    </div>
    <h3 class="text-lg font-semibold text-slate-900 mb-2">Lightning Performance</h3>
</div>
```

## Do / Don't
- ✅ 用功能網格一次展示完整能力，每格搭配圖示與一句說明。
- ✅ 用彩色圖示底色為不同功能分類，維持版面活潑但有秩序。
- ✅ 深色 Hero 對比淺底內文區，建立段落層次。
- ❌ 不要每個功能寫長段文字，卡片描述維持一句話即可。
- ❌ 不要讓圖示顏色過於雜亂而失去品牌主色（藍）。
