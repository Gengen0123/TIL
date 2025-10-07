# dockerの使い方  
>dockerfileとdocker-compose.ymlの違い  

**Dockerfile**  
コンテナを作るための素材(=設計図)としてのdockerfile  
アプリコードと併せて一つのイメージ。一つのdockerfileに一つのコンテナ。

**docker-compose.yml**  
dockerfileを集めておいて、一気に色々な情報や設定を入力しながらコンテナを立ち上げられる便利な仕組みがdocker-compose.yml  
docker-compose.ymlをルートディレクトリ（最上位フォルダ）に置いておくことで、docker-compose.ymlの中で示す、各コンテナの材料置き場を指定するパスがシンプルで分かりやすくなる。  

>Laravel、Reactの概念  

laravelやreactは、作ったコンテナの中に設置するアプリなのでdockerfileには記載がない。  
コンテナを起動後に、backend/とfrontend/のそれぞれにコマンドによって入れていく。  

>wsl2をwindowsに入れる理由  

dockerがLinuxの持つ機能（カーネル機能：cgroups や namespace）を使用してコンテナを作っているから。


