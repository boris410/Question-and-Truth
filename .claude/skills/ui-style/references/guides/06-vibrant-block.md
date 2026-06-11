# #06 Vibrant & Block-based

- **分類**: General
- **檔案**: examples/06-vibrant-block.html
- **一句話**: 黑底之上撞色螢光大色塊,大膽、充滿能量且帶玩心的區塊式排版。

## 字型
- Space Grotesk;字重 400 / 500 / 600 / 700,標題用 `font-bold` 大尺寸 (`text-6xl`)。

## 配色 (取自實際 HTML)
| 用途 | 色值 |
|---|---|
| 背景 | #000000（`bg-black`) |
| 螢光綠 | #39FF14 |
| 電光紫 | #BF00FF |
| 鮮豔粉 | #FF1493 / #FF006E |
| 亮青/橘/萊姆 | #00FFFF / #FFAA00 / #CCFF00 |

## 招牌技法
- 大圓角色塊 (`rounded-3xl`/`rounded-2xl`) 以螢光純色填滿,黑底襯托更跳。
- 不規則網格拼貼:`grid grid-cols-2` 與 `col-span-2` 混搭製造大小區塊節奏。
- 區塊內保留大留白與粗標題 (`text-6xl font-bold leading-tight`),強調「大色塊 + 大字」。
- 半透明深色玻璃導覽列 `bg-black/80 backdrop-blur-md border border-white/10`。

## 關鍵程式片段
```html
<div class="grid grid-cols-2 gap-6">
  <div class="bg-[#39FF14] rounded-3xl p-12 text-black">
    <h1 class="text-6xl font-bold leading-tight">BOLD.<br/>ENERGETIC.<br/>PLAYFUL.</h1>
  </div>
  <div class="grid grid-cols-2 gap-6">
    <div class="bg-[#BF00FF] rounded-3xl p-6 flex items-end"><span class="text-2xl font-bold">Electric</span></div>
    <div class="bg-[#FF1493] rounded-3xl p-6 flex items-end"><span class="text-2xl font-bold">Vivid</span></div>
  </div>
</div>
```

## Do / Don't
- ✅ 在黑底上用高飽和螢光色製造最大反差。
- ✅ 螢光淺色塊(綠、青、橘、萊姆)上的文字改用黑色確保可讀。
- ✅ 區塊間留大間距(48px+),讓每塊都有呼吸感。
- ❌ 不要同畫面塞太多飽和色,會視覺疲勞。
- ❌ 不要在螢光底放白字,對比不足難以閱讀。
