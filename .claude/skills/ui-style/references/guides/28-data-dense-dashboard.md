# #28 Data-Dense Dashboard

- **分類**: BI-Analytics
- **檔案**: examples/28-data-dense-dashboard.html
- **一句話**: 深色高密度後台,用小間距網格與等寬字塞進最多 KPI 與即時數據。

## 字型
- Google Fonts：JetBrains Mono（400/500）作數字 `.font-mono`;Inter（400/500/600/700）作介面 `.font-sans`。
- 等寬字呈現數字對齊、終端機般的專業數據感。

## 配色 (取自實際 HTML)
| 用途 | 色值 (Tailwind token / 對應 hex) |
|---|---|
| 背景 | `bg-slate-900` #0f172a（主底）、卡片/側欄 `bg-slate-800` #1e293b |
| 主色/強調 | `blue-600` #2563eb（選中導覽 / 按鈕）、ring `blue-500` |
| 文字 | `text-white` #ffffff、次要 `text-slate-400` #94a3b8 |
| 數據漲跌 | `text-green-400` #4ade80（上升）、`text-red-400` #f87171（下降）、在線點 `bg-green-500` |
| 分隔 | `border-slate-700` #334155 |

## 招牌技法
- 暗色主題 `bg-slate-900 text-white` 降低長時間盯盤的視覺疲勞。
- 小間距高密度網格 `grid grid-cols-6 gap-3`,KPI 卡 `p-3` 緊湊排列。
- 數字用等寬 `font-mono` 確保欄位對齊,搭配漲跌色碼(綠升紅降)。
- 固定左側 `w-48` 窄側欄導覽,選中項 `bg-blue-600` 高亮。
- 即時感:`animate-pulse` 綠點 + 「Last updated: 2 sec ago」。

## 關鍵程式片段
```html
<body class="bg-slate-900 min-h-screen font-sans text-white">
<div class="grid grid-cols-6 gap-3 mb-4">
    <div class="bg-slate-800 rounded p-3 border border-slate-700">
        <p class="text-xs text-slate-400 mb-1">Revenue</p>
        <p class="text-xl font-bold font-mono">$847.2K</p>
        <p class="text-xs text-green-400">+12.5%</p>
    </div>
    <div class="bg-slate-800 rounded p-3 border border-slate-700">
        <p class="text-xs text-slate-400 mb-1">Conversion</p>
        <p class="text-xl font-bold font-mono">3.42%</p>
        <p class="text-xs text-red-400">-0.3%</p>
    </div>
</div>
```

## Do / Don't
- ✅ 用暗底 + 小間距網格在單屏內塞入最多資訊。
- ✅ 數字一律用等寬字並以綠/紅標示漲跌。
- ✅ 提供即時更新時間戳與在線脈動指示。
- ❌ 不要在高密度後台用大圓角、大留白(浪費可視面積)。
- ❌ 不要過度用色,漲跌綠紅以外維持中性灰避免雜訊。
