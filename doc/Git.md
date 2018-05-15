
# Git

## 運用

* Gitホスティングサービス
  * [GitLab](https://about.gitlab.com/) 
     * オンプレミスでも利用可能
      * Ref. : [GitHubの代替えGitLabのインストール方法と紹介（Ubuntu16.04版)]()
  * [GitHub](https://github.com/)
    * プライベートレポジトリ作成は有料オプション
* Gitツール
  * Windowsでは[TortoiseGit](https://tortoisegit.org/)を利用
* Gitコマンド
  * git rebaseは使わない
    * Ref. : [なぜ git rebase をやめるべきか](https://frasco.io/why-you-should-stop-using-git-rebase-535fa30d7e25)
  * Git更新手順
    * GitLab/GitHubで git cloneでレポジトリを取得
    * 別branchを作成し、ローカル環境で更新
    * git pull --rebase で mergeした後、GitLab/GitHubに pushし、そのあと、プルリクエストを行う
    * Ref. :
      * [git pull と git pull –rebase の違いって？図を交えて説明します！](http://kray.jp/blog/git-pull-rebase/)

      * [何故 git rebase は駄目で git pull –rebase はいいのか](https://www.lancard.com/blog/2016/11/07/git-rebase-and-pull-rebase/)
      * [GitHubを使うなら最低限知っておきたい、プルリクエストの送り方とレビュー、マージの基本](http://www.atmarkit.co.jp/ait/articles/1702/27/news022.html)

## 権限管理

* [GitLabのユーザ権限](https://qiita.com/mats116/items/f11e2e25731c325eeda8)
* [GitLab運用方法と設定手順について](https://qiita.com/mikoski01/items/7a7795a8a1e98d9ba6d9)

* [git submodule は癖がすごいとの噂だったが素直につきあっていけそうという話](https://www.d-wood.com/blog/2014/05/22_6257.html)

## remote変更


* [gitのremote urlを変更する(レポジトリ移行時)](https://qiita.com/minoringo/items/917e325892733e0d606e)

## Submodule

* submoduleも masterブランチを追う場合 (とってきたsubmoduleでも開発したい場合)

```
$ git submodule update --init
$ git submodule foreach git checkout master
```

* すべて最新に更新

```
$ git submodule foreach git pull
```

* [Git Submoduleについてまとめてみる](https://qiita.com/BlueSilverCat/items/19bb9b814572cd35b2ae)
*  [git submoduleを今風な感じで削除する](https://qiita.com/u1aryz/items/8d1923da79158439eeaa)
*  [git submodulesで間違えて追加したときの削除手順](https://qiita.com/knsh14/items/941f2ec2ec76ef1d1940)
*  [git submoduleについてのメモ 追加/削除/更新等](https://rcmdnk.com/blog/2013/10/18/computer-git/)
* [gitでクローンと同時にサブモジュールを初期化、アップデートする](https://blog.isao.co.jp/git%E3%81%A7%E3%82%AF%E3%83%AD%E3%83%BC%E3%83%B3%E3%81%A8%E5%90%8C%E6%99%82%E3%81%AB%E3%82%B5%E3%83%96%E3%83%A2%E3%82%B8%E3%83%A5%E3%83%BC%E3%83%AB%E3%82%92%E5%88%9D%E6%9C%9F%E5%8C%96%E3%80%81/)
* [submodule の向き先 url を変更する](https://qiita.com/8mamo10/items/fd11d8c7a2d928b39173)

   ​

## How to

```
# git remote のリストをみるとき
git remote -v
# gitでリモートのブランチにローカルを強制一致させたい時
git fetch
git reset --hard origin/master
```

## GitLab

* [Gitlabのバージョンを確認する](https://orebibou.com/2016/10/gitlab%E3%81%AE%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%82%92%E7%A2%BA%E8%AA%8D%E3%81%99%E3%82%8B/)
* [GitLab(Docker版)の設定でSignin enabledのチェック外しを元に戻す手順](https://qiita.com/mikoski01/items/14ee930c44eba8eb2fdb)
* [GitLabがメモリ不足で遅いときの対処法](https://qiita.com/lanevok/items/33a694150c8473d9ab48)
* [GitLab リポジトリの Clone URL として表示されるホスト名を変更する](https://maku77.github.io/git/gitlab/change-hostname.html)
* [GitLab on docker のバージョンアップをしてみた](https://qiita.com/DG0426/items/28b205901fca9eaff80a)


## GitLab Docker

* GitHub: [sameersbn](https://github.com/sameersbn)/**docker-gitlab**
* Tips
  * GitLabリポジトリのClone URL として表示されるホスト名を変更する。
    * --> environment で GITLAB_HOST を設定する。

## Link

* [TortoiseGitのセットアップ](https://qiita.com/SkyLaptor/items/6347f38c8c010f4d5bd2)
  * Gitインストール時の注意事項
    * Choosing the default editor used By Git部
     * Use the Nano editor by default を選択する
    * Adjusting your PATH environment部
     * Use Git from Git Bash only を選択する
    * Choosing HTTPS transport backend部
     * Use the OpenSSL Libraryを選択する
    * Configuraing the line ending conversions部
     * Checkout as-is, commit as-is を選択する
    * Configuring the terminal emulator to use with Git Bash部
     * Use MinTTY (the default terminal of MSYS2)を選択する
  * Turtoise Gitインストール時の注意事項
   * SSHクライアントは TortoiseGitPlink... を選択する
* Linux での　git tools
   * [tig](https://github.com/jonas/tig) 
   * [linuxでtigをコンパイルする](https://qiita.com/tdrk/items/06b21bedff3244e21aae)
* 秘密鍵・公開鍵
  * [Bitbucketのリモートリポジトリを使う](http://moondoldo.com/DoldoWorkz/?Git%2FBitbucket%E3%81%AE%E3%83%AA%E3%83%A2%E3%83%BC%E3%83%88%E3%83%AA%E3%83%9D%E3%82%B8%E3%83%88%E3%83%AA%E3%82%92%E4%BD%BF%E3%81%86)
   * Git Bashで OpenSSHの秘密鍵・公開鍵を作成する
   * OpenSSH の秘密鍵からPutty形式の秘密鍵を作成する
   * Gitクライアント側で公開鍵を設定する
   * TortoiseGitのPuttyで秘密鍵を設定する
* Git branching
  * [LearnGitBranching](k.swd.cc/learnGitBranching-ja/)
  * [[日本語訳]A successful Git branching model](https://qiita.com/homhom44/items/9f13c646fa2619ae63d0)
* Git submodule
  * [Git submoduleの押さえておきたい理解ポイントのまとめ](https://qiita.com/kinpira/items/3309eb2e5a9a422199e9)
  * [Git submoduleの基礎](https://qiita.com/sotarok/items/0d525e568a6088f6f6bb)
  * [Git submoduleの押さえておきたい理解ポイントのまとめ](https://qiita.com/kinpira/items/3309eb2e5a9a422199e9)
* よく使う？項目
    * [git push originで複数箇所にプッシュする](https://qiita.com/sasaplus1/items/ed518bb14ef8e3da06bf)
    * [反則技 git push -f](https://qiita.com/ppworks/items/94c0107d98e55f903ea9)
    * [git addを取り消す](http://tweeeety.hateblo.jp/entry/2015/06/10/212631)
    * [gitでリモートのブランチにローカルを強制一致させたい時](https://qiita.com/ms2sato/items/72b48c1b1923beb1e186)
* stash
    * [git stash. コミットはせずに変更を退避したいとき](https://qiita.com/chihiro/items/f373873d5c2dfbd03250)
    * [コミット前の内容を一時的に避けておく「git stash」の使い方](https://www.granfairs.com/blog/staff/git-stash)
* 履歴削除
    * [Gitのコミット履歴を全消去して初期化する方法](http://sagelog.com/2017/10/12/post-485/)
    * [GitLab Protected Branches](https://docs.gitlab.com/ce/user/project/protected_branches.html)
* その他
    * [わかりやすい README 駆動開発](https://qiita.com/b4b4r07/items/c80d53db9a0fd59086ec)
    * [空のディレクトリを維持するための、 .gitkeep と .gitignore の使い分け](https://qiita.com/ndxbn/items/f124d2b183b60cb074e2)
    * [複数Githubアカウントでssh接続を使い分ける手順](https://qiita.com/yampy/items/24638156abd383e08758)
    * [Gitプロトコルを受け入れるためのファイアーウォールの設定(Linux)](https://www.ipentec.com/document/document.aspx?page=linux-firewall-accept-git-protocol)
    * [Git/gitlabで共同作業をするための最小限の知識](https://doss.eidos.ic.i.u-tokyo.ac.jp/html/git.html)
    * [GitLab への Git repository の移動方法についての備忘録](https://www.labohyt.net/blog/server/post-435/)
    * [GitLab運用方法と設定手順について](https://qiita.com/mikoski01/items/7a7795a8a1e98d9ba6d9)
    * [`git push -u` オプションの意味](https://qiita.com/ironsand/items/6c301fef730d53f35bc3)
    * [githubでリポジトリを削除する方法](https://qiita.com/PlanetMeron/items/4d164eff7bff2243cf06)
    * [GIT超絶まとめ](https://qiita.com/masashi127/items/2e103c3fba9d1b058961)
    * [図で分かるgit-mergeの--ff, --no-ff, --squashの違い](http://d.hatena.ne.jp/sinsoku/20111025/1319497900)
    * [初めてGitHubリポジトリにpushしたらrejectedエラーになったときの対応メモ](https://qiita.com/takanatsu/items/fc89de9bd11148da1438)
    * [git fetchの理解からgit mergeとpullの役割](https://qiita.com/osamu1203/items/cb94ef9da02e1ec3e921)
    * [忘れやすい人のための git diff チートシート](https://qiita.com/shibukk/items/8c9362a5bd399b9c56be)
    * [GitHub の Markdown に TOC (目次) を付けるブックマークレット (vanilla JS 編)](https://qiita.com/hokkun_dayo/items/bd3ec64fba293f4aca08)
    * [gibo で .gitignore を作るときに .python-version を書かなくても良くなっていた。](https://qiita.com/kitsuyui/items/51cf7ddcafb345d5ba5a)
    * [【備忘録】Windowsにおける.gitkeepファイル作成方法](http://chu-bura.hateblo.jp/entry/2017/10/01/161415)
    * [git add -A と git add . と git add -u の違い](https://qiita.com/YusukeHigaki/items/06e38eec96387d408780)
    * [Git for Windowsでのシンボリックリンク ](https://opcdiary.net/?p=31100)
    * [GitHubで実行ファイル（ソースコードを含まない）をZIPファイルで配布してみる](https://qiita.com/keita69sawada/items/da6d8f6b6fb8f05ca670)
    * [git push時に表示されるwarning: `push.default is unset...`の意味と解決方法](https://qiita.com/yaotti/items/a8e9f5de8dcca81d3214)


