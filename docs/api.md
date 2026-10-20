# API 規格

> 這份文件是前後端串接的**唯一依據**。
> 前端照這裡的格式呼叫、後端照這裡的格式回傳。要改格式，先改這份文件並在 Discord 通知。

狀態：**待定義**（題目與功能確定後填寫）

---

## 共通規則

- Base URL（本機開發）：`http://localhost:<port>/api`（port 待確認）
- 資料格式：JSON，編碼 UTF-8
- 欄位命名：camelCase（例如 `stopName`、`arrivalTime`）
- 時間格式：ISO 8601，例如 `2026-11-01T14:30:00+08:00`

### 成功回應

```json
{
  "success": true,
  "data": { }
}
```

### 失敗回應

```json
{
  "success": false,
  "error": {
    "code": "NOT_FOUND",
    "message": "找不到這個站牌"
  }
}
```

| HTTP 狀態碼 | `error.code` | 意思 |
|---|---|---|
| 400 | `BAD_REQUEST` | 請求參數有誤 |
| 404 | `NOT_FOUND` | 查無資料 |
| 500 | `SERVER_ERROR` | 後端發生錯誤 |
| 502 | `UPSTREAM_ERROR` | 外部資料來源（開放資料 API）失敗 |

---

## API 清單

| 方法 | 路徑 | 用途 | 負責人 | 狀態 |
|---|---|---|---|---|
| GET | `/api/health` | 確認後端有在運作 | 待定 | 待實作 |

---

## 每支 API 的寫法範本

### `GET /api/health`

用途：確認後端有在運作，前端可以用它測試串接是否成功。

**請求參數**：無

**成功回應範例**：
```json
{
  "success": true,
  "data": {
    "status": "ok"
  }
}
```

---

<!--
新增 API 時複製以下範本：

### `方法 /api/路徑`

用途：

**請求參數**：
| 名稱 | 位置（query/path/body） | 型別 | 必填 | 說明 |
|---|---|---|---|---|

**成功回應範例**：
```json
```

**可能的錯誤**：
-->
