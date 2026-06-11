# #01 Minimalism & Swiss Style

- **分類**: General
- **檔案**: examples/01-minimalism.html
- **一句話**: 用數學般精準的網格、極致留白與高對比黑白,讓內容自己說話。

## 字型
- Inter(主)、Helvetica Neue(備援);字重 300 / 400 / 500 / 600 / 700,標題用 bold + `tracking-tight`,內文用 `text-gray-600`。

## 配色 (取自實際 HTML)
| 用途 | 色值 |
|---|---|
| 背景 | #FFFFFF（`bg-white`)、輔助 `bg-gray-50` |
| 主色/強調 | #000000（`bg-black`) |
| 次要灰 | #808080（`bg-gray-500`)、邊框 `border-gray-200` |
| 米色點綴 | #F5F1E8 |
| 文字 | 黑 #000000 / `text-gray-600` / `text-gray-400` |

## 招牌技法
- 12 欄網格 (`grid grid-cols-12 gap-8`) 搭配 `col-span-4`,呈現瑞士式數學排版。
- 大量留白與 `max-w-5xl mx-auto` 置中容器,區塊間以 `py-20` 與 `border-t border-gray-100` 細線分隔。
- 標籤文字採 `text-sm text-gray-400 uppercase tracking-widest` 製造編號式索引感。
- 按鈕純色填滿無圓角陰影 (`bg-black text-white hover:bg-gray-800`),次要按鈕用 `border-2 border-black` 反白 hover。

## 關鍵程式片段
```html
<section class="py-20 px-6">
  <div class="max-w-5xl mx-auto">
    <div class="grid grid-cols-12 gap-8">
      <div class="col-span-4">
        <span class="text-sm text-gray-400 uppercase tracking-widest">01</span>
        <h2 class="text-2xl font-semibold mt-2 mb-4">Typography</h2>
        <p class="text-gray-600">High contrast between headings and body text.</p>
      </div>
    </div>
  </div>
</section>
```

## Do / Don't
- ✅ 維持高對比(黑字白底),確保 WCAG AAA;善用留白與精準對齊。
- ✅ 限制色彩數量,以黑白灰為主、米色僅作點綴。
- ✅ 用一致的 gutter 與 margin 建立節奏感。
- ❌ 不要加裝飾性陰影、漸層或多餘圓角。
- ❌ 不要塞滿版面,留白本身就是設計元素。
