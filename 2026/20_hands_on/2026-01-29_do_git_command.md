# TIL

## 学習時間
- 開始：08:00
- 終了：15:00
- 合計：420分
---

## 今日触れたこと
## ファイルの変更の取り消し
git checkout -- <ファイル名>
git checkout -- <ディレクトリ名>
全変更を取り消す
git checkout -- .
git checkout を入力した後にgit statusを実行すると、何も変更されていないと表示される。

## ステージした変更を取り消す　
git reset HEAD <ファイル名>
git reset HEAD <ディレクトリ名>
全変更を取り消す
git reset HEAD .
ステージから取り消すだけなので、ワークツリーのファイルはそのまま残っていることに注意。
今はgit restore --stagedを推奨

## 直前のコミットをやり直す
コミットした後にファイルを変更したくなった時に便利
リモートリポジトリにpushしたコミットをやり直すと、他の誰かがcloneしていた時に相違がでてしまう。
git commit --amend


## 設定しているリモートリポジトリの情報を表示する
git remote
対応するURLを表示
git remote -v
fetchとpushの2つでてくる　取得と反映の方向の違い


## リモートリポジトリの追加
リモートリポジトリは複数登録することができる
git remote add <リモート名>　<リモートURL>
例えばバックアップ用のリポジトリをgithub側で作ったら、そのURLをコピーして、git remote bak <コピーしたURL>とターミナルに貼ると設定が入る


## リモートから情報を取得する（フェッチ）
リモートリポジトリから、"ローカルリポジトリ"に情報を落とす操作
git fetch <ブランチ名>
git fetch origin
fetchしてローカルに落とせても、ワークツリーを切り替えないと触ることができない。
git branch -aで自分がいまどのワークツリーを見ているのかわかる
git checkout <移動したい先のブランチ名>を実行して、ようやくfetchしたファイルを触ることができる。
git merge <fetchしたブランチ>でワークツリーを今いるブランチに持ってくることができる。


## リモートから情報を取得してマージする(プル)
git fetchとgit mergeを一度に行なっている。
git pull <ブランチ名>
今いるブランチにマージしてしまうので、ミスしてしまうリスクがある
フェッチしてから、手動で指定のブランチに入れた方が安全。

## リモートの詳細情報を表示する
git remote show <リモート名>
git remote show origin


## リモートを変更・削除する
git remote rename <旧リモート名><新リモート名>
git remote rm <リモート名>


# ブランチとは
並行して複数の開発をするための機能がブランチ

## ブランチを新規追加する
git branch <ブランチ名>
git branch だけだと今いるブランチを表示
git branch -a 全てのブランチを表示


## ブランチの切り替え
git checkout <既存ブランチ名>
git checkout feature
git checkout -b <新ブランチ名>で新規作成と切り替えを同時に実施

## マージする
git merge <ブランチ名>
git merge <リモート名/ブランチ名>
git merge origin/main

---

## 参考にした教材・資料
- 教材名：
- URL：
---

## 今日の気づき・引っかかり
- 疲れた　gitわからん
---

## 今日のコンディション
- 気分：1
- 集中度：5
---

## 次にやるなら
- gitにトドメを刺す
