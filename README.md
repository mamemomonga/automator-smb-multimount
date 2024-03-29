# Automatorを使ったファイルサーバへの一括マウント

Automatorを使ってダブルクリック１回とクリック１回でファイルサーバの複数のパスのマウントとアンマウントを行うことができる。

## 事前準備

### 1.マウント先フォルダの準備

このツールでは、一般的に使用される /Volumes/xxxx にはマウントせず、事前に用意したパスにマウントします。ベースディレクトリを作成し、その下にマウントするディレクトリを作成します。マウントするディレクトリは決め打ちになっていて、 home, music, photo, videoとなっています。これらのフォルダは事前に作成してください。マウントするディレクトリを変更する場合はスクリプトのソースを編集してください。

フォルダの作成例

    /Users/user/fileserver/home
    /Users/user/fileserver/music
    /Users/user/fileserver/photo
    /Users/user/fileserver/video

### 2.Automatorでのアプリケーション作成

1. smb-multimount.workflow をダブルクリックしてAutomatorで開いてください。
2. 「ファイル→変換」で「アプリケーション」を選び、「ファイル→保存」でフォーマットを「アプリケーション」にし、任意の名前で保存してください。

### 3.変数の設定

「表示→変数」で右下に変数一覧を表示させて、以下の変数を編集してください。

変数 | 内容 | 例
---|---|---
SMB_BASEDIR | 作成したベースディレクトリ | /Users/username/fileserver
SMB_HOST | Sambaサーバ | fileserver.local
SMB_USER | Sambaユーザ名 | username
SMB_PASS | Sambaパスワード | p@ssw0rd
SMB_CHKDIR | マウント状況を確認する相対パス | home

### 4.実行の確認

保存し、Automatorで「実行」を選ぶと実行できます。保存したアプリをダブルクリックでも実行できます。保存したアプリをAutomatorで開けば再度編集できます。


