# ardge-website-demo

ARDGE demo site 清單，使用 [Docsify](https://docsify.js.org/) 建置，透過 GitHub Pages 發佈。
配色使用 [Catppuccin for Docsify](https://github.com/catppuccin/docsify)，預設依系統設定切換 Latte（淺色）/ Mocha（深色），也可用左側目錄下方的「自動 / 淺色 / 深色」按鈕手動切換（記在瀏覽器 localStorage），強調色為哆啦A夢藍（淺色 `#0072B8`、深色 `#0096E0`）。

- 網站：https://ardge-field.github.io/ardge-website-demo/
- 內容位於 `docs/`，依分類分檔：
  - `docs/internal.md` — 業務展示用
  - `docs/external.md` — 廠商測試機
  - `docs/support.md` — 技術資訊站

## 驗證碼

打開網站時需輸入 4 位數驗證碼：瀏覽者電腦當天日期的 `MMDD`（例如 10 月 12 日為 `1012`）。
輸入時以圓點遮罩。通過後記在瀏覽器工作階段 cookie，關閉瀏覽器或按左側目錄下方的「🚪 登出」後需重新輸入。

> 僅用來擋一般外部訪客，並非安全機制：repo 為 public，內容檔可直接存取。

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

## 發佈 Release

推送 `v` 開頭的 tag 時，GitHub Actions（`.github/workflows/release.yml`）會把 `docs/` 打包成 `ardge-website-demo-<版本>.zip`，並建立 Release，附上自動產生的變更清單。

```bash
git tag v1.1.0
git push origin v1.1.0
```

下載：https://github.com/ardge-field/ardge-website-demo/releases

zip 內為網站檔案；Docsify 與主題從 CDN 載入，需連網才能正常顯示。

## 本機預覽

```bash
npx docsify-cli serve docs
```
