概要
===

* Tensorflowでトレーニングする環境を作るDockerfileです

前提
===

* ホストの/share/の下にcheckpointファイルを出力する想定です


使い方
===

* 下記コマンドでイメージをビルドします

```
nvidia-docker build -t s-onishi/tensorflow:v1_0 .
```

* 下記コマンドでコンテナを生成・起動します

```
nvidia-docker run -it --name tensorflow_1_0_20161215 -v /share:/share s-onishi/tensorflow:v1_0 /bin/bash
```

* exitで出た後は下記てアクセスできます
  * dockerの中でscreenは使えないので、ホスト側のscreenから下記で接続します
```
docker start tensorflow_1_0_20161215
docker exec -it tensorflow_1_0_20161215 /bin/bash
```

バージョン類
===

* Dockerfileをみてください

その他
===

* /root/models/inception にinception-v3が置かれています
