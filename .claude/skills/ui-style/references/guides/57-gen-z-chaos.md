# #57 Gen Z Chaos

- **分類**: Modern
- **檔案**: examples/57-gen-z-chaos.html
- **一句話**: 「more is more」的 Z 世代混亂美學,旋轉貼紙卡、漸層動畫字與 glitch 抖動加上俚語梗滿溢。

## 字型
- Clash Display (400/500/600/700) — 大標與卡片標題(`.font-display`)
- Space Mono (400/700) — 內文與標籤(`.font-mono`)

## 配色 (取自實際 HTML)
| 用途 | 色值 |
|---|---|
| 背景(深藍紫) | `#1a1a2e` |
| 主色珊瑚紅 | `#FF6B6B` |
| 主色青綠 | `#4ECDC4` |
| 強調黃 | `#FFE66D` |
| 漸層用紫/薄荷 | `#A388EE` / `#95E1D3` |

## 招牌技法
- 動畫漸層裁字 `.gradient-text`:四色 `linear-gradient(135deg, #FF6B6B,#4ECDC4,#FFE66D,#95E1D3)` + `background-clip:text` + 5s 位移動畫。
- 多組無限動畫:`@keyframes wobble`(±2deg 搖擺)、`float-chaos`(浮動+旋轉)、`color-shift`(hue-rotate 360deg)。
- Glitch hover 抖動 `.glitch:hover`:`@keyframes glitch` 在 90%+ 才隨機位移,平時靜止。
- 貼紙陰影 `.sticker`:`filter: drop-shadow(3px 3px 0 rgba(0,0,0,0.3))` 配 `rotate-2`/`-rotate-3` 製造手貼感。
- 大圓角 `rounded-full`/`rounded-3xl`、emoji 與俚語梗(「no cap」「it's giving」「fr fr」)堆疊製造混亂能量。

## 關鍵程式片段
```html
<style>
  .gradient-text {
    background: linear-gradient(135deg,#FF6B6B,#4ECDC4,#FFE66D,#95E1D3);
    background-size: 300% 300%;
    -webkit-background-clip: text; -webkit-text-fill-color: transparent;
    animation: gradient 5s ease infinite;
  }
  @keyframes wobble { 0%,100%{transform:rotate(-2deg);} 50%{transform:rotate(2deg);} }
  .glitch:hover { animation: glitch 0.3s ease infinite; }
  .sticker { filter: drop-shadow(3px 3px 0 rgba(0,0,0,0.3)); }
</style>
<div class="bg-[#FF6B6B] p-6 rounded-3xl transform rotate-2 hover:rotate-0 transition-transform sticker">
  <span class="text-4xl block">🔥</span>
  <h3 class="font-display text-2xl">it's giving</h3>
</div>
```

## Do / Don't
- ✅ 大膽混用衝突鮮豔色、旋轉角度與動畫。
- ✅ 善用 emoji、貼紙陰影與俚語文案製造個性。
- ✅ 用漸層動畫字與 glitch 抖動當焦點。
- ❌ 不要追求對齊與留白克制,本風格刻意混亂。
- ❌ 不要全程開滿動畫到妨礙閱讀,重點處點綴即可。
