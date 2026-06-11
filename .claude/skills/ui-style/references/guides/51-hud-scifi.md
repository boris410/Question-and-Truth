# #51 HUD / Sci-Fi Interface

- **分類**: Modern
- **檔案**: examples/51-hud-scifi.html
- **一句話**: 軍事與科幻抬頭顯示器風格,以青色發光、掃描線與角框打造高密度資訊戰術介面。

## 字型
- Orbitron (400/500/600/700) — 標題與數值(`.font-hud`)
- Share Tech Mono — 標籤與系統訊息(`.font-mono`)

## 配色 (取自實際 HTML)
| 用途 | 色值 |
|---|---|
| 背景 | `bg-slate-950` / `bg-slate-900/50` |
| 主色/強調 | `cyan-400` / `cyan-300` / `cyan-500`,發光基底 `rgba(0,255,255,...)` |
| 邊框/網格 | `border-cyan-900` / `border-cyan-500` |
| 狀態色 | `green-400`(正常)、`yellow-400`(警告) |
| 文字 | `text-cyan-400` / `text-cyan-600`(次要) |

## 招牌技法
- 半透明青色描邊面板 `.hud-border`:`border: 1px solid rgba(0,255,255,0.3)` 搭配 135deg 線性漸層底。
- 全螢幕掃描線疊層 `.scan-line`:`repeating-linear-gradient` 每 2px 一條 `rgba(0,255,255,0.03)`,以 `fixed inset-0 pointer-events-none z-50` 覆蓋。
- 脈衝發光動畫 `.glow-pulse`:`box-shadow` 在 `0 0 5px` 到 `0 0 20px rgba(0,255,255,0.8)` 間呼吸。
- 四角 L 形角框裝飾:`absolute` 定位 + `border-t-2 border-l-2 border-cyan-500` 組合。
- 等寬字註解語法(`// SYSTEM STATUS //`)強化終端機觀感。

## 關鍵程式片段
```html
<style>
  .hud-border {
    border: 1px solid rgba(0, 255, 255, 0.3);
    background: linear-gradient(135deg, rgba(0,255,255,0.05) 0%, transparent 50%);
  }
  .scan-line {
    background: repeating-linear-gradient(0deg,
      transparent, transparent 2px,
      rgba(0,255,255,0.03) 2px, rgba(0,255,255,0.03) 4px);
  }
  @keyframes pulse-glow {
    0%,100% { box-shadow: 0 0 5px rgba(0,255,255,0.5), inset 0 0 5px rgba(0,255,255,0.1); }
    50%     { box-shadow: 0 0 20px rgba(0,255,255,0.8), inset 0 0 10px rgba(0,255,255,0.2); }
  }
</style>
<div class="hud-border rounded-lg p-8 relative">
  <div class="absolute top-0 left-0 w-8 h-8 border-t-2 border-l-2 border-cyan-500"></div>
</div>
```

## Do / Don't
- ✅ 維持單一霓虹青主色,僅以綠/黃做狀態點綴。
- ✅ 大量使用等寬字標籤、進度條與小數值營造儀表感。
- ✅ 保留掃描線與角框等「裝置感」裝飾元素。
- ❌ 不要使用圓潤柔和的陰影或粉彩,會破壞冷硬科技感。
- ❌ 不要在淺色背景上使用,發光效果會失效。
