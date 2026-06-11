# #48 Kinetic Typography

- **分類**: Modern
- **檔案**: examples/48-kinetic-typography.html
- **一句話**: 黑底上的巨大顯示字配各式動態與 hover 效果,讓文字會呼吸、會移動、會搶眼。

## 字型
- **Bebas Neue** (single weight):窄高大寫顯示字 (`.font-display`),用於巨型標題與按鈕
- **Inter** (400/500/600/700):無襯線內文 (`.font-sans`)

## 配色 (取自實際 HTML)
| 用途 | 色值 |
|---|---|
| 背景 | bg-black |
| 反白跑馬燈 | bg-white + text-black |
| 強調紅 | text-red-500 / bg-red-600 |
| 強調藍 | text-blue-500 |
| 文字 | text-white / text-gray-400 |
| 邊框 | border-gray-800 (hover border-white) |

## 招牌技法
- 漂浮動畫:`@keyframes float` 50% 時 `translateY(-20px)`,逐字加 `animation-delay` 製造錯落跳動。
- 無限跑馬燈:`@keyframes slide` 從 `translateX(-100%)` 到 `translateX(100%)`,`.animate-slide` 20s linear infinite。
- 逐字互動:`.letter:hover { transform: scale(1.2) rotate(5deg); }`,單字母拆成 `<span>` 排列。
- 巨型字 `text-[15rem]` / `text-[10rem]`,搭 `leading-none tracking-tight`。
- hover 觸發多種動態:`group-hover:animate-pulse`、`group-hover:translate-x-4`、`group-hover:rotate-12`、`group-hover:tracking-widest`,以及 `transform -skew-x-12` 斜切。

## 關鍵程式片段
```html
<style>
    @keyframes float { 0%,100% { transform: translateY(0); } 50% { transform: translateY(-20px); } }
    @keyframes slide { from { transform: translateX(-100%); } to { transform: translateX(100%); } }
    .animate-float { animation: float 3s ease-in-out infinite; }
    .letter { display: inline-block; transition: transform 0.3s ease; }
    .letter:hover { transform: scale(1.2) rotate(5deg); }
</style>
<div class="font-display text-[15rem] leading-none tracking-tight">
    <span class="letter text-white">M</span>
    <span class="letter text-red-500 animate-float" style="animation-delay: 0.1s">O</span>
    <span class="letter text-white">V</span>
    <span class="letter text-blue-500 animate-float" style="animation-delay: 0.3s">E</span>
</div>
```

## Do / Don't
- ✅ 把單字拆成 `<span>` 逐字套用動畫與 hover 效果,製造律動。
- ✅ 用 Bebas Neue 巨型顯示字 + 跑馬燈、float、skew 等動態手法。
- ❌ 不要在小尺寸內文上濫用動畫,動態應集中在主視覺文字。
- ❌ 避免過多同時進行的動畫,會讓畫面失焦且影響可讀性。
