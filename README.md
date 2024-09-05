# Next.js + Django + PostgresSQL DevContainer SetUp Guide

## 前提条件

- Docker
- Visual Studio Code
- Visual Studio CodeのRemote - Containers拡張機能

## セットアップ

0. `Docker for desktop` 起動していることを確認します。
1. このリポジトリをクローンします。
2. Visual Studio Codeでプロジェクトフォルダを開きます。
3. `Cmd + Shift + P`（macOS）または`Ctrl + Shift + P`（Windows/Linux）を押してコマンドパレットを開きます。
4. "Remote-Containers: Reopen in Container"と入力し、選択します。
5. さらに、"Rebuild and Reopen in Container"を選択して、キャッシュを使用せずにコンテナを再構築します。
6. DevContainerのビルドが完了するまで待ちます。

※ 1回目のコンテナ起動時にエラーが発生する場合はRetryを押して下さい(2回以上失敗する場合は表示されるエラーに対応して下さい)

## フロントエンド（Next.js）の起動方法

1. ターミナルで以下のコマンドを実行します：

```bash
cd frontend
yarn dev
```

ブラウザで http://localhost:3000 にアクセスして、Next.jsアプリケーションが起動していることを確認します。


## バックエンド（Django）の起動方法
別のターミナルで以下のコマンドを実行します：
```bash
cd backend
python manage.py runserver 0.0.0.0:8000
```

ブラウザで http://localhost:8000 にアクセスして、Djangoアプリケーションが起動していることを確認します。


## ライブラリやパッケージの追加方法
### フロントエンド（Next.js）
frontend ディレクトリに移動します：
```bash
cd frontend
```

必要なパッケージを yarn でインストールします：
```bash
yarn add パッケージ名
```

### バックエンド（Django）
backend ディレクトリに移動します：
```bash
cd backend
```

必要なパッケージを pip でインストールします：
```bash
pip install パッケージ名
```

インストールしたパッケージを requirements.txt に追加します：
```bash
pip freeze > requirements.txt
```