
# Docker

[TOC]

## 基本事項

* [Docker & Docker-Composeの基本的な使い方](https://qiita.com/koka/items/3d3d4ee5680f92a0ad89)
* [DockerHubのイメージのタグ一覧をコマンドで取得する](www.mazn.net/blog/2015/12/26/1548.html)



## インストール

* [CentOS7にDockerをインストールする](https://qiita.com/inakadegaebal/items/be9fecce813cebec5986)
* [Install Docker Compose](https://docs.docker.com/compose/install/)
* [CentOS7.3にDocker Composeまでインストール](https://qiita.com/sawadashota/items/2bed41598d825d488701)
* Ref.
  * [Docker Compose](https://github.com/docker/compose)


​


## CentOS7にDockerをインストール

* 以下のコマンドで　docker関連がインストールされているか確認する。インストールされていれば削除する。

  ```
  $ yum list installed | grep docker
  ```

* 必要なパッケージをインストール

  ```
  $ sudo yum install -y yum-utils device-mapper-persistent-data lvm2
  
  ```

* レポジトリ追加

  ```
  $ sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
  ```

* yum のパッケージインデックスを更新(DockerのINSTALLやUPGRADEの前に一回実行することが推奨されている)

  ```
  $ sudo yum makecache fast
  ```

* インストール可能バージョンを調べる。

  ```
  $ yum list docker-ce.x86_64 --showduplicates | sort -r
  ```

* インストールする

  ```
  バージョン指定
  $ sudo yum install docker-ce-17.06.0.ce-1.el7.centos
  最新バージョン
  $ sudo yum install docker-ce
  
  ```

* 起動

  ```
  $ sudo systemctl start docker
  ```

* 確認

  ```
  $ sudo docker run hello-world
  ```

* いちいちsudoを書かなくてもようにする(セキュリティー面を考慮してやるかやらないかの方針決めが必要)

  ```
  dockerグループはすでにあるはずだけど念の為
  $ sudo groupadd docker
  現在のユーザーをdockerグループに入れる
  $ sudo usermod -aG docker $USER
  ```

* 確認

  ```
  再ログイン後(仮想環境であれば、再起動が必要な場合もある)
  $ docker run hello-world
  ```

* OS起動後にDockerを自動起動にする

  ```
  $ sudo systemctl enable docker
  ```


## CentOS7に docker composeをインストール

* 以下のコマンドを実行

  ```
  sudo curl -L https://github.com/docker/compose/releases/download/1.19.0/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose
  ```

* Apply executable permissions to the binary

  ```
  sudo chmod +x /usr/local/bin/docker-compose
  ```

* Test the installation

  ```
  $ docker-compose --version
  docker-compose version 1.19.0, build 1719ceb
  ```


## CentOS6

* [CentOS6にdockerを構築する手順](https://qiita.com/is_mgmt_dept/items/f4a7c64d72c2cba440c2)

##  /var/lib/docker

* [Dockerの/var/lib/dockerを移動する](https://qiita.com/masato/items/e967e531e75101796c30)

## 運用面

* [Dockerの本番運用](https://postd.cc/docker-in-production-an-update/)
* [Dockerの期待と現実～Docker都市伝説はなぜ生まれるのか～](https://www.slideshare.net/zembutsu/docker-expectations-and-reality)
* [Systemdとdocker-composeでカジュアルにdockerを運用する](https://qiita.com/kanga/items/5f956bc47068c9774522)

## 再起動の自動処理

* [ホストを再起動した時などにDockerコンテナを自動的に再起動できるようにする](https://unskilled.site/ホストを再起動した時などにdockerコンテナを自動的/) 
* [Docker, 起動中のコンテナに --restart=always オプションを後から適用する](https://qiita.com/suzuki86/items/3b6d5b3a6e83a82c4f28) 

## バックアップ

* [Dockerのシステム移行手順（バックアップおよび復元方法）](https://qiita.com/mikoski01/items/7d71ef7d167a6b78219a)
* [Dockerのデータボリュームをバックアップ・リストア](https://www.lancard.com/blog/2016/09/06/dockerのデータボリュームをバックアップ・リストア/)

## 永続ストレージ

* [Dockerで永続ストレージを実現する4つの方法](http://techtarget.itmedia.co.jp/tt/news/1612/16/news01.html)
* [Docker でデータのポータビリティをあげ永続化しよう](https://qiita.com/mopemope/items/b05ff7f603a5ad74bf55)

## ネットワーク、Docker container間の連携

* [Dockerのネットワークの基礎](https://deeeet.com/writing/2014/05/11/docker-network/)
* [Assign static IP to Docker container](https://stackoverflow.com/questions/27937185/assign-static-ip-to-docker-container)
* [Docker container間の連携について](https://qiita.com/taka4sato/items/b1bf33941a1ec8b69fd2)
* [docker-compose で別の docker-compose.yml で作ったコンテナとリンクする (ネットワークを繋げる)](https://qiita.com/reneice/items/20e981062b093264cd0a)
* [dockerコンテナにファイルを転送する](https://qiita.com/bunty/items/04c3bdd93ac3520c53eb)

## docker-compose

* [docker-compose コマンドまとめ](https://qiita.com/aild_arch_bfmv/items/d47caf37b79e855af95f)

## ARGの取り扱い

* [Dockerfile ARG入門](https://qiita.com/nacika_ins/items/cf8ceb20711bd077f770)
* [Docker コンテナの動作に必要な設定を起動時に渡す](http://blog.amedama.jp/entry/2018/01/30/230221)

## サービス化

* [docker-compose で作ったサービス用の /etc/init.d スクリプト](https://qiita.com/megmogmog1965/items/acbe83fd594e07fe7395#systemd-centos7)
* [dockerのコンテナの自動起動をsystemdにて行う際の注意点について](www.memotansu.jp/2016/10/docker/563/)

## MySQL

* [dockerで、いい感じでMySQL環境を作る](https://qiita.com/akinoriikeda/items/db4291dc4db3aa7c4b55 )


## Nginx

* [DockerfileでNginxの起動とログのローテーションまで](https://qiita.com/k7tak29/items/993ba3af8b0ac62a02c5)
* [Docker 版 Nginx で timezone 指定にハマらない簡単な方法](http://munepom.hatenablog.com/entry/2017/03/13/225431)


## 日本時間設定など

* [【Docker】開発時に使ってるコンテナのDockerfileまわり](https://qiita.com/xecus/items/02c65379c5b2c541d3bc)



## トラブル対応

* [dockerの出すログファイルでディスクが100%になった](https://gomiba.co.in/blog/archives/1790)
* [肥大化してしまったdockerコンテナのログを消し去る方法](https://qiita.com/Hi-king/items/fe5ac34170c7cdf12cc0)



## Link

* [コンテナに入りたい？それ docker exec でできるよ](https://qiita.com/yosisa/items/a5670e4da3ff22e9411a)
* [Dockerで、既存のイメージを少しだけ変えて再コミットする](https://qiita.com/udzura/items/484073046e2437c83a8c)
* [Docker for Windows をインストールしてdocker-composeを動かすまで(Windows10)](https://qiita.com/chr/items/184b6af37d105bdad145)
* [Docker ノウハウ集](https://qiita.com/hana_shin/items/392bd01be6aff9fc1dd4)
* [Dockerfileについて](https://qiita.com/tanan/items/e79a5dc1b54ca830ac21)
* [docker-composeを使うと複数コンテナの管理が便利に](https://qiita.com/y_hokkey/items/d51e69c6ff4015e85fce)
* [Dockerコマンドメモ](https://qiita.com/curseoff/items/a9e64ad01d673abb6866)
* [Dockerイメージとコンテナの削除方法](https://qiita.com/tifa2chan/items/e9aa408244687a63a0ae)
* [docker, コンテナを一括削除](https://qiita.com/ozhaan/items/9e2090da22ffd6c7ad2a)
* [Docker・コンテナの確認と接続(ps, attach, execコマンド)](http://www.ajisaba.net/develop/docker/docker_attach.html)
* [Docker Compose - docker-compose.yml リファレンス](https://qiita.com/zembutsu/items/9e9d80e05e36e882caaa)
* [Compose ファイル・リファレンス](http://docs.docker.jp/compose/compose-file.html)
* [docker-compose.ymlの命令を理解して、よりDockerを有効活用したい！](http://aspec7.hateblo.jp/entry/2015/11/08/134228)
* [docker, CMD とENTRYPOINT の違いを試してみた](https://qiita.com/hihihiroro/items/d7ceaadc9340a4dbeb8f)
* [dockerfileでDockerイメージを作成する](https://qiita.com/umchifre/items/0447c58173b051510f78)
* [Docker volumeの削除](https://qiita.com/Ikumi/items/b319a12d7e2c9f7b904d)
* [DockerのVolumeのアクセス権限の問題について](https://qiita.com/mrk_21/items/137b0c39e09c3ed6c95a)
* [Docker: マウントしたVolumeにApacheが書き込めないとき](https://qiita.com/suin/items/3a0361102af83d0b69aa)
* [Dockerのパーミッションエラーを調べる](https://qiita.com/reflet/items/3516400c37c4f5b0cd6d)
* [dockerのデータボリュームとそのバックアップ方法](https://qiita.com/74th/items/41393f506d223850f2c3)
* [Docker+Convoyでバックアップ](https://qiita.com/kuri_hei/items/50c50b5430426f04cc25)
* [Docker コンテナ内でのデータ管理](https://qiita.com/t-yotsu/items/82572b1749964671fb2f)
  * バックアップ＆リストアの方法
* [CentOS 7のDockerコンテナ内でsystemdを使ってサービスを起動する](https://qiita.com/yunano/items/9637ee21a71eba197345)
* [Docker+systemd+複数サービス起動](https://qiita.com/kuri_hei/items/bccd699af8c77a9463c4)
* [Docker Compose で起動するコンテナ名を変更する](https://qiita.com/ymm1x/items/56961f8e2ffb48b8dbe3)
* [docker run --restart=alwaysがどれくらいrestartしてくれるか調べた](https://qiita.com/manabuishiirb/items/f7edf11572f9256018b2)
* [Docker の基本学習 ~ コンテナ間のリンク](https://qiita.com/Arturias/items/75828479c1f9eb8d43fa)
* [docker-compose.ymlの中で環境変数を展開する](https://qiita.com/friedaji/items/c1894821a2c49395cfd7)
* [docker-composeで環境変数を使う](http://blog.brains-tech.co.jp/entry/2017/12/01/170600)
* [Docker for Windowsで快適な環境を得るまでの そこそこ長い闘い](https://qiita.com/YukiMiyatake/items/73c7d6c4f2c9739ebe60)
* [Dockerコンテナの分割は開発時はプロセス毎にしたほうがいい](https://qiita.com/kotamat/items/1f3f12a1c78612065e47)
* [今さら人に聞けない Kubernetes とは？](https://qiita.com/MahoTakara/items/85096f8b2632c802ab22)
* [突然Dockerコンテナ内からネットワークに繋がらなくなったらiptablesを疑ってみよう](https://blue1st-tech.hateblo.jp/entry/2017/01/29/232733)


