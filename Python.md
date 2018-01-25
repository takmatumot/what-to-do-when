
# Python

## 運用

* [Python](https://www.python.org/)バージョン
  * Python3.6を用いる。
  * 利用しているPythonモジュールが動作しない等、やむをえない場合に限りPython2.7を用いる。
* Python開発環境
  * [Conda](https://conda.io/docs/index.html) による仮想開発環境を用いる。
    * Ref. : [condaによるポータブルなPython環境構築のすすめ](https://qiita.com/yubessy/items/2dd43551aa8308dc7eca)
    * Ref. : [Anacondaのcondaコマンドによる仮想環境の使い方のまとめ](http://minus9d.hatenablog.com/entry/2016/01/29/235916)
* Python統合開発環境
  * [PyCharm](https://www.jetbrains.com/pycharm/) を用いる。
  * Ref. : [最強のPython統合開発環境PyCharm](https://qiita.com/yamionp/items/f88d50da8d6b548fc44c)
  * Ref. : [virtualenvやcondaで作成した仮想環境をIntelliJ IDEA(PyCharm)のプロジェクトに反映させる(メモ)](https://qiita.com/yoppe/items/c1a814986690b5742e31)
* コード規約
  * [PEP8](http://pep8-ja.readthedocs.io/ja/latest/)になるべく従う。
  * [pycodestyle](https://pypi.python.org/pypi/pycodestyle)を使ってPEP8規約を満たしているか確認する。
   * Ref. : [Python: pep8 は pycodestyle になったし pep257 は pydocstyle になった](http://blog.amedama.jp/entry/2017/06/13/222556)
  * [autopep8](https://pypi.python.org/pypi/autopep8)を用いて可能な範囲でpep8を満たすように自動変換することができる。
* pythonモジュール生成
 * setup スクリプトを書いてインストールする方式を用いる
   * Ref. : [setup スクリプトを書く](https://docs.python.jp/3/distutils/setupscript.html)
* ドキュメント
 * [pydoc](https://docs.python.jp/3/library/pydoc.html)を用いてドキュメント閲覧できるようにする
   * Ref. [pydoc さわってみた](http://carumisu.hatenablog.com/entry/2015/10/12/204148)
  * headerでのdocument書き方の例
    * Ref. : [What is the common header format of Python files?
](https://stackoverflow.com/questions/1523427/what-is-the-common-header-format-of-python-files)
  * 関数部のdocumentの書き方は google style, numpy, reSTスタイルがあるが、reST スタイルを用いる。 (PyCharm利用時に reSTスタイルでdocstringが自動補完されるため)
   * Ref. : [Pythonのdocstringの書き方について](http://tsukin.hateblo.jp/entry/2017/09/27/151427)
  * Pythonのドキュメント生成は[SPhinx](http://www.sphinx-doc.org/ja/stable/)を用いる。

## Conda

conda のコマンド

```
# conda の入っている環境名リストを取得する
> conda info -e
# condaの仮想環境作成
> conda create -n <myenv> python=3.6
# 仮想環境に入る
> activate <myenv>
# 仮想環境から抜ける
> deactivate
# conda環境を削除する
> conda remove -n <myenv> --all
```

* condaを単体でつかった場合にはシェバンがきかないので "xxx.py"のファイルをそのまま実行しようとしてもうまっくいかない。
  * Ref. : https://github.com/ContinuumIO/anaconda-issues/issues/149

## Link

* [What is the correct way to document a **kwargs parameter?](https://stackoverflow.com/questions/1137161/what-is-the-correct-way-to-document-a-kwargs-parameter)
* [バージョン番号を２度書かないために](http://methane.hatenablog.jp/entry/20120401/1333260681)
* [PythonスクリプトをWindowsのexeにする方法 (調査中)](http://minus9d.hatenablog.com/entry/2016/06/20/232653)
* [PyInstallerでPythonスクリプトをexe化](http://minus9d.hatenablog.com/entry/2016/07/06/215323)
