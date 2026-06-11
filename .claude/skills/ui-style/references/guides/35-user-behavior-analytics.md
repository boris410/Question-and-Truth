# #35 User Behavior Analytics

- **分類**: BI-Analytics
- **檔案**: examples/35-user-behavior-analytics.html
- **一句話**: 用漸層藍漏斗圖呈現使用者轉換流程,把「人怎麼一步步流失」視覺化。

## 字型
- **Inter** (400/500/600/700),透過 `* { font-family: 'Inter' }` 全域套用

## 配色 (取自實際 HTML)
| 用途 | 色值 |
|---|---|
| 背景 | bg-gray-100 |
| 卡片/導覽 | bg-white / border-gray-200 |
| 漏斗層級(由深到淺) | bg-blue-500 → bg-blue-400 → bg-blue-300 |
| 文字 | text-gray-900 / text-gray-500 |

## 招牌技法
- 轉換漏斗:`flex items-end justify-between gap-4 h-64`,每段柱子用 inline `style="height: 68%"` 表示留存率
- 漏斗各層用遞減的藍色階(blue-500→400→300),視覺暗示逐步流失
- 每段標明絕對人數(text-2xl font-bold)+ 百分比(text-gray-500),量化每步
- 下拉時間範圍 `<select>`(Last 30 days),控制分析區間
- 統一卡片 `bg-white rounded-xl p-6 shadow-sm border`
- 用 flex 等寬柱 + 百分比高度,免外掛圖表庫即可手刻漏斗

## 關鍵程式片段
```html
<div class="flex items-end justify-between gap-4 h-64">
    <div class="flex-1 flex flex-col items-center">
        <div class="w-full bg-blue-500 rounded-t" style="height: 100%"></div>
        <p class="mt-2 text-sm font-medium text-gray-900">Visitors</p>
        <p class="text-2xl font-bold text-gray-900">45,231</p>
        <p class="text-sm text-gray-500">100%</p>
    </div>
    <div class="flex-1 flex flex-col items-center">
        <div class="w-full bg-blue-400 rounded-t" style="height: 68%"></div>
        <p class="mt-2 text-sm font-medium text-gray-900">Signed Up</p>
        <p class="text-2xl font-bold text-gray-900">30,757</p>
    </div>
</div>
```

## Do / Don't
- ✅ 漏斗每階同時給人數與百分比,讓流失點一目了然
- ✅ 用同色系深淺表示流程順序,視覺上自然「漸窄」
- ✅ 提供時間區間切換,行為數據需可按週期比較
- ❌ 不要用無關聯的雜色標示漏斗各層,會破壞「同一條路徑」的認知
- ❌ 避免只給百分比不給絕對人數,難以判斷樣本規模
