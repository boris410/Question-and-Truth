# #18 Zero Interface (零介面)

- **分類**: General
- **檔案**: examples/18-zero-interface.html
- **一句話**: 最好的 UI 就是沒有 UI — 以語音優先、手勢與 AI 驅動的隱形控制,主動預測使用者需求。

## 字型
- 全站: `Inter` (300/400/500/600) — 偏細字重,強調輕盈低存在感

## 配色 (取自實際 HTML)
| 用途 | 色值 |
|---|---|
| 背景 | #FAFAFA (極淺灰) |
| 卡片 | 白 / white/80 + backdrop-blur |
| 強調漸層 | blue-400 → purple-500 |
| 對話氣泡 | blue-500 (使用者) / gray-100 (AI) |
| 情境色塊 | #F5F1E8 / #E5E5E5 等柔和中性色 |
| 文字 | gray-800 + gray-400/gray-500 |

## 招牌技法
- 極簡導覽: `bg-white/80 backdrop-blur-sm`,文字用 gray-300/gray-400 近乎隱形
- 語音麥克風球: `bg-gradient-to-br from-blue-400 to-purple-500 rounded-full` + `pulse-slow` 緩慢脈動 (scale 1↔1.1, opacity 0.8↔1, 3s)
- 打字指示動畫 `typing-dot`: opacity 0.3↔1,1s 循環,三點以 `animation-delay` 0.2s/0.4s 錯開
- 對話式 UI: 圓角氣泡 `rounded-2xl` 搭配 `rounded-br-none / rounded-bl-none` 製造方向尾巴
- 大量留白與置中單欄 (`max-w-2xl / max-w-md mx-auto text-center`),弱化控制元件存在感

## 關鍵程式片段
```html
<style>
  body { background: #FAFAFA; }
  @keyframes pulse-slow {
    0%,100% { transform: scale(1); opacity: 0.8; }
    50%     { transform: scale(1.1); opacity: 1; }
  }
  .pulse-slow { animation: pulse-slow 3s ease-in-out infinite; }
  .typing-dot { animation: typing 1s ease-in-out infinite; }
</style>
<div class="w-32 h-32 rounded-full bg-gradient-to-br from-blue-400 to-purple-500 pulse-slow">
  <div class="w-8 h-8 bg-white rounded-full"></div>
</div>
<h1 class="text-4xl font-light text-gray-800">The Best UI is No UI</h1>
```

## Do / Don't
- ✅ 適合語音助理、AI 對話、情境感知與穿戴式/環境運算介面
- ✅ 用緩慢脈動與打字點等「呼吸感」動效暗示系統正在聆聽/思考
- ✅ 以柔和中性色與大量留白降低介面存在感
- ❌ 不要塞入過多顯式按鈕與裝飾,違背「零介面」精神
- ❌ 不要完全移除視覺回饋,使用者仍需知道系統狀態
