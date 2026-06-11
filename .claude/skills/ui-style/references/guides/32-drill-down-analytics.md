# #32 Drill-Down Analytics

- **分類**: BI-Analytics
- **檔案**: examples/32-drill-down-analytics.html
- **一句話**: 以麵包屑層級與可點擊表格,讓使用者一層層往下鑽探資料的明亮分析介面。

## 字型
- **Inter** (400/500/600/700),透過 `* { font-family: 'Inter' }` 全域套用

## 配色 (取自實際 HTML)
| 用途 | 色值 |
|---|---|
| 背景 | bg-slate-100 |
| 卡片/導覽 | bg-white / border-slate-200 |
| 主色/強調 | bg-blue-600 / text-blue-600 / hover:bg-blue-50 |
| 正向數值 | text-green-600 |
| 負向數值 | text-red-600 |
| 文字 | text-slate-900 / text-slate-500 |

## 招牌技法
- 麵包屑導覽:藍色連結 + `→` slate-400 分隔,末層 `text-slate-600 font-medium` 不可點
- 摘要卡片 `bg-white rounded-xl p-6 shadow-sm border`,內含 4 欄 `bg-slate-50 rounded-lg` 小指標
- 可鑽探資料表:`thead` 用 `bg-slate-50`、`uppercase tracking-wider` 表頭
- 整列可點:`<tr class="hover:bg-blue-50 cursor-pointer group">` 暗示往下層
- 漲跌以綠/紅文字呈現,維持 BI 慣例

## 關鍵程式片段
```html
<div class="flex items-center gap-2 text-sm mb-6">
    <a href="#" class="text-blue-600 hover:underline cursor-pointer">All Regions</a>
    <span class="text-slate-400">→</span>
    <a href="#" class="text-blue-600 hover:underline cursor-pointer">North America</a>
    <span class="text-slate-400">→</span>
    <span class="text-slate-600 font-medium">California</span>
</div>
<tr class="hover:bg-blue-50 cursor-pointer group">
    <td class="px-6 py-4">...</td>
</tr>
```

## Do / Don't
- ✅ 用麵包屑清楚標示目前鑽探深度,讓使用者能逐層回退
- ✅ 整列 hover 變色 + cursor-pointer,明示「點我可深入」
- ✅ 卡片與表格統一用 rounded-xl + shadow-sm + slate 邊框,保持輕量一致
- ❌ 不要在同一層塞太多維度,鑽探的價值在於漸進揭露
- ❌ 避免漲跌不分顏色,BI 使用者依賴紅綠快速判讀
