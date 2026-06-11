# #33 Comparative Analytics

- **分類**: BI-Analytics
- **檔案**: examples/33-comparative-analytics.html
- **一句話**: 用「本期 vs 去年」雙色對照,把比較關係視覺化成並排數字與差異進度條。

## 字型
- **Inter** (400/500/600/700),透過 `* { font-family: 'Inter' }` 全域套用

## 配色 (取自實際 HTML)
| 用途 | 色值 |
|---|---|
| 背景 | bg-gray-50 |
| 卡片/導覽 | bg-white / border-gray-200 |
| 當期(主色) | text-blue-600 / bg-blue-500 / bg-blue-100 |
| 對照期(灰) | text-gray-400 / bg-gray-400 / bg-gray-100 |
| 成長差異 | text-green-600 / bg-green-500 |
| 文字 | text-gray-900 / text-gray-500 |

## 招牌技法
- 期間選擇器:藍膠囊 (2024) 對 灰膠囊 (2023),中間夾 `vs`,色彩即代表資料系列
- 比較卡:`flex items-end justify-between`,左當期(藍)右對照期(灰),視覺權重分明
- 差異進度條 `h-2 bg-gray-200 rounded-full` 內填 `bg-green-500`,寬度對應成長百分比
- 一致用 `rounded-xl p-5 shadow-sm border`,卡片排成 `grid-cols-4 gap-4`
- 藍=最新/焦點、灰=歷史/基準,全頁顏色語意統一

## 關鍵程式片段
```html
<div class="bg-white rounded-xl p-5 shadow-sm border border-gray-200">
    <p class="text-sm text-gray-500 mb-3">Revenue</p>
    <div class="flex items-end justify-between">
        <div><p class="text-2xl font-bold text-blue-600">$4.2M</p><p class="text-sm text-gray-400">2024</p></div>
        <div class="text-right"><p class="text-2xl font-bold text-gray-400">$3.5M</p><p class="text-sm text-gray-400">2023</p></div>
    </div>
    <div class="mt-3 flex items-center gap-2">
        <span class="text-green-600 font-semibold">+20%</span>
        <div class="flex-1 h-2 bg-gray-200 rounded-full"><div class="h-2 bg-green-500 rounded-full" style="width: 20%"></div></div>
    </div>
</div>
```

## Do / Don't
- ✅ 用固定一組「主色 vs 灰」表達兩個被比較的時間/群組,全頁一致
- ✅ 把差異百分比放大並配進度條,讓「差多少」一眼可見
- ✅ 當期數字權重高於對照期(顏色更飽和),引導視線
- ❌ 不要超過兩個系列還沿用同套色,會分不清誰對誰
- ❌ 避免只給數字不給差異,比較介面的重點是「差距」
