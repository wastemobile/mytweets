# 如何使用你的 Twitter 封存檔

使用你的 Twitter 封存資料最簡單的方式就是透過此檔案提供的庫存瀏覽介面。只要雙擊根目錄的 `index.html` 你就能夠在你的瀏覽器裡瀏覽你的全部推文歷史。

---

在 `data` 資料夾裡，你的 Twitter 庫存將呈現兩種格式：JSON 和 CSV 以月份和年份匯出。

* CSV 是一種通用格式可以匯入到許多資料工具、試算表應用程式或簡單以程式語言來使用。

## 開發者用 JSON

* JSON 匯出包含你推文的完整表示如同 Twitter API 1.1 版所回傳。參閱 https://dev.twitter.com/docs/api/1.1 取得更多資訊。
* JSON 匯出也運用在庫存瀏覽介面上 (index.html)。
* 要使用匯出在任何語言的通用 JSON 剖析器上，去掉每個檔案的第一行和最後一行。

要提供反饋、發問、或分享想法給其他的 Twitter 開發者，加入討論群組於 https://dev.twitter.com。