# 今日知ったコマンド
---

## HTML

header
ヘッダーを作る

ul
順序のないリスト　箇条書きのようなリストを作成する　ヘッダー内の項目を列記するのに使用

li
ul内の各項目を作る


section
ページの大枠　お問い合わせとか、タイトルページとかの区画を決める

div
情報の塊を表現する

img src alt
写真を挿入する　ディレクトリを書いて選択　もしもうまく表示できなかった時はaltに書いたテキストが反映される

form action method
フォームに入力された値をactionで示された場所に送る




### おまけ
rowとcolの使い方
│ <div class="row">             │ ← 横並びの「行」
│   <div class="col">A</div>    │ ← 縦の「列」
│   <div class="col">B</div>    │
│   <div class="col">C</div>    │
│ </div>   
 
 rowは行、colはその中の列。

---

## CSS
z-index
レイヤーの順番を決める　大きい数字ほど手前に表示される


position: absolute / relative
場所を決める　absoluteは絶対的、relativeは相対的に決定する
この要素の中に場所を決めたい子がいた時は、参照元である親として場所を決める必要がある。
その際はposition: relativeを入れておけばおｋ

display: flex
親要素に適用する　子要素を柔軟に配置していいと宣言するときに使う　横に並んでいく

justify-content: space-between;
左右に綺麗に配置　ヘッダーで、右にロゴ、左にメニューみたいな使い方する

flex-wrap: wrap;
折り返しを許可　横に並びきらなければ次の行行っていいよってやつ

align-items: center;
縦方向の整列　上下中央揃え

background-position / size
positionで決めた所定のエリアに対して、どの辺に配置するか、大きさにするか決める
背景に使用したい画像に対して使うなら、center coverにしておく


opacity
透明度　適当なタグを使って画面全体に色を付けて、透かしたいときとかに使う

transition-duration: .2s;
変化するまでの時間　hoverと併せて、カーソルが乗った時に対象がゆっくり変化してほしい時に使う


