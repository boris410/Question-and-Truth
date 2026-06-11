# #52 Pixel Art / Retro Gaming

- **分類**: Modern
- **檔案**: examples/52-pixel-art.html
- **一句話**: 致敬 Game Boy 的 8-bit 復古遊戲介面,四色綠調點陣字搭配硬邊像素框。

## 字型
- Press Start 2P — 全站唯一字型(`* { font-family: 'Press Start 2P', cursive; }`)

## 配色 (取自實際 HTML,Game Boy 四色調色盤)
| 用途 | 色值 |
|---|---|
| 背景(最深) | `#0f380f` |
| 面板(中綠) | `#306230` |
| 邊框/次文字 | `#8bac0f` |
| 主文字(亮綠) | `#9bbc0f` |

## 招牌技法
- `image-rendering: pixelated` 全域套用,確保縮放不抗鋸齒。
- 粗實邊框 `border-4` / `border-2`,色值用對比綠 `#0f380f` 或 `#8bac0f`。
- SVG `border-image` 製作點陣化邊框:2x2 黑點貼圖 `border-image: url(...) 1`。
- 進度條以兩層 div 堆疊(外框 `#0f380f` + 內條 `#9bbc0f`),呈現血條/經驗條。
- 極小字級 `text-[8px]` / `text-xs` 配合 ASCII 符號(`>`、`★♦♠♣`)塑造選單感。

## 關鍵程式片段
```html
<style>
  * { font-family: 'Press Start 2P', cursive; image-rendering: pixelated; }
  .pixel-border {
    border: 4px solid;
    border-image: url("data:image/svg+xml,%3Csvg ... %3E%3Crect width='2' height='2' fill='%23000'/%3E%3C/svg%3E") 1;
  }
</style>
<body class="bg-[#0f380f] text-[#9bbc0f]">
  <button class="w-full text-left text-xs p-3 bg-[#0f380f] border-2 border-[#8bac0f]
                 hover:bg-[#8bac0f] hover:text-[#0f380f] transition-colors">
    &gt; START GAME
  </button>
</body>
```

## Do / Don't
- ✅ 嚴守四色限制調色盤,顏色越少越像真主機。
- ✅ 一律使用點陣字,字級維持小且整數倍縮放。
- ✅ 用粗硬邊框與雙層血條呈現遊戲 UI。
- ❌ 不要加平滑漸層、模糊陰影或抗鋸齒圓角。
- ❌ 不要混用無襯線正文字型,會立刻失去復古感。
