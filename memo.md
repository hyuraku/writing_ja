# 1. きっかけ  
これまでrails4.2.0を使って学習していたが、
最近テキストを見ながらrails 5.0.0をインストールした際に
次のコマンドを実行するように記載されていた。

```
rbenv rehash
```
しかし、どうしてこのコマンドを使わなればいけなかったかの記載がなかったので
調べてみることにした。

# 2. rbenv rehash
いろいろとWebサイトを見てみたところ、やはり一次ソースを調べるのが早いのかなと思い
[githubのrbenv](https://github.com/rbenv/rbenv#rbenv-rehash)のページで調べてみた。
思ったとおり、rbenv rehashについて解説があった。以下解説文を引用する。
```
Installs shims for all Ruby executables known to rbenv
(i.e., ~/.rbenv/versions/＊/bin/＊).
Run this command after you install a new version of Ruby, or
install a gem that provides commands.
$ rbenv rehash
```
次はshimsを調べてみる。
# 3. shims
同じページ内に[shimsの解説](https://github.com/rbenv/rbenv#understanding-shims)を発見
さっそく解説を読んでみる。
```
--<中略>--
Shims are lightweight executables that simply pass your command along to rbenv.
--<中略>--
```
次の2つのことがわかった。
- shimsはコマンドをrbenvに渡すだけの軽量実行ファイル。
- rbenv rehashはshimsをインストールしている。
