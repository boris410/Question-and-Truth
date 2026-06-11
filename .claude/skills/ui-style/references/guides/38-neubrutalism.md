# #38 Neubrutalism

- **分類**: Modern
- **檔案**: examples/38-neubrutalism.html
- **一句話**: 粗黑邊框、硬陰影、飽和糖果色,刻意「不修飾」的大膽原始美學。

## 字型
- **Space Grotesk** (400/500/600/700),透過 `* { font-family: 'Space Grotesk' }` 全域套用;大量 font-bold

## 配色 (取自實際 HTML)
| 用途 | 色值 |
|---|---|
| 背景 | #FFF8E7 (奶油黃) |
| 邊框/陰影/主文字 | #000000 / #000 |
| 強調紅 | #FF6B6B |
| 青綠 | #4ECDC4 |
| 鵝黃 | #FFE66D |
| 薄荷綠 / 中性灰 | #A8E6CF / #E8E8E8 |

## 招牌技法
- 自訂硬陰影:`.brutal-shadow { box-shadow: 4px 4px 0 0 #000; }` 與 `.brutal-shadow-lg { box-shadow: 8px 8px 0 0 #000; }`(無模糊、純黑偏移)
- 一律 `border-4 border-black` 粗黑邊框包住每個區塊
- hover 互動:`hover:translate-x-1 hover:translate-y-1 hover:shadow-none transition-all`,按下時方塊「貼地」陰影消失
- 平塗飽和色塊(#FF6B6B / #4ECDC4 / #FFE66D),不用漸層
- 超大粗體標題 `text-6xl font-bold`,全大寫文案強化態度

## 關鍵程式片段
```html
<style>
    .brutal-shadow { box-shadow: 4px 4px 0 0 #000; }
    .brutal-shadow-lg { box-shadow: 8px 8px 0 0 #000; }
</style>
<div class="bg-[#FF6B6B] border-4 border-black brutal-shadow-lg p-12 text-center">
    <h1 class="text-6xl font-bold text-black mb-4">BOLD. RAW. HONEST.</h1>
    <button class="bg-black text-white px-8 py-4 text-xl font-bold border-4 border-black brutal-shadow hover:translate-x-1 hover:translate-y-1 hover:shadow-none transition-all cursor-pointer">
        GET STARTED →
    </button>
</div>
```

## Do / Don't
- ✅ 陰影用純黑、零模糊、固定偏移(4px/8px),這是 neubrutalism 的靈魂
- ✅ 平塗飽和色 + 粗黑邊框,顏色之間不過渡
- ✅ hover 時位移並收掉陰影,做出「實體按下」手感
- ❌ 不要加柔和漸層或模糊陰影,會立刻失去「粗野」氣質
- ❌ 避免細邊框或低對比配色,邊框越粗、對比越強越對味
