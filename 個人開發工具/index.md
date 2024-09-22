# 個人開發工具


<!--more-->

本文分享我開發機上會安裝的工具

## 截圖

* [Snipaste](https://zh.snipaste.com/): 截圖好工具

## 版本控管

* [Git](https://git-scm.com/downloads): 檔案時光機等級，IT人員必備
* [TortoiseGit](https://tortoisegit.org/): 我都叫他小烏龜🐢，方便Git的GUI操作
* [TortoiseSVN](https://tortoisesvn.net/): 這也是小烏龜🐢，SVN偏伺服端安裝的，本機版控時不會考慮使用

## 資料庫

* [SSMS](https://learn.microsoft.com/zh-tw/sql/ssms/download-sql-server-management-studio-ssms?view=sql-server-ver16#download-ssms): 專門用於[SQL Server]^(MSSQL)的資料庫管理工具
* [DBeaver](https://dbeaver.io/): 支援多類型資料庫的管理工具

## IDE

* [Visual Studio](https://visualstudio.microsoft.com/zh-hant/downloads/): 地表最強開發IDE
* [Visual Studio Code](https://code.visualstudio.com/download): 俗稱VSCode
* [Cursor](https://cursor.sh/): 結合AI的VSCode，試用後覺得很方便，猶豫要不要課金

## 應用程式

* [NotePad++](https://notepad-plus-plus.org/downloads/)
* [LINQPad](https://www.linqpad.net/Download.aspx)
* [Notepad2e](https://github.com/ProgerXP/Notepad2e)
* [7Zip](https://www.7-zip.org/download.html): 免費的壓縮、解壓縮工具
* [wox](http://www.wox.one/): 快速啟動應用程式
* [everything](https://www.voidtools.com/zh-cn/downloads/): 電腦內所有檔案建立查詢索引，可以`wox`配合快速搜尋檔案
* [Postman](https://www.postman.com/downloads/): 測試API
* [WinMerge](https://winmerge.org/?lang=zh_tw): 文字內容差異比對，可比對純文字、檔案、目錄內所有檔案
* [WinSCP](https://winscp.net/eng/download.php): UI介面操作FTP

## 網站

* [Miro](https://miro.com/): 便條紙白板
* [excalidraw](https://excalidraw.com/): 手繪風格白板
* [draw.io](https://app.diagrams.net/): 畫流程圖的好工具
* [sequencediagram](https://sequencediagram.org/): 畫時序圖的好工具
* [dbdiagram](https://dbdiagram.io/d) 資料庫設計網站
* [regex101](https://regex101.com/) 驗證正則表達式

## 套件

### Visual Studio

* [GitHub Copilot](https://marketplace.visualstudio.com/items?itemName=GitHub.copilotvs)
AI文字提示工具，開發時會跳出提示文字，按下Tab就可以套用，但是缺點是要錢 大概一個月20鎂
* [codeium](https://codeium.com/)
免費仔用的AI文字提示工具，開發時會跳出提示文字，按下Tab就可以套用
* [Toggle Comment](https://marketplace.visualstudio.com/items?itemName=techhypno.ToggleComment)
註解快捷工具，按下`Ctrl+/`可以快速註解或取消註解。
* [SonarLint](https://marketplace.visualstudio.com/items?itemName=SonarSource.SonarLintforVisualStudio2022)
靜態程式碼分析工具，會在有問題的程式碼字串出現綠色波浪，提示快速修改或轉跳說明網站
* [ClaudiaIDE](https://marketplace.visualstudio.com/items?itemName=kbuchi.ClaudiaIDE)
更改美美的背景圖，可以每季把新老婆放上來一起Coding(?)
* [MatchMargin](https://marketplace.visualstudio.com/items?itemName=VisualStudioPlatformTeam.MatchMargin)
框選文字時候凸顯其他同樣文字位置
* [Spell Checker](https://marketplace.visualstudio.com/items?itemName=EWoodruff.VisualStudioSpellCheckerVS2022andLater)
英文拼字檢查工具，在[Visual Studio中檢查拼字是否正確](https://blog.poychang.net/visual-studio-spell-checker/)文章有教排除中文錯誤
* [GhostDoc](https://marketplace.visualstudio.com/items?itemName=sergeb.GhostDoc)
自動撰寫XML註解工具，在方法前使用`///`時候會辨識方法及變數套用到註解上

### VSCode

* [Codeium: AI Coding Autocomplete and Chat for Python, Javascript, Typescript, Java, Go, and mo](https://marketplace.visualstudio.com/items?itemName=Codeium.codeium)
免費的AI文字提示工具，開發時會跳出提示文字，按下Tab就可以套用
* [AWS Toolkit - Amazon Q, CodeWhisperer, and more](https://marketplace.visualstudio.com/items?itemName=AmazonWebServices.aws-toolkit-vscode)
免費的AI文字提示工具，開發時會跳出提示文字，按下Tab就可以套用
* [Encode Decode](https://marketplace.visualstudio.com/items?itemName=mitchdenny.ecdc) 
文字編碼轉換工具，像是符號轉換HTML編碼、加密之類的
預設是`Shift+Ctrl+P`輸入`Encode/Decode: Convert Selection`，我是設定`Ctrl+Ali+X`
* [Git Extension Pack](https://marketplace.visualstudio.com/items?itemName=doggy8088.git-extension-pack)
保哥精選Git工具大禮包
* [Markdown All in One](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one)
Markdown工具大禮包
* [Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker)
英文拼字確認
* [Error Lens](https://marketplace.visualstudio.com/items?itemName=usernamehw.errorlens)
錯誤訊息於該行後面呈現，但有時會有點亂會關掉

### Edge&Chrome

兩邊瀏覽器的擴充套記基本上互通就一起介紹

* [新同文堂](https://microsoftedge.microsoft.com/addons/detail/%E6%96%B0%E5%90%8C%E6%96%87%E5%A0%82/ijddgmclgedepadbikmfekambhhfjfnl)
簡繁轉換工具，可以設定自動簡轉繁&轉換字典
* [Chrome Remote Desktop](https://chromewebstore.google.com/detail/chrome-remote-desktop/inomeogfingihgjfjlpeplalcfajhgai)
神奇遠端程式，綁定Google帳號並輸入對應pin碼，只要有開機就算沒登入也可以直接連入遠端電腦(怕)
* [ChatGPT 萬能工具箱](https://chromewebstore.google.com/detail/chatgpt-%E8%90%AC%E8%83%BD%E5%B7%A5%E5%85%B7%E7%AE%B1/fmijcafgekkphdijpclfgnjhchmiokgp)
ChatGPT提供快捷按鈕、URL帶參數快速查詢，可拿來配合wow工具快速啟動
* [Adblock](https://microsoftedge.microsoft.com/addons/detail/adblock-plus-free-ad-bl/gmgoamodcdcjnbaobigkjelfplakmdhh)
擋廣告(有些整版廣告真的太惱人了，想支持的再開白名單)
* [Video Speed Controller](https://chrome.google.com/webstore/detail/nffaoalbilbmmfgbnbgppjihopabppdk)
影片加速快捷鍵工具
預設是`G`2倍速，我會改成 `G`1.5倍速 `H`2倍速
* [JSON Formatter](https://chromewebstore.google.com/detail/json-formatter/bcjindcccaagfpapjjmafapmmgkkhgoa)
網頁上的JSON以格式化方式呈現
* [Dark Reader](https://chromewebstore.google.com/detail/dark-reader/eimadpbcbfnmbkopoojfekhnkhdbieeh)
強制網頁深色模式保護眼睛
設定`Alt+C`加入`僅反轉列出清單`
* [Tampermonkey](https://microsoftedge.microsoft.com/addons/detail/%E7%AF%A1%E6%94%B9%E7%8C%B4/iikmkjmpaadaobahmlepeloendndfphd)
網頁腳本擴充程式
<!-- * [動畫瘋 Plus](https://chromewebstore.google.com/detail/%E5%8B%95%E7%95%AB%E7%98%8B-plus/ajgafpcbdchnokkfimcnmoemeldnefnl) -->
<!-- * [動畫瘋·Plus](https://chromewebstore.google.com/detail/%E5%8B%95%E7%95%AB%E7%98%8B%C2%B7plus/jkpkmeimgkhodlppajjgikfcodlilmpd) -->

### Tampermonkey

* [Fix &lt;code&gt; bug for Edge translator](https://greasyfork.org/zh-CN/scripts/485715-fix-code-bug-for-edge-translator): 修正Edge翻譯後標籤文字位移問題
* [圖片瀏覽器](https://greasyfork.org/zh-CN/scripts/29205-%E5%9C%96%E7%89%87%E7%80%8F%E8%A6%BD%E5%99%A8)
<!-- * [優化動畫瘋彈幕](https://greasyfork.org/zh-TW/scripts/31468-%E5%84%AA%E5%8C%96%E5%8B%95%E7%95%AB%E7%98%8B%E5%BD%88%E5%B9%95) -->

### JS腳本

把JS腳本存入瀏覽器我的最愛的URL部分，點擊時就會觸發JS腳本

* 還我右鍵/複製功能
```js
javascript:(function() { function R(a){ona = "on"+a; if(window.addEventListener) window.addEventListener(a, function (e) { for(var n=e.originalTarget; n; n=n.parentNode) n[ona]=null; }, true); window[ona]=null; document[ona]=null; if(document.body) document.body[ona]=null; } R("contextmenu"); R("click"); R("mousedown"); R("mouseup"); R("selectstart");})()
```
* CSDN回復複製功能
```js
javascript:window.oncontextmenu=document.oncontextmenu=document.oncopy=null; [...document.querySelectorAll('body')].forEach(dom => dom.outerHTML = dom.outerHTML); [...document.querySelectorAll('body, body *')].forEach(dom => {['onselect', 'onselectstart', 'onselectend', 'ondragstart', 'ondragend', 'oncontextmenu', 'oncopy'].forEach(ev => dom.removeAttribute(ev)); dom.style['user-select']='auto';});
```
* [MSDN中英轉換](https://blog.miniasp.com/post/2008/03/07/One-click-transfer-MSDN-document-to-Traditional-Chinese-version-in-IE)
```js
javascript:(function(){var n;location.hostname.indexOf("google.com")>=0&&(n=location.search.indexOf("hl="),n==-1?location.search.indexOf("?")==0?void(location.search+="&hl=en-us"):void(location.search+="?hl=en-us"):location.search.substr(n+3,2)=="en"?void(location.search=location.search.replace(/hl=(\w\w)(-\w+)?/i,"hl=zh-Hant")):void(location.search=location.search.replace(/hl=(\w\w)(-\w+)?/i,"hl=en-us")));location.hostname.indexOf("microsoft.com")>=0&&(location.hostname.indexOf("support.microsoft.com")>=0?(n=location.pathname.search(/^\/kb\/\d+/i),n>=0&&(location.pathname.search(/^\/kb\/\d+\/?$/i)>=0?void(location.pathname=location.pathname.replace(/^(\/kb\/\d+)(\/)?(\w\w-\w\w)?$/i,"$1/en-us")):location.pathname.search(/^\/kb\/\d+\/(\w\w)(-\w\w)?/i)>=0?location.pathname.search(/^(\/kb\/\d+\/)en(-\w\w)?$/i)>=0?void(location.pathname=location.pathname.replace(/^(\/kb\/\d+\/)en(-\w\w)?$/i,"$1zh-tw")):void(location.pathname=location.pathname.replace(/^(\/kb\/\d+\/)\w\w(-\w\w)?$/i,"$1en-us")):void(location.pathname=location.pathname.replace(/^(\/kb\/\d+)(\/\w\w-\w\w)?$/i,"$1/en-us")))):location.pathname.search(/^\/(\w\w)(-\w\w)?\/?/i)>=0&&(location.pathname.search(/^\/(en)(-\w\w)?(\/)?(.*)/i)>=0?void(location.pathname=location.pathname.replace(/^\/(en)(-\w\w)?(\/)?(.*)/i,"/zh-tw$3$4")):void(location.pathname=location.pathname.replace(/^\/(\w\w)(-\w\w)?(\/)?(.*)/i,"/en-us$3$4"))))})()
```

## 字型

* [Fira](https://github.com/tonsky/FiraCode) 
是免費開源的等寬字體，並且將多字符組合成連貫的長字串，相當便於閱讀
![](https://github.com/tonsky/FiraCode/raw/master/extras/ligatures.png "Fira")

## 其他

* [華碩智慧輸入法](https://www.microsoft.com/store/productId/9MT4L79Z1G0N?ocid=pdpshare): 中英混合輸入，解決我不喜歡一直切換輸入法的問題(懶)。只是對中文打錯字容錯不高要習慣

