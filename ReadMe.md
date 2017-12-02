# このソフトウェアについて

pybabelを使ってみた。

pybabelはPythonパッケージBabelをインストールすると使える。

指定ディレクトリ配下の全`py`ファイルから`pot`ファイルを作成したり、既存`po`ファイルの更新などができる。[pygettext.py](https://github.com/python/cpython/blob/6f0eb93183519024cb360162bdd81b9faec97ba6/Tools/i18n/pygettext.py)、[msgfmt.py](https://github.com/python/cpython/blob/6f0eb93183519024cb360162bdd81b9faec97ba6/Tools/i18n/msgfmt.py)の2ツールを使い分けるだけでは不可能なことができるので便利。

* ドメイン名やパスなどは自動管理してくれず、コマンドの引数が多くて面倒
* 翻訳することと、翻訳したテキストをファイルに書き込むのは手作業である

# 参考

* http://d.hatena.ne.jp/fgshun/20100319/1269004530
* https://docs.python.jp/3/library/gettext.html
* https://ja.wikipedia.org/wiki/ISO_639-1%E3%82%B3%E3%83%BC%E3%83%89%E4%B8%80%E8%A6%A7

# 詳細

以下参照。

[pybabelを使ってみた](http://ytyaru.hatenablog.com/entry/2018/11/09/000000)。

今回はpybabelコマンドで`./res/i18n/`配下のファイルを生成した。`languages/`配下のうち、`ja/`は最新状態に更新しているが、`en`はマージしただけで翻訳テキストを入力していない。`de`はマージもしていない。

各言語ごとに実行結果がどうなるか確かめてみると、翻訳データがない箇所はソースコードにあるリテラルをそのまま表示していた。

```sh
$ python main.py
```

# 開発環境

* Linux Mint 17.3 MATE 32bit
* [pyenv](https://github.com/pylangstudy/201705/blob/master/27/Python%E5%AD%A6%E7%BF%92%E7%92%B0%E5%A2%83%E3%82%92%E7%94%A8%E6%84%8F%E3%81%99%E3%82%8B.md) 1.0.10
    * Python 3.6.1
* [pygettext.py](https://github.com/python/cpython/blob/6f0eb93183519024cb360162bdd81b9faec97ba6/Tools/i18n/pygettext.py)
* [msgfmt.py](https://github.com/python/cpython/blob/6f0eb93183519024cb360162bdd81b9faec97ba6/Tools/i18n/msgfmt.py)

# ライセンス

* https://sites.google.com/site/michinobumaeda/programming/pythonconst

Library|License|Copyright
-------|-------|---------
[Babel](https://github.com/python-babel/babel)|[BSD 3-clause](https://github.com/python-babel/babel/blob/master/LICENSE)|[Copyright (C) 2013 by the Babel Team, see AUTHORS for more information.](https://github.com/python-babel/babel/blob/master/LICENSE)
