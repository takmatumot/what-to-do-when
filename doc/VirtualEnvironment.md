
# 仮想環境


## VirtualBox

* [初心者でもわかる】VirtualBoxインストール方法を詳しく！](https://eng-entrance.com/virtualbox-install)
* [VirtualBoxの仮想マシンフォルダ変更手順メモ]( https://qiita.com/sugard12/items/8b4f420b3afed79fe003)

## Docker

* [プライベートなDockerレジストリサーバーをコンテナで立てる](https://qiita.com/rsakao/items/617f54579278173d3c20)

## Vagrant

* [開発環境の構築・共有を簡単にするVagrant入門](https://thinkit.co.jp/story/2015/03/19/5740)
* [VagrantとDockerについて名前しか知らなかったので試した](https://qiita.com/hidekuro/items/fc12344d36d996198e96)
* [VirtualBox+Vagrantで楽々Docker環境構築（Windows）](https://qiita.com/mikoski01/items/7ed36ac9e402658bb93e)
* [Discover Vagrant Boxes](https://app.vagrantup.com/boxes/search)
* [Vagrant ssh-configでvagrant sshを快適にする](https://qiita.com/Sanche/items/43d615beef05cd9417e2)
* [Docker (for Windows)と Vagrant の比較と活用事例](https://qiita.com/yoshiwatanabe/items/a42af12a0043faed1a5e)
* [Vagrantを使ってWindowsの仮想環境を構築してみた](https://curecode.jp/tech/vagrant_with_windows_guests/)
* [Vagrant で作ったり壊したりできる Windows 環境を手に入れるまでの手順](tech.nitoyon.com/ja/blog/2014/02/20/vagrant-win-guest/)
* [個人開発環境をvagrantで建てるべきか、dockerで建てるべきか](https://qiita.com/hirohero/items/1eaa22b7f87eb66b2f2d)
* [KVM用仮想マシンをVagrantで手軽に作る](https://knowledge.sakura.ad.jp/2535/)
* [vagrantのboxフォルダ変更手順メモ](https://qiita.com/sugard12/items/85b2e70c87a354675a0e)
* [【まとめ】Vagrant コマンド一覧]( https://qiita.com/oreo3@github/items/4054a4120ccc249676d9)
* [Vagrantの環境でGUIを立ち上げるための環境構築](http://msyksphinz.hatenablog.com/entry/2015/11/24/020000)

### Vagrant setup

1. インストール
 * [VirtualBox](https://www.virtualbox.org/)
 * [Vagrant](https://www.vagrantup.com/)
2. VM用ディレクトリの作成
3. Vagrantfileの生成
  ```
  > vagrant init --minimal ubuntu/trusty64
  ```
  * 利用するbox(Atlas)は[こちら](https://app.vagrantup.com/boxes/search)を参照。
4. VMの起動とssh ログイン
  ```
  > vagrant up

  > vagrant ssh
  ```

* トラブルがあり最初からやり直すばあいのVMの消去および再スタート

  ```
  > vagrant destroy

  > vagrant up
  ```

## ssh セッティング

* Vagrantfileに以下の記述をいれておく。

```
config.ssh.forward_agent = true
config.ssh.forward_x11 = true
```

* 修正後 vagrant reload で設定を反映させる

* vagrant上にX11用のライブラリをインストール

  * 参考情報

    * [How to enable and use SSH X11 Forwarding on Vagrant Instances](https://computingforgeeks.com/how-to-enable-and-use-ssh-x11-forwarding-on-vagrant-instances/)

  * For CentOS 7 and below, Fedora 21 and below run

    ```
    yum install xorg-x11-xauth
    ```

  * For Debian based systems: Ubuntu/Debian/Linux Mint, Kali Linux e.t.c, do

    ```
    sudo apt-get install xauth
    ```

  * For Fedora 22 and 23, run

    ```
    dnf install xorg-x11-xauth
    ```

* Putty側の設定

  * 参考情報
    * [[Vagrant] VagrantでSSH接続するためのSSH client導入法 for Windows ユーザー [PuTTY]](https://qiita.com/pakiran/items/eeeb736cbef5d8b609db)
    * [PuTTYでは、SSH接続するための秘密鍵はpemファイルじゃだめ](http://d.hatena.ne.jp/kaishitaeiichi/20120104/1326122048)
    * [Vagrantの環境でGUIを立ち上げるための環境構築](http://msyksphinz.hatenablog.com/entry/2015/11/24/020000)

## Windowsコンテナ

* [Windowsコンテナー](https://docs.microsoft.com/ja-jp/virtualization/windowscontainers/about/)

## LXD

* [LXD 環境を構築する](https://qiita.com/nakaniko/items/ce3d8e4873ab9ddfcff2)

## Link

* [ホストOS型の仮想化ツール比較](https://qiita.com/heignamerican/items/58599220b5111bf5488d)