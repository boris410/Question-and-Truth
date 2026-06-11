# #29 Heatmap & Density

- **分類**: BI-Analytics
- **檔案**: examples/29-heatmap-density.html
- **一句話**: 用 GitHub 貢獻圖式的色階方塊,在極暗底上以顏色深淺視覺化密度與強度。

## 字型
- Google Fonts：Inter，字重 400 / 500 / 600 / 700（全域 `* { font-family: 'Inter', sans-serif; }`）。

## 配色 (取自實際 HTML)
熱力色階為自訂 CSS class(實際 hex):
| 用途 | 色值 |
|---|---|
| 背景 / 最低 | `bg-slate-950` 主底、`.heat-0` #1e293b |
| 低 | `.heat-1` #1e3a5f |
| 中低 | `.heat-2` #0369a1 |
| 中 | `.heat-3` #0284c7 |
| 高 | `.heat-4` #38bdf8 |
| 最高 | `.heat-5` #7dd3fc |

文字:`text-white` #ffffff、次要 `text-slate-400` #94a3b8;卡片 `bg-slate-900`、邊框 `border-slate-800`。

## 招牌技法
- 自訂六階熱力色票 `.heat-0`～`.heat-5`,由深藍灰漸亮到淺天藍表示由低到高強度。
- GitHub 貢獻圖佈局:`grid grid-rows-7 gap-1` 直排成週,每格 `w-3 h-3 rounded`。
- hover 高亮 `hover:ring-1 hover:ring-white` 讓單格在密集網格中可被指認。
- 圖例 Less → More:並排五色方塊說明色階對應。
- 極暗 `bg-slate-950` 底色讓亮色資料點對比最大化。

## 關鍵程式片段
```html
<style>
    .heat-0 { background-color: #1e293b; }
    .heat-1 { background-color: #1e3a5f; }
    .heat-2 { background-color: #0369a1; }
    .heat-3 { background-color: #0284c7; }
    .heat-4 { background-color: #38bdf8; }
    .heat-5 { background-color: #7dd3fc; }
</style>
<div class="grid grid-rows-7 gap-1">
    <div class="w-3 h-3 rounded heat-2 cursor-pointer hover:ring-1 hover:ring-white"></div>
    <div class="w-3 h-3 rounded heat-0 cursor-pointer hover:ring-1 hover:ring-white"></div>
    <div class="w-3 h-3 rounded heat-3 cursor-pointer hover:ring-1 hover:ring-white"></div>
</div>
```

## Do / Don't
- ✅ 用一致的多階色票,色階深淺單調對應數值高低。
- ✅ 極暗背景搭配亮色資料點,放大密度對比。
- ✅ 提供 Less/More 圖例與單格 hover 高亮供精確判讀。
- ❌ 不要用彩虹多色相做色階(難以判斷高低順序)。
- ❌ 不要省略圖例,否則色塊無法解讀。
