# #12 Flat Design (扁平化設計)

- **分類**: General
- **檔案**: examples/12-flat-design.html
- **一句話**: 沒有陰影、沒有漸層、沒有 3D,只靠大膽純色與乾淨字型讓內容說話。

## 字型
- 全站: `Open Sans` (400/600/700) — 開源人文無襯線,清晰好讀

## 配色 (取自實際 HTML)
| 用途 | 色值 |
|---|---|
| 背景 | #ffffff / gray-100 |
| 主色 (Peter River 藍) | #3498db |
| 紅 (Alizarin) | #e74c3c |
| 橘 / 黃 | #f39c12 / #f1c40f |
| 綠 (Nephritis) | #27ae60 |
| 紫 (Amethyst) | #9b59b6 |
| 深色資訊區 | #2c3e50 |

## 招牌技法
- 完全零陰影、零圓角、零漸層 — 純色色塊直接拼接 (`grid-cols-4 gap-0`)
- Flat UI Colors 經典色票 (Alizarin / Peter River / Nephritis 等)
- hover 只用 `hover:opacity-80 transition-opacity`,不做位移或陰影
- 卡片以色塊頂圖 + 純白內容區呈現,無 border、無 shadow
- 表單用 `border-2 border-gray-300`,focus 時換成主色邊框 `focus:border-[#3498db]`

## 關鍵程式片段
```html
<section class="py-16 px-6">
  <div class="grid grid-cols-4 gap-0">
    <div class="bg-[#e74c3c] text-white p-8">
      <div class="text-4xl font-bold mb-2">01</div>
      <h3 class="text-xl font-bold mb-2">Bold Colors</h3>
      <p class="text-sm opacity-90">Bright, solid colors without gradients</p>
    </div>
    <div class="bg-[#f39c12] text-white p-8">...</div>
    <div class="bg-[#27ae60] text-white p-8">...</div>
    <div class="bg-[#9b59b6] text-white p-8">...</div>
  </div>
</section>
```

## Do / Don't
- ✅ 適合 Web/Mobile App、跨平台、SaaS 後台,效能與無障礙俱佳 (WCAG AAA)
- ✅ 用色塊面積與純色對比建立層級,而非陰影深度
- ✅ 保持低複雜度,讓內容優先於裝飾
- ❌ 不要為了「立體感」偷偷加陰影或漸層,會破壞扁平一致性
- ❌ 不要同時使用過多飽和主色於同一視窗,易造成視覺疲勞
