(程式下載)

https://github.com/max32002/ddddext/releases

下載說明:
* 目前有打包的「執行檔」，只有Windows 平台，其他作業系統需要使用原始碼來執行。當然Windows 平台也可以用原始碼執行 DDDDEXT.
* 如果你是要用「原始碼」執行 DDDDEXT, 在透過git clone 或在github按下載原始碼的 zip檔。

# Demo 
(示範影片)

* 網頁驗證碼自動輸入使用教學 https://youtu.be/wZy4BQ-z-S4
* 自動打勾+輸入欄位內容 https://youtu.be/98YikOWDLjo
* 在特定欄位自動打勾/移除勾勾 https://youtu.be/q17yvLtRato
* 用 ChatGPT 寫 jQuery 腳本 https://youtu.be/IRcC7cHs__I


# Feature
(主要功能)

* OCR驗證碼欄位，並輸入到指定輸入框。
* 填入內容到指定欄位內。
* 自動打勾。
* 注入 Javascript 到指定網頁。
* 設定 cookie 內容。
* 匯入其他創作者的設定檔。
* 啟動被隔離的瀏覽器。


# How to Use 
(使用教學)

* https://ddddext.max-everyday.com/usage/

# How to Execute Source Code 
(透過原始碼的執行方法)

透過原始碼執行 DDDDEXT 有2種執行方式：
1. Load unpacked extension (只可以使用部份功能)
2. 下指令執行主程式 (可以使用完整功能)

## Load unpacked extension

DDDDEXT 可以不安裝就在各個平台的 chrome 瀏覽器上執行，使用方式先從 gibhub 是先下載原始檔的zip 檔, 並解壓縮, 在 chrome 瀏覽器的網址輸入 chrome://extensions, 右邊啟用 Developer mode，就可以 Load unpacked extension. 擴充功能的目錄在 /ddddext/webdriver/ 目錄下.

說明：沒有透過 start.py (或 start.exe) 並按下「搶票」，而是透過「Load unpacked extension」只執行 chrome extension（擴充功能）的方式，需要指定「OCR Server URL」為網路上的其他伺服器，才有辦法進行 OCR。建議透過 start.py (或 start.exe) 並按下「搶票」來執行 ddddext.

透過 start.py (或 start.exe) 並按下「搶票」開出來的瀏覽，請不要去修改「OCR Server URL」的內容值，使用預設的 「http://127.0.0.1:16888/」 即可。

## 執行 start 主程式
透過原始碼執行ddddext教學影片：
https://youtu.be/HpVG91j0lbI

使用原始碼的解法，第一步是先取得原始碼後，開啟 Terminal(終端機) 視窗來下指令，應該是4行指令就可以了。

### Step 1: 取得source code:

<code>git clone https://github.com/max32002/ddddext.git</code>

### Step 2: 進入 clone 的資料夾: ddddext:

<code>cd ddddext </code>

### Step 3: 安裝第三方套件:

<code>python3 -m pip install -r requirement.txt</code>

說明：Windows 作業系統要用 python 指令，不是 python3, macOS / Linux 作業系統由於可能有多個 python 版本的環境，所以才是使用 python3 指令。

### Step 4: 執行設定介面主桯式:

<code>python3 start.py</code>

不管是 macOS 還是 Windows 預設都是沒有 git 這個指令，如果 Step 1 執行後,  沒有檔案被下載, 請先安裝 git 到你的作業系統。或是使用github 網頁裡的 Download 功能把python 腳本下載。

如果你選擇下載 github 上的 zip 檔, 在 Step 2 進入目錄的指令可能會遇到問題, 因為「直接解壓縮」後的目錄名稱並不是 ddddext 而是 ddddext-main, 你在進入的資料夾名稱, 需要調整為你實際解壓縮後的目錄名稱。

透過瀏覽器下載 github 上的 zip 檔, 在 Windows / macOS / Linux 平台, 預設的路徑在「下載」(~/Download) 的資料夾, 你在執行的 Terminal 視窗的路徑, 與你解壓縮的路徑可能不同, 直接執行上面的指令, 會無法進入到預期的資料夾內。

### Q: 取得source code後跑出來fatal: destination path 'ddddext' already exists and is not an empty directory.想問是什麼意思?

A: 執行 git clone 2次, 重覆取得 source code, 才會有這個問題, 如果 ddddext 目錄已經存在, 直接 cd ddddext 就可以了。
如果你想把已下載的刪除, 可以直把把 ddddext 目錄刪掉即可。
如果你想更新 source code, 可以重新下載, 或是先 cd ddddext 目錄後, 再執行 git pull , 可以更新 source code 為新的版本。

### Q: 取得source code後跑出來錯誤訊息：no module named requests

A: 請先確定你的python 執行環境下已安裝 nodriver 及相關的套件，請參考 requirement.txt 檔案內容。

### Q: 最新版 websockets 會造成 nodriver 打不開的情況

A: 我個人使用的 Windows 11 與 macOS 都沒遇到這個問題，請在手動移除 websockets，再指定修改 requirement.txt 將 <code>websockets</code> 修改為 <code>websockets==13.1</code> ，指定版本 13.1 即可以解決此問題。


# File Description
(檔案說明)
* nodriver_ddddext.py : 使用的元件是nodriver，用來把擴充功能放進瀏覽器。
* start.py : 編輯 settings.json 的 GUI 介面。提供圖片OCR功能給chrome擴充功能。

# Questions and Answers
### Q：無法在 Safari 瀏覽器運行
A：由於完整功能是透過 nodriver 在實作，所以只支援 chrome 瀏覽器。

nodirver 傳送門：https://github.com/ultrafunkamsterdam/nodriver


# Extension Privacy 

(DDDDEXT Plus擴充功能隱私權政策)

## 產品如何收集、使用及分享使用者資料

* 擴充取得會取得特定網頁內容, 並且自動輸入內容。

## 使用者資料的所有分享對象。

* 擴充功能沒有分享使用者資料。

## 擴充功能主要功能：

* 特定網頁驗證碼自動輸入功能, 需要同時開啟 DDDDEXT 主程式。
* 特定網頁自動填入內容值。
* 特定網頁內容打勾/取消打勾。
