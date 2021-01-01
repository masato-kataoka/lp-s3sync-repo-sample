# 使い方
## レポジトリの準備
### このレポジトリをgit cloneする
```
$ git clone git@github.com:masato-kataoka/lp-s3sync-repo-sample.git (新しいレポジトリ名)
```
### push先のURLを変更する
```
$ git remote set-url origin (自分で作ったレポジトリ名)
```
## gatsby.jsの用意
git cloneしてきたディレクトリ内でgatsby.jsの導入を行う。
```
$ npm install -g gatsby-cli
```
## gatsby newの実行
```
$ gatsby new (サイト名)
```
途中でyarnかnpmのどちらを使うか聞かれますが、このサンプルを使う場合はyarnを選択します。

```
$ gatsby new my-site
? Which package manager would you like to use ? › - Use arrow-keys. Return to submit.
❯   yarn
    npm
```
