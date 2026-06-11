# #49 Parallax Storytelling

- **分類**: Modern
- **檔案**: examples/49-parallax-storytelling.html
- **一句話**: 以全螢幕章節分段的捲動敘事,用多層深度與漸進揭露把內容講成一個故事。

## 字型
- **Playfair Display** (400/500/600/700):優雅襯線標題 (`.font-serif`),用於章節大標
- **Inter** (400/500/600):無襯線內文 (`.font-sans`)

## 配色 (取自實際 HTML)
| 用途 | 色值 |
|---|---|
| 背景 | bg-slate-900 (漸層至 indigo-900 / black) |
| 章節強調 | text-indigo-400 · text-purple-400 · text-cyan-400 · text-rose-400 · text-amber-400 |
| 主漸層 | from-blue-600 to-purple-600 / from-cyan-500 to-blue-500 |
| 卡片 | bg-slate-800 / border-slate-700 |
| 文字 | text-white / text-slate-300 / text-slate-400 |

## 招牌技法
- 全螢幕章節:每段 `min-h-screen flex items-center`,以 "Chapter One/Two..." 標籤 + 大寫寬字距 `tracking-widest uppercase` 分段。
- 模糊光暈背景:`bg-indigo-500/20 rounded-full blur-3xl` 漂浮在 hero,製造氛圍縱深。
- 多層偏移色塊:旋轉 + 位移堆疊 `-rotate-12` / `rotate-6` / `translate-x-16 translate-y-16` 模擬 parallax 深度。
- 漸層背景轉場:section 之間用 `bg-gradient-to-b from-slate-900 to-indigo-900` / `to-black` 平滑過渡。
- 捲動提示 `animate-bounce` 向下箭頭,毛玻璃統計卡 `bg-slate-800/50 backdrop-blur`。

## 關鍵程式片段
```html
<section class="min-h-screen flex items-center justify-center relative overflow-hidden">
    <div class="absolute inset-0 bg-gradient-to-b from-indigo-900/50 to-slate-900"></div>
    <div class="absolute top-20 left-20 w-64 h-64 bg-indigo-500/20 rounded-full blur-3xl"></div>
    <div class="absolute bottom-20 right-20 w-96 h-96 bg-purple-500/20 rounded-full blur-3xl"></div>
    <div class="relative text-center z-10 px-6">
        <span class="text-indigo-400 text-sm tracking-widest uppercase mb-4 block">Chapter One</span>
        <h1 class="font-serif text-7xl mb-6">The Journey Begins</h1>
    </div>
</section>
```

## Do / Don't
- ✅ 以 min-h-screen 全螢幕章節 + "Chapter" 標籤建立線性敘事節奏。
- ✅ 用 blur-3xl 光暈與多層旋轉位移色塊製造 parallax 深度感。
- ❌ 不要把所有內容擠在一屏,失去逐段揭露的故事張力。
- ❌ 避免高彩度撞色;深色底配低透明度光暈才能維持沉浸氛圍。
