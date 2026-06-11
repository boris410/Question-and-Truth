# #02 Neumorphism

- **分類**: General
- **檔案**: examples/02-neumorphism.html
- **一句話**: 用同色系雙向陰影營造柔軟浮凸與內凹的觸覺感,像從背景擠壓出來的軟 UI。

## 字型
- Inter;字重 300 / 400 / 500 / 600 / 700,內文用 `text-gray-700`、`text-gray-500`,標題 `font-semibold` / `font-bold`。

## 配色 (取自實際 HTML)
| 用途 | 色值 |
|---|---|
| 背景/主體 | #e8e8e8 |
| 亮部陰影 | #ffffff |
| 暗部陰影 | #d1d1d1 |
| 凸面漸層 | #fafafa → #d4d4d4 |
| 點綴色票 | #C8E0F4 / #F5E0E8 / #D4F5E9 |

## 招牌技法
- 核心 `.neu-flat`:`box-shadow: -5px -5px 15px #ffffff, 5px 5px 15px #d1d1d1`,雙向陰影製造浮起感。
- `.neu-pressed` 用 `inset` 陰影 (`inset -3px -3px 7px #ffffff, inset 3px 3px 7px #d1d1d1`) 製造內凹。
- `.neu-convex` 以 `linear-gradient(145deg, #fafafa, #d4d4d4)` 加凸面陰影做按鈕。
- 按下互動 `.neu-btn:active` 切換成 inset 陰影,模擬實體按壓回饋。
- 全部使用大圓角 (`rounded-2xl`/`rounded-3xl`) 強化柔軟感。

## 關鍵程式片段
```css
.neu-flat {
  background: #e8e8e8;
  box-shadow: -5px -5px 15px #ffffff, 5px 5px 15px #d1d1d1;
}
.neu-pressed {
  background: #e8e8e8;
  box-shadow: inset -3px -3px 7px #ffffff, inset 3px 3px 7px #d1d1d1;
}
.neu-convex {
  background: linear-gradient(145deg, #fafafa, #d4d4d4);
  box-shadow: -5px -5px 15px #ffffff, 5px 5px 15px #d1d1d1;
}
```

## Do / Don't
- ✅ 背景與元件同色,靠光影分層;一致的光源方向(左上亮、右下暗)。
- ✅ 用於健康、冥想、健身等需要柔和氛圍的 App。
- ❌ 不要用於需要高對比與無障礙的關鍵介面(對比過低)。
- ❌ 不要混入過多飽和色,會破壞單色柔光的整體性。
