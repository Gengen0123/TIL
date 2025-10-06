dockerの環境構築手順

VSCodeのターミナルを起動、wslからコマンドを入力していく
mkdirでdocker-compose.ymlを入れるためのフォルダを作成する
laravelを使う場合は、同じ階層にさらにもう一つフォルダを作っておく
→mkdir　〇〇　××　みたいな感じ



なぜ1つのフォルダにまとめないの？

Dockerの基本思想は「1つのコンテナ = 1つの役割」
だから設定もそれぞれ独立して持たせる

php コンテナ → コード実行専用
nginx コンテナ → リクエスト受付・レスポンス返却専用

これにより：

再利用しやすい（他プロジェクトにも転用可）
不具合を切り分けやすい（nginxだけ再起動できる）
保守しやすい（設定変更が役割ごとに完結）





docker-compose.ymlを作っていく
wslで

touch docker-compose.yml
touch php/Dockerfile
touch nginx/nginx.conf

docker-laravel/
├─ docker-compose.yml     ← 全体構成
├─ php/
│   └─ Dockerfile         ← PHPの設定
└─ nginx/
    └─ nginx.conf         ← nginxの設定
    

上記3つのファイルにそれぞれコードを書き込んでいく
内容の詳細はこれから勉強します汗



ビルド、起動コマンド
docker compose build
docker compose up -d

再起動したいとき（ポート番号変えた時とか）は、
docker compose down
docker compose up -d




Laravelをプロジェクト直下に導入

docker compose exec app bash -lc "composer create-project laravel/laravel:^11.0 ."
docker compose exec app
→ app という名前のコンテナ（＝PHPが動いているコンテナ）でコマンドを実行する。

bash -lc "..."
→ bashシェルを起動して、その中で "..." の中のコマンドを実行する。
-l はログインシェルとして起動、-c はコマンド実行を意味する。

composer create-project laravel/laravel:^11.0 .
→ Composer（PHPのパッケージ管理ツール）を使って、
Laravelの最新11系を 現在のディレクトリ（.） にインストールする。


docker compose exec app php artisan key:generate
artisan はLaravelに付属しているコマンドラインツール。

key:generate は「アプリケーションキー」を生成するコマンド。

Laravelはセッションや暗号化などに「アプリケーションキー（APP_KEY）」を使う。
これを .env ファイルに自動で書き込むのがこのコマンド。




