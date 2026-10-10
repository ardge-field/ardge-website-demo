# ardge-website-demo

ARDGE demo site 清單，使用 [Docsify](https://docsify.js.org/) 建置，透過 GitHub Pages 發佈。

- 網站：https://ardge-field.github.io/ardge-website-demo/
- 內容位於 `docs/`，依分類分檔：
  - `docs/external.md` — 對外
  - `docs/internal.md` — 內測
  - `docs/support.md` — 支援

## 新增站台

在對應分類檔的表格加一行：

```markdown
| 站台名稱 | https://example.com |
```

## 本機預覽

```bash
npx docsify-cli serve docs
```
