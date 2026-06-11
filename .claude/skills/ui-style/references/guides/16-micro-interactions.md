# #16 Micro-interactions (微互動)

- **分類**: General
- **檔案**: examples/16-micro-interactions.html
- **一句話**: 小細節、大影響 — 透過觸覺回饋、手勢回應與情境動畫帶來愉悅感。

## 字型
- 全站: `Inter` (400/500/600/700)

## 配色 (取自實際 HTML)
| 用途 | 色值 |
|---|---|
| 背景 | slate-100 |
| 卡片 | 白 + shadow |
| 主色 | blue-500 (#3B82F6 focus 環) |
| 成功 | #22C55E |
| 錯誤 | #EF4444 |
| 警告 | #F59E0B |

## 招牌技法
- 漣漪按鈕 `.btn-ripple`: `::after` 偽元素由 0 擴張至 300px 圓形,`:active` 觸發 (`transition: width/height 0.4s`)
- 自訂 Checkbox: `:checked + label .checkmark` 變色 + 勾號 `transform: scale(0→1)`
- 開關 `.toggle-switch.active`: 背景轉 `#22C55E`,旋鈕 `translateX(24px)`,JS `classList.toggle('active')` 控制
- 愛心 `.like-btn.liked`: `fill: #EF4444` + `scale(1.2)` 即時放大回饋
- 輸入框 focus: `box-shadow: 0 0 0 3px rgba(59,130,246,0.2)` 柔和聚焦環
- 即時回饋微動: `active:scale-95`、`hover:scale-105`、`transition-transform`,時長 50–100ms 級

## 關鍵程式片段
```html
<style>
  .btn-ripple::after {
    content: ''; position: absolute; top: 50%; left: 50%;
    width: 0; height: 0; background: rgba(255,255,255,0.3);
    border-radius: 50%; transform: translate(-50%, -50%);
    transition: width 0.4s, height 0.4s;
  }
  .btn-ripple:active::after { width: 300px; height: 300px; }
  .toggle-switch.active { background: #22C55E; }
  .toggle-switch.active .toggle-knob { transform: translateX(24px); }
</style>
<div class="toggle-switch ..." onclick="this.classList.toggle('active')">
  <div class="toggle-knob ..."></div>
</div>
```

## Do / Don't
- ✅ 適合行動 App、觸控介面、生產力與消費型應用 (搭 React Spring / Framer)
- ✅ 對每個互動 (點擊、勾選、收藏) 提供即時視覺回饋
- ✅ 動畫保持極短 (50–100ms),回饋才覺得「跟手」
- ❌ 不要讓回饋動畫拖長或誇張,反而妨礙操作流暢
- ❌ 不要僅以顏色傳達狀態 (成功/錯誤應同時搭配圖示)
