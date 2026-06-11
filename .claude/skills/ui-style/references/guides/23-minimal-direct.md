# #23 Minimal & Direct

- **分類**: Landing
- **檔案**: examples/23-minimal-direct.html
- **一句話**: 大量留白、細字重與單欄敘事,用最少的元素直白傳達單一訊息。

## 字型
- Google Fonts：Inter，字重 300 / 400 / 500 / 600（注意刻意省略粗字重,偏好 `font-light`）。

## 配色 (取自實際 HTML)
| 用途 | 色值 (Tailwind token / 對應 hex) |
|---|---|
| 背景 | `bg-white` #ffffff、定價區 `bg-gray-50` #f9fafb |
| 主色/強調 | `gray-900` #111827（按鈕底、底線）作為唯一「強調色」 |
| 文字 | `text-gray-900` #111827（標題）、`text-gray-500` #6b7280（內文）、`text-gray-300` #d1d5db（編號） |
| 邊框 | `border-gray-100` #f3f4f6、`border-gray-200` #e5e7eb 細分隔線 |

## 招牌技法
- 幾乎全程 `font-light`，標題 `text-6xl font-light` 製造輕盈高級感。
- 滿版置中 Hero `min-h-screen flex items-center justify-center`，內容寬度限制在 `max-w-2xl` / `max-w-xl`。
- 連結用底線取代按鈕：`border-b-2 border-gray-900 pb-1`，互動時轉灰。
- 功能用極簡編號清單（`01 / 02 / 03`，編號用 `text-gray-300`）取代圖示卡片。
- 無彩色:整頁只有黑白灰,以巨大行距 `leading-relaxed` 與 `space-y-12` 留白營造節奏。

## 關鍵程式片段
```html
<section class="min-h-screen flex items-center justify-center px-6">
    <div class="max-w-2xl text-center">
        <h1 class="text-6xl font-light text-gray-900 mb-8 leading-tight">Simple.</h1>
        <p class="text-xl text-gray-500 mb-12 leading-relaxed">
            A minimal approach to design.<br/>Less noise. More impact.
        </p>
        <a href="#" class="inline-block text-gray-900 border-b-2 border-gray-900 pb-1 hover:text-gray-600 hover:border-gray-600 transition-colors">
            Get started
        </a>
    </div>
</section>
```

## Do / Don't
- ✅ 大量留白,單欄、限制最大寬度（`max-w-xl`）保持閱讀焦點。
- ✅ 用 `font-light` 與細底線連結取代厚重按鈕與多彩元素。
- ✅ 訊息直白,一句話講完賣點。
- ❌ 不要加入多彩強調色或多欄網格,會破壞極簡氛圍。
- ❌ 不要塞太多功能或文字,違背「少即是多」核心。
