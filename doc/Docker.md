
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


## Link

* [docker-composeを使うと複数コンテナの管理が便利に](https://qiita.com/y_hokkey/items/d51e69c6ff4015e85fce)