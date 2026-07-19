# City Spiral — Initial Public Playtest Build

建置日期：2026-07-19  
來源版本：`master` / `c1a2efb`

## 本版重點

- 新增 AI Bot，單一真人玩家也能搭配 Bot 開始房間。
- 新增 Senator、People's Committee Chairman、Yamaguchi Team Leader 三種 Agent 行為與對話。
- 更新遊戲動畫、操作特效、材質、背景與角色圖示。
- 保留公開／私人房間、Lobby 與房間設定流程。
- Lobby 聊天訊息會透過房間伺服器同步給所有房間成員。
- Windows 房主工具會自動啟動本機房間伺服器及 TryCloudflare Tunnel，並顯示邀請連結與 QR Code。
- 關閉房主工具時，會一併停止本機 server 與 tunnel。

## 下載與啟動

- 一般玩家／房主建議下載 `CitySpiralSetup.exe`，雙擊安裝後啟動。
- 免安裝版請下載 `CitySpiral-win-x64-portable.zip`，完整解壓縮後再執行資料夾內的 `CitySpiral.exe`。
- 不要單獨複製 portable 資料夾裡的 `CitySpiral.exe`；它需要同資料夾內的其他程式與資源。
- 支援 Windows 10／11 64-bit，建立或加入跨網路房間時需要網際網路連線。

## 已知限制

- TryCloudflare 網址是臨時網址，每次重新啟動房主工具都可能改變。
- 房間資料只存在房主記憶體中；房主關閉程式後，房間與對局不會保留。
- 此測試版尚未使用程式碼簽章，Windows SmartScreen 可能顯示「Windows 已保護您的電腦」。請只從團隊公布的正式下載位置取得檔案，並比對 SHA-256。

## 驗證

- 自動測試：120 / 120 通過。
- Production web build：通過。
- Packaged app smoke test：成功啟動 server 與 TryCloudflare Tunnel、經公開網址建立房間、驗證邀請連結與 QR Code，並正常關閉背景程序。
