

[TOC]

# Elasticsearch


* [Elasticsearch Reference](https://www.elastic.co/guide/en/elasticsearch/reference/current/index.html)
* [Elasticsearchのbool queryを利用してAND OR NOTを書いてみる](https://qiita.com/vanhuyz/items/04a6871ae5f53ba5a97f)
* Javaのバージョン

  * 1.8.0_131  or a later version


## CentOS7でのインストール

*  OpenJDKのインストール

  * Ref: [CentOS 7 に Java 8 (OpenJDK) を yum インストールする手順](https://weblabo.oscasierra.net/installing-openjdk8-on-centos7/)

    ```
    ## javaバージョンの確認
    $java -version
    java version "1.8.0_92"
    Java(TM) SE Runtime Environment (build 1.8.0_92-b14)
    Java HotSpot(TM) 64-Bit Server VM (build 25.92-b14, mixed mode)
    ## java アンインストール
    $sudo yum remove java
    ## javaインストール
    $yum search java-1.8.0-openjdk
    $sudo yum install java-1.8.0-openjdk -y
    $sudo yum install java-1.8.0-openjdk-devel -y
    ## javaバージョンの再確認
    $java -version
    openjdk version "1.8.0_161"
    OpenJDK Runtime Environment (build 1.8.0_161-b14)
    OpenJDK 64-Bit Server VM (build 25.161-b14, mixed mode)
    ```

* rpmでのインストール

  * Ref. : [Install Elasticsearch with RPM](https://www.elastic.co/guide/en/elasticsearch/reference/6.2/rpm.html)

  * Elasticsearch PGP Keyのインストール

    ```
    $ sudo rpm --import https://artifacts.elastic.co/GPG-KEY-elasticsearch
    ```

  * /etc/yum.repos.d/elasticsearch.repo を以下のように生成

    ```
    [elasticsearch-6.x]
    name=Elasticsearch repository for 6.x packages
    baseurl=https://artifacts.elastic.co/packages/6.x/yum
    gpgcheck=1
    gpgkey=https://artifacts.elastic.co/GPG-KEY-elasticsearch
    enabled=1
    autorefresh=1
    type=rpm-md
    ```

  * インストール

    ```
    $ sudo yum install elasticsearch -y
    ```

* SysV init を用いて稼働

  * elasticsearchの start, stop

    ```
    $sudo systemectl list-unit-files | grep elastic
    elasticsearch.service 			disabled
    $sudo systemctl enable elasticsearch.service
    $sudo service elasticsearch start
    $sudo service elasticsearch stop
    ```


  * 動作確認

    ```
    $ curl http://localhost:9200
    {
      "name" : "1oyRChF",
      "cluster_name" : "elasticsearch",
      "cluster_uuid" : "RNtl8NlQTT6bH4TXXiqpFQ",
      "version" : {
        "number" : "6.2.1",
        "build_hash" : "7299dc3",
        "build_date" : "2018-02-07T19:34:26.990113Z",
        "build_snapshot" : false,
        "lucene_version" : "7.2.1",
        "minimum_wire_compatibility_version" : "5.6.0",
        "minimum_index_compatibility_version" : "5.0.0"
      },
      "tagline" : "You Know, for Search"
    }
    ```

  ## kibana

  * Ref. :  [Install Kibana with RPM](https://www.elastic.co/guide/en/kibana/current/rpm.html#rpm)

  * Elastic PGP Keyの import

    ```
    $sudo rpm --import https//artifacts.elastic.co/GPG-KEY-elasticsearch
    ```

  * /etc/yum.repos.d/kibana.repo を生成

    ```
    [kibana-6.x]
    name=Kibana repository for 6.x packages
    baseurl=https://artifacts.elastic.co/packages/6.x/yum
    gpgcheck=1
    gpgkey=https://artifacts.elastic.co/GPG-KEY-elasticsearch
    enabled=1
    autorefresh=1
    type=rpm-md
    ```

  * インストール

    ```
    $sudo yum install kibana
    ```

  * SysV init を用いて稼働

    ```
    $ systemctl list-unit-files | grep  kibana
    kibana.service           disabled
    $ sudo systemctl enable kibana.service

    ## edit /etc/kibana/kibana.yml
    # server.host: "localhost"
    server.host: "0.0.0.0"

    $ sudo systemctl start kibana
    $ sudo systemctl stop kibana

    ## access to http://localhost:5601
    ```

  ## kuromoji

  * Ref. 

      * [japanese (kuromoji) analysis plugin](https://www.elastic.co/guide/en/elasticsearch/plugins/6.2/analysis-kuromoji.html)

    * [Elasticsearch に kuromoji を入れて日本語全文検索をする](https://qiita.com/mserizawa/items/8335d39cacb87f12b678)

      ```
      /usr/shared/elasticsearch/bin/elasticsearch-plugin install analysis-kuromoji

      ```

    * elasticsearchを再起動し、pluginがインストールされたかどうかを確認する

      ```
      $ sudo systemctl restart elasticsearch
      $ curl -XGET  http://localhost:9200/_nodes/plugins
      ```

## head

* Ref:

  * [elasticsearch-head](https://github.com/mobz/elasticsearch-head)

* インストール

  ```
  $ sudo yum install nodejs
  $ git clone git://github.com/mobz/elasticsearch-head.git
  $ cd elasticsearch-head
  $ npm install
  $ npm run start
  open http://loclahost:9100
  ```



## Dockerでのインストール

* Ref.

  * [Install Elasticsearch with Docker](https://www.elastic.co/guide/en/elasticsearch/reference/6.2/docker.html)
  * [Dockerを利用して Elasticsearch + Kibana の環境を作る](https://qiita.com/akym03/items/f981a35a95598d7ab97b)
  * [Dockerを利用して Elasticsearch + Kibana の環境で kuromoji + Neologd を試す](https://qiita.com/akym03/items/e99fafe36eb758cefd89)
  *  [公式コンテナイメージを使用した際のX-Packの無効化について](https://discuss.elastic.co/t/x-pack/86805)

## 基本情報

* [Elasticsearch index,typeについて](https://qiita.com/ystkr/items/3ade38d55ebaabdc2267)



## 運用

* [ElasticSearchの運用とか (2)](http://t-cyrill.hatenablog.jp/entry/2014/04/19/161422)

* [Elasticsearch導入前に気を付けておきたいこと！](https://qiita.com/uzresk/items/e0b10c14875b79c450f2)

* [公式コンテナイメージを使用した際のX-Packの無効化について](https://discuss.elastic.co/t/x-pack/86805)






