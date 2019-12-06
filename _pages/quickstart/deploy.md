---
title: デプロイ
keywords: deploy
tags: [quickstart, deploy]
permalink: quickstart/deploy
forder: quickstart
---

EC-CUBEは主要なレンタルサーバー、VPS、クラウドサーバー（AWS等）、多くのホスティングサービスの環境で簡単な手順で動作します。

WebサーバーでのEC-CUBEの手順はあらゆる方法がありますが、

本記事ではEC-CUBE4のパッケージ版をFTPでサーバーへアップロードし、

インストールする手順についてチュートリアル形式で説明します。

## 概要

### EC-CUBE4をサーバーにインストールするまでの流れ

EC-CUBE4をサーバー上に公開するためには以下の手順が必要となります。

1. サーバー上に EC-CUBE4 用のデータベースを作成
2. EC-CUBE4の最新パッケージをダウンロード
3. FTPでアップロード
4. EC-CUBE4 パッケージを解凍
5. EC-CUBEのWebインストール

### 必要なもの

本チュートリアルを行うためには以下の情報が必要となります。

- サーバーのドメイン名：〇〇〇〇〇〇〇〇
- サーバーのパスワード：**********
- FTPサーバ名：〇〇〇〇〇〇〇〇
- FTPユーザー名：〇〇〇〇〇〇〇〇
- FTPパスワード：**********
- データベースサーバーのホスト名：〇〇〇〇〇〇〇〇
- データベース名：〇〇〇〇〇〇〇〇
- データベースユーザー名：〇〇〇〇〇〇〇〇
- データベースパスワード：**********


## サーバー上に EC-CUBE4 用のデータベースを作成

サーバー上に EC-CUBE4 用のデータベースと、

そのデータベースへの全アクセス権・編集権を持つ MySQL、あるいは PostgreSQLのユーザーを作成します。

契約しているレンタルサーバー等の管理画面などから、データベースを作成して下さい。

また、作成する際には

- データベースサーバーのホスト名
- データベース名
- データベースユーザー名
- データベースパスワード

を設定しますが、Webインストール時に利用するので控えておいてください。

## EC-CUBE4の最新パッケージをダウンロード

<a href="https://www.ec-cube.net/download/other.php" target="_blank">EC-CUBE公式サイトのダウンロードページ</a>より、EC-CUBEのパッケージをダウンロードします。

今回はzip形式のものを利用します。

## FTPでアップロード

ダウンロードしたzipファイルをそのままFTPクライアントツールでアップロードしていきます。

### WINSCPをインストール

今回は<a href="https://forest.watch.impress.co.jp/library/software/winscp/" target="_blank">WinSCP</a>というツールを利用します。

インストールしていない方は、インストールして下さい。

### FTP接続設定

WinSCPを起動し、新しいサイトの接続設定を行います。

以下の項目を設定し、保存します。

|  項目  |  設定例  |
| ---- | ---- |
|  転送プロトコル |  SFTP  |
|  ホスト名  |  FTPサーバ名  |
|  ポート番号  |  22  |
|  ユーザー名  |  FTPユーザー名  |
|  パスワード  |  FTPパスワード  |

![WinSCPの設定](/images/quickstart/deploy/scp.png)

ログインボタンを押すと、サーバーに接続できます。

その後、ウェブ公開ディレクトリ（ドキュメントルート）（さくらレンタルサーバーの場合は、`/home/アカウント名/www`）に移動して下さい。

### EC-CUBE4のzipファイルをサーバーにアップロード

WinSCPに接続できたら、zipファイルをサーバーにアップロードしていきます。

WinSCPの画面の右側のエリア（サーバー側）にファイルをドラック&ドロップしてください。

## EC-CUBE4 パッケージを解凍


WinSCPでzipファイル上で右クリック＞ ファイル カスタム コマンド ＞ Untar/Gzip を実行すると、ファイルを解凍できます。

![unzipの方法](/images/quickstart/deploy/unzip.png)


## EC-CUBEのWebインストール

今回は、`http://example.com/eccube-4.0.3`にアクセスすると、

EC-CUBE4のトップページが表示表示されるようにしていきます。




※ EC-CUBE4 を`http://example.com`のように表示したい場合は、別途設定が必要となります。
{: .notice--danger}


以上です！これで EC-CUBE4 はインストールされたはずです。

