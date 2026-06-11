# #25 Interactive Product Demo

- **分類**: Landing
- **檔案**: examples/25-interactive-demo.html
- **一句話**: 把可操作的產品預覽直接放進 Hero,用「先試再買」的互動降低轉換門檻。

## 字型
- Google Fonts：Inter，字重 400 / 500 / 600 / 700 / 800（全域 `* { font-family: 'Inter', sans-serif; }`）。

## 配色 (取自實際 HTML)
| 用途 | 色值 (Tailwind token / 對應 hex) |
|---|---|
| 背景 | `bg-slate-50` #f8fafc、demo 視窗內底 `bg-slate-100` #f1f5f9 |
| 主色/強調 | `blue-600` #2563eb（按鈕）、focus `ring-blue-500`、脈動光暈 `rgba(59, 130, 246, ...)` |
| 文字 | `text-slate-900` #0f172a、`text-slate-600` #475569、`text-slate-400` #94a3b8 |
| 狀態點綴 | `green-600`/`green-500` #22c55e（Interactive 在線）、視窗紅黃綠燈 `red-400`/`yellow-400`/`green-400` |

## 招牌技法
- 自訂脈動動畫 `demo-highlight`：`@keyframes pulse-highlight` 用 `box-shadow` 從 `rgba(59,130,246,0.5)` 擴散到透明,提示「點我試試」。
- 兩欄 Hero：左文案、右側模擬 app 視窗卡片 `rounded-2xl p-6 shadow-xl border border-slate-200`。
- 模擬瀏覽器視窗：三顆紅黃綠燈 `w-3 h-3 bg-red-400/yellow-400/green-400 rounded-full`。
- 在線狀態用 `animate-pulse` 綠點 + 「Interactive」標籤即時感。
- 雙按鈕組合：主 `bg-blue-600` Start Demo + 次 `border border-slate-300` Watch Video。

## 關鍵程式片段
```html
<style>
    .demo-highlight { animation: pulse-highlight 2s ease-in-out infinite; }
    @keyframes pulse-highlight {
        0%, 100% { box-shadow: 0 0 0 0 rgba(59, 130, 246, 0.5); }
        50% { box-shadow: 0 0 0 8px rgba(59, 130, 246, 0); }
    }
</style>
<div class="bg-slate-100 rounded-xl p-4 mb-4">
    <div class="flex gap-2 mb-3">
        <div class="w-3 h-3 bg-red-400 rounded-full"></div>
        <div class="w-3 h-3 bg-yellow-400 rounded-full"></div>
        <div class="w-3 h-3 bg-green-400 rounded-full"></div>
    </div>
    <button class="px-4 py-2 bg-blue-600 text-white rounded text-sm font-medium hover:bg-blue-700 cursor-pointer demo-highlight">Try</button>
</div>
```

## Do / Don't
- ✅ 把可操作的 demo 區放在折疊線上方,標示「No signup required」。
- ✅ 用脈動光暈引導使用者點擊互動按鈕。
- ✅ 模擬 app/瀏覽器視窗外框增強「真實產品」感。
- ❌ 不要讓 demo 只是靜態截圖卻號稱互動。
- ❌ 不要用過多動畫干擾,脈動只用在唯一的引導按鈕。
