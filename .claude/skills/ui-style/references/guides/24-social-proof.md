# #24 Social Proof-Focused

- **分類**: Landing
- **檔案**: examples/24-social-proof.html
- **一句話**: 用評分、頭像牆、客戶 logo 與見證牆堆疊信任,讓「別人都在用」說服訪客。

## 字型
- Google Fonts：Inter，字重 400 / 500 / 600 / 700 / 800（全域 `* { font-family: 'Inter', sans-serif; }`）。

## 配色 (取自實際 HTML)
| 用途 | 色值 (Tailwind token / 對應 hex) |
|---|---|
| 背景 | `bg-white` #ffffff、logo 雲與見證區 `bg-gray-50` #f9fafb |
| 主色/強調 | `blue-600` #2563eb（CTA）、`blue-400` #60a5fa（頭像） |
| 文字 | `text-gray-900` #111827（標題）、`text-gray-600` #4b5563（內文）、`text-gray-400` #9ca3af |
| 評分/點綴 | `text-yellow-400` #facc15 星等、avatar 多彩 `green-400` / `purple-400` / `pink-400` / `orange-400` |

## 招牌技法
- 折疊線上方就放星等 `★★★★★` 與「4.9/5 from 2,500+ reviews」即時建立信任。
- 重疊頭像牆 `flex -space-x-4`，每顆 `border-4 border-white`，末尾用 `+50K` 計數泡泡收尾。
- Logo 雲 `grid grid-cols-6 ... opacity-60` 淡化處理,呈現「眾多客戶」氛圍。
- 三欄見證卡片 `grid grid-cols-3 gap-6`，每張含星等 + 引言 + 頭像 + 姓名職稱。
- 玻璃感導覽 `bg-white/90 backdrop-blur-md border-b border-gray-100`。

## 關鍵程式片段
```html
<div class="flex items-center justify-center gap-2 mb-6">
    <span class="text-yellow-400 text-xl">★★★★★</span>
    <span class="text-gray-600">4.9/5 from 2,500+ reviews</span>
</div>
<div class="flex -space-x-4">
    <div class="w-12 h-12 bg-blue-400 rounded-full border-4 border-white"></div>
    <div class="w-12 h-12 bg-green-400 rounded-full border-4 border-white"></div>
    <div class="w-12 h-12 bg-purple-400 rounded-full border-4 border-white"></div>
    <div class="w-12 h-12 bg-gray-200 rounded-full border-4 border-white flex items-center justify-center text-sm font-bold text-gray-600">+50K</div>
</div>
```

## Do / Don't
- ✅ 在 Hero 就疊滿信任元素：星等、用戶數、頭像牆、客戶 logo。
- ✅ 用真實姓名 + 職稱 + 頭像的見證卡片增加可信度。
- ✅ logo 雲用降低透明度的中性呈現,避免喧賓奪主。
- ❌ 不要只放空泛數字而無具體見證內容。
- ❌ 不要讓多彩頭像與星等搶過唯一的藍色 CTA。
