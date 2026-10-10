# ardge-website-demo

ARDGE demo site 清單，使用 [Docsify](https://docsify.js.org/) 建置，透過 GitHub Pages 發佈。
配色使用 [Catppuccin for Docsify](https://github.com/catppuccin/docsify)，依系統設定自動切換 Latte（淺色）/ Mocha（深色），強調色為哆啦A夢藍（淺色 `#0072B8`、深色 `#0096E0`）。

- 網站：https://ardge-field.github.io/ardge-website-demo/
- 內容位於 `docs/`，依分類分檔：
  - `docs/internal.md` — 業務展示用
  - `docs/external.md` — 廠商測試機
  - `docs/support.md` — 技術資訊站

## 新增站台

需改兩個地方：

1. 在對應分類檔加一個章節：

   ```markdown
   ## 站台名稱

   - URL：https://example.com
   - 說明：
     - 附註一
     - 附註二
   ```

2. 在 `docs/_sidebar.md` 該分類下加一行（`id` 為標題轉小寫、空白換成 `-`）：

   ```markdown
     - [站台名稱](internal.md?id=站台名稱)
   ```

左側目錄下方的「更新日期」會自動顯示網站最後一次部署的時間。

## 本機預覽

```bash
npx docsify-cli serve docs
```
