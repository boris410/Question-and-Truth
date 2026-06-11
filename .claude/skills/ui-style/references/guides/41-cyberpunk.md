# #41 Cyberpunk

- **分類**: Modern
- **檔案**: examples/41-cyberpunk.html
- **一句話**: 黑底 + 霓虹螢光 (洋紅/青/黃),發光字、掃描線與 glitch 抖動,打造「高科技、低生活」的賽博龐克終端介面。

## 字型
- **Orbitron** (400-900):科技標題字 (`.font-cyber`),用於 hero 與卡片標題
- **Share Tech Mono** (monospace):等寬內文 (`.font-mono`),營造終端機/程式碼質感

## 配色 (取自實際 HTML)
| 用途 | 色值 |
|---|---|
| 背景 | bg-black / bg-gray-900 / bg-gray-950 |
| 霓虹洋紅 | #FF00FF (fuchsia-500) |
| 霓虹青 | #00FFFF (cyan-400) |
| 霓虹黃 | #FFFF00 (yellow-400) |
| 邊框/強調 | border-cyan-500/30 · border-fuchsia-500/50 · text-green-400 |
| 文字 | text-white / text-gray-400 |

## 招牌技法
- 霓虹發光字:`text-shadow: 0 0 5px #FF00FF, 0 0 10px #FF00FF, 0 0 20px #FF00FF`(青/黃同理)
- Glitch 抖動動畫:`@keyframes glitch` 在 0.3s 內以 ±2px translate 快速抖動
- 掃描線疊層:`repeating-linear-gradient(0deg, rgba(0,0,0,0.1) 1px, transparent 2px)` 全螢幕 `fixed inset-0 opacity-20`
- 半透明深色卡片 + 細霓虹邊 `bg-gray-900/80 border border-cyan-500/30`,卡片頂端漸層光條
- 漸層文字標題 `bg-clip-text bg-gradient-to-r from-fuchsia-500 via-cyan-400 to-yellow-400`

## 關鍵程式片段
```html
<style>
    .neon-pink { text-shadow: 0 0 5px #FF00FF, 0 0 10px #FF00FF, 0 0 20px #FF00FF; }
    .glitch { animation: glitch 0.3s infinite; }
    @keyframes glitch {
        0%,100% { transform: translate(0); }
        20% { transform: translate(-2px,2px); } 40% { transform: translate(-2px,-2px); }
        60% { transform: translate(2px,2px); } 80% { transform: translate(2px,-2px); }
    }
    .scanline { background: repeating-linear-gradient(0deg, rgba(0,0,0,0.1), rgba(0,0,0,0.1) 1px, transparent 1px, transparent 2px); }
</style>
<h1 class="font-cyber text-8xl font-black text-transparent bg-clip-text bg-gradient-to-r from-fuchsia-500 via-cyan-400 to-yellow-400">NIGHT CITY</h1>
```

## Do / Don't
- ✅ 黑/深灰底搭洋紅·青·黃霓虹,並用 text-shadow 發光營造氛圍
- ✅ 等寬字寫成 `>> SYSTEM ONLINE_` / `// USERS` 等終端機文案,加掃描線疊層
- ✅ 卡片用半透明深色 + 細霓虹邊框與頂端漸層光條
- ❌ 不要用亮底或柔和粉彩,會破壞賽博龐克的暗黑霓虹反差
- ❌ 避免圓潤可愛的造型;此風格靠硬邊、發光與 glitch 取勝
