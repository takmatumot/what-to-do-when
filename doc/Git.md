
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

## How to

```
# git remote のリストをみるとき
git remote -v
# gitでリモートのブランチにローカルを強制一致させたい時
git fetch
git reset --hard origin/master
```

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
   *  SSHクライアントは TortoiseGitPlink... を選択する
* Linux での　git tools
   * [tig](https://github.com/jonas/tig) 
   * [linuxでtigをコンパイルする](https://qiita.com/tdrk/items/06b21bedff3244e21aae)
* 秘密鍵・公開鍵
  * [Bitbucketのリモートリポジトリを使う](http://moondoldo.com/DoldoWorkz/?Git%2FBitbucket%E3%81%AE%E3%83%AA%E3%83%A2%E3%83%BC%E3%83%88%E3%83%AA%E3%83%9D%E3%82%B8%E3%83%88%E3%83%AA%E3%82%92%E4%BD%BF%E3%81%86)
   * Git Bashで OpenSSHの秘密鍵・公開鍵を作成する
   * OpenSSH の秘密鍵からPutty形式の秘密鍵を作成する
   * Gitクライアント側で公開鍵を設定する
   * TortoiseGitのPuttyで秘密鍵を設定する

* その他
 * [わかりやすい README 駆動開発](https://qiita.com/b4b4r07/items/c80d53db9a0fd59086ec)
 * [空のディレクトリを維持するための、 .gitkeep と .gitignore の使い分け](https://qiita.com/ndxbn/items/f124d2b183b60cb074e2)
 * [複数Githubアカウントでssh接続を使い分ける手順](https://qiita.com/yampy/items/24638156abd383e08758)
 * [Gitプロトコルを受け入れるためのファイアーウォールの設定(Linux)](https://www.ipentec.com/document/document.aspx?page=linux-firewall-accept-git-protocol)
 * [Git/gitlabで共同作業をするための最小限の知識](https://doss.eidos.ic.i.u-tokyo.ac.jp/html/git.html)
 * [GitLab への Git repository の移動方法についての備忘録](https://www.labohyt.net/blog/server/post-435/)
 * [GitLab運用方法と設定手順について](https://qiita.com/mikoski01/items/7a7795a8a1e98d9ba6d9)
 * [`git push -u` オプションの意味](https://qiita.com/ironsand/items/6c301fef730d53f35bc3)
 * [git push originで複数箇所にプッシュする](https://qiita.com/sasaplus1/items/ed518bb14ef8e3da06bf)
 * [githubでリポジトリを削除する方法](https://qiita.com/PlanetMeron/items/4d164eff7bff2243cf06)
 * [GIT超絶まとめ](https://qiita.com/masashi127/items/2e103c3fba9d1b058961)
 * [図で分かるgit-mergeの--ff, --no-ff, --squashの違い](http://d.hatena.ne.jp/sinsoku/20111025/1319497900)
 * [初めてGitHubリポジトリにpushしたらrejectedエラーになったときの対応メモ](https://qiita.com/takanatsu/items/fc89de9bd11148da1438)
 * [git fetchの理解からgit mergeとpullの役割](https://qiita.com/osamu1203/items/cb94ef9da02e1ec3e921)
 * [忘れやすい人のための git diff チートシート](https://qiita.com/shibukk/items/8c9362a5bd399b9c56be)
 
 * [GitHub の Markdown に TOC (目次) を付けるブックマークレット (vanilla JS 編)](https://qiita.com/hokkun_dayo/items/bd3ec64fba293f4aca08)
 * [gitでリモートのブランチにローカルを強制一致させたい時](https://qiita.com/ms2sato/items/72b48c1b1923beb1e186)
 * [gibo で .gitignore を作るときに .python-version を書かなくても良くなっていた。](https://qiita.com/kitsuyui/items/51cf7ddcafb345d5ba5a)
 * [【備忘録】Windowsにおける.gitkeepファイル作成方法](http://chu-bura.hateblo.jp/entry/2017/10/01/161415)
 

