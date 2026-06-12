# 繁體中文協作者指南

歡迎加入神經多樣性 Wiki 的繁體中文（zh-hant）維護！本指南將帶你從入門到熟練完成審校與貢獻。

## 目錄

- [誰需要讀這份指南](#誰需要讀這份指南)
- [背景知識](#背景知識)
- [環境設定](#環境設定)
- [審校工作流程](#審校工作流程)
- [術語規範](#術語規範)
- [常見操作](#常見操作)
- [FAQ](#faq)
- [聯絡方式](#聯絡方式)

## 誰需要讀這份指南

- **繁體中文審校者**：審校自動轉換後的繁體頁面
- **繁體中文貢獻者**：新增或大幅修改繁體頁面內容
- **地區術語維護者**：維護臺灣、香港等地區術語對照

不需要程式設計背景。你只需要熟悉 Markdown 和 Git 的基本操作。

> **⚠️ 重要：術語轉換目前由 AI 完成，全部頁面均待人工討論與審校。** 本倉庫的所有頁面均由 OpenCC 從簡體自動轉為繁體——字形層面的轉換由機器處理，但詞彙層面的選擇（例如「自閉症譜系」還是「自閉光譜」）尚未經過社群討論。不要將現有術語視為最終決定，它們只是等待討論的起點。

## 背景知識

### 專案結構

```
ndwiki-cn (簡體主倉庫)          ndwiki-hant (繁體子倉庫，即本倉庫)
├── wiki/                       ├── README.md
│   ├── 00-知識地圖.md           ├── COLLABORATING.md  ← 你正在讀的檔案
│   ├── 01-基礎/                ├── 01-基礎/
│   ├── ...                     ├── ...
│   └── works/                  └── works/
├── wiki-zh-hant/  ← 本倉庫
├── sources/                    ├── 00-知識地圖.md
└── ...                         └── 閱讀路線.md
```

- **簡體主倉庫**（[ndwiki-cn](https://github.com/xyzhou0323/ndwiki-cn)）：內容的來源，作者以簡體中文寫作
- **繁體子倉庫**（ndwiki-hant，即本倉庫）：OpenCC 自動轉換 + 人工審校的繁體版本
- 本倉庫作為主倉庫的 git submodule 存在於 `wiki-zh-hant/` 路徑

### 同步機制

```
簡體作者編輯 wiki/頁面.md
       │
       ▼
維護者執行 sync-zh-hant.py
       │
       ├─ OpenCC 字字轉換（s2t）
       ├─ 檔名和內容同時轉換
       ├─ 添加 zh-hans: [[wiki/...]] 反向連結
       └─ 添加 needs-review: true 標記
       │
       ▼
繁體協作者（你！）審校 needs-review 頁面
       │
       ▼
移除 needs-review，提交 PR
```

### 關鍵概念

- **zh-hant**：ISO 15924 繁體漢字腳本代碼，涵蓋臺灣、香港、澳門等地區，不預設地區
- **needs-review: true**：frontmatter 標記，表示該頁面由 OpenCC 自動轉換後尚未經人工審校
- **OpenCC**：開源簡繁轉換工具，處理字形層面（簡→繁），不處理詞彙層面（如「殘疾」↔「身心障礙」）

## 環境設定

### 方式一：獨立使用（推薦）

如果你只需要審校繁體頁面，可以直接 clone 本倉庫：

```bash
git clone https://github.com/xyzhou0323/ndwiki-hant.git
cd ndwiki-hant
```

用 [Obsidian](https://obsidian.md) 打開 `ndwiki-hant` 資料夾即可瀏覽和編輯。

### 方式二：作為主倉庫子模組

如果你同時需要簡體和繁體版本：

```bash
git clone --recurse-submodules https://github.com/xyzhou0323/ndwiki-cn.git
cd ndwiki-cn/wiki-zh-hant
```

## 審校工作流程

### 第一步：找到待審校頁面

在倉庫中搜尋 frontmatter 含有 `needs-review: true` 的頁面：

**用命令列**：
```bash
grep -rl "needs-review: true" --include="*.md" .
```

**用 Obsidian**：安裝 [Dataview](https://github.com/blacksmithgu/obsidian-dataview) 外掛，建立以下查詢：

```dataview
TABLE description, updated
FROM ""
WHERE needs-review = true
SORT updated DESC
```

**用 GitHub**：在 GitHub 倉庫頁面搜尋 `needs-review: true`。

### 第二步：逐頁審校

打開一個標記為待審校的頁面，逐項檢查：

#### 檢查清單

- [ ] **字形轉換**：OpenCC 轉換是否正確？有無殘留簡體字？
- [ ] **地區術語**：關鍵術語是否符合本地用法？（見下方[術語規範](#術語規範)）
- [ ] **Wikilinks**：`[[頁面名]]` 是否指向繁體版本中的正確頁面？
- [ ] **Frontmatter**：`zh-hans` 欄位是否正確指向簡體原頁面？
- [ ] **外部連結**：URL 是否完整、可訪問？
- [ ] **引用格式**：APA 引用是否完整（尤其著作頁的 `citation_apa` 欄位）？

#### 地區術語處理原則

同一概念在臺灣、香港、澳門可能有不同譯法。處理原則：

1. **頁面標題**：採用臺灣用語為預設（本倉庫主要面向臺灣讀者）
2. **括號加註**：首次出現時加註地區差異，格式為「孤獨譜系（港：自閉症譜系）」
3. **術語對照表**：在[[術語對照表]]中記錄所有地區差異
4. **一致性**：同一頁面內同一概念的譯法保持一致

#### 常見需修正處

| 問題 | 範例 | 修正 |
|------|------|------|
| OpenCC 過度轉換 | 文件→檔案（但前後文為公文） | 手動改回 |
| 一簡對多繁錯誤 | 干預→干預（正確應為「干預」或「干預」視上下文） | 審查上下文 |
| Wikilinks 未轉換 | `[[神经多样性]]` → 應為 `[[神經多樣性]]` | 手動修正 |
| 術語差異 | 簡「生活质量」→ 繁「生活質量」 | 改為「生活品質」（臺）/「生活質素」（港） |

### 第三步：提交變更

審校完成後：

1. **移除 `needs-review: true`**：從 frontmatter 中刪除該行
2. **更新 `updated` 日期**：改為審校當日（`YYYY-MM-DD`）
3. **提交**：

```bash
git add .
git commit -m "review: <頁面名稱> 繁體審校"
git push origin main
```

4. **發起 Pull Request**（如果你 fork 了倉庫）

> **注意**：一次 PR 建議包含 3-10 個頁面的審校，方便維護者 review。

## 術語規範

> **以下所有術語對照為 AI 暫定版本，未經社群討論。** 不要當作既定規範——它們只是供審校時參考的起點。如果你對任何術語有不同看法，請發起討論或在審校中直接修改。

### 核心術語對照（暫定）

參見[[術語對照表]]（`術語對照表.md`）獲取完整清單。以下為最常見的差異，**僅供參考**：

| 簡體（zh-hans） | 臺灣（zh-hant） | 香港（zh-hant） | 備註 |
|---|---|---|---|
| 孤独谱系 | 自閉症譜系 | 自閉症譜系 | ASD |
| 注意缺陷多动障碍 | 注意力不足過動症 | 專注力失調/過度活躍症 | ADHD |
| 神经多样性 | 神經多樣性 | 神經多樣性 | Neurodiversity |
| 神经殊异 | 神經殊異 | 神經殊異 | Neurodivergent |
| 神经典型 | 神經典型 | 神經典型 | Neurotypical |
| 残障 | 身心障礙 | 殘疾 | Disability |
| 述情障碍 | 述情障礙 | 述情障礙 | Alexithymia |
| 双相障碍 | 雙相障礙 | 雙相障礙 | Bipolar |
| 生活质量 | 生活品質 | 生活質素 | Quality of life |
| 干预 | 介入/干預 | 介入 | Intervention |
| 行为 | 行為 | 行為 | Behavior |
| 研究 | 研究 | 研究 | Research（一致） |

### 術語處理原則

1. **已確立譯法優先**：若臺灣/香港學術界已有通用譯法，優先採用
2. **可理解性**：若無通用譯法，優先選擇讀者最容易理解的版本
3. **首次加註**：術語首次出現時，以括號加註其他地區的譯法
4. **保持連結**：Wikilinks 指向的頁面名必須與目標頁面的實際檔名一致

## 常見操作

### 搜尋特定術語

```bash
# 搜尋所有含「孤独谱系」的頁面（OpenCC 可能未轉換）
grep -rl "孤独谱系" --include="*.md" .

# 搜尋所有含特定 frontmatter 標記的頁面
grep -rl "needs-review: true" --include="*.md" .
```

### 批量檢查 Wikilinks

```bash
# 列出所有 wikilinks 中可能指向簡體頁面的連結
grep -roh "\[\[.*?\]\]" --include="*.md" . | sort | uniq -c | sort -rn
```

### 建立新頁面

如果你要新增繁體原創頁面（非從簡體轉換）：

1. 遵循 [CONTRIBUTING.md](https://github.com/xyzhou0323/ndwiki-cn/blob/main/CONTRIBUTING.md) 的頁面規範
2. Frontmatter 無需 `zh-hans` 欄位（該頁面沒有簡體對應版本）
3. 添加到主倉庫的[[術語對照表]]中
4. 提交時在 commit message 中註明「繁體原創」

### 處理簡體版更新

當簡體主倉庫更新後，同步腳本會推送新變更到本倉庫。你會看到有新頁面標記了 `needs-review: true`：

1. `git pull origin main` 取得最新變更
2. 按[審校工作流程](#審校工作流程)操作
3. 優先審校主題頁面和核心概念頁面

## FAQ

### Q: 我發現 OpenCC 轉換錯誤，該如何回報？

A: 直接在審校中修正即可。如果是系統性問題（同一錯誤在多個頁面出現），請在 Issue 中描述，附上範例。

### Q: 臺灣和香港用語不同時，以哪個為準？

A: 頁面主體採用臺灣用語為預設，香港用語以括號加註。如果某頁面主要面向香港讀者，可在 frontmatter 添加 `region: hk` 標記並以香港用語為主。

### Q: 我可以直接修改簡體主倉庫的內容嗎？

A: 繁體子倉庫僅包含繁體頁面。如需修改簡體原頁面，請向 [ndwiki-cn](https://github.com/xyzhou0323/ndwiki-cn) 提交 PR。

### Q: 如何知道哪些頁面最需要審校？

A: 優先審校以下頁面：
1. 核心概念頁面（`01-基礎/`，如[[神經多樣性]]）
2. 導航頁面（[[00-知識地圖]]、[[閱讀路線]]）
3. 最近更新的頁面（檢視 git log）

### Q: 我沒有 Git 經驗，可以參與嗎？

A: 可以！GitHub 網頁版支援直接在瀏覽器中編輯檔案。找到待審校頁面 → 點擊編輯按鈕 → 修改 → 提交 Pull Request。

## 聯絡方式

- **GitHub Issues**：[在 ndwiki-hant 倉庫發 Issue](https://github.com/xyzhou0323/ndwiki-hant/issues)
- **簡體主倉庫**：[ndwiki-cn](https://github.com/xyzhou0323/ndwiki-cn)
- **線上版**：[neuroxyz.cn/wiki/zh-hant](https://neuroxyz.cn/wiki/zh-hant/)
