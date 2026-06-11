# ui-style — UI 設計風格樣板庫 Skill

把 57 種可重複取用的網頁 UI 設計風格打包成一個 Claude Code skill，讓**任何專案**都能挑一個既有風格、套用其規格，產出風格一致的頁面。

## 安裝到其他專案

這是一個自包含的 skill 目錄，整包複製即可：

```bash
# 複製到目標專案（專案層級，僅該專案可用）
cp -R ui-style /path/to/your-project/.claude/skills/

# 或安裝到使用者層級（所有專案皆可用）
cp -R ui-style ~/.claude/skills/
```

> 路徑必須是 `.claude/skills/`（複數），Claude Code 才會自動辨識並載入這個 skill。

## 怎麼用

安裝後，在目標專案直接跟 Claude 說需求即可，例如：

- 「做一個 SaaS 著陸頁，要有信任感」→ 會挑 Landing 類風格
- 「用 Glassmorphism 做個登入頁」→ 直接套用 #03
- 「做個賽博龐克風的活動頁」→ 套用 #41

Claude 會：挑風格 → 讀對應 `references/guides/NN-name.md` 規格 → 依規格與技術慣例產出單檔 HTML。

也可以直接呼叫 `/ui-style`（若以 slash command 形式觸發）。

## 結構

```
ui-style/
├── SKILL.md                  # 觸發描述、工作流程、技術慣例、57 風格速查表
├── README.md                 # 本檔（給人看的安裝說明）
├── index.html                # 串起全部 57 種風格的畫廊首頁（連到 examples/，可直接 open）
├── references/
│   ├── INDEX.md              # 57 風格完整速查表
│   └── guides/NN-name.md     # 各風格設計規格（字型/配色/技法/程式片段/Do-Don't）
└── examples/NN-name.html     # 各風格可直接 open 的 HTML 參考實作
```

來源：本 skill 由 57 種 HTML 風格樣板庫轉製而成。
