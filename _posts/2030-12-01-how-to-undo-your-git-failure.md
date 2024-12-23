---
title: Git 新手完全指南：讓你的版本控制更簡單?
tags: [Developer Guide, Git]
style: fill
color: info
description: Using `git reflog` and `git reset` to save your code.
external_url:
---

### Git 新手完全指南：讓你的版本控制更簡單

Git 是一個功能強大的版本控制系統，能有效地幫助你管理專案的版本，無論是個人專案還是多人協作，都可以讓工作流程更加流暢。以下將簡單介紹 Git 的用途及如何快速上手。

---

## 為什麼需要 Git？

1. **版本管理**  
   Git 讓你可以記錄每次的修改，並隨時回到之前的版本，避免手動命名多個檔案（例如 `v1`, `最終版`, `最終版修正版`）。
2. **多人協作**  
   在多人開發中，Git 能幫助協調團隊成員的修改，避免覆蓋他人更改。

3. **同步備份**  
   Git 支援與遠端倉庫（如 GitHub）的同步，確保專案不會因本地設備損壞而遺失。

---

## Git 的基本操作流程

以下為 Git 的基本指令及用法，幫助你快速掌握基礎操作。

### 1. 初始化專案

在專案資料夾中執行以下指令，開始使用 Git：

```bash
git init
```

> **說明**：這會在資料夾內建立一個隱藏的 `.git` 資料夾，用於追蹤版本資訊。

---

### 2. 檢查檔案狀態

確認哪些檔案已被修改或尚未加入 Git 的版本控制：

```bash
git status
```

- **紅色**：尚未加入版本控制的檔案。
- **綠色**：已準備提交的檔案。

---

### 3. 加入檔案到版本控制

告訴 Git 要追蹤哪些檔案：

```bash
git add <檔案名稱>  # 單個檔案
git add .           # 所有檔案
```

---

### 4. 提交變更

將檔案的變更保存為一個版本，並加上簡短的說明訊息：

```bash
git commit -m "修改了首頁樣式"
```

> **建議**：使用有意義的訊息，方便未來查看歷史版本。

---

### 5. 推送到遠端

將本地的專案同步到遠端倉庫（如 GitHub）。  
先連結遠端倉庫：

```bash
git remote add origin <遠端倉庫網址>
```

然後推送本地分支到遠端：

```bash
git push -u origin main
```

> **注意**：`main` 是分支名稱，有些倉庫可能預設為 `master`。

---

## 常見問題與解決方法

### 1. 回到過去的版本

使用以下指令切換到之前的版本：

```bash
git log --oneline            # 簡要查看歷史版本
git checkout <commit-hash>   # 切換到某個版本
```

若需覆蓋當前版本：

```bash
git reset --hard <commit-hash>
```

---

### 2. 解決合併衝突

多人修改同一檔案時可能發生衝突，Git 會標記出衝突區域。解決衝突的步驟如下：

1. 打開檔案，手動處理衝突標記。
2. 保存修改後，將檔案加入版本控制：

   ```bash
   git add <檔案名稱>
   ```

3. 提交解決後的版本：

   ```bash
   git commit -m "解決衝突"
   ```

---

### 3. 刪除或恢復檔案

- **刪除檔案**：

  ```bash
  git rm <檔案名稱>
  git commit -m "刪除了檔案"
  ```

- **恢復檔案**（從上一版本）：

  ```bash
  git checkout HEAD <檔案名稱>
  ```

---

## 提高效率的小技巧

1. **使用分支進行實驗**  
   在進行新功能或修復時，建立新分支，避免影響主分支：

   ```bash
   git branch <分支名稱>
   git checkout <分支名稱>
   ```

2. **清晰的命名與訊息**  
   提交訊息（commit message）應簡潔明瞭，描述修改內容，方便日後回顧。

3. **定期推送到遠端**  
   定期將本地修改同步到遠端，避免資料遺失。

---

## Git 工作流程總結

1. 初始化專案：`git init`
2. 修改檔案 -> 加入版本控制：`git add`
3. 提交變更：`git commit`
4. 推送到遠端：`git push`

---

## 結語

Git 是一個功能強大的工具，初學者可能覺得複雜，但掌握基本指令後，便能大幅提高開發效率。希望這篇指南能幫助你更快上手，讓版本控制變得簡單而有趣！
