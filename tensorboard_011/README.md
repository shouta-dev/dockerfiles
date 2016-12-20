概要
===

* Tensorflowでトレーニングする環境を作るDockerfileです

前提
===

* 事前にホストの/share/train/の下にcheckpointファイルが配置されている想定です
* 別の場所にcheckpointがある場合はsymlinkで/share/train経由で参照できるようにしてください

```
$ ln -s /share/train-1 /share/train
```

使い方
===

* 下記コマンドでイメージをビルドします

```
nvidia-docker build -t s-onishi/tensorboard:v0_11 .
```

* 下記コマンドでコンテナを生成・起動します

```
nvidia-docker run -d --name tensorboard_011_20161215 -p 6006:6006 -v /share:/share s-onishi/tensorboard:v0_11
```
