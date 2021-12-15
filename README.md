# docker
docker勉強用です。

## コマンド集

```bash
$ docker login   // ログイン
$ docker pull <image>   // イメージをプルする
$ docker run it <image> bash   // イメージからコンテナを起動してシェルを実行する
$ exit   // プロセスを終了してコンテナから抜ける
$ docker ps -a   // すべてのコンテナを表示する
$ docker images   // イメージを表示する
$ docker restart   // Exited 状態のコンテナを再起動する
$ docker exec -it <container> bash   // コンテナに対してコマンドを実行する
$ docker commit <container> <image>   // コンテナから新しいイメージを作成する
$ docker docker tag <source> <target>   // イメージの名前を変更する
$ docker push <image>   // Docker Hub にイメージをプッシュする
$ docker rmi <image>   // イメージを削除する
```
