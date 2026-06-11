# #10 Aurora UI

- **分類**: General
- **檔案**: examples/10-aurora-ui.html
- **一句話**: 靈感來自極光的流動漸層,色彩緩慢呼吸流轉,營造夢幻氛圍深度。

## 字型
- Inter;字重 300 / 400 / 500 / 600 / 700,文字以白與 `text-white/80`、`text-white/60` 透明度變體為主。

## 配色 (取自實際 HTML)
| 用途 | 色值 |
|---|---|
| 極光漸層 | #667eea → #764ba2 → #f093fb → #f5576c → #4facfe |
| Mesh 漸層 | 多個 `hsla()` 放射點(28°/189°/355°/340° 等) |
| 玻璃卡片 | rgba(255,255,255,0.1) |
| 玻璃邊框 | rgba(255,255,255,0.2) |
| 文字 | 白 + `text-white/80`、`text-white/60` |

## 招牌技法
- `.aurora-bg`:135deg 五色漸層 + `background-size: 400% 400%` + `animation: aurora 15s ease infinite`,讓背景緩慢流動。
- `@keyframes aurora` 在 `background-position` 0%→100%→0% 之間循環,製造極光呼吸感。
- `.mesh-gradient` 用多個 `radial-gradient(at x% y%, hsla(...) 0px, transparent 50%)` 疊出網狀多點色彩。
- 內容用 `.glass-card`(半透明白 + `backdrop-filter: blur(20px)`)浮在漸層之上,hover `bg-white/20`。

## 關鍵程式片段
```css
.aurora-bg {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 25%, #f093fb 50%, #f5576c 75%, #4facfe 100%);
  background-size: 400% 400%;
  animation: aurora 15s ease infinite;
}
@keyframes aurora {
  0%   { background-position: 0% 50%; }
  50%  { background-position: 100% 50%; }
  100% { background-position: 0% 50%; }
}
```

## Do / Don't
- ✅ 動畫週期放慢(8–15 秒),色彩流動才柔和不躁。
- ✅ 內容卡片用玻璃材質浮在漸層上,維持可讀性。
- ✅ 用 mesh 多點放射漸層增加色彩層次與深度。
- ❌ 不要把動畫加太快,會分散注意力且耗效能。
- ❌ 不要在漸層上直接放小字無底色,可讀性差。
