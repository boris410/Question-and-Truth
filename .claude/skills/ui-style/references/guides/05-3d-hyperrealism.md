# #05 3D & Hyperrealism

- **分類**: General
- **檔案**: examples/05-3d-hyperrealism.html
- **一句話**: 用透視、立體旋轉與多層擬真陰影,打造金屬光澤與沉浸式空間深度。

## 字型
- Inter;字重 300 / 400 / 500 / 600 / 700 / 800,標題用 `font-extrabold` 並以漸層裁切文字 (`bg-clip-text text-transparent`)。

## 配色 (取自實際 HTML)
| 用途 | 色值 |
|---|---|
| 背景 | slate-900 → slate-800 → slate-900 漸層 |
| 金色漸層 | #FFD700 → #FFA500 → #FFD700 (135deg) |
| 金屬紫漸層 | #667eea → #764ba2 → #667eea |
| 卡片 | slate-800 / slate-900、`border-slate-700` |
| 文字 | 白 / `text-slate-400` |

## 招牌技法
- `.perspective { perspective: 1000px }` + `.card-3d { transform-style: preserve-3d }`,hover 觸發 `rotateY(10deg) rotateX(5deg)` 立體傾斜。
- 多層擬真陰影 `.realistic-shadow`:外陰影疊 `inset 0 1px 0 rgba(255,255,255,0.2)` 高光,模擬實體受光。
- `.depth-shadow` 用超大模糊長距陰影製造漂浮深度。
- 金/金屬漸層搭配彩色光暈陰影 (`box-shadow: 0 15px 35px rgba(255,215,0,0.3)`) 強化材質感。

## 關鍵程式片段
```css
.card-3d {
  transform-style: preserve-3d;
  transition: transform 0.5s;
}
.card-3d:hover { transform: rotateY(10deg) rotateX(5deg); }
.realistic-shadow {
  box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.5),
              0 10px 20px -5px rgba(0, 0, 0, 0.3),
              inset 0 1px 0 rgba(255, 255, 255, 0.2);
}
```

## Do / Don't
- ✅ 在深色背景上用金屬/金色漸層與多層陰影,材質才突出。
- ✅ hover 立體旋轉幅度保持輕微(5–10 度),過度會暈眩。
- ✅ 用 inset 高光線模擬光源,增加真實感。
- ❌ 不要在淺色背景上用,陰影層次會消失。
- ❌ 不要忽略效能,過多 3D transform 與大陰影會掉幀。
