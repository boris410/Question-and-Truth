# #13 Skeuomorphism (擬物化設計)

- **分類**: General
- **檔案**: examples/13-skeuomorphism.html
- **一句話**: 用材質、光影與真實細節模擬實體物件 (皮革、木紋、金屬、玻璃),讓介面有觸摸得到的質感。

## 字型
- HTML 載入 `Georgia`,但 body 實際使用 `'Helvetica Neue', Arial, sans-serif` (擬物化的系統 UI 字型)

## 配色 (取自實際 HTML)
| 用途 | 色值 |
|---|---|
| 背景 (灰金屬漸層) | #c8c8c8 → #a0a0a0 |
| 皮革 (棕) | #8B4513 → #5D3A1A,邊框 #3D2A15 |
| 木紋 | #DEB887 / #CD853F |
| 金屬按鈕 | #f5f5f5 → #d8d8d8 → #b8b8b8 |
| 強調文字 (米色) | #DEB887 / #D2B48C |

## 招牌技法
- 金屬按鈕: `linear-gradient(180deg,...)` 三段灰漸層 + `box-shadow: 0 2px 4px rgba(0,0,0,0.3), inset 0 1px 0 rgba(255,255,255,0.8)` 製造高光
- 按下狀態翻轉: `:active` 反向漸層 + `inset` 內陰影,模擬被壓下
- 內凹輸入框 `.inset-field`: `box-shadow: inset 0 2px 4px rgba(0,0,0,0.2)` 製造凹槽
- 材質背景: 皮革 `.leather-bg`、木紋 `.wood-bg`、玻璃 `.glass-surface` 各以漸層 + 邊框模擬
- 記事本紋路: `repeating-linear-gradient(transparent 27px, #e8e8e8 28px)` 模擬橫線紙

## 關鍵程式片段
```html
<style>
  .metal-button {
    background: linear-gradient(180deg, #f5f5f5 0%, #d8d8d8 50%, #b8b8b8 100%);
    border: 1px solid #888;
    box-shadow: 0 2px 4px rgba(0,0,0,0.3), inset 0 1px 0 rgba(255,255,255,0.8);
  }
  .metal-button:active {
    background: linear-gradient(180deg, #b8b8b8 0%, #d8d8d8 50%, #e8e8e8 100%);
    box-shadow: inset 0 2px 4px rgba(0,0,0,0.2);
  }
  .inset-field {
    background: #fff; border: 1px solid #999;
    box-shadow: inset 0 2px 4px rgba(0,0,0,0.2), inset 0 0 0 1px rgba(0,0,0,0.05);
  }
</style>
```

## Do / Don't
- ✅ 適合遊戲介面、沉浸式敘事、高端/教育模擬類產品
- ✅ 用多層 `inset` 與外陰影同時呈現高光與凹陷,材質才逼真
- ✅ 善用真實物件隱喻 (開關、記事本、皮革底) 降低學習成本
- ❌ 不要在效能或無障礙敏感的場景使用 (重度陰影、低對比、行動裝置支援差)
- ❌ 不要混用過多材質於同一畫面,易顯廉價雜亂
