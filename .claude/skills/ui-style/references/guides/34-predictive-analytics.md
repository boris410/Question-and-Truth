# #34 Predictive Analytics

- **分類**: BI-Analytics
- **檔案**: examples/34-predictive-analytics.html
- **一句話**: 暗色 AI 預測儀表板,用紫色 AI-Powered 標記與信賴區間,呈現「機器在替你看未來」。

## 字型
- **Inter** (400/500/600/700),透過 `* { font-family: 'Inter' }` 全域套用

## 配色 (取自實際 HTML)
| 用途 | 色值 |
|---|---|
| 背景 | bg-slate-900 |
| 卡片/導覽 | bg-slate-800 / border-slate-700 |
| AI 強調 | bg-purple-600 / text-purple-400 |
| 預測正向 | text-green-400 / bg-green-500 |
| 風險警示 | text-yellow-400 |
| 模型/數據 | text-blue-400 |
| 次要文字 | text-slate-400 / text-slate-500 |

## 招牌技法
- 「AI-Powered」紫色徽章 `px-2 py-1 bg-purple-600 text-xs rounded` 標示智慧來源
- 暗色卡片 `bg-slate-800 rounded-xl p-5 border border-slate-700`,搭配大數值 `text-3xl font-bold`
- 預測值附信賴區間文字(95% confidence: $4.8M - $5.6M),強調機率而非定論
- 多彩語意值:綠=預測收入、藍=模型準確度、黃=風險、紫=成長機率
- 狀態圓點 `w-2 h-2 bg-green-500 rounded-full` 點綴卡片標題

## 關鍵程式片段
```html
<span class="px-2 py-1 bg-purple-600 text-xs rounded">AI-Powered</span>
<div class="bg-slate-800 rounded-xl p-5 border border-slate-700">
    <div class="flex items-center gap-2 mb-2">
        <span class="w-2 h-2 bg-green-500 rounded-full"></span>
        <span class="text-sm text-slate-400">Predicted Q1 2025</span>
    </div>
    <p class="text-3xl font-bold text-green-400">$5.2M</p>
    <p class="text-sm text-slate-500 mt-1">95% confidence: $4.8M - $5.6M</p>
</div>
```

## Do / Don't
- ✅ 預測值務必附信賴區間或機率,誠實表達不確定性
- ✅ 用紫色統一標示「AI / 模型」相關元素,與一般指標區隔
- ✅ 暗色背景讓螢光綠/藍數字更突出,適合分析情境
- ❌ 不要把預測呈現得像確定事實(去掉區間會誤導決策)
- ❌ 避免顏色語意混用,風險(黃)與正向(綠)必須分明
