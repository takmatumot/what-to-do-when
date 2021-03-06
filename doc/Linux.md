[TOC]

# Linux

## Bash
* [bash シェルスクリプト入門 -シェルスクリプトのいろは-](http://shellscript.sunone.me/tutorial.html)
* [【初心者向け】エイリアスの設定方法](https://qiita.com/yutat93/items/b5bb9c0366f21bcbea62)
* [bashのプロンプトを変更するには](http://www.atmarkit.co.jp/flinux/rensai/linuxtips/002cngprmpt.html)
* [bash_historyを便利に使う](https://qiita.com/nagane/items/f45fcc85b4864fca3909)
* [本当に正しい .bashrc と .bash_profile の使ひ分け](https://qiita.com/magicant/items/d3bb7ea1192e63fba850)
* [.bash_profileや.bashrcをフラグメントする(.bash.d)](https://qiita.com/NewGyu/items/e3a5b3e2224f96b68fcc)
* [bash 実行スクリプトの絶対パスの取得](https://qiita.com/koara-local/items/2d67c0964188bba39e29)
* Pattern substitution, [echo | sedなんていらなかったんだ！](https://qiita.com/r_plus/items/ac0093fd8c317ed96b4b)
* [シェル変数のデフォルト値を設定する](https://gist.github.com/doi-t/7853853)

##  ssh

* [ssh-copy-idで公開鍵を渡す](https://qiita.com/kentarosasaki/items/aa319e735a0b9660f1f0)
* [OpenSSHの警告メッセージを出さないようにする方法](https://qiita.com/shotaTsuge/items/48bdaccdafa5475d9016)
* [sshトンネル (京大マイコンクラブ)](https://www.kmc.gr.jp/advent-calendar/ssh/2013/12/09/tunnel2.html)
* [Reverse ssh tunnel を安定運用する](https://qiita.com/syoyo/items/d31e9db6851dfee3ef82) 

## systemd

* [Systemdを使ってさくっと自作コマンドをサービス化してみる](https://qiita.com/DQNEO/items/0b5d0bc5d3cf407cb7ff)

* [cron が入ってないのね Archさん](https://mtunn.wordpress.com/2014/12/19/cron-が入ってないのね-archさん/)

* [cronの代わりにsystemdのtimerで定期実行を定義してみる](https://blog.monophile.net/posts/20180113_systemd_timer_cron.html)

  ​

## LXD

* [Ubuntu 17.10 で LXD を試してみる](https://blog.1q77.com/2017/11/lxd-on-ubuntu-17-10/)
* [Windows and Linux on LXD](https://askubuntu.com/questions/890307/windows-and-linux-on-lxd)




## Misc.

* [FirefoxをゲストOSで起動しようとすると、localeエラーが発生して起動できない]( https://github.com/hageyahhoo/RecipesForWDJ/issues/1)
* [CentOS7の日本語化（日本語環境で利用する)](http://vps-okinawa-blog.net/?p=97)
* [[CentOS\]CentOS7でのロケール(locale)の確認及び変更](http://zero-config.com/centos/changelocale-002.html)
* [Dockerで立てたCentOS7コンテナの日本語環境とかtimezone設定とか](https://7me.oji.0j0.jp/2016/centos7-locale-timezone.html)
* [CentOSに日本語のmanをインストールする方法](http://kaworu.jpn.org/kaworu/2007-11-24-3.php)
* [Docker：Centos7公式コンテナにmanを入れてもマニュアルが出てこないときのインストール法](http://okisanjp.hatenablog.jp/entry/2017/01/06/214353)
* [Address already in use の対処法](https://qiita.com/Arashi/items/8b8d9d2f1f040b2aecf1)
* [CentOS7最小限のインストールからのGnomeデスクトップ環境構築](http://zero-config.com/centos/gnome-0001.html)
* [CentOS7ネットワーク設定](https://www.server-world.info/query?os=CentOS_7&p=initial_conf&f=3)
* [ポートが空いてるか調べる](https://www.softel.co.jp/blogs/linux/archives/53)
* [SSH/SCP のログイン自動化に sshpass が便利すぎた](http://blog.amedama.jp/entry/2017/06/03/131852)
* [CentOS6で「visudo: コマンドが見つかりません」の対処法](http://dqn.sakusakutto.jp/2012/01/centos6visudo.html)
* [【Linux CentOS 7（1511）64bit】LibreOffice5をRPMパッケージからインストールした](http://akira-arets.blogspot.com/2016/11/linux-centos7-installing-libreoffice5.html)


## gnome-terminal

* gnome-terminalが起動しなくなったとき
  * バックで動いている dbus-daemon  or dbus-launch を kill してみる。
  * "dbus-launch gnome-terminal"で起動させてみる。
  * "unset LANG" を試してみる。

## CentOS

* [CentOS 7 の Hostname を変更する](https://qiita.com/n-oshiro/items/d18ab37bce2b25b2d5b0) 

* [CentOS7のネットワーク設定(nmtui)](www.unknownengineer.net/entry/2016/06/21/123537)

* [nmcli をもちいたCentOS7ネットワーク設定](https://qiita.com/taro0219/items/8d3be39c5cb882d1ba5d)

* [CentOS 7でのネットワーク設定・確認方法](mzgkworks.com/post/linux-centos7-network-setting/)

* [CentOS7の標準ファイアウォール「firewalld」について](http://hikaku-server.com/linux/entry461.html)

* [CentOS7、ファイアウォールポート開放と閉じる方法](https://meideru.com/archives/1302#i-7)

* [CentOS７ ファイアウォール停止方法](http://www.server-memo.net/centos-settings/centos7/firewalld-stop.html)

* [Centos7 でポートを開放する方法：コマンドとファイル書き込み](https://omohikane.com/centos7_port_firewalld/) 

* 

* [ 【CentOS7】firewallで特定のポートに特定のホストからのみアクセスさせる設定](http://kimuraysp.hatenablog.com/entry/2017/09/20/003112)

* ](http://kimuraysp.hatenablog.com/entry/2017/09/20/003112)

* [CentOS7のhttpd設定で詰まった点](https://qiita.com/sky_y/items/b92fa6ba57d926f25370)

  --> httpsポートの開放の方法

* [CentOSでuserをsudo可能にする](https://qiita.com/Esfahan/items/a159753d156d23baf180)

* [CentOS7にChromeをインストール](https://qiita.com/shadowhat/items/af6b973df43d75abfe8e)

* [CentOS7.5にLibreOfficeをyumでインストールする](https://blog.katsubemakito.net/centos/install_libreoffice_with_yum)



##  自動起動

* [【新旧対応】Linuxでの自動起動の設定方法を解説](https://eng-entrance.com/linux_startup#systemd)

## yum

* [【yum list】パッケージ一覧を表示・確認する](http://uxmilk.jp/9146)

## Chrome

* [CentOS7にChromeをインストール](https://qiita.com/shadowhat/items/af6b973df43d75abfe8e)

## Firefox

* [Firefox tab crashes at startup](https://support.mozilla.org/ja/questions/1167673)


## ntp

* [CentOSにntpサーバを入れて、日本標準時刻に自動的に合わせるためのメモ](https://qiita.com/tsu_nera/items/9be676b04b190e45b281)
* ​