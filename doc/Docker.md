
# Docker


* [コンテナに入りたい？それ docker exec でできるよ](https://qiita.com/yosisa/items/a5670e4da3ff22e9411a)
* [Dockerで、既存のイメージを少しだけ変えて再コミットする](https://qiita.com/udzura/items/484073046e2437c83a8c)
* [Docker for Windows をインストールしてdocker-composeを動かすまで(Windows10)](https://qiita.com/chr/items/184b6af37d105bdad145)
* [Docker ノウハウ集](https://qiita.com/hana_shin/items/392bd01be6aff9fc1dd4)




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


## 永続ストレージ

* [Dockerで永続ストレージを実現する4つの方法](http://techtarget.itmedia.co.jp/tt/news/1612/16/news01.html)
* [Docker でデータのポータビリティをあげ永続化しよう](https://qiita.com/mopemope/items/b05ff7f603a5ad74bf55)

## Link

* [Dockerfileについて](https://qiita.com/tanan/items/e79a5dc1b54ca830ac21)
* [docker-composeを使うと複数コンテナの管理が便利に](https://qiita.com/y_hokkey/items/d51e69c6ff4015e85fce)
* [Dockerコマンドメモ](https://qiita.com/curseoff/items/a9e64ad01d673abb6866)
* [Dockerイメージとコンテナの削除方法](https://qiita.com/tifa2chan/items/e9aa408244687a63a0ae)
* [docker, コンテナを一括削除](https://qiita.com/ozhaan/items/9e2090da22ffd6c7ad2a)
* [Docker・コンテナの確認と接続(ps, attach, execコマンド)](http://www.ajisaba.net/develop/docker/docker_attach.html)
* [Docker Compose - docker-compose.yml リファレンス](https://qiita.com/zembutsu/items/9e9d80e05e36e882caaa)
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


