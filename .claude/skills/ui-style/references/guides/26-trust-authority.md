# #26 Trust & Authority

- **分類**: Landing
- **檔案**: examples/26-trust-authority.html
- **一句話**: 以襯線標題、認證徽章與中性莊重配色,塑造企業級「業界標準」的權威感。

## 字型
- Google Fonts：Playfair Display（serif，400/500/600/700）作標題 `.font-serif`；Inter（sans，400/500/600）作內文 `.font-sans`。
- 雙字型搭配:襯線標題建立權威 + 無襯線內文確保易讀。

## 配色 (取自實際 HTML)
| 用途 | 色值 (Tailwind token / 對應 hex) |
|---|---|
| 背景 | `bg-white` #ffffff、認證區 `bg-gray-50` #f9fafb |
| 主色/強調 | `gray-900` #111827（CTA 與標題,沉穩無彩) |
| 文字 | `text-gray-900` #111827、`text-gray-600` #4b5563、`text-gray-500` #6b7280 |
| 點綴 | `text-green-600` #16a34a（驗證勾選圖示）、認證圓徽 `bg-white border-gray-200` |

## 招牌技法
- 襯線大標 `font-serif text-6xl font-bold` 傳達傳統與權威。
- 信任徽章膠囊 `px-4 py-2 bg-gray-50 rounded-full` + 綠色驗證勾,放在標題上方。
- 認證牆：SOC 2 / ISO / GDPR / HIPAA / FedRAMP 用統一圓徽 `w-16 h-16 rounded-full border border-gray-200`。
- 全程中性無彩配色(黑白灰)+ 極克制的綠色點綴,避免花俏以突顯可信賴。
- 區塊用 `border-y border-gray-200` 細線分隔,版面工整嚴謹。

## 關鍵程式片段
```html
<div class="flex items-center gap-2 px-4 py-2 bg-gray-50 rounded-full">
    <svg class="w-5 h-5 text-green-600" fill="currentColor" viewBox="0 0 20 20">
        <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293..." clip-rule="evenodd"/>
    </svg>
    <span class="text-sm text-gray-600">Verified by 10,000+ enterprises</span>
</div>
<h1 class="font-serif text-6xl font-bold text-gray-900 mb-6 leading-tight">
    The Industry Standard for Enterprise Security
</h1>
<div class="w-16 h-16 mx-auto bg-white rounded-full flex items-center justify-center border border-gray-200 mb-2">
    <span class="font-bold text-gray-700">SOC 2</span>
</div>
```

## Do / Don't
- ✅ 用襯線標題 + 無襯線內文的雙字型體系建立權威層次。
- ✅ 展示具體認證、合規標章與企業客戶數字。
- ✅ 維持中性莊重配色,克制使用彩色。
- ❌ 不要用花俏漸層、霓虹色或誇張動畫,會削弱可信度。
- ❌ 不要把襯線字型用在大量內文(易讀性下降)。
