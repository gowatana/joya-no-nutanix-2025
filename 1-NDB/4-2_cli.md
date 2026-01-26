# 4-2. CLI

## NDB CLI（era コマンド）

NDB の DB 管理操作で利用できる CLI で、Web UI と同様の操作が可能です。
NDB Server に SSH 接続して利用する CLI で、コマンドの名前は旧製品名である「era」のままです。
NDB の Web UI からダウンロードしてローカルの Linux / macOS マシンで実行することも可能です。

> - [Blog] NDB CLI を DB サーバから実行してみる。  
>   https://blog.ntnx.jp/entry/2022/12/12/235825


## era-server CLI

NDB Server の設定（ネットワーク設定など）で利用します。
NDB Server に SSH 接続して利用する CLI ですが、NDB CLI（era コマンド）とは別のツールです。


## データベース サーバーの確認 スクリプト（pre-requirement script）

NDB に DB サーバを登録する前のチェックに利用するスクリプトです。
NDB の Web UI、もしくは NDB CLI からダウンロードできます。

- era_linux_prechecks.sh（Linux 用）
- era_windows_prechecks.ps1（Windows 用）


## NDB のアンインストール スクリプト

NDB に登録した DB サーバから、NDB コンポーネントをアンインストールする際に利用します。
NDB の Web UI、もしくは NDB CLI からダウンロードできます。

- era_linux_uninstall.sh（Linux 用）
- era_windows_uninstall.ps1（Windows 用）


# 参考ドキュメント
