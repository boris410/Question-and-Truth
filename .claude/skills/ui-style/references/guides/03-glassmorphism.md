# #03 Glassmorphism

- **分類**: General
- **檔案**: examples/03-glassmorphism.html
- **一句話**: 半透明毛玻璃疊在繽紛漸層之上,用模糊與透光營造層次與深度。

## 字型
- Inter;字重 300 / 400 / 500 / 600 / 700,文字主要為白色與 `text-white/70`、`text-white/60` 等透明度變體。

## 配色 (取自實際 HTML)
| 用途 | 色值 |
|---|---|
| 漸層背景 | #667eea → #764ba2 → #f093fb (135deg) |
| 替代漸層 | #0080FF → #8B00FF → #FF1493 |
| 玻璃面 | rgba(255,255,255,0.15) |
| 玻璃邊框 | rgba(255,255,255,0.2) |
| 點綴/光暈 | #FF1493 / #8B00FF / #20B2AA |
| 文字 | 白 + `text-white/70`、`text-white/60` |

## 招牌技法
- 核心 `.glass`:`background: rgba(255,255,255,0.15)` + `backdrop-filter: blur(20px)` + `1px solid rgba(255,255,255,0.2)` 邊框。
- 背景用 `linear-gradient(135deg, ...)` 全屏漸層,玻璃才有可透光的內容。
- 漂浮光球:`rounded-full mix-blend-multiply filter blur-3xl opacity-70 animate-pulse`,加 `animation-delay` 錯開節奏。
- hover 提升透明度 `hover:bg-white/20` 增強互動回饋。

## 關鍵程式片段
```css
.glass {
  background: rgba(255, 255, 255, 0.15);
  backdrop-filter: blur(20px);
  -webkit-backdrop-filter: blur(20px);
  border: 1px solid rgba(255, 255, 255, 0.2);
}
.gradient-bg {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 50%, #f093fb 100%);
}
```

## Do / Don't
- ✅ 玻璃下方一定要有色彩豐富的背景,模糊才有意義。
- ✅ 同時加 `-webkit-backdrop-filter` 確保 Safari 相容。
- ✅ 邊框用半透明白增加玻璃邊緣的反光感。
- ❌ 不要在純色或低對比背景上用玻璃,效果會消失。
- ❌ 不要疊太多層 blur,會嚴重影響效能與可讀性。
