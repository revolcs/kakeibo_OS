# 羊的家計簿（GitHub Pages 版）

單一 HTML 檔。數據存喺瀏覽器，亦可以經 GitHub 同步去手機同電腦。

## 第一步：開網頁版（頁面 repo）
1. 新建一個 **Public** repo，例如 `kakeibo`
2. 上傳 `index.html`、`README.md`、`.gitignore`
3. Settings → Pages → Source 揀 `Deploy from a branch`，Branch 揀 `main`，資料夾 `/(root)`，Save
4. 等幾分鐘，打開 `https://你的用戶名.github.io/kakeibo/`

頁面入面**冇任何數據**，公開都安全。

## 第二步：開一個私人數據 repo（同步用）
1. 新建一個 **Private** repo，例如 `kakeibo-data`，留空白就得
2. 去 GitHub 頭像 → Settings → Developer settings → Personal access tokens → **Fine-grained tokens** → Generate new token
3. 設定：
   - Token name：`kakeibo`
   - Expiration：揀一個日子（例如 1 年），到期要重做
   - Repository access：揀 **Only select repositories**，只揀 `kakeibo-data`
   - Permissions → Repository permissions → **Contents：Read and write**
4. 生成後 copy 落嚟（只會顯示一次）

## 第三步：喺網頁填設定
打開網頁 → 「⚙️ 設定」→ 「☁️ GitHub 同步」：
- 倉庫：`你的用戶名/kakeibo-data`
- 檔案路徑：`kakeibo.json`（留預設就得）
- Token：貼上第二步嗰個
- 撳「💾 儲存設定」，再撳「⬆️ 上傳」

之後手機同電腦都做同樣設定，然後撳「⬇️ 還原」就會拎到最新數據。勾咗「改數之後自動上傳」就唔使手動撳，改完停 15 秒自動上傳。

## 注意
- **同一時間只可以一部機主力記數。** 如果兩部機都改咗數，後上傳嗰部會見到「有較新版本」並被擋住，要先撳「⬇️ 還原」，唔會覆蓋對方嘅數。
- 自動上傳係停 15 秒後先做，**撳走個 app 太快可能未上傳**，要即刻撳「⬆️ 上傳」。
- Token 只存喺呢部機瀏覽器。手機唔見咗或者想斷開，去 GitHub 將個 token 刪除就得。
- 每次上傳都會喺 `kakeibo-data` 留低一個 commit，即係有歷史紀錄。
- 另外仲可以「📦 匯出備份」做本機備份。
