# docker
Docker勉強用です。

## コマンド集

```bash
$ docker login   // ログイン
$ docker pull <image>   // イメージをプルする

$ docker create <image>   // イメージからコンテナを作成する
$ docker start <container>   // コンテナを起動する
$ docker run <container>   // create + start
$ docker run -it <image> bash   // イメージからコンテナを起動してシェルを実行する
$ docker run <image> <default command>   // コンテナ起動時に実行するコマンドを変更する
$ docker run --name <container name> <image>   // 名前付きでコンテナを作成・起動する
$ docker run -d <image>   // コンテナ起動後にプロセスをバックグラウンドに移動する
$ docker run --rm <image>   // コンテナ起動・コマンド実行後にコンテナを削除する

$ exit   // プロセスを終了してコンテナから抜ける
$ ctrl + p + q   // コンテナを起動したままホストに戻る

$ docker ps -a   // すべてのコンテナを表示する
$ docker images   // イメージを表示する
$ docker restart   // Exited 状態のコンテナを再起動する
$ docker exec -it <container> bash   // コンテナに対してコマンドを実行する

$ docker commit <container> <image>   // コンテナから新しいイメージを作成する
$ docker docker tag <source> <target>   // イメージの名前を変更する
$ docker push <image>   // Docker Hub にイメージをプッシュする

$ docker rmi <image>   // イメージを削除する
$ docker rm <container>   // コンテナを削除する
$ docker system prune   // 起動していないコンテナを全て削除する

$ docker build -t <name> <directory>   // ディレクトリ配下にあるDockerfileから名前付きイメージを作成する
```

## Dockerfileのルール

```Dockerfile
FROM <image>   // ベースとなる Docker image を指定する
RUN <command>   // 実行するコマンドを記述する
COPY <src> <dest>   // ホストにあるデータをコンテナ内にコピーする
ADD <src> <dest>   // ホストにある圧縮ファイルをコンテナ内にコピーして解凍する
CMD [ <command>, [param1, param2, ..., paramN] ]   // コンテナ起動時に実行するコマンドを指定する
```

**ポイント**
- Dockerfileは `RUN` ごとにイメージレイヤが作成されるので、なるべく `RUN` の数を減らすようにしたい。
- Linuxコマンドは `&&` で繋げられるのでうまく活用する。
- キャッシュを利用してビルドできるので、Dockerfileを作成する段階では `RUN` を細かく分けていき、処理が確定した段階でコマンドを繋げるようにすると効率的。 
- `RUN` はレイヤを作る。`CMD` はレイヤを作らない
- ホストにあるデータをコンテナに共有する際、基本的には `COPY` を使い、サイズが大きいデータを共有するときは、圧縮した後 `ADD` を使う。