#### 以 Etag 支援快取

於所有回應加入 `ETag` 標頭，辨別特定版本的回傳資源。這讓使用者得以將資源存入快取，並於需求的 `If-None-Match` 標頭加入原 `ETag` 值判別快取是否須更新。
