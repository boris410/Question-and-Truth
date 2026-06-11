# #45 Vaporwave

- **分類**: Modern
- **檔案**: examples/45-vaporwave.html
- **一句話**: 80/90 年代懷舊未來主義,粉紫青漸層、捲動網格、鉻金屬字與日文點綴,迷幻又復古的數位鄉愁。

## 字型
- **Press Start 2P** (cursive):點陣電玩字 (`.font-retro`),用於主標與小標
- **VT323** (monospace):復古終端等寬字 (`.font-vt`),用於內文與日文裝飾

## 配色 (取自實際 HTML)
| 用途 | 色值 |
|---|---|
| 背景漸層 | from-purple-900 via-pink-600 to-cyan-400 |
| 網格線 | #FF71CE (粉) |
| 鉻金屬字 | #fff → #c0c0c0 → #fff → #c0c0c0 |
| 強調色 | text-pink-400 / text-cyan-400 / text-cyan-300 |
| 卡片 | bg-black/50 backdrop-blur + border pink-400/cyan-400 |
| 文字 | text-white / text-pink-200 / text-cyan-200 |

## 招牌技法
- 捲動網格背景:`.grid-bg` 雙向 `linear-gradient(#FF71CE 1px, transparent 1px)` 40px 格,搭 `@keyframes scroll` 無限下捲
- 鉻金屬字:`.chrome-text` 以 `linear-gradient(180deg,#fff,#c0c0c0,#fff,#c0c0c0)` + `background-clip:text` 模擬反光金屬
- 字母間距撐開的全形標題 `A E S T H E T I C`,搭日文 `アエステティック / 永遠 / 夢幻`
- 半透明毛玻璃卡 `bg-black/50 backdrop-blur border-2 border-pink-400/cyan-400`
- 粉/青螢光陰影按鈕 `shadow-lg shadow-pink-500/50`,搭 Tailwind 漸層色塊

## 關鍵程式片段
```html
<style>
    .grid-bg {
        background-image: linear-gradient(#FF71CE 1px, transparent 1px),
                          linear-gradient(90deg, #FF71CE 1px, transparent 1px);
        background-size: 40px 40px; animation: scroll 20s linear infinite;
    }
    @keyframes scroll { 0% { background-position: 0 0; } 100% { background-position: 0 40px; } }
    .chrome-text { background: linear-gradient(180deg,#fff 0%,#c0c0c0 50%,#fff 51%,#c0c0c0 100%);
        -webkit-background-clip: text; -webkit-text-fill-color: transparent; }
</style>
<h1 class="font-retro text-5xl mb-6 chrome-text">A E S T H E T I C</h1>
<span class="font-vt text-6xl text-cyan-300">アエステティック</span>
```

## Do / Don't
- ✅ 用粉紫青漸層底 + 捲動網格 + 鉻金屬字營造復古數位感
- ✅ 混入日文片假名與全形展開英文,搭點陣 (Press Start 2P) 與 VT323
- ✅ 卡片用毛玻璃半透明 + 粉/青螢光邊框與陰影
- ❌ 不要用沉穩中性配色或襯線字,會失去 vaporwave 的迷幻復古
- ❌ 避免乾淨扁平的現代風;此風格靠漸層、發光與懷舊質感取勝
