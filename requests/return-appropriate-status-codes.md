#### 回傳適當的狀態碼

於每個回應回傳適當的狀態碼。成功地回應應該根據以下原則編碼：

* `200`: 同步需求執行成功，包含 `GET` 呼叫、`DELETE` 或 `PATCH` 呼叫、`PUT` 更新資源呼叫。
* `201`: 同步需求執行成功，包含 `POST` 呼叫，及 `PUT` 建立資源呼叫。
* `202`: 非同步需求已接受，包含 `POST`、`PUT`、`DELETE` 及 `PATCH`。
* `206`: `GET` 需求成功，但只回傳部分回應。詳見前一章[以 Range 分頁](foundations/divide-large-responses-across-requests-with-ranges.md)。

謹慎使用認證與授權的錯誤碼：

* `401 Unauthorized`: 需求失敗，因為使用者未經認證。
* `403 Forbidden`: 需求失敗，由於使用者未經授權即存取特定資源。

回傳適合的狀態碼以提供錯誤資訊：

* `422 Unprocessable Entity`: 需求可被理解，但含有無效的參數。
* `429 Too Many Requests`: 超過次數限制，等下再試。
* `500 Internal Server Error`: 伺服器端出錯，應檢查站台狀態或回報問題。

參考 [HTTP response code spec](https://tools.ietf.org/html/rfc7231#section-6) 規範來對應使用者錯誤及伺服器錯誤的案例。
