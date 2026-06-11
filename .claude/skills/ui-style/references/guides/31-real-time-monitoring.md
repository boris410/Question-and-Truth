# #31 Real-Time Monitoring

- **分類**: BI-Analytics
- **檔案**: examples/31-real-time-monitoring.html
- **一句話**: 暗色機房儀表板,用脈動指示燈與等寬數字營造「系統正在即時呼吸」的監控感。

## 字型
- **JetBrains Mono** (400/500/600):用於所有數據、百分比、時間戳
- **Inter** (400/500/600/700):用於介面文字與標題

## 配色 (取自實際 HTML)
| 用途 | 色值 |
|---|---|
| 背景 | bg-gray-950 |
| 卡片/導覽 | bg-gray-900 / border-gray-800 |
| 正常狀態(綠) | bg-green-600 / text-green-400 / bg-green-500 |
| 警示狀態(黃) | bg-yellow-500 / text-yellow-400 |
| 數據(藍) | text-blue-400 |
| 次要文字 | text-gray-400 / text-gray-500 |

## 招牌技法
- 自訂 `@keyframes pulse-green`(2s ease-in-out infinite,opacity 1→0.5)製造「心跳」狀態燈
- 頂部全寬綠色狀態列 + `animate-pulse` 圓點,傳達 All Systems Operational
- 五欄即時指標卡 `grid-cols-5 gap-3`,大字用 `text-3xl font-mono font-bold`
- 細進度條 `h-1 bg-gray-800` 內嵌 inline `style="width: 42%"` 表示即時負載
- 顏色語意化:綠=正常、黃=警告,直接以指示燈與數字顏色傳達狀態

## 關鍵程式片段
```html
<style>
    .font-mono { font-family: 'JetBrains Mono', monospace; }
    @keyframes pulse-green { 0%, 100% { opacity: 1; } 50% { opacity: 0.5; } }
    .animate-pulse-green { animation: pulse-green 2s ease-in-out infinite; }
</style>
<div class="bg-gray-900 rounded-lg p-4 border border-gray-800">
    <div class="flex justify-between items-start mb-2">
        <span class="text-xs text-gray-500">CPU Usage</span>
        <span class="w-2 h-2 bg-green-500 rounded-full animate-pulse-green"></span>
    </div>
    <p class="text-3xl font-mono font-bold text-green-400">42%</p>
    <div class="h-1 bg-gray-800 rounded mt-2"><div class="h-1 bg-green-500 rounded" style="width: 42%"></div></div>
</div>
```

## Do / Don't
- ✅ 數值一律用等寬字 (font-mono),對齊與跳動才穩定
- ✅ 用顏色 + 脈動動畫表達系統健康狀態,降低閱讀負擔
- ✅ 暗背景搭高對比螢光色,符合 NOC/監控大螢幕情境
- ❌ 不要讓所有指標燈同時亂閃或用過多顏色,會稀釋警示意義
- ❌ 避免在標題文字也用等寬字,易讀性會下降
