# lp-s3sync-repo-sample
## lp-s3sync-repo-sampleとは？
gatsbyJSで作った静的ページ(htmlファイルやCSSファイル)を本番環境用S3とテスト環境用S3にコピーする際に、簡単に作成できるようにしたものです。
GitHub Actionsを利用してます。

## 使い方
### このレポジトリをコピーする
```
$ git clone git@github.com:masato-kataoka/lp-s3sync-repo-sample.git
```
### GitHub上にレポジトリ作成する
GitHubの https://github.com/new に接続してレポジトリを作る。

### 作ったレポジトリをコピーする
作ったレポジトリをgit cloneする。

### staging-mainブランチを作り、GitHubに登録する
```
$ git checkout -b staging-main
$ git push -u origin staging-main
```
### staging-mainブランチをデフォルトブランチにする
作ったレポジトリからSettings→Branchesにアクセスした後、そこにある「Default branch」の`main`を staging-main に変更する。

### ファイルをコピーする
.github/workflow/ディレクトリとその中にあるファイルを、作ったレポジトリにコピーする
```
$ cp -pr lp-s3sync-repo-sample/.github/workflows/*.yml s3-sync-repo/.github/workflows/
```

### GatsbyJSの用意
git cloneしてきたディレクトリ内でGatsbyJSの導入を行う。
```
$ npm install -g gatsby-cli
$ gatsby new (サイト名)
```
途中でyarnかnpmのどちらを使うか聞かれるが、このサンプルを使う場合はyarnを選択する。

```
? Which package manager would you like to use ? › - Use arrow-keys. Return to submit.
❯   yarn
    npm
```

### S3にコピーする時に利用するIAMユーザ作成
S3にコピーをするため、AWSにIAMユーザを作ります。
ユーザ作成後に出力される`アクセスキーID`と`シークレットアクセスキー`を控えておきます。

|設定項目|||
|:-|:-|:-|
|設定するポリシー|S3FullAccess|本番環境とテスト環境のバケットに絞る|
|アクセスの種類|プログラムによるアクセス|S3へのコピーで使うだけなので、Webコンソールへのアクセスは不要|

### シークレット情報を登録する
`Settings`→`Secrets`にアクセスして設定します


|設定項目|設定値|
|:-|:-|
|AWS_ACCESS_KEY_ID|IAMユーザのACCESS_KEY_ID|
|AWS_SECRET_ACCESS_KEY|IAMユーザのSECRET_ACCESS_KEY|
|STAGING_S3_BUCKET|テスト環境のS3バケット|
|S3_BUCKET|本番環境のS3バケット|
