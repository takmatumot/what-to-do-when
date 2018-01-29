
# 仮想環境


## VirtualBox

* [初心者でもわかる】VirtualBoxインストール方法を詳しく！](https://eng-entrance.com/virtualbox-install)

## Docker

* [プライベートなDockerレジストリサーバーをコンテナで立てる](https://qiita.com/rsakao/items/617f54579278173d3c20)
 
## Vagrant

* [開発環境の構築・共有を簡単にするVagrant入門](https://thinkit.co.jp/story/2015/03/19/5740)
* [VagrantとDockerについて名前しか知らなかったので試した](https://qiita.com/hidekuro/items/fc12344d36d996198e96)
* [VirtualBox+Vagrantで楽々Docker環境構築（Windows）](https://qiita.com/mikoski01/items/7ed36ac9e402658bb93e)
* [Discover Vagrant Boxes](Discover Vagrant Boxes)
* [Vagrant ssh-configでvagrant sshを快適にする](https://qiita.com/Sanche/items/43d615beef05cd9417e2)
* [Docker (for Windows)と Vagrant の比較と活用事例](https://qiita.com/yoshiwatanabe/items/a42af12a0043faed1a5e)
* [Vagrantを使ってWindowsの仮想環境を構築してみた](https://curecode.jp/tech/vagrant_with_windows_guests/)
* [Vagrant で作ったり壊したりできる Windows 環境を手に入れるまでの手順](tech.nitoyon.com/ja/blog/2014/02/20/vagrant-win-guest/)
* [個人開発環境をvagrantで建てるべきか、dockerで建てるべきか](https://qiita.com/hirohero/items/1eaa22b7f87eb66b2f2d)
* [KVM用仮想マシンをVagrantで手軽に作る](https://knowledge.sakura.ad.jp/2535/)

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

## Windowsコンテナ

* [Windowsコンテナー](https://docs.microsoft.com/ja-jp/virtualization/windowscontainers/about/)

## LXD

* [LXD 環境を構築する](https://qiita.com/nakaniko/items/ce3d8e4873ab9ddfcff2)

## Link

* [ホストOS型の仮想化ツール比較](https://qiita.com/heignamerican/items/58599220b5111bf5488d)