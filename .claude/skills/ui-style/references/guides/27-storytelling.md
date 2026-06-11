# #27 Storytelling-Driven

- **分類**: Landing
- **檔案**: examples/27-storytelling.html
- **一句話**: 把著陸頁拆成一章一章的敘事,用襯線長文與滿版章節帶讀者走完品牌旅程。

## 字型
- Google Fonts：Merriweather（serif，300/400/700）作敘事內文 `.font-story`；Inter（sans，400/500/600）作 UI 介面 `.font-ui`。
- 襯線體承載故事段落,營造「閱讀一本書」的沉浸感。

## 配色 (取自實際 HTML)
| 用途 | 色值 (Tailwind token / 對應 hex) |
|---|---|
| 背景 | `bg-white` #ffffff、對比章節 `bg-gray-900` #111827（深色翻頁） |
| 主色/強調 | `blue-500` #3b82f6（引言左框線）、`blue-600` #2563eb（時間軸節點） |
| 文字 | `text-gray-900` #111827、`text-gray-600` #4b5563、深底上 `text-gray-300` #d1d5db |
| 章節標記 | `text-gray-400` #9ca3af `uppercase tracking-widest`（Chapter One…） |

## 招牌技法
- 每章用滿版 `min-h-screen flex items-center` / `py-32`,一頁一章節奏。
- 章節小標 `uppercase tracking-widest`(Chapter One/Two/Three)建立敘事結構。
- 明暗章節交替:`bg-gray-900 text-white` 深色章節製造翻頁戲劇張力。
- 引言區塊 `border-l-4 border-blue-500 pl-6 italic` 突顯金句。
- 視覺時間軸:編號圓點 `w-12 h-12 bg-blue-100 rounded-full` + 日期里程碑。
- Hero 底部 `animate-bounce` 向下箭頭引導捲動繼續閱讀。

## 關鍵程式片段
```html
<section class="py-32 px-6 bg-gray-900 text-white">
    <div class="max-w-3xl mx-auto">
        <span class="text-sm text-gray-500 uppercase tracking-widest mb-4 block">Chapter Two</span>
        <h2 class="font-story text-4xl leading-tight mb-8">The problem that kept us up at night</h2>
        <blockquote class="border-l-4 border-blue-500 pl-6 py-2 text-xl text-white italic">
            "There has to be a better way."
        </blockquote>
    </div>
</section>
```

## Do / Don't
- ✅ 用「章節」結構組織內容,一頁一節推進故事。
- ✅ 明暗章節交替製造節奏與戲劇感。
- ✅ 用襯線體承載敘事,搭配引言區塊突顯金句。
- ❌ 不要在敘事頁堆滿功能網格或表單,會打斷沉浸感。
- ❌ 不要每章太短,留足長文與行距讓故事呼吸。
