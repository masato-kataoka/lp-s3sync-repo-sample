# 使い方
## このレポジトリをコピーする
```
$ git clone git@github.com:masato-kataoka/lp-s3sync-repo-sample.git
```
## GitHub上にレポジトリ作成する
GitHubの https://github.com/new に接続してレポジトリを作る。

## 作ったレポジトリをコピーする
作ったレポジトリをgit cloneします。

## デフォルトブランチを変更する
### staging-mainブランチを作る
```
$ git checkout -b staging-main
```
### staging-mainブランチをGitHubに登録する
```
$ git push -u origin staging-main
```
### staging-mainブランチをデフォルトブランチにする
作ったレポジトリからSettings→Branchesにアクセスした後、そこにある「Default branch」の`main`を staging-main に変更する。

## ファイルをコピーする
.github/workflow/ディレクトリとその中にあるファイルを、作ったレポジトリにコピーする
```
$ cp -pr lp-s3sync-repo-sample/.github/workflows/*.yml s3-sync-repo/.github/workflows/
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
途中でyarnかnpmのどちらを使うか聞かれるが、このサンプルを使う場合はyarnを選択する。

```
? Which package manager would you like to use ? › - Use arrow-keys. Return to submit.
❯   yarn
    npm
```

