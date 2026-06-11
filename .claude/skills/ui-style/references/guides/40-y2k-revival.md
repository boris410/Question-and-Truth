# #40 Y2K Revival

- **分類**: Modern
- **檔案**: examples/40-y2k-revival.html
- **一句話**: 千禧年科技樂觀主義復刻,霓虹漸層、發光字與毛玻璃泡泡按鈕,閃亮又浮誇。

## 字型
- **Orbitron** (400-900):科技感標題字 (`.font-y2k`),大量用於 hero 與標題
- **Inter** (400/500/600):內文 (`.font-sans`)

## 配色 (取自實際 HTML)
| 用途 | 色值 |
|---|---|
| 背景漸層 | from-purple-900 via-pink-600 to-cyan-400 |
| 霓虹洋紅 | #FF00FF |
| 霓虹青 | #00FFFF |
| 霓虹黃 | #FFFF00 |
| 強調 | bg-fuchsia-500 / bg-cyan-500/30 |
| 文字 | text-white / text-white/80 / text-white/60(半透明白) |

## 招牌技法
- 自訂霓虹漸層與漸層文字:`.gradient-y2k`(135deg #FF00FF→#00FFFF→#FF00FF)與 `.text-gradient-y2k`(background-clip:text + transparent fill)
- 發光字:`.glow { text-shadow: 0 0 10px #FF00FF, 0 0 20px #FF00FF, 0 0 30px #FF00FF; }`
- 毛玻璃:大量 `backdrop-blur-lg bg-white/10 border border-white/20`,泡泡卡片
- 玻璃泡泡鈕 `.bubble-btn`(白色半透明線性漸層 + 半透明白邊),配 `rounded-full`
- 全圓角 + 螢光陰影 `shadow-lg shadow-fuchsia-500/50`,營造塑膠光澤感

## 關鍵程式片段
```html
<style>
    .text-gradient-y2k { background: linear-gradient(90deg, #FF00FF, #00FFFF, #FFFF00); -webkit-background-clip: text; -webkit-text-fill-color: transparent; }
    .glow { text-shadow: 0 0 10px #FF00FF, 0 0 20px #FF00FF, 0 0 30px #FF00FF; }
    .bubble-btn { background: linear-gradient(180deg, rgba(255,255,255,0.4) 0%, rgba(255,255,255,0.1) 100%); border: 2px solid rgba(255,255,255,0.3); }
</style>
<body class="bg-gradient-to-br from-purple-900 via-pink-600 to-cyan-400 ...">
    <h1 class="font-y2k text-7xl font-black mb-6 glow">FUTURE<br/>NOSTALGIA</h1>
    <button class="bubble-btn px-8 py-4 rounded-full font-y2k font-semibold backdrop-blur-lg hover:bg-white/30">ENTER SITE ✦</button>
```

## Do / Don't
- ✅ 用霓虹洋紅/青/黃漸層 + 發光 text-shadow,堆出千禧年螢光感
- ✅ 毛玻璃半透明卡 (backdrop-blur + bg-white/10) 疊在彩色漸層背景上
- ✅ 大量圓角、星形符號 (✦ ★ ◆) 與 Orbitron 字型強化「未來感」
- ❌ 不要用沉穩低彩度配色,會徹底失去 Y2K 的浮誇樂觀
- ❌ 避免方正硬邊與扁平無光澤元素,此風格靠光澤與圓潤取勝
