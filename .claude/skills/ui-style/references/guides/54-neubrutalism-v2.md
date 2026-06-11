# #54 Neubrutalism v2

- **分類**: Modern
- **檔案**: examples/54-neubrutalism-v2.html
- **一句話**: 粗黑邊框、硬實位移陰影與衝突鮮豔色塊的新粗獷主義升級版,張揚而毫不妥協。

## 字型
- Space Grotesk (400/500/600/700) — 全站(`* { font-family: 'Space Grotesk', sans-serif; }`)

## 配色 (取自實際 HTML)
| 用途 | 色值 |
|---|---|
| 背景(米白) | `#FFFBF0` |
| 邊框/陰影/文字 | `#000` |
| 主色(紫) | `#A388EE`(亦見 `#C4A1FF`) |
| 強調黃 | `#FFE156` |
| 強調紅/青/綠 | `#FF6B6B` / `#4ECDC4` / `#BAFFC9` |

## 招牌技法
- 硬實位移陰影 `.brutal-shadow`:`box-shadow: 6px 6px 0 #000`(大版 `10px 10px 0`),無模糊無漸層。
- 互動下壓效果 `.brutal-shadow-hover:hover`:陰影縮為 `3px 3px 0` 並 `transform: translate(3px,3px)`,模擬按壓。
- 一律 `border-4 border-black` 粗黑邊框(至少 4px)。
- 飽和衝突色塊大面積鋪陳,直角不圓角。
- 表單 focus 用 `focus:ring-4 focus:ring-[#FFE156]` 維持粗獷感。

## 關鍵程式片段
```html
<style>
  .brutal-shadow      { box-shadow: 6px 6px 0 #000; }
  .brutal-shadow-lg   { box-shadow: 10px 10px 0 #000; }
  .brutal-shadow-hover:hover { box-shadow: 3px 3px 0 #000; transform: translate(3px, 3px); }
</style>
<section class="border-4 border-black bg-[#A388EE] brutal-shadow-lg p-12">
  <span class="inline-block px-4 py-2 bg-[#FFE156] border-2 border-black font-bold">
    DESIGN STYLE #54
  </span>
  <button class="px-8 py-4 bg-black text-white font-bold border-4 border-black
                 brutal-shadow brutal-shadow-hover transition-all">GET STARTED</button>
</section>
```

## Do / Don't
- ✅ 邊框至少 4px、陰影一律純黑無模糊。
- ✅ 大膽混用衝突飽和色,直角優先。
- ✅ hover 用位移+陰影收縮模擬實體按壓。
- ❌ 不要用柔和漸層或羽化陰影。
- ❌ 不要把字級與字重壓低,粗獷主義要大而黑。
