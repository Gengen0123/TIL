新しく作ったWebページ（新規フォルダ）のファイルをGitHubに挙げるまでの流れ（Windows想定）
================================================================================

前提：プロジェクトの例
C:\Users\Kakugen Shota\web\carrer
C:\Users\Kakugen Shota\web\itcom

※ それぞれ独立プロジェクトの場合は、各フォルダごとに以下を実行します。

-------------------------------------------------------------------------------
【A】最初の一回だけ必要な初期設定（まだGit管理していない新規フォルダ）
-------------------------------------------------------------------------------

① 対象フォルダへ移動
例：
cd "C:\Users\Kakugen Shota\web\carrer"

② Gitの初期化（フォルダをGit管理化）
git init

③ （任意だが推奨）ブランチ名をmainに統一
git branch -M main

④ （任意だが推奨）.gitignoreを作成（不要ファイルの除外）
例：.gitignore（プロジェクト直下に作成）
--------------------------------------
# OS
.DS_Store
Thumbs.db

# Editor
.vscode/
.idea/

# Build / cache
node_modules/
dist/
--------------------------------------

⑤ GitHubで空のリポジトリを作成（README等は作らない方が楽）
例： https://github.com/<ユーザー名>/carrer.git

⑥ リモート（origin）を登録
git remote add origin https://github.com/<ユーザー名>/carrer.git

⑦ 状態を確認
git status

⑧ 変更をステージ（コミット対象に選択）
git add .
（特定ファイルだけなら）git add index.html など

⑨ コミット（ローカル履歴に記録）
git commit -m "first commit: carrer site"

⑩ 初回プッシュ（GitHubへ反映）
git push -u origin main
※ -u を付けると次回以降は「git push」だけでOK。


-------------------------------------------------------------------------------
【B】2回目以降（ファイルを編集・追加したときの通常フロー）
-------------------------------------------------------------------------------

① 対象フォルダへ移動
cd "C:\Users\Kakugen Shota\web\carrer"

② 状態を確認
git status

③ 変更をステージ
git add .

④ コミット
git commit -m "変更内容の要約（例：Add hero section / Fix header link）"

⑤ プッシュ
git push


-------------------------------------------------------------------------------
【C】よくある分岐・つまずき対処
-------------------------------------------------------------------------------

■ リモートoriginが未設定
fatal: 'origin' does not appear to be a git repository
→ リモート設定を追加（またはURL変更）
git remote -v
git remote add origin https://github.com/<ユーザー名>/<repo>.git
（変更したい時）git remote set-url origin https://github.com/<ユーザー名>/<repo>.git

■ ブランチ名の不一致（mainでpushできない）
error: src refspec main does not match any
→ ローカルにmainがないので作る/変更する
git branch -M main
git push -u origin main

■ GitHub側に先にREADMEを作ってしまった（リモートに履歴がある）
→ 初回にpull --rebase で整合
git pull --rebase origin main
git push -u origin main

■ コミットメッセージ（-m）を直したい（push前）
git commit --amend -m "修正後のメッセージ"

■ コミットメッセージを直したい（push後／自分のブランチ）
※ 履歴を書き換えるので練習用や個人ブランチでのみ推奨
git commit --amend -m "修正後のメッセージ"
git push --force-with-lease

■ いまいるブランチを知りたい
git branch

■ 直近のコミット履歴を見たい（1行表示）
git log --oneline --graph --decorate --all

-------------------------------------------------------------------------------
【D】実運用のコツ
-------------------------------------------------------------------------------
- 1プロジェクト=1リポジトリ（carrer と itcom は別々のリポジトリ）
- コミットメッセージは「要約: 詳細（任意）」形式だと読みやすい
  例：
  feat: add footer navigation
  fix: correct header logo link
  style: adjust spacing on hero section
- README.md を用意すると、後から見たときに把握しやすい（プロジェクト概要、使った技術、フォルダ構成など）
