# #09 Claymorphism

- **分類**: General
- **檔案**: examples/09-claymorphism.html
- **一句話**: 厚實、圓潤、像黏土玩具般的 3D 元件,柔軟又充滿玩心。

## 字型
- Nunito(圓潤無襯線,呼應軟陶質感);字重 400 / 600 / 700 / 800,標題用 `font-extrabold`。

## 配色 (取自實際 HTML)
| 用途 | 色值 |
|---|---|
| 背景漸層 | #fef3f2 → #f0f9ff (135deg) |
| 黏土白 | #ffffff → #e6e6e6 |
| 粉 / 藍 | #FDBCB4 / #ADD8E6 |
| 薄荷 / 丁香紫 | #98FF98 / #E6E6FA |
| 文字 | `text-gray-800` / `text-gray-700` |

## 招牌技法
- 核心 `.clay`:`linear-gradient(145deg, #ffffff, #e6e6e6)` + 3px 半透明白邊框 + 雙層 inset 高光暗影,外加硬偏移陰影 `8px 8px 0 rgba(0,0,0,0.08)` 製造厚黏土感。
- 大圓角 `border-radius: 20px`(及 `rounded-3xl`),邊角飽滿圓潤。
- 多彩黏土變體(`.clay-pink` / `.clay-blue` / `.clay-mint` / `.clay-lilac`)各自帶同色系偏移陰影。
- 互動 `.clay-btn`:hover `translateY(-2px)` 浮起、active `translateY(2px)` 壓下,陰影偏移同步變化模擬擠壓。

## 關鍵程式片段
```css
.clay {
  background: linear-gradient(145deg, #ffffff, #e6e6e6);
  border-radius: 20px;
  border: 3px solid rgba(255,255,255,0.8);
  box-shadow:
    8px 8px 0 rgba(0,0,0,0.08),
    inset -2px -2px 4px rgba(0,0,0,0.05),
    inset 2px 2px 4px rgba(255,255,255,0.8);
}
.clay-btn:hover { transform: translateY(-2px); }
.clay-btn:active { transform: translateY(2px); }
```

## Do / Don't
- ✅ 用大圓角 + inset 高光暗影 + 硬偏移陰影,堆出厚實黏土體積。
- ✅ 色票選柔和粉彩(粉、藍、薄荷、丁香),搭配 Nunito 圓體字。
- ✅ hover/active 用 translateY 與陰影偏移做出按壓回饋。
- ❌ 不要用銳角或細邊框,會失去黏土的圓潤感。
- ❌ 不要用高飽和刺眼色,與柔軟調性衝突。
