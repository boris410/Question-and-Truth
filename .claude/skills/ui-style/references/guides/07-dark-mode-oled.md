# #07 Dark Mode (OLED)

- **分類**: General
- **檔案**: examples/07-dark-mode-oled.html
- **一句話**: 純黑底配螢光發光強調色,為 OLED 省電而生的深色主題。

## 字型
- Inter;字重 300 / 400 / 500 / 600 / 700,標題搭配發光效果,內文用 `text-gray-500`。

## 配色 (取自實際 HTML)
| 用途 | 色值 |
|---|---|
| 純黑背景 | #000000 |
| 卡片/表面 | #121212 |
| 螢光綠強調 | #39FF14 |
| 藍強調 | #0080FF |
| 金/紫強調 | #FFD700 / #BF00FF |
| 深藍點綴 | #0A0E27 |

## 招牌技法
- `body { background: #000000 }` 純黑,OLED 上像素關閉達到零耗電與無限對比。
- 文字發光 `.glow-green { text-shadow: 0 0 20px rgba(57,255,20,0.5) }`,各色都有對應 glow class。
- 表面用 #121212 微微提亮並加 `border border-white/5` 極細邊框分層。
- 圖示底盒加彩色外發光 `box-shadow: 0 0 30px rgba(57,255,20,0.3)`。

## 關鍵程式片段
```css
body { background: #000000; }
.glow-green { text-shadow: 0 0 20px rgba(57, 255, 20, 0.5); }
.glow-blue  { text-shadow: 0 0 20px rgba(0, 128, 255, 0.5); }
.glow-gold  { text-shadow: 0 0 20px rgba(255, 215, 0, 0.5); }
```
```html
<div class="bg-[#121212] rounded-2xl p-6 border border-white/5">
  <h3 class="glow-green text-[#39FF14]">Power Efficient</h3>
</div>
```

## Do / Don't
- ✅ 背景用真正的 #000000 才能發揮 OLED 省電與深黑優勢。
- ✅ 強調色用螢光色並加 text-shadow 發光,黑底上更亮眼。
- ✅ 表面用 #121212 微提亮並加極細邊框做層次。
- ❌ 不要大面積用發光螢光色當底色,會刺眼。
- ❌ 不要用灰底(#1a1a1a 以上)當主背景,失去 OLED 純黑優勢。
