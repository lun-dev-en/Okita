# Okita

## ブランチについて

- `main`
  - 完成版・安定版を置くブランチ
  - 基本的に直接編集しない

- `develop`
  - 各メンバーの機能を統合するブランチ
  - 動作確認を行い、問題なければ `main` にマージする
  - 基本的に直接編集しない

- `feature/機能名`
  - 各自が機能開発を行うブランチ
  - `develop` から作成する

---

# 作業を始めるとき

## 1. developブランチに移動

```bash
git switch develop
```

## 2. 最新のdevelopを取得

```bash
git pull origin develop
```

## 3. 新しい作業ブランチを作成

```bash
git switch -c feature/機能名
```

例：

```bash
git switch -c feature/login
```

---

# 開発中によく使うコマンド

## 現在のブランチを確認

```bash
git branch
```

`*` が付いているブランチが現在いるブランチ


## 変更内容を確認

```bash
git status
```

## 変更したファイルを追加

```bash
git add .
```

## コミット

```bash
git commit -m "変更内容"
```

---

# GitHubにPushする

## 初めてPushするとき

```bash
git push -u origin feature/機能名
```

## 2回目以降

```bash
git push

---

# Pull Request

機能が完成したら、GitHubでPull Requestを作成

```text
feature/機能名
      ↓
   develop
```

---


# 基本的な開発フロー

```text
developを最新にする
        ↓
featureブランチを作る
        ↓
開発する
        ↓
commit
        ↓
push
        ↓
Pull Request
        ↓
developへMerge
        ↓
全体の動作確認
        ↓
develop → main
```

---

# 作業開始時の3コマンド

```bash
git switch develop
git pull origin develop
git switch -c feature/機能名
```

---

# 作業終了時の基本コマンド

```bash
git add .
git commit -m "変更内容"
git push
```

初回Pushの場合のみ、ブランチきる

```bash
git push -u origin feature/機能名
```


---

# チーム開発ルール

- `main` には直接Pushしない
- `develop` にも基本的に直接Pushしない
- 新しい機能は `feature/機能名` ブランチで開発する
- 新しいブランチを作る前に `develop` を最新にする
- 1機能につき1ブランチを作成する
- 作業が完成したら `feature → develop` にPull Requestを出す
- Pull Requestを確認してからMergeする
- 全体が完成したら `develop → main` にPull Requestを出す

---



# 困ったときに使うコマンド

現在の状態を確認：

```bash
git status
```

ブランチを確認：

```bash
git branch
```

developに戻る：

```bash
git switch develop
```

最新のdevelopを取得：

```bash
git pull origin develop
```
