# #43 AI-Native Interface

- **分類**: Modern
- **檔案**: examples/43-ai-native.html
- **一句話**: 以對話為核心的 AI 助理介面,聊天泡泡、打字中動畫、漸層頭像與行動卡片,乾淨克制的紫色點綴。

## 字型
- **Inter** (400/500/600/700):全站唯一字型 (`* { font-family: 'Inter' }`),中性現代無襯線

## 配色 (取自實際 HTML)
| 用途 | 色值 |
|---|---|
| 背景 | bg-slate-50 / bg-white |
| 主色 (使用者泡泡/按鈕) | bg-violet-600 (hover violet-700) |
| 漸層頭像 | from-violet-500 to-purple-600 |
| AI 泡泡 / 輸入框 | bg-slate-100 |
| 自訂漸層 | #667eea → #764ba2 (.gradient-border) |
| 文字 | text-slate-900 / text-slate-600 / text-slate-400 |

## 招牌技法
- 打字中動畫:`.thinking-dots span` 以 `blink 1.4s` + 0.2s/0.4s 延遲,三點依序閃爍
- 聊天泡泡不對稱圓角:使用者 `rounded-2xl rounded-tr-md`、AI `rounded-2xl rounded-tl-md`,並左右對齊區分角色
- 漸層圓形頭像 `bg-gradient-to-br from-violet-500 to-purple-600 rounded-full` 內嵌 SVG 圖示
- 行動卡片 (action card) `bg-white rounded-xl border hover:border-violet-300 hover:shadow-sm`,emoji + 標題
- 輸入列 `focus:ring-2 focus:ring-violet-500`,大量 `rounded-xl/2xl` 與淺灰邊框

## 關鍵程式片段
```html
<style>
    .thinking-dots span { animation: blink 1.4s infinite both; }
    .thinking-dots span:nth-child(2) { animation-delay: 0.2s; }
    .thinking-dots span:nth-child(3) { animation-delay: 0.4s; }
    @keyframes blink { 0%,80%,100% { opacity:0; } 40% { opacity:1; } }
</style>
<div class="flex justify-end">
    <div class="bg-violet-600 text-white rounded-2xl rounded-tr-md px-4 py-3">…</div>
</div>
<div class="thinking-dots flex gap-1">
    <span class="w-2 h-2 bg-slate-400 rounded-full"></span> …
</div>
```

## Do / Don't
- ✅ 以對話流為主軸:左右對齊的聊天泡泡 + 不對稱角 (rounded-tr/tl-md)
- ✅ 用紫色 (violet) 當唯一強調色,其餘維持白/slate 中性灰
- ✅ 加 thinking-dots 打字動畫與漸層頭像,強化「AI 在思考」的臨場感
- ❌ 不要塞入高彩度或多色裝飾,會破壞乾淨克制的助理質感
- ❌ 避免硬邊與重陰影;此風格靠柔和圓角與細邊框營造輕盈
