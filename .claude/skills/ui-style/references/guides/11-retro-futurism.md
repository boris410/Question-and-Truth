# #11 Retro-Futurism (復古未來主義)

- **分類**: General
- **檔案**: examples/11-retro-futurism.html
- **一句話**: 80 年代美學遇上未來想像,用霓虹輝光、CRT 掃描線與合成波氛圍打造賽博龐克視覺。

## 字型
- 標題與內文: `Orbitron` (400/500/600/700/800/900) — 科技感幾何無襯線
- 像素強調: `Press Start 2P` — 8-bit 復古遊戲字型

## 配色 (取自實際 HTML)
| 用途 | 色值 |
|---|---|
| 背景 (深黑藍) | #1A1A2E |
| 強調 / 霓虹藍 | #0080FF |
| 霓虹粉 | #FF006E |
| 霓虹青 | #00FFFF |
| 紫 | #5D34D0 |
| 文字 | 白 + gray-400/gray-500 輔助 |

## 招牌技法
- 霓虹輝光文字: `text-shadow: 0 0 10px, 0 0 20px, 0 0 40px <color>` 三層疊加製造光暈
- 霓虹邊框盒: `.neon-box` 用 `2px solid #0080FF` 配合 `box-shadow: 0 0 10px, 0 0 20px, inset 0 0 10px rgba(0,128,255,0.1)`
- CRT 掃描線: `repeating-linear-gradient(0deg, transparent 2px, rgba(0,0,0,0.3) 2px 4px)` 全螢幕 overlay
- 網格背景: 雙向 `linear-gradient` 1px 線條,`background-size: 50px 50px`
- 閃爍動畫: `@keyframes flicker` opacity 1↔0.8,週期 0.1s

## 關鍵程式片段
```html
<style>
  body { background: #1A1A2E; font-family: 'Orbitron', sans-serif; }
  .neon-cyan { color: #00FFFF; text-shadow: 0 0 10px #00FFFF, 0 0 20px #00FFFF, 0 0 40px #00FFFF; }
  .neon-box {
    box-shadow: 0 0 10px #0080FF, 0 0 20px #0080FF, inset 0 0 10px rgba(0,128,255,0.1);
    border: 2px solid #0080FF;
  }
  .scanlines {
    background: repeating-linear-gradient(0deg, transparent, transparent 2px, rgba(0,0,0,0.3) 2px, rgba(0,0,0,0.3) 4px);
  }
</style>
<h1 class="text-6xl font-black"><span class="neon-cyan">CYBER</span><span class="neon-pink">WAVE</span></h1>
```

## Do / Don't
- ✅ 用於遊戲、娛樂、音樂平台與藝術性質的科技品牌,以深色為主調
- ✅ 全大寫文字配 `tracking-widest`,強化復古終端機感
- ✅ 霓虹色限制在 2-3 種主色,避免畫面過於雜亂
- ❌ 不要用在需要長時間閱讀或高無障礙要求的場景 (霓虹輝光對比與可讀性差)
- ❌ 不要把掃描線疊在表單輸入區上,會干擾辨識
