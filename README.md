# townpass-teamb

城市通（TownPass）微服務黑客松｜Team B 共同作業 repo

> 專題主題：**數位落差**（細節待確認）
> 技術選型：**待確認**（前端／後端技術決定後會更新本檔）

---

## 第一次來？照這個順序做

1. 接受 GitHub 寄給你的 collaborator 邀請（信箱或 GitHub 通知裡）
2. 安裝 [Git](https://git-scm.com/downloads)，確認可以執行：`git --version`
3. 把 repo 下載到自己電腦：
   ```bash
   git clone https://github.com/1142028/townpass-teamb.git
   cd townpass-teamb
   ```
4. 讀完 [CONTRIBUTING.md](CONTRIBUTING.md)：團隊的工作流程，**每個人都要照這套做**
5. 完成 [Git 演練](CONTRIBUTING.md#git-演練賽前每個人都要做一次)：在 `docs/team.md` 寫上自己的名字並發 PR
6. 用 AI 工具寫程式前，先讓它讀 [CLAUDE.md](CLAUDE.md)

---

## 資料夾結構

```
townpass-teamb/
├── frontend/        # 前端程式（技術待定）
├── backend/         # 後端程式（技術待定）
├── docs/
│   ├── api.md       # API 規格：前後端串接的唯一依據
│   └── team.md      # 成員名單與分工
├── .github/         # PR 與 Issue 範本
├── CLAUDE.md        # 給 AI 工具的專案規則
├── CONTRIBUTING.md  # 團隊工作流程
└── .env.example     # 環境變數範例（真正的 .env 不上傳）
```

## 如何啟動專案

> ⚠️ 技術選型確定後補上。

### 後端
```bash
# 待補
```

### 前端
```bash
# 待補
```

## 任務在哪裡看？

- **Issues**：一個任務一張，寫清楚要做什麼、做完的標準
- **Projects 看板**：待做 → 進行中 → 待審 → 完成

## 三條規則

1. **不要直接改 `main`**：一律開分支、發 PR
2. **前後端的資料格式以 `docs/api.md` 為準**：要改格式，先改文件、在群組說一聲
3. **不要上傳密碼或 API key**：放在 `.env`，它已經被 `.gitignore` 排除
