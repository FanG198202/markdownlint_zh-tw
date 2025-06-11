# markdownlint

> 用於 Markdown/CommonMark 文件的 Node.js 風格檢查與 lint 工具。

> **Language**: [English](README.md)

[![npm version][npm-image]][npm-url]
[![License][license-image]][license-url]

## 安裝

```bash
npm install markdownlint --save-dev
```

## 概述

[Markdown][markdown] 標記語言旨在易於閱讀、撰寫和理解。它確實做到了——而其彈性同時也是優點與缺點。許多風格皆可實現，導致格式可能不一致；某些結構在所有解析器中效果不佳，應予避免。

`markdownlint` 是一個針對 [Node.js][nodejs] 的[靜態分析][static-analysis]工具，擁有一套規則庫，用於強制執行 Markdown 文件的標準與一致性。它的靈感來自 Mark Harrison 的 Ruby 版 [markdownlint][markdownlint-ruby]，並受其影響甚深。最初的規則、規則文件與測試案例均來自該專案。

`markdownlint` 使用 [`micromark` 解析器][micromark]，並遵循 [CommonMark][commonmark] 之規範。此外也支援常見的 [GitHub Flavored Markdown (GFM)][gfm] 語法，例如自動連結與表格、指令、註腳、數學語法等，皆由 [`micromark` 擴充][micromark-extensions] 實現。

[commonmark]: https://commonmark.org/
[gfm]: https://github.github.com/gfm/
[markdown]: https://en.wikipedia.org/wiki/Markdown
[markdownlint-ruby]: https://github.com/markdownlint/markdownlint
[micromark]: https://github.com/micromark/micromark
[micromark-extensions]: https://github.com/micromark/micromark?tab=readme-ov-file#list-of-extensions
[nodejs]: https://nodejs.org/
[static-analysis]: https://en.wikipedia.org/wiki/Static_program_analysis

### 相關工具

- CLI
  - [markdownlint-cli][markdownlint-cli]：Node.js 指令列界面（[適用於 pre-commit][markdownlint-cli-precommit]）
  - [markdownlint-cli2][markdownlint-cli2]：Node.js 指令列界面（[適用於 pre-commit][markdownlint-cli2-precommit]）
- GitHub
  - [markdownlint-cli2 的 GitHub Action][markdownlint-cli2-action]
  - [GitHub Super-Linter Action][super-linter]
  - [markdownlint-cli 問題匹配器][markdownlint-problem-matcher]
- 編輯器
  - [VS Code 專用 vscode-markdownlint 擴充][vscode-markdownlint]
  - [Sublime Text 用 markdownlint][sublimelinter]
  - [Vim/Neovim 的 coc-markdownlint 擴充][coc]
  - [Emacs 的 flymake-markdownlint-cli2 擴充][emacs-flymake]
- 工具鏈
  - [ESLint 的 eslint-plugin-markdownlint][eslint-plugin]
  - [Grunt 任務管理器專用 grunt-markdownlint][grunt-markdownlint]
  - [Cake 自動化系統的 Cake.Markdownlint 外掛][cake]
  - [MSBuild (.NET) 的 Lombiq Node.js Extensions][nodejs-extensions]
- Ruby
  - [markdownlint/mdl Ruby gem][rubygems-mdl]

[cake]: https://github.com/cake-contrib/Cake.Markdownlint
[coc]: https://github.com/fannheyward/coc-markdownlint
[emacs-flymake]: https://github.com/ewilderj/flymake-markdownlint-cli2
[eslint-plugin]: https://github.com/paweldrozd/eslint-plugin-markdownlint
[grunt-markdownlint]: https://github.com/sagiegurari/grunt-markdownlint
[markdownlint-cli]: https://github.com/igorshubovych/markdownlint-cli
[markdownlint-cli-precommit]: https://github.com/igorshubovych/markdownlint-cli#use-with-pre-commit
[markdownlint-cli2]: https://github.com/DavidAnson/markdownlint-cli2
[markdownlint-cli2-action]: https://github.com/marketplace/actions/markdownlint-cli2-action
[markdownlint-cli2-precommit]: https://github.com/DavidAnson/markdownlint-cli2#pre-commit
[markdownlint-problem-matcher]: https://github.com/xt0rted/markdownlint-problem-matcher
[nodejs-extensions]: https://github.com/Lombiq/NodeJs-Extensions
[rubygems-mdl]: https://rubygems.org/gems/mdl
[sublimelinter]: https://github.com/jonlabelle/SublimeLinter-contrib-markdownlint
[super-linter]: https://github.com/super-linter/super-linter
[vscode-markdownlint]: https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint

### 參考資料

如遇語法歧義，以下規範具有權威性：

- [CommonMark](https://spec.commonmark.org/current/)
- [GitHub Flavored Markdown Spec](https://github.github.com/gfm/)

## 演示

[`markdownlint` 線上演示](https://dlaa.me/markdownlint/)，互動式瀏覽器 playground，方便學習與探索。

## 規則 / 別名

<!-- markdownlint-disable line-length -->

- **[MD001](doc/md001.md)** *heading-increment* - 標題階層應僅一次遞增一級
- **[MD003](doc/md003.md)** *heading-style* - 標題樣式
- **[MD004](doc/md004.md)** *ul-style* - 無序列表樣式
- **[MD005](doc/md005.md)** *list-indent* - 同層級項目縮排不一致
- **[MD007](doc/md007.md)** *ul-indent* - 無序列表縮排
- **[MD009](doc/md009.md)** *no-trailing-spaces* - 行尾多餘空格
- **[MD010](doc/md010.md)** *no-hard-tabs* - 硬式 Tab
- **[MD011](doc/md011.md)** *no-reversed-links* - 反向連結語法
- **[MD012](doc/md012.md)** *no-multiple-blanks* - 多行連續空白
- **[MD013](doc/md013.md)** *line-length* - 行長限制
- **[MD014](doc/md014.md)** *commands-show-output* - 命令前出現 $ 符號但未顯示輸出
- **[MD018](doc/md018.md)** *no-missing-space-atx* - ATX 樣式標題 # 後缺空格
- **[MD019](doc/md019.md)** *no-multiple-space-atx* - ATX 樣式標題 # 後多餘空格
- **[MD020](doc/md020.md)** *no-missing-space-closed-atx* - 封閉式 ATX 標題內部缺空格
- **[MD021](doc/md021.md)** *no-multiple-space-closed-atx* - 封閉式 ATX 標題內部多餘空格
- **[MD022](doc/md022.md)** *blanks-around-headings* - 標題上下應有空白行
- **[MD023](doc/md023.md)** *heading-start-left* - 標題應從行首開始
- **[MD024](doc/md024.md)** *no-duplicate-heading* - 標題重複
- **[MD025](doc/md025.md)** *single-title/single-h1* - 文件中僅有一個頂層標題
- **[MD026](doc/md026.md)** *no-trailing-punctuation* - 標題尾端有標點
- **[MD027](doc/md027.md)** *no-multiple-space-blockquote* - 區塊引言符號後多餘空格
- **[MD028](doc/md028.md)** *no-blanks-blockquote* - 區塊引言中有空白行
- **[MD029](doc/md029.md)** *ol-prefix* - 有序列表前綴
- **[MD030](doc/md030.md)** *list-marker-space* - 列表標記後空格
- **[MD031](doc/md031.md)** *blanks-around-fences* - 程式碼區塊上下應有空白行
- **[MD032](doc/md032.md)** *blanks-around-lists* - 列表上下應有空白行
- **[MD033](doc/md033.md)** *no-inline-html* - 禁用內嵌 HTML
- **[MD034](doc/md034.md)** *no-bare-urls* - 裸露 URL
- **[MD035](doc/md035.md)** *hr-style* - 水平分隔線樣式
- **[MD036](doc/md036.md)** *no-emphasis-as-heading* - 標題不可用強調語法
- **[MD037](doc/md037.md)** *no-space-in-emphasis* - 強調標記內有空格
- **[MD038](doc/md038.md)** *no-space-in-code* - 行內程式碼區塊內有空格
- **[MD039](doc/md039.md)** *no-space-in-links* - 連結文字內有空格
- **[MD040](doc/md040.md)** *fenced-code-language* - 程式碼區塊應指定語言
- **[MD041](doc/md041.md)** *first-line-heading/first-line-h1* - 文件首行應為頂層標題
- **[MD042](doc/md042.md)** *no-empty-links* - 禁用空連結
- **[MD043](doc/md043.md)** *required-headings* - 必要標題結構
- **[MD044](doc/md044.md)** *proper-names* - 專有名稱應正確大小寫
- **[MD045](doc/md045.md)** *no-alt-text* - 圖片應有替代文字（alt text）
- **[MD046](doc/md046.md)** *code-block-style* - 程式碼區塊樣式
- **[MD047](doc/md047.md)** *single-trailing-newline* - 文件僅以一個換行結尾
- **[MD048](doc/md048.md)** *code-fence-style* - 程式碼區塊圍欄樣式
- **[MD049](doc/md049.md)** *emphasis-style* - 強調語法樣式
- **[MD050](doc/md050.md)** *strong-style* - 粗體樣式
- **[MD051](doc/md051.md)** *link-fragments* - 連結片段應有效
- **[MD052](doc/md052.md)** *reference-links-images* - 參考連結與圖片應有定義
- **[MD053](doc/md053.md)** *link-image-reference-definitions* - 僅定義有用到的連結與圖片
- **[MD054](doc/md054.md)** *link-image-style* - 連結與圖片樣式
- **[MD055](doc/md055.md)** *table-pipe-style* - 表格分隔線樣式
- **[MD056](doc/md056.md)** *table-column-count* - 表格欄位數量
- **[MD058](doc/md058.md)** *blanks-around-tables* - 表格上下需空白行
- **[MD059](doc/md059.md)** *descriptive-link-text* - 連結文字應具描述性

<!-- markdownlint-restore -->

更多規則細節請參見 [Rules.md](doc/Rules.md)。

### 自訂規則

除內建規則外，也可使用自訂規則以符合專案需求。社群規則可在 npm 搜尋 [關鍵字 `markdownlint-rule`][markdownlint-rule]。撰寫自訂規則請參考 [CustomRules.md](doc/CustomRules.md)。

[markdownlint-rule]: https://www.npmjs.com/search?q=keywords:markdownlint-rule

## 標籤

標籤用以分組相關規則，並可一次啟用/停用多條規則。

- **`accessibility`** - `MD045`, `MD059`
- **`atx`** - `MD018`, `MD019`
- **`atx_closed`** - `MD020`, `MD021`
- **`blank_lines`** - `MD012`, `MD022`, `MD031`, `MD032`, `MD047`
- **`blockquote`** - `MD027`, `MD028`
- **`bullet`** - `MD004`, `MD005`, `MD007`, `MD032`
- **`code`** - `MD014`, `MD031`, `MD038`, `MD040`, `MD046`, `MD048`
- **`emphasis`** - `MD036`, `MD037`, `MD049`, `MD050`
- **`hard_tab`** - `MD010`
- **`headings`** - `MD001`, `MD003`, `MD018`, `MD019`, `MD020`, `MD021`,
  `MD022`, `MD023`, `MD024`, `MD025`, `MD026`, `MD036`, `MD041`, `MD043`
- **`hr`** - `MD035`
- **`html`** - `MD033`
- **`images`** - `MD045`, `MD052`, `MD053`, `MD054`
- **`indentation`** - `MD005`, `MD007`, `MD027`
- **`language`** - `MD040`
- **`line_length`** - `MD013`
- **`links`** - `MD011`, `MD034`, `MD039`, `MD042`, `MD051`, `MD052`, `MD053`,
  `MD054`, `MD059`
- **`ol`** - `MD029`, `MD030`, `MD032`
- **`spaces`** - `MD018`, `MD019`, `MD020`, `MD021`, `MD023`
- **`spelling`** - `MD044`
- **`table`** - `MD055`, `MD056`, `MD058`
- **`ul`** - `MD004`, `MD005`, `MD007`, `MD030`, `MD032`
- **`url`** - `MD034`
- **`whitespace`** - `MD009`, `MD010`, `MD012`, `MD027`, `MD028`, `MD030`,
  `MD037`, `MD038`, `MD039`

## 設定

`markdownlint` 會將輸入的文字解析為 Markdown，分析後回報所有問題。大多數規則會忽略兩種區塊：

- [HTML 註解](https://www.w3.org/TR/html5/syntax.html#comments)
- [Front matter](https://jekyllrb.com/docs/frontmatter/)（見下方 `options.frontMatter`）

可透過 `options.config`（說明見下方）啟用、停用或設定規則，定義一組輸入預期行為。如需在特定位置啟用/停用規則，可插入下列標記（HTML 註解不會出現在最終標記中）：

- 停用所有規則：`<!-- markdownlint-disable -->`
- 啟用所有規則：`<!-- markdownlint-enable -->`
- 僅停用當前行：`<!-- markdownlint-disable-line -->`
- 僅停用下一行：`<!-- markdownlint-disable-next-line -->`
- 停用指定規則：`<!-- markdownlint-disable MD001 MD005 -->`
- 啟用指定規則：`<!-- markdownlint-enable MD001 MD005 -->`
- 僅停用當前行指定規則：`<!-- markdownlint-disable-line MD001 MD005 -->`
- 僅停用下一行指定規則：`<!-- markdownlint-disable-next-line MD001 MD005 -->`
- 捕捉目前規則配置：`<!-- markdownlint-capture -->`
- 還原捕捉的規則配置：`<!-- markdownlint-restore -->`

例如：

```markdown
<!-- markdownlint-disable-next-line no-space-in-emphasis -->
space * in * emphasis
```

或：

```markdown
space * in * emphasis <!-- markdownlint-disable-line no-space-in-emphasis -->
```

或：

```markdown
<!-- markdownlint-disable no-space-in-emphasis -->
space * in * emphasis
<!-- markdownlint-enable no-space-in-emphasis -->
```

若要暫時停用規則，之後還原配置：

```markdown
<!-- markdownlint-capture -->
<!-- markdownlint-disable -->
any violations you want
<!-- markdownlint-restore -->
```

預設會自動捕捉初始設定（如同每份文件開頭都有 `<!-- markdownlint-capture -->`），所以可簡化為：

```markdown
<!-- markdownlint-disable -->
any violations you want
<!-- markdownlint-restore -->
```

更動自註解所在行即生效，因此下例無作用：

```markdown
space * in * emphasis <!-- markdownlint-disable --> <!-- markdownlint-enable -->
```

若需影響整份文件，可用下列語法：

- 停用所有規則：`<!-- markdownlint-disable-file -->`
- 啟用所有規則：`<!-- markdownlint-enable-file -->`
- 停用指定規則：`<!-- markdownlint-disable-file MD001 -->`
- 啟用指定規則：`<!-- markdownlint-enable-file MD001 -->`

可將 `markdownlint` 註解「隱藏」於文件底部。

如需針對文件更動一或多條規則的設定，可用進階語法：

- 設定：`<!-- markdownlint-configure-file { options.config JSON } -->`

例如：

```markdown
<!-- markdownlint-configure-file { "hr-style": { "style": "---" } } -->
```

或

```markdown
<!-- markdownlint-configure-file
{
  "hr-style": {
    "style": "---"
  },
  "no-trailing-spaces": false
}
-->
```

這些更動影響整份文件。若有多個註解，會自上而下依序套用。預設內容視為 JSON，可用 [`options.configParsers`](#optionsconfigparsers) 支援其他格式。

## API

### Lint 檢查

使用 `import { lint } from "markdownlint/async"` 非同步 API：

```javascript
/**
 * 檢查指定 Markdown 文件。
 *
 * @param {Options | null} options 設定選項。
 * @param {LintCallback} callback 回呼 (err, result)。
 * @returns {void}
 */
function lint(options, callback) { ... }
```

使用 `import { lint } from "markdownlint/sync"` 同步 API：

```javascript
/**
 * 檢查指定 Markdown 文件。
 *
 * @param {Options | null} options 設定選項。
 * @returns {LintResults} 結果物件。
 */
function lint(options) { ... }
```

使用 `import { lint } from "markdownlint/promise"` Promise API：

```javascript
/**
 * 檢查指定 Markdown 文件。
 *
 * @param {Options | null} options 設定選項。
 * @returns {Promise<LintResults>} 結果物件。
 */
function lint(options) { ... }
```

#### options

型別：`Object`

用於設定函式。所有屬性皆為可選，但至少需要設定 `files` 或 `strings`。

##### options.config

型別：`Object`（鍵為 `String`，值可為 `Boolean` 或 `Object`）

指定使用哪些規則。

物件鍵為規則名稱或別名；值為該規則的設定。`false` 停用該規則，`true` 啟用預設設定，物件值則自訂規則。`default` 為特殊鍵，`true` 或 `false` 代表預設啟用/停用所有規則。未指定設定時，預設所有規則皆啟用。可設定標籤（如 `whitespace`）來一次影響多條規則。

`default` 最先套用，其餘依順序覆蓋。鍵（含規則名、別名、標籤、`default`）皆不分大小寫。

範例：

```json
{
  "default": true,
  "MD003": { "style": "atx_closed" },
  "MD007": { "indent": 4 },
  "no-hard-tabs": false,
  "whitespace": false
}
```

詳見 [.markdownlint.jsonc](schema/.markdownlint.jsonc) 與
[.markdownlint.yaml](schema/.markdownlint.yaml) 之完整設定範例。

規則組（稱為「風格」）可獨立儲存並以 [JSON](https://en.wikipedia.org/wiki/JSON) 匯入。

JavaScript 使用內建風格範例：

```javascript
const options = {
  "files": [ "..." ],
  "config": require("style/relaxed.json")
};
```

`.markdownlint.json` 透過 `extends` 引用範例：

```json
{
  "extends": "markdownlint/style/relaxed"
}
```

更多範例請參見 [style](style) 目錄。

[markdownlint-config-schema.json](schema/markdownlint-config-schema.json) 提供 `options.config` 之 [JSON Schema](https://json-schema.org/)。

[ValidatingConfiguration.md](schema/ValidatingConfiguration.md) 介紹如何用該 Schema 驗證設定。

進階情境下，風格可用 `extends` 關鍵字繼承其他風格。`readConfig` 可用於讀取合併後的設定。

假設有 `base.json`：

```json
{
  "default": true
}
```

以及 `custom.json`：

```json
{
  "extends": "base.json",
  "line-length": false
}
```

則程式碼：

```javascript
const options = {
  "config": markdownlint.readConfigSync("./custom.json")
};
```

會合併 `custom.json` 與 `base.json`，等同於：

```javascript
const options = {
  "config": {
    "default": true,
    "line-length": false
  }
};
```

##### options.configParsers

型別：*可選* `Array`，元素為接收 (`String`) 並回傳 `Object` 的函式

用於解析 `markdownlint-configure-file` 區塊內容。

如 [設定](#configuration) 所示，可用內嵌註解自訂 [設定物件](#optionsconfig)。預設用 `JSON.parse`，也可指定自訂解析器。內容會依序傳遞給每個解析器，直到有一個成功回傳。建議嚴格解析器排前面。

範例：

```javascript
[ JSON.parse, require("toml").parse, require("js-yaml").load ]
```

##### options.customRules

型別：`Array` of `Object`

自訂規則陣列，與預設規則一同執行。

每個元素應定義一條規則。可引用其他套件，也可自訂。

範例：

```javascript
const extraRules = require("extraRules");
const options = {
  "customRules": [ extraRules.one, extraRules.two ]
};
```

自訂規則撰寫詳見 [CustomRules.md](doc/CustomRules.md)。

##### options.files

型別：`Array` of `String`

欲 lint 的檔案清單。

每個元素為一個檔案路徑（可為相對或絕對路徑）；[globbing](https://en.wikipedia.org/wiki/Glob_%28programming%29) 需自行處理。

範例：`[ "one.md", "dir/two.md" ]`

##### options.frontMatter

型別：`RegExp`

匹配檔案開頭的 [front matter](https://jekyllrb.com/docs/frontmatter/)。

某些 Markdown 內容以中繼資料開頭；本選項預設為常見型態。可指定自訂正則或設為 `null` 停用。

預設值：

```javascript
/((^---[^\S\r\n\u2028\u2029]*$[\s\S]+?^---\s*)|(^\+\+\+[^\S\r\n\u2028\u2029]*$[\s\S]+?^(\+\+\+|\.\.\.)\s*)|(^\{[^\S\r\n\u2028\u2029]*$[\s\S]+?^\}\s*))(\r\n|\r|\n|$)/m
```

可忽略 [YAML](https://en.wikipedia.org/wiki/YAML)、[TOML](https://en.wikipedia.org/wiki/TOML)、[JSON](https://en.wikipedia.org/wiki/JSON) 等 front matter：

```text
---
layout: post
title: Title
---
```

注意：必須出現在檔案最前。

##### options.fs

型別：實作 [file system API][node-fs-api] 的 `Object`

進階情境下，可自訂檔案系統。只會呼叫 `readFile` 與 `readFileSync`。

[node-fs-api]: https://nodejs.org/api/fs.html

##### options.handleRuleFailures

型別：`Boolean`

捕捉規則處理時的例外，並回報為規則違反。

預設規則（或函式本身）丟出例外時，會直接拋出。設為 `true` 時，將視為違規並繼續檢查。適用於自訂規則錯誤時不中斷檢查。

##### options.markdownItFactory

型別：回傳 [`markdown-it` 解析器][markdown-it] 實例的函式

提供自訂 `markdown-it` 解析器的工廠函式。

舊版 markdownlint 會直接依賴 `markdown-it`，本選項可避開。若需外掛，請自行 `use` 再回傳實例。

非同步情境下可回傳 `Promise` 延遲載入：

```javascript
const markdownItFactory = () => import("markdown-it").then((module) => module.default({ "html": true }));
```

> 注意：僅有自訂規則用到 `markdown-it` 時才會呼叫此函式。

[custom-rules]: #custom-rules
[markdown-it]: https://github.com/markdown-it/markdown-it
[markdown-it-plugin]: https://www.npmjs.com/search?q=keywords:markdown-it-plugin

##### options.noInlineConfig

型別：`Boolean`

停用內嵌設定（如 `<!-- markdownlint-enable -->`）切換規則。

預設允許用 HTML 註解例外部分內容。設為 `true` 時會忽略所有該類註解。

##### options.resultVersion

型別：`Number`

指定回傳 `result` 物件的版本（見下方「用法」範例）。

resultVersion = `0`：原始簡易格式，僅有規則名與行號。*已棄用*

resultVersion = `1`：詳細格式，含行號、規則名、別名、描述等。*已棄用*

resultVersion = `2`：詳細格式，含多條規則名、描述等。*已棄用*

resultVersion = `3`：同 version 2，但含自動修正訊息，且所有錯誤皆列出（其他版本僅列出每條規則的首個錯誤）。預設行為。

##### options.strings

型別：`Object`（鍵、值皆為 `String`）

用於直接傳入 Markdown 內容。

當 Markdown 內容不以檔案存在時，可用字串傳入。物件鍵做為輸出識別。

範例：

```json
{
  "readme": "# README\n...",
  "changelog": "# CHANGELOG\n..."
}
```

#### callback

型別：函式，參數為 (`Error`, `Object`)

標準完成回呼。

#### result

型別：`Object`

可用 `result.toString()` 輸出，或直接檢查結構。傳入 `true` 會用別名（如 `no-hard-tabs`）代替規則名（如 `MD010`）。

### 設定

`options.config` 設定物件可獨立存檔，方便閱讀與重用。`readConfig` 函式可讀取設定，並支援 `extends` 關鍵字繼承檔案或套件（見上文）。

預設設定檔為 JSON 格式（檔名 `.markdownlint.json`）。可自訂解析器支援 JSONC、YAML、TOML 等格式。

使用 `import { readConfig } from "markdownlint/async"` 非同步 API：

```javascript
/**
 * 讀取設定檔。
 *
 * @param {string} file 設定檔名。
 * @param {ConfigurationParser[] | ReadConfigCallback} [parsers] 解析函式。
 * @param {Object} [fs] 檔案系統實作。
 * @param {ReadConfigCallback} [callback] 回呼。
 * @returns {void}
 */
function readConfig(file, parsers, fs, callback) { ... }
```

使用 `import { readConfig } from "markdownlint/sync"` 同步 API：

```javascript
/**
 * 讀取設定檔。
 *
 * @param {string} file 設定檔名。
 * @param {ConfigurationParser[]} [parsers] 解析函式。
 * @param {Object} [fs] 檔案系統實作。
 * @returns {Configuration} 設定物件。
 */
function readConfig(file, parsers, fs) { ... }
```

使用 `import { readConfig } from "markdownlint/promise"` Promise API：

```javascript
/**
 * 讀取設定檔。
 *
 * @param {string} file 設定檔名。
 * @param {ConfigurationParser[]} [parsers] 解析函式。
 * @param {Object} [fs] 檔案系統實作。
 * @returns {Promise<Configuration>} 設定物件。
 */
function readConfig(file, parsers, fs) { ... }
```

#### file

型別：`String`

設定檔路徑。

相對於當前工作目錄解析。若有 `extends`，則以相對於該檔案的路徑尋找，並遞迴讀取。`extends` 先套用，被引用的鍵會被後者覆蓋。若 `file` 或 `extends` 路徑以 `~` 開頭，則代表家目錄。

#### parsers

型別：*可選* `Array`，元素為接收 (`String`) 並回傳 `Object` 的函式

用於設定檔解析。

內容依序傳給每個解析器，直到其中一個成功解析。建議嚴格解析器排前面。

範例：

```javascript
[ JSON.parse, require("toml").parse, require("js-yaml").load ]
```

#### fs

型別：*可選* 實作 [file-system-api][file-system-api] 的 `Object`

[file-system-api]: https://nodejs.org/api/fs.html

進階情境下，可自訂檔案系統。只會呼叫 `readFile`、`readFileSync`、`access`、`accessSync`。

#### callback

型別：函式，參數為 (`Error`, `Object`)

標準完成回呼。

#### result

型別：`Object`

設定物件。

### 自動修正

可自動修正的規則會含有 `fixInfo` 屬性，詳見 [自訂規則文件](doc/CustomRules.md#authoring)。可用 `applyFix`/`applyFixes` 方法應用修正，方法如下：

```javascript
import { applyFix, applyFixes } from "markdownlint";

/**
 * 套用單條修正建議於某行。
 *
 * @param {string} line Markdown 內容行。
 * @param {RuleOnErrorFixInfo} fixInfo 修正資訊。
 * @param {string} [lineEnding] 行尾字元，預設 "\n"。
 * @returns {string | null} 修正後內容，若刪除則為 null。
 */
function applyFix(line, fixInfo, lineEnding = "\n") { ... }

/**
 * 盡可能套用多條修正建議。
 *
 * @param {string} input Markdown 內容。
 * @param {RuleOnErrorInfo[]} errors 錯誤資訊。
 * @returns {string} 修正後內容。
 */
function applyFixes(input, errors) { ... }
```

範例：

```javascript
import { applyFixes } from "markdownlint";
import { lint as lintSync } from "markdownlint/sync";

const results = lintSync({ "strings": { "content": original } });
const fixed = applyFixes(original, results.content);
```

### 其他

取得函式庫 [Semantic Version][semver] 可用 `getVersion`：

```javascript
/**
 * 取得函式庫版本字串。
 *
 * @returns {string} SemVer 版本字串。
 */
function getVersion() { ... }
```

範例：

```javascript
import { getVersion } from "markdownlint";

// 顯示函式庫版本
console.log(getVersion());
```

[semver]: https://semver.org

## 用法

呼叫 `lint` 並用 `result.toString()` 輸出：

```javascript
import { lint as lintAsync } from "markdownlint/async";

const options = {
  "files": [ "good.md", "bad.md" ],
  "strings": {
    "good.string": "# good.string\n\nThis string passes all rules.",
    "bad.string": "#bad.string\n\n#This string fails\tsome rules."
  }
};

lintAsync(options, function callback(error, results) {
  if (!error && results) {
    console.log(results.toString());
  }
});
```

輸出：

```text
bad.string: 3: MD010/no-hard-tabs Hard tabs [Column: 19]
bad.string: 1: MD018/no-missing-space-atx No space after hash on atx style heading [Context: "#bad.string"]
bad.string: 3: MD018/no-missing-space-atx No space after hash on atx style heading [Context: "#This string fails        some rules."]
bad.string: 1: MD041/first-line-heading/first-line-h1 First line in a file should be a top-level heading [Context: "#bad.string"]
bad.md: 3: MD010/no-hard-tabs Hard tabs [Column: 17]
bad.md: 1: MD018/no-missing-space-atx No space after hash on atx style heading [Context: "#bad.md"]
bad.md: 3: MD018/no-missing-space-atx No space after hash on atx style heading [Context: "#This file fails      some rules."]
bad.md: 1: MD041/first-line-heading/first-line-h1 First line in a file should be a top-level heading [Context: "#bad.md"]
```

同步呼叫：

```javascript
import { lint as lintSync } from "markdownlint/sync";

const results = lintSync(options);
console.log(results.toString());
```

Promise 方式直接檢查結果物件：

```javascript
import { lint as lintPromise } from "markdownlint/promise";

const results = await lintPromise(options);
console.dir(results, { "colors": true, "depth": null });
```

輸出：

```json
{
  "good.md": [],
  "bad.md": [
    { "lineNumber": 3,
      "ruleNames": [ "MD010", "no-hard-tabs" ],
      "ruleDescription": "Hard tabs",
      "ruleInformation": "https://github.com/DavidAnson/markdownlint/blob/v0.0.0/doc/md010.md",
      "errorDetail": "Column: 17",
      "errorContext": null,
      "errorRange": [ 17, 1 ] },
    { "lineNumber": 1,
      "ruleNames": [ "MD018", "no-missing-space-atx" ],
      "ruleDescription": "No space after hash on atx style heading",
      "ruleInformation": "https://github.com/DavidAnson/markdownlint/blob/v0.0.0/doc/md018.md",
      "errorDetail": null,
      "errorContext": "#bad.md",
      "errorRange": [ 1, 2 ] },
    { "lineNumber": 3,
      "ruleNames": [ "MD018", "no-missing-space-atx" ],
      "ruleDescription": "No space after hash on atx style heading",
      "ruleInformation": "https://github.com/DavidAnson/markdownlint/blob/v0.0.0/doc/md018.md",
      "errorDetail": null,
      "errorContext": "#This file fails\tsome rules.",
      "errorRange": [ 1, 2 ] },
    { "lineNumber": 1,
      "ruleNames": [ "MD041", "first-line-heading", "first-line-h1" ],
      "ruleDescription": "First line in a file should be a top-level heading",
      "ruleInformation": "https://github.com/DavidAnson/markdownlint/blob/v0.0.0/doc/md041.md",
      "errorDetail": null,
      "errorContext": "#bad.md",
      "errorRange": null }
  ]
}
```

可與 [gulp](https://gulpjs.com/) 构建系統整合：[gulpfile.cjs](example/gulpfile.cjs)。

與 [Grunt](https://gruntjs.com/) 整合方式類似：[Gruntfile.cjs](example/Gruntfile.cjs)。

## 瀏覽器支援

`markdownlint` 亦支援瀏覽器端。

可用以下指令打包：

```bash
npm run build-demo
```

然後引用 `markdownlint-browser` 腳本：

```html
<script src="demo/markdownlint-browser.min.js"></script>
```

呼叫方式如下：

```javascript
const options = {
  "strings": {
    "content": "Some Markdown to lint."
  }
};

const results = globalThis.markdownlint.lintSync(options).toString();
```

## 範例

如需將 `markdownlint` 整合入工作流程，可參考下列專案或 [相關工具](#相關工具)：

- [.NET 文件][dot-net-doc]（[搜尋 repo][dot-net-doc-search]）
- [ally.js][ally-js]（[搜尋 repo][ally-js-search]）
- [Apache Airflow][airflow]（[搜尋 repo][airflow-search]）
- [Boostnote][boostnote]（[搜尋 repo][boostnote-search]）
- [CodiMD][codimd]（[搜尋 repo][codimd-search]）
- [Electron][electron]（[搜尋 repo][electron-search]）
- [ESLint][eslint]（[搜尋 repo][eslint-search]）
- [Garden React Components][garden]（[搜尋 repo][garden-search]）
- [MDN Web Docs][mdn]（[搜尋 repo][mdn-search]）
- [MkDocs][mkdocs]（[搜尋 repo][mkdocs-search]）
- [Mocha][mocha]（[搜尋 repo][mocha-search]）
- [Pi-hole 文件][pi-hole]（[搜尋 repo][pi-hole-search]）
- [Reactable][reactable]（[搜尋 repo][reactable-search]）
- [V8][v8]（[搜尋 repo][v8-search]）
- [webhint][webhint]（[搜尋 repo][webhint-search]）
- [webpack][webpack]（[搜尋 repo][webpack-search]）
- [WordPress][wordpress]（[搜尋 repo][wordpress-search]）

進階整合案例：

- [GitHub Docs 內容檢查][content-linter]
- [GitHub 的 `markdownlint-github` repo][markdownlint-github]

[ally-js]: https://allyjs.io/
[ally-js-search]: https://github.com/medialize/ally.js/search?q=markdownlint
[airflow]: https://airflow.apache.org
[airflow-search]: https://github.com/apache/airflow/search?q=markdownlint
[boostnote]: https://boostnote.io/
[boostnote-search]: https://github.com/BoostIO/Boostnote/search?q=markdownlint
[codimd]: https://github.com/hackmdio/codimd
[codimd-search]: https://github.com/hackmdio/codimd/search?q=markdownlint
[content-linter]: https://docs.github.com/en/contributing/collaborating-on-github-docs/using-the-content-linter
[dot-net-doc]: https://docs.microsoft.com/en-us/dotnet/
[dot-net-doc-search]: https://github.com/dotnet/docs/search?q=markdownlint
[electron]: https://www.electronjs.org
[electron-search]: https://github.com/electron/electron/search?q=markdownlint
[eslint]: https://eslint.org/
[eslint-search]: https://github.com/eslint/eslint/search?q=markdownlint
[garden]: https://zendeskgarden.github.io/react-components/
[garden-search]: https://github.com/zendeskgarden/react-components/search?q=markdownlint
[markdownlint-github]: https://github.com/github/markdownlint-github
[mdn]: https://developer.mozilla.org/
[mdn-search]: https://github.com/mdn/content/search?q=markdownlint
[mkdocs]: https://www.mkdocs.org/
[mkdocs-search]: https://github.com/mkdocs/mkdocs/search?q=markdownlint
[mocha]: https://mochajs.org/
[mocha-search]: https://github.com/mochajs/mocha/search?q=markdownlint
[pi-hole]: https://docs.pi-hole.net
[pi-hole-search]: https://github.com/pi-hole/docs/search?q=markdownlint
[reactable]: https://glittershark.github.io/reactable/
[reactable-search]: https://github.com/glittershark/reactable/search?q=markdownlint
[v8]: https://v8.dev/
[v8-search]: https://github.com/v8/v8.dev/search?q=markdownlint
[webhint]: https://webhint.io/
[webhint-search]: https://github.com/webhintio/hint/search?q=markdownlint
[webpack]: https://webpack.js.org/
[webpack-search]: https://github.com/webpack/webpack.js.org/search?q=markdownlint
[wordpress]: https://wordpress.org/gutenberg/
[wordpress-search]: https://github.com/WordPress/gutenberg/search?q=markdownlint

## 貢獻

詳見 [CONTRIBUTING.md](CONTRIBUTING.md)。

## 發行

詳見 [ReleaseProcess.md](doc/ReleaseProcess.md)。

## 歷史

詳見 [CHANGELOG.md](CHANGELOG.md)。

[npm-image]: https://img.shields.io/npm/v/markdownlint.svg
[npm-url]: https://www.npmjs.com/package/markdownlint
[license-image]: https://img.shields.io/npm/l/markdownlint.svg
[license-url]: https://opensource.org/licenses/MIT
