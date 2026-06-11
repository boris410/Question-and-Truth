# #42 Organic Biophilic

- **分類**: Modern
- **檔案**: examples/42-organic-biophilic.html
- **一句話**: 大地色系 + 有機不規則圓角 (organic / leaf shape),用襯線字與自然意象帶來平靜、療癒的生物親和設計。

## 字型
- **Cormorant Garamond** (400-700):優雅襯線標題 (`.font-serif`),用於 hero 與卡片標題
- **Nunito** (400/500/600):柔和無襯線內文 (`.font-sans`)

## 配色 (取自實際 HTML)
| 用途 | 色值 |
|---|---|
| 背景 (奶油) | #F5F1E8 |
| 深森林綠 (主色) | #3E4A32 |
| 鼠尾草綠 | #5D6B4D |
| 苔綠 / 葉綠 | #8FBC8F / #D4E4C1 |
| 沙土 / 米褐 | #C8B89E / #E8E0D0 |
| 邊框 / 輔助文字 | #E0D8C8 / #8A9A7B |

## 招牌技法
- 有機不規則圓角:`.organic-shape { border-radius: 30% 70% 70% 30% / 30% 30% 70% 70%; }`
- 葉片造型:`.leaf-shape { border-radius: 5% 95% 10% 90% / 85% 15% 85% 15%; }` 用於圖示底框
- 超大柔軟圓角容器:`rounded-[2rem]` / `rounded-[3rem]` / `rounded-full` 按鈕
- 角落漂浮的有機色塊裝飾 `absolute -top-10 -right-10 ... organic-shape opacity-50`
- 大地色塊堆疊與襯線字搭配,色票均為自訂 hex,帶葉片/植物 emoji 與 SVG

## 關鍵程式片段
```html
<style>
    .organic-shape { border-radius: 30% 70% 70% 30% / 30% 30% 70% 70%; }
    .leaf-shape { border-radius: 5% 95% 10% 90% / 85% 15% 85% 15%; }
</style>
<body class="bg-[#F5F1E8] min-h-screen font-sans">
    <div class="bg-[#E8E0D0] rounded-[2rem] p-8 relative overflow-hidden">
        <div class="absolute -top-10 -right-10 w-32 h-32 bg-[#D4E4C1] organic-shape opacity-50"></div>
        <div class="w-16 h-16 bg-[#8FBC8F] leaf-shape flex items-center justify-center mb-6">…</div>
        <h3 class="font-serif text-2xl text-[#3E4A32]">Natural Materials</h3>
    </div>
```

## Do / Don't
- ✅ 用 organic-shape / leaf-shape 不對稱圓角,模擬自然形態
- ✅ 配色固定在森林綠—鼠尾草—苔綠—沙米的大地調,搭奶油底
- ✅ 襯線標題 (Cormorant Garamond) + 圓角容器營造柔和療癒感
- ❌ 不要用高彩度螢光或正圓/直角硬邊,會失去自然有機感
- ❌ 避免冷色科技藍與機械質感,違背 biophilic 的「親近自然」精神
