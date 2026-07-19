# City Spiral v0.1.1 — Tunnel Startup Hotfix

建置日期：2026-07-19  
來源版本：`codex/fix-tunnel-startup` / `caa321d`

## 修正內容

- 修正 launcher 已取得有效 TryCloudflare 網址，卻因 Node `fetch` 間歇性失敗而顯示「Cloudflare Tunnel did not become ready」並阻止玩家繼續的問題。
- 一般玩家啟動時，改以 `cloudflared` connector 註冊完成作為開啟遊戲頁面的依據；公開 health check 不再是阻斷啟動的必要條件。
- 嚴格的公開 health check 仍保留在 packaged smoke test，避免真正的 Tunnel 故障被測試忽略。
- launcher 新增「重新開啟遊戲頁面」按鈕；瀏覽器未自動開啟或網路較慢時，可以直接重試。
- 改善 Windows installer 建置流程：先在本機暫存目錄產生 Squirrel installer，再複製到輸出目錄，降低大型檔案在 workspace 磁碟寫入時失敗的機率。

## 下載與啟動

- 一般玩家／房主建議下載 `CitySpiralSetup.exe`。
- 免安裝版請下載 `CitySpiral-win-x64-portable.zip`，完整解壓縮後再執行資料夾內的 `CitySpiral.exe`。
- 請勿單獨複製或直接從 ZIP 預覽視窗執行 `CitySpiral.exe`；它需要 portable 資料夾中的其他程式與資源。
- 支援 Windows 10／11 64-bit，建立或加入跨網路房間時需要網際網路連線。

## 已知限制

- TryCloudflare 網址是臨時網址，每次重新啟動房主工具都可能改變。
- 房間資料只存在房主記憶體中；房主關閉程式後，房間與對局不會保留。
- 此測試版尚未使用程式碼簽章，Windows SmartScreen 可能顯示警告。

## 驗證

- 自動測試：120 / 120 通過。
- Production web build：通過。
- Portable packaged smoke test：以真正的 process handle 等待完成，exit code 0。
- Portable 正常模式：launcher 與 Tunnel 正常維持執行；關閉後無殘留 CitySpiral／cloudflared 程序。
- Setup 安裝測試：成功安裝 `app-0.1.1`。
- 安裝後 packaged smoke test：exit code 0。
- 解除安裝測試：通過。
