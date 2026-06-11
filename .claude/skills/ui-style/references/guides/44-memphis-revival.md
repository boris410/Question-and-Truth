# #44 Memphis Revival

- **分類**: Modern
- **檔案**: examples/44-memphis-revival.html
- **一句話**: 復刻 1980 年代 Memphis Group,幾何色塊、粗黑外框、硬陰影與波浪線,大膽俏皮、反極簡。

## 字型
- **Archivo Black** (single weight):超粗顯示字 (`.font-display`),用於標題與按鈕
- **Poppins** (400-700):圓潤無襯線內文 (`.font-sans`)

## 配色 (取自實際 HTML)
| 用途 | 色值 |
|---|---|
| 背景 (米黃) | #FFF5E6 |
| 珊瑚紅 (主色) | #FF6B6B |
| 蒂芬尼藍綠 | #4ECDC4 |
| 亮黃 | #FFE66D |
| 薄荷綠 / 梅紫 | #A8E6CF / #DDA0DD |
| 外框 / 文字 | black (border-4 border-black) |

## 招牌技法
- 粗黑外框:幾乎所有區塊 `border-4 border-black`,色塊互相碰撞
- 硬陰影按鈕:`shadow-[4px_4px_0_0_#000] hover:shadow-none hover:translate-x-1 hover:translate-y-1`(按下位移效果)
- 幾何裝飾形:圓 `rounded-full`、旋轉方塊 `transform rotate-45`、三角 `clip-path: polygon(50% 0%,0% 100%,100% 100%)`
- 波浪線圖樣:`.squiggle` 以 inline SVG (`stroke='%23FF6B6B'`) `background-repeat: repeat-x` 平鋪
- 角落浮出小色塊裝飾 `absolute -top-6 -left-6 ... border-4 border-black`

## 關鍵程式片段
```html
<style>
    .squiggle {
        background-image: url("data:image/svg+xml,%3Csvg ... %3Cpath d='M0 10 Q 25 0 50 10 T 100 10' fill='none' stroke='%23FF6B6B' stroke-width='3'/%3E%3C/svg%3E");
        background-repeat: repeat-x;
    }
</style>
<button class="bg-[#FF6B6B] text-white px-8 py-4 font-display text-xl border-4 border-black
    shadow-[4px_4px_0_0_#000] hover:shadow-none hover:translate-x-1 hover:translate-y-1 transition-all">
    GET STARTED
</button>
<div class="absolute ... w-12 h-12 bg-[#A8E6CF]" style="clip-path: polygon(50% 0%, 0% 100%, 100% 100%);"></div>
```

## Do / Don't
- ✅ 用珊瑚紅/藍綠/黃/薄荷的高彩度撞色 + 粗黑 border-4 外框
- ✅ 散布圓、旋轉方塊、三角與 squiggle 波浪線等幾何裝飾
- ✅ 按鈕用 `shadow-[4px_4px_0_0_#000]` 硬陰影 + hover 位移
- ❌ 不要追求對稱平衡或留白克制,Memphis 就是要混亂俏皮
- ❌ 避免柔和漸層與細陰影,會稀釋粗框平塗的視覺衝擊
