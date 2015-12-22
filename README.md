# Twitter 封存檔

每個人都能從 Twitter 管理頁申請自己的「歷史推文庫存檔」，申請後需要一點時間，你會得到一個壓縮檔案。這個壓縮檔案解開來非常有趣，不但有兩種格式的所有歷史推文，還包含一個極簡單、卻又很完整的靜態網站。

使用你的 Twitter 封存資料最簡單的方式就是透過此檔案提供的庫存瀏覽介面。只要雙擊根目錄的 `index.html` 你就能夠在你的瀏覽器裡瀏覽你的全部推文歷史。

你甚至可以將整個目錄擺到真正的網站上，就像是一個正常、一般的靜態網站，讓你很容易點擊進入某年某月的推文整理，甚至還有搜尋功能。因為搜尋對象真的就是你所有的推文，因此任何時間的推都可以搜尋得到，比 Twitter 網站還好用（怎麼會這樣？）。

## 更新

當然這個「歷史推文庫存」，就只到你申請下載的那個時間點而已，於是有大神寫了小程序，讓你能夠持續更新。

https://github.com/DeMarko/grailbird_updater

如果你懂 Ruby Gem 的安裝，或本機已經是個代碼開發環境，兩步驟就完了：

1. $ gem install grailbird_updater
2. grailbird_updater /path/to/twitter/archive

甚至還可以建立每天自動更新（cron job）：

```
@daily /bin/bash -l -c 'cd /home/username/grailbird && grailbird_updater /path/to/twitter/archive'
```

第一次執行時，程序會提供說明讓你前往 Twitter 開發人員後台，建立一個新的應用程式，並取得 Consumer key 與 secret，根據指示建立、複製貼到終端機就行了。

## GitHub Pages

我更懶了一點，於是將整個庫存目錄擺進 Git，再利用 GitHub 提供的靜態頁面服務，這就連自己的網站空間都不必了，所有歷史推文等同於通通擺進 Git 倉儲管理。

ps. 根目錄下有一個 `yourtwittername_keys.yaml` 檔案，要預先使用 `gitignore` 排除，否則就公開自己的 Consumer key & secret 了，請小心。

---

在 `data` 資料夾裡，你的 Twitter 庫存將呈現兩種格式：JSON 和 CSV 以月份和年份匯出。

* CSV 是一種通用格式可以匯入到許多資料工具、試算表應用程式或簡單以程式語言來使用。

## 開發者用 JSON

* JSON 匯出包含你推文的完整表示如同 Twitter API 1.1 版所回傳。參閱 https://dev.twitter.com/docs/api/1.1 取得更多資訊。
* JSON 匯出也運用在庫存瀏覽介面上 (index.html)。
* 要使用匯出在任何語言的通用 JSON 剖析器上，去掉每個檔案的第一行和最後一行。

要提供反饋、發問、或分享想法給其他的 Twitter 開發者，加入討論群組於 https://dev.twitter.com。