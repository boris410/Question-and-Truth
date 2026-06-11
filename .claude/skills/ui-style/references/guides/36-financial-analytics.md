# #36 Financial Analytics

- **分類**: BI-Analytics
- **檔案**: examples/36-financial-analytics.html
- **一句話**: 深色交易終端風,用等寬數字與翡翠綠漸層突顯投資組合的盈虧。

## 字型
- **JetBrains Mono** (400/500):用於金額、百分比、貨幣等所有財務數字
- **Inter** (400/500/600/700):用於介面文字

## 配色 (取自實際 HTML)
| 用途 | 色值 |
|---|---|
| 背景 | bg-slate-950 |
| 卡片/導覽 | bg-slate-900 / border-slate-800 |
| 主視覺漸層 | from-emerald-600 to-emerald-700 |
| 獲利(正) | text-green-400 / bg-emerald-500/30 |
| 文字 | text-white / text-slate-400 / text-slate-500 |

## 招牌技法
- 投資組合主卡用 `col-span-2 bg-gradient-to-br from-emerald-600 to-emerald-700`,跨欄+漸層強化主指標
- 所有金額用 `font-mono font-bold`,大者 `text-4xl`(如 $2,847,521.84),數字對齊整齊
- 漲幅徽章 `bg-emerald-500/30 rounded text-xs`(半透明)貼在金額旁
- 五欄不對稱網格 `grid-cols-5`,主卡占 2 欄、其餘各 1 欄
- 深 slate-950 背景 + 綠色盈利文字,典型金融終端配色

## 關鍵程式片段
```html
<div class="col-span-2 bg-gradient-to-br from-emerald-600 to-emerald-700 rounded-xl p-6">
    <p class="text-emerald-100 text-sm mb-1">Total Portfolio Value</p>
    <p class="text-4xl font-bold font-mono mb-2">$2,847,521.84</p>
    <div class="flex items-center gap-2">
        <span class="text-emerald-200 font-mono">+$124,847.32</span>
        <span class="px-2 py-0.5 bg-emerald-500/30 rounded text-xs">+4.58%</span>
    </div>
</div>
```

## Do / Don't
- ✅ 金額與百分比一律用等寬字,小數點與千分位才會對齊
- ✅ 用漸層主卡突顯最重要的單一數字(總資產)
- ✅ 保留完整小數(如 .84),財務情境要求精確
- ❌ 不要用比例字呈現金額,跳動時數字會晃動難讀
- ❌ 避免在深色背景用低對比灰字標示關鍵盈虧
