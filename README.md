# severless fremework v4 の手順書

# 初期設定

### severless ライブラリーをインストール

```bash
npm install -g serverless
```

### serverless fremework をアカウントを作成

- 初回に sls コマンドを叩くと、serverless fremework のアカウントを作れと言われるので、login/register で登録する。

```bash
sls
# Please login/register or enter your license key: …
#❯ Login/Register
  #Get A License
  #Enter A License Key
  #Explain Licensing Basics
```

# プロジェクトの作成

1. sls コマンドを聞くと、使用する fremework を選択
2. project の名前を入力
3. serverless fremework のプロジェクトを作成、編集するかを選択(基本的に Create A New App)
4. serverless fremework のプロジェクト名を指定

```bash
sls
#Serverless ϟ Framework

#Welcome to Serverless Framework V.4

#Create a new project by selecting a Template to generate scaffolding for a specific use-case.

#? Select A Template: …
#❯ AWS / Node.js / HTTP API
  #AWS / Node.js / Express API
  #AWS / Node.js / Express API with DynamoDB
  #AWS / Node.js / Scheduled Task
  #AWS / Node.js / Simple Function
  #AWS / Python / HTTP API
  #AWS / Python / Flask API
  #AWS / Python / Flask API with DynamoDB
  #AWS / Python / Scheduled Task
  #AWS / Python / Simple Function
  #AWS / Compose / Serverless + Cloudformation + SAM

#✔ Name Your Project: · test

#Create Or Select An Existing App: …
#❯ Create A New App
 # sample
 # sample-python
 # Skip Adding An App

 # ✔ Name Your New App: · test
```

# デプロイ

1. serverless.yaml を編集

- region 名を指定(東京の場合：ap-northeast-1)
- profile 名 aws cli で設定している名前を指定

```yaml:serverless.yaml
provider:
  name: aws
  runtime: python3.12
  stage: dev
  region: ap-northeast-1
  profile: profile名[default]
```

```bash
sls deploy
```

# リソースの取り消し

```bash
sls remove
```

# ローカルで作成方法

```bash
# ライブラリーをインストール
 npm install --save-dev serverless-offline
```

```bash
# ローカルでサーバ起動
 sls offline start
```

```.gitignore
# node_modulesは、サイズが大きいためgit管理から外す
node_modules
```
