# #14 Liquid Glass (液態玻璃)

- **分類**: General
- **檔案**: examples/14-liquid-glass.html
- **一句話**: 流動變形的有機形狀、彩虹虹彩與深度模糊玻璃,營造高端、夢幻的流體質感。

## 字型
- 全站: `Inter` (300/400/500/600/700)

## 配色 (取自實際 HTML)
| 用途 | 色值 |
|---|---|
| 背景 (流體漸層) | #667eea → #764ba2 → #f093fb |
| 玻璃面 | rgba(255,255,255,0.15) + blur(30px) |
| 邊框 | rgba(255,255,255,0.3) |
| 虹彩 | 紅/黃/綠/青/藍/紫 各 0.1 透明度漸層 |
| 文字 | 白 + white/80、white/60、white/50 階層 |

## 招牌技法
- 液態玻璃 `.liquid-glass`: `background: rgba(255,255,255,0.15)` + `backdrop-filter: blur(30px)` + 30px 大圓角
- 虹彩 `.iridescent`: 六色 `linear-gradient(135deg)` 低透明度疊加製造全息色散
- 形狀變形動畫 `morph`: `border-radius` 在 `60% 40% 30% 70% / 60% 30% 70% 40%` 與 `30% 60% 70% 40% / 50% 60% 30% 60%` 間流動,8s 循環
- 漂浮動畫 `float`: `translateY(0 → -20px)` 6s,並以 `animation-delay` 錯開多個 blob
- 背景模糊光球: `bg-pink-400/30 rounded-full filter blur-3xl morphing floating`

## 關鍵程式片段
```html
<style>
  body { background: linear-gradient(135deg, #667eea 0%, #764ba2 50%, #f093fb 100%); }
  .liquid-glass {
    background: rgba(255,255,255,0.15);
    backdrop-filter: blur(30px); -webkit-backdrop-filter: blur(30px);
    border: 1px solid rgba(255,255,255,0.3);
    border-radius: 30px;
  }
  @keyframes morph {
    0%,100% { border-radius: 60% 40% 30% 70% / 60% 30% 70% 40%; }
    50%     { border-radius: 30% 60% 70% 40% / 50% 60% 30% 60%; }
  }
  .morphing { animation: morph 8s ease-in-out infinite; }
</style>
```

## Do / Don't
- ✅ 適合高端 SaaS、精品電商、創意平台與品牌體驗 (建議搭 Framer / GSAP)
- ✅ 用 `animation-delay` 錯開漂浮與變形,避免所有元素同步抖動
- ✅ 玻璃面需在彩色背景上才看得出折射感,務必配漸層底
- ❌ 注意對比:白字配淺色玻璃可能不達無障礙標準,需檢查 contrast
- ❌ `backdrop-filter: blur(30px)` 效能成本高,不要在低階裝置大量堆疊
