# #30 Executive Summary Dashboard

- **分類**: BI-Analytics
- **檔案**: examples/30-executive-summary.html
- **一句話**: 淺色、留白、細字重的高階主管儀表板,把關鍵指標濃縮成一目了然的卡片。

## 字型
- Google Fonts：Inter，字重 300 / 400 / 500 / 600 / 700;大量使用 `font-light` 呈現高階報告的精緻感。

## 配色 (取自實際 HTML)
| 用途 | 色值 (Tailwind token / 對應 hex) |
|---|---|
| 背景 | `bg-gray-50` #f9fafb、卡片 `bg-white` #ffffff |
| 主色/強調 | `gray-900` #111827（重點長條 / Export 按鈕,沉穩無彩） |
| 文字 | `text-gray-900` #111827（KPI 數字）、`text-gray-500` #6b7280、`text-gray-400` #9ca3af |
| 點綴 | `text-green-600` #16a34a（正向變化）、警示 `text-yellow-600` / `bg-yellow-100`、長條 `bg-gray-200` |

## 招牌技法
- 淺底 `bg-gray-50` + 白卡 `rounded-2xl p-6 shadow-sm`,大圓角柔和投影呈現高級感。
- KPI 數字用 `text-4xl font-light`,刻意細字重而非粗體,顯示克制與精緻。
- 變化指標用綠色 `text-green-600` + 灰色對照文字(vs last quarter)。
- 純 CSS 長條圖:`flex items-end` + inline `style="height: ..px"`,當期 `bg-gray-900` 高亮、歷史季 `bg-gray-200` 淡化。
- 頂部報告期間標籤 + Export PDF 按鈕,符合主管「拿了就報告」的情境。

## 關鍵程式片段
```html
<div class="grid grid-cols-4 gap-6 mb-8">
    <div class="bg-white rounded-2xl p-6 shadow-sm">
        <p class="text-sm text-gray-500 mb-2">Total Revenue</p>
        <p class="text-4xl font-light text-gray-900">$4.2M</p>
        <div class="flex items-center gap-2 mt-2">
            <span class="text-green-600 text-sm font-medium">+18.2%</span>
            <span class="text-gray-400 text-sm">vs last quarter</span>
        </div>
    </div>
</div>
<div class="h-64 flex items-end gap-4">
    <div class="flex-1 text-center">
        <div class="bg-gray-900 rounded-t mx-auto w-12" style="height: 220px"></div>
        <p class="text-sm text-gray-900 font-medium mt-2">Q4</p>
    </div>
</div>
```

## Do / Don't
- ✅ 只放最關鍵的少數 KPI,每張卡含數字 + 變化 + 對照基準。
- ✅ 用淺底白卡 + 細字重 + 大留白營造高階報告質感。
- ✅ 用當期高亮、歷史淡化的方式凸顯最新數據。
- ❌ 不要像營運後台塞滿密集表格,違背「摘要」定位。
- ❌ 不要用粗體與飽和色,會破壞主管儀表板的克制感。
