# TIL

## 学習時間
- 開始：20:45
- 終了：21:00
- 合計：15分
---

## 今日触れたこと
```
shotakakugen@MacBook-Air git_tutorial % git status
On branch main
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   index.html

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   index.html
```
- ステージに上げる前の状態。コミットしろ、ステージに上げろと言われている
---
```
shotakakugen@MacBook-Air git_tutorial % git add index.html
shotakakugen@MacBook-Air git_tutorial % git status
On branch main
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   index.html
```
- git add 指定のファイル名　で、指定のファイルをステージに上げたから当該指摘が無くなりコミットしろとだけ言われている。
---

```
shotakakugen@MacBook-Air git_tutorial % git commit 
[main d404d08] git statusコマンドを追記
 1 file changed, 3 insertions(+), 1 deletion(-)
shotakakugen@MacBook-Air git_tutorial % git status
On branch main
nothing to commit, working tree clean
```
- git commitでコミット。前回のコミットがうまくいかなかった場合表示されるエラーに対してはDeleteのDを押下。コメントを入力後はEscを押下後、:wq!(write,quit,強制実行)

---

## 参考にした教材・資料
- 教材名：
- URL：https://www.udemy.com/course/unscared_git/learn/lecture/6680162#overview

---

## 今日の気づき・引っかかり
- gitのステージとリポジトリの構造がよく理解できた。その便利さも少しづつわかってきた。
- どうして:wqだけではなく!も付けないとコメントを終了できないのかが気になる。読み取り専用ファイルになっているからとかで、その原因を知りたい思った。

---

## 今日のコンディション
- 気分：3
- 集中度：4

---

## 次にやるなら
- Gitの具体的な用途を学ぶ
