# City Spiral Releases

這是 City Spiral 官方的 Windows 公開測試版下載頁。本 repository 只保存發佈說明；遊戲執行檔請由 GitHub Releases 下載。

## 下載

請前往 [Latest Release](https://github.com/BianIO/CitySpiral-Releases/releases/latest)：

- 一般使用者建議下載 `CitySpiralSetup.exe`。
- 免安裝版本請下載 `CitySpiral-win-x64-portable.zip`，完整解壓縮後執行資料夾內的 `CitySpiral.exe`。
- `CitySpiral.exe` 不能脫離 portable 資料夾單獨使用，因為它需要同資料夾內的 `resources` 等檔案。
- 可使用 Release 內的 `SHA256SUMS.txt` 驗證下載檔案。

## 系統需求

- Windows 10／11 64-bit
- 建立或加入跨網路房間時需要網際網路連線

## 測試版提醒

City Spiral 目前仍是 playtest build。房主工具使用 TryCloudflare 臨時 Tunnel，每次重新啟動時邀請網址可能改變；房主關閉程式後，房間與對局不會保留。

目前程式尚未簽署程式碼憑證，Windows SmartScreen 可能顯示警告。請只從本 repository 的 Releases 下載，並比對 SHA-256。