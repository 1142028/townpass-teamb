# 團隊工作流程

我們使用最簡單的 **GitHub Flow**：

```
main（永遠可以執行）
 ├── feat/xxx  →  PR  →  隊長檢查  →  合併回 main
 └── fix/yyy   →  PR  →  隊長檢查  →  合併回 main
```

`main` 已設定保護，**無法直接 push**，一定要透過 Pull Request（PR）合併。

---

## 每次開始一個新任務

```bash
# 1. 回到 main，抓最新版本（每次開工前都要做）
git switch main
git pull

# 2. 開一個新分支（名稱見下方規則）
git switch -c feat/bus-api

# 3. 寫程式……

# 4. 存檔進度（可以做很多次）
git add .
git commit -m "feat: 新增公車到站查詢 API"

# 5. 推上 GitHub
git push -u origin feat/bus-api
```

推上去後，到 GitHub repo 頁面會看到黃色提示 **「Compare & pull request」**，點下去發 PR，依範本填寫，再到 Discord 通知隊長。

### 合併之後

```bash
git switch main
git pull
git branch -d feat/bus-api   # 刪掉已合併的本地分支
```

---

## 命名規則

### 分支名稱

| 前綴 | 用途 | 範例 |
|---|---|---|
| `feat/` | 新功能 | `feat/login-page` |
| `fix/` | 修 bug | `fix/api-timeout` |
| `docs/` | 只改文件 | `docs/update-api-spec` |

用英文小寫，單字之間用 `-` 連接。

### Commit 訊息

格式：`類型: 做了什麼`，中文或英文都可以。

```
feat: 新增首頁地圖元件
fix: 修正日期格式錯誤
docs: 更新 API 規格中的錯誤碼
```

---

## 重要習慣

1. **分支要小、要常合併**：一個分支只做一件事，最多半天就要發 PR。分支開越久，衝突越大。
2. **開工前先 `git pull`**：確保你是在最新版本上改。
3. **發 PR 前自己先跑一次**：確認程式能執行，再請別人看。
4. **AI 寫的程式碼，你要看得懂才能 commit**：至少要能說明這段程式在做什麼、放在哪裡、輸入輸出是什麼。
5. **改到 `docs/api.md`（資料格式）一定要在 Discord 說**：前後端都會受影響。

---

## 遇到衝突（conflict）怎麼辦？

衝突的意思是：你和別人改了同一個檔案的同一個地方，Git 不知道要留哪一個。

```bash
git switch main
git pull
git switch 你的分支
git merge main
```

Git 會在衝突的檔案中標出：

```
<<<<<<< HEAD
你寫的版本
=======
別人寫的版本
>>>>>>> main
```

處理方式：

1. 和寫另一個版本的人確認要留哪個（**不要直接刪掉別人的程式碼**）
2. 把檔案改成正確的樣子，並刪掉 `<<<<<<<`、`=======`、`>>>>>>>` 這三行標記
3. 存檔後：
   ```bash
   git add .
   git commit -m "fix: 解決與 main 的衝突"
   git push
   ```

處理不了就**先停下來**，到 Discord 找隊長，不要用 `git push --force`。

---

## Git 演練（賽前每個人都要做一次）

目的：在比賽前把整套流程走過一遍，比賽當天才不會卡在 Git。

1. `git clone` 這個 repo
2. 開分支：`git switch -c docs/add-<你的英文名>`
3. 在 [`docs/team.md`](docs/team.md) 的表格中**填上自己那一列**
4. commit、push、發 PR，並在 Discord 通知
5. 隊長合併後，回到 main 並 `git pull`，確認看得到所有人的名字

**衝突練習**（隊長安排兩人一組）：兩人同時修改 `docs/team.md` 的「衝突練習區」同一行，先合併的人不會有事，後合併的人照上面的「遇到衝突怎麼辦」解決。
