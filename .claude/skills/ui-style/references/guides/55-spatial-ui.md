# #55 Spatial UI

- **分類**: Modern
- **檔案**: examples/55-spatial-ui.html
- **一句話**: 受 Apple Vision Pro 啟發的空間運算介面,以毛玻璃、景深與環境光暈營造三維懸浮感。

## 字型
- SF Pro Display (400-700) 與 Inter (400-700)
- 實際套用:`* { font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif; }`

## 配色 (取自實際 HTML,Tailwind 色票)
| 用途 | 色值 |
|---|---|
| 背景漸層 | `from-slate-900 via-purple-900 to-slate-900` |
| 環境光暈 | `bg-purple-500/30`、`bg-blue-500/30`、`bg-pink-500/20`(`blur-3xl`) |
| 玻璃面板 | `rgba(255,255,255,0.15)`(亮)/ `rgba(30,30,30,0.6)`(暗) |
| 圖示漸層 | `from-blue-400 to-blue-600`、`from-green-400 to-emerald-600`、`from-purple-400 to-violet-600` |
| 文字 | `text-white` / `text-white/70` / `text-white/50` |

## 招牌技法
- 毛玻璃面板 `.glass-panel`:`backdrop-filter: blur(40px)` + `rgba(255,255,255,0.15)` 底 + 半透明白邊。
- 深色玻璃變體 `.glass-panel-dark`:`rgba(30,30,30,0.6)` 底,適合主面板。
- 空間陰影 `.spatial-shadow`:雙層 `0 8px 32px rgba(0,0,0,0.12)` + `0 2px 8px rgba(0,0,0,0.08)` 製造漂浮。
- 景深層 `.depth-layer`:`perspective(1000px)`,hover 時 `translateZ(20px)` 推出。
- 巨型 `blur-3xl` 彩色圓形作環境光,以 `fixed inset-0 pointer-events-none` 鋪底。

## 關鍵程式片段
```html
<style>
  .glass-panel {
    background: rgba(255,255,255,0.15);
    backdrop-filter: blur(40px); -webkit-backdrop-filter: blur(40px);
    border: 1px solid rgba(255,255,255,0.2);
  }
  .spatial-shadow { box-shadow: 0 8px 32px rgba(0,0,0,0.12), 0 2px 8px rgba(0,0,0,0.08); }
  .depth-layer       { transform: perspective(1000px) translateZ(0); transition: transform .3s ease; }
  .depth-layer:hover { transform: perspective(1000px) translateZ(20px); }
</style>
<div class="glass-panel rounded-2xl p-6 depth-layer cursor-pointer">…</div>
```

## Do / Don't
- ✅ 玻璃面板務必有彩色背景在後方,blur 才有意義。
- ✅ 用大圓角、半透明白邊與雙層柔陰影營造懸浮。
- ✅ hover 以 translateZ 推進製造三維景深。
- ❌ 不要用不透明純色底,會喪失空間玻璃感。
- ❌ 不要省略環境光暈,介面會顯得扁平死板。
