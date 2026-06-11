# #46 Dimensional Layering

- **分類**: Modern
- **檔案**: examples/46-dimensional-layering.html
- **一句話**: 用堆疊色塊、偏移陰影與模糊光暈製造三維縱深,讓每一層承擔不同的視覺層級。

## 字型
- **Inter** (400/500/600/700/800):全站唯一字型 (`* { font-family: 'Inter' }`),中性現代無襯線

## 配色 (取自實際 HTML)
| 用途 | 色值 |
|---|---|
| 背景 | bg-slate-100 |
| 卡片 | bg-white / border-slate-200 |
| 主漸層 | from-blue-500 to-violet-600 / from-indigo-500 to-purple-600 |
| 強調色塊 | from-pink-500 to-rose-500 · from-amber-500 to-orange-500 · from-emerald-500 to-teal-500 |
| 深色區塊 | from-slate-900 to-slate-800 |
| 文字 | text-slate-900 / text-slate-600 / text-slate-400 |

## 招牌技法
- 卡片堆疊製造縱深:同位 `absolute inset-0` 多層,搭 `rotate-6 translate-x-8 translate-y-8 opacity-20`、`rotate-3 ... opacity-40`、前景全不透明。
- hover 位移加深感:`group-hover:translate-x-3 group-hover:translate-y-3 transition-transform` 讓陰影色塊滑出。
- 偏移彩色陰影層:卡片底下墊一層漸層 `translate-x-2 translate-y-2` 模擬 3D 投影。
- 模糊光暈:`bg-blue-500/20 rounded-full blur-3xl` 漂浮在深色區塊角落。
- 多重陰影層級 `shadow-xl` / `shadow-2xl` + 毛玻璃 `bg-white/10 backdrop-blur-lg` 浮動卡片並 `-rotate-3`。

## 關鍵程式片段
```html
<div class="relative h-96 max-w-2xl mx-auto perspective-1000">
    <div class="absolute inset-0 bg-gradient-to-br from-indigo-500 to-purple-600 rounded-3xl transform rotate-6 translate-x-8 translate-y-8 opacity-20"></div>
    <div class="absolute inset-0 bg-gradient-to-br from-violet-500 to-indigo-600 rounded-3xl transform rotate-3 translate-x-4 translate-y-4 opacity-40 shadow-xl"></div>
    <div class="absolute inset-0 bg-gradient-to-br from-blue-500 to-violet-600 rounded-3xl shadow-2xl p-12 text-white flex flex-col justify-center">
        <h2 class="text-4xl font-bold mb-4">Stacked Perspectives</h2>
    </div>
</div>
```

## Do / Don't
- ✅ 用 translate 偏移 + 遞減 opacity 堆疊多層,製造可感知的深度。
- ✅ 搭配 blur-3xl 光暈與多級陰影 (shadow-xl / shadow-2xl) 強化縱深。
- ❌ 不要把所有元素放在同一平面,失去層次就失去風格核心。
- ❌ 避免過度旋轉與偏移,會讓版面顯得雜亂、難以閱讀。
