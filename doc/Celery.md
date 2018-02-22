
# Celery


* [Celery: Distributed Task Queue](http://www.celeryproject.org/)




## flower

* [【Celery】Celery タスクの追加とflower編](http://dnond.hatenablog.com/entry/2013/07/31/221130)

* 使い方

  * flower用サーバーを立ち上げる

    ```
    $ celery flower
    ```

  * flower用Web(以下URLにアクセスする

    ```
    http://localhost:5555
    ```

    ​

## セットアップ(CentOS7)

* Redis

  * Ref. :  [Redis を CentOS 7 に yum インストールする手順](https://weblabo.oscasierra.net/redis-centos7-install-yum/)

  * 手順

    * redisがインストールされているかどうか確認

      ```
      $ yum list installed | grep redis
      ```

    * Redis は CentOS 7 標準の公式 yum リポジトリでは提供されていない。エンタープライズ Linux 用の拡張パッケージ(EPEL)リポジトリで提供されているため、EPEL リポジトリを追加する。

      ```
      $ yum -y install epel-release
      ```

    * redisをインストールする

      ```
      $ yum -y install redis
      ```

    * 動作確認

      ```
      $ redis-server --version
      Redis server v=3.2.3 sha=00000000:0 malloc=jemalloc-3.6.0 bits=64 build=672aed6eb816ad6c 
      ```

    * 稼働させる

      ```
      $ systemctl enable redis
      $ systemctl start redis
      ```

## Docker

* [celery docker](https://hub.docker.com/r/_/celery/)

* [Configuring and Running Django + Celery in Docker Containers](https://blog.syncano.io/configuring-running-django-celery-docker-containers-pt-1/)

* [Docker: Use Celery in Django(Redis as Broker)](http://ruddra.com/2016/11/14/docker-do-stuff-using-celery-using-redis-as-broker/index.html)

* [jameshiew/django-celery-docker-example](https://github.com/jameshiew)

  ​

  ​

  ​