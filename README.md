# docker
docker勉強用です。

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
```
