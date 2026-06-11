# #37 Sales Intelligence

- **分類**: BI-Analytics
- **檔案**: examples/37-sales-intelligence.html
- **一句話**: 明亮的銷售管線儀表板,用 indigo 行動色與綠色成交數據驅動業務決策。

## 字型
- **Inter** (400/500/600/700),透過 `* { font-family: 'Inter' }` 全域套用

## 配色 (取自實際 HTML)
| 用途 | 色值 |
|---|---|
| 背景 | bg-gray-50 |
| 卡片/導覽 | bg-white / border-gray-200 |
| 主行動色 | bg-indigo-600 / hover:bg-indigo-700 |
| 成交/成長 | text-green-600 |
| 文字 | text-gray-900 / text-gray-500 |

## 招牌技法
- 主要 CTA 用 indigo 實心鈕 `bg-indigo-600 text-white rounded-lg hover:bg-indigo-700`(+ New Deal)
- 五欄管線摘要卡 `grid-cols-5 gap-4`,各卡 `rounded-xl p-5 shadow-sm border`
- 關鍵數字 `text-2xl font-bold`,成交額用綠色突顯(Closed Won = text-green-600)
- 對照敘述 `text-sm text-green-600`(+18% vs last quarter)直接掛在數字下
- 明亮中性底 + 單一 indigo 強調色,維持商務專業感

## 關鍵程式片段
```html
<button class="px-4 py-2 bg-indigo-600 text-white rounded-lg text-sm font-medium hover:bg-indigo-700 cursor-pointer">+ New Deal</button>
<div class="grid grid-cols-5 gap-4 mb-6">
    <div class="bg-white rounded-xl p-5 shadow-sm border border-gray-200">
        <p class="text-sm text-gray-500 mb-1">Pipeline Value</p>
        <p class="text-2xl font-bold text-gray-900">$4.2M</p>
        <p class="text-sm text-green-600">+18% vs last quarter</p>
    </div>
    <div class="bg-white rounded-xl p-5 shadow-sm border border-gray-200">
        <p class="text-sm text-gray-500 mb-1">Closed Won</p>
        <p class="text-2xl font-bold text-green-600">$1.8M</p>
    </div>
</div>
```

## Do / Don't
- ✅ 用單一行動色(indigo)集中所有「新增/前進」操作,引導業務動作
- ✅ KPI 數字下方附對照敘述(vs last quarter / vs avg),給予脈絡
- ✅ 成交相關數值用綠色,強化「拿下生意」的正向回饋
- ❌ 不要把每張卡都用不同強調色,管線數據需要平靜可掃讀的版面
- ❌ 避免缺少對照基準的孤立數字,業務需要的是趨勢而非快照
