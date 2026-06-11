# #21 Conversion-Optimized

- **分類**: Landing
- **檔案**: examples/21-conversion-optimized.html
- **一句話**: 用緊迫感、信任訊號與單一行動呼籲把訪客最大化轉換成註冊。

## 字型
- Google Fonts：Inter，字重 400 / 500 / 600 / 700 / 800（全域 `* { font-family: 'Inter', sans-serif; }`）。

## 配色 (取自實際 HTML)
| 用途 | 色值 (Tailwind token / 對應 hex) |
|---|---|
| 背景 | `bg-white` #ffffff、區塊 `bg-gray-50` #f9fafb、深色見證區 `bg-gray-900` #111827 |
| 主色/強調 | `green-600` #16a34a（CTA）、`green-500` #22c55e、`green-100` #dcfce7 標籤底 |
| 文字 | `text-gray-900` #111827（主標）、`text-gray-600` #4b5563（內文）、`text-gray-400` #9ca3af（次要） |
| 點綴 | `text-yellow-400` #facc15 星等、avatar `bg-blue-400` / `bg-purple-400` |

## 招牌技法
- 頂部 `fixed top-0` 倒數計時 CTA bar（`bg-green-600`）製造緊迫感，導覽列再 `fixed top-8` 疊在其下。
- 兩欄 Hero：左側賣點清單、右側轉換表單卡片 `rounded-2xl p-8 shadow-2xl border border-gray-100`。
- CTA 按鈕用彩色投影 `shadow-lg shadow-green-600/30` 強化點擊欲望。
- 輸入框 focus 態 `focus:ring-2 focus:ring-green-500 focus:border-transparent` 統一綠色聚焦。
- 信任訊號列：重疊頭像 `flex -space-x-2`、星等、Fortune 500 / SOC 2 字樣。

## 關鍵程式片段
```html
<div class="fixed top-0 left-0 right-0 bg-green-600 text-white py-2 text-center z-50 text-sm">
    Limited Time: Get 50% OFF with code <span class="font-bold">SAVE50</span> - Ends in <span class="font-bold">23:59:42</span>
</div>
<div class="bg-white rounded-2xl p-8 shadow-2xl border border-gray-100">
    <h3 class="text-2xl font-bold text-gray-900 mb-2 text-center">Start Your Free Trial</h3>
    <input type="email" placeholder="Work Email" class="w-full px-4 py-4 border border-gray-200 rounded-lg focus:outline-none focus:ring-2 focus:ring-green-500 focus:border-transparent text-lg">
    <button type="submit" class="w-full py-4 bg-green-600 text-white rounded-lg font-bold text-lg hover:bg-green-700 transition-colors cursor-pointer shadow-lg shadow-green-600/30">
        Start Free Trial Now
    </button>
</div>
```

## Do / Don't
- ✅ 單一明確 CTA（綠色），全頁重複導向同一動作。
- ✅ 在折疊線上方就放表單與信任訊號（評分、用戶數、認證）。
- ✅ 用倒數 / 限時折扣製造緊迫感。
- ❌ 不要塞多個競爭的行動呼籲或過多導覽連結分散注意力。
- ❌ 不要用過長表單欄位，維持 30 秒可填完的精簡度。
