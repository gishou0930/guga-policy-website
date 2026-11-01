# 咕嘎 AI Threads 隱私政策網站

這是可部署到 GitHub Pages 的純靜態網站，沒有建置步驟、追蹤程式或第三方前端套件。

## 上線前必做

1. 在 `index.html` 和 `data-deletion.html` 搜尋「上線前請填入聯絡 Email」，換成可收信的隱私聯絡地址。
2. 確認政策中對資料用途、資料保存位置及刪除方式的描述仍與目前程式一致。
3. 推送到 GitHub 後，等 Pages 部署完成，再將實際網站 URL 填入 Meta App 的 Privacy Policy URL。若 Meta 另外要求資料刪除網址，使用網站的 `data-deletion.html`。

## 從整個 ai-threads 專案部署

專案根目錄的 `.github/workflows/policy-website-pages.yml` 會在 `policy-website/` 內容推送到 `main` 後，自動將這個資料夾發布到 GitHub Pages。

1. 將整個專案推送到 GitHub 的 `main` 分支。
2. 在 GitHub 專案的 **Settings → Pages → Build and deployment**，將 **Source** 設為 **GitHub Actions**。
3. 在 **Actions** 等待 `Publish privacy policy` 工作流程完成。GitHub 會顯示實際網址，常見格式是 `https://<帳號>.github.io/<儲存庫>/`。
4. Meta 使用的網址通常是：
   - Privacy Policy URL：`https://<帳號>.github.io/<儲存庫>/`
   - User Data Deletion Instructions URL（若需要）：`https://<帳號>.github.io/<儲存庫>/data-deletion.html`

GitHub Pages 網站會公開供網際網路讀取，請勿把 Token、App Secret、`.env` 或本機資料庫放進此資料夾。

## 只把此資料夾做成獨立儲存庫

將本資料夾中的檔案放在新儲存庫根目錄後，可在 **Settings → Pages → Build and deployment** 選擇 **Deploy from a branch**，指定 `main` 與 `/(root)`。這種方式不需要專案根目錄的 Actions 工作流程。
