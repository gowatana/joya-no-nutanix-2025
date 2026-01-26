# 4-1. GUI

NDB を運用するための主要なツールを紹介します。

## NDB Server の Web UI

NDB Server に HTTPS でアクセスすると利用できる Web UI で、基本的に NDB の操作には Prism ではなくこの UI を利用します。
NDB Server 自体の設定と DB の管理操作や、監視などで利用します。


この UI で対応していない操作では、CLI や API を利用することになります。
後述の NDB CLI やスクリプトには、この Web UI からダウンロード可能なものがあります。


## REST API Explorer

NDB には、Prismとは別の REST API が用意されています。NDB Serverには、API を確認・実行できる、SwaggerベースのREST API Explorerが内蔵されています。これは、NDB ServerのWeb UIからアクセスできます。


## Prism Elemtnt

Nutanix HCI においてNutanix クラスタや仮想マシンの管理ツールで、Web ブラウザから利用します。Prism Element を集中管理する「Prism Central」も存在しますが、NDB からは直接的に利用しません。

NDB の運用においては、登録する DB サーバの構築や、NDB でプロビジョニングした DB サーバの停止や再起動をする際に利用することになります。

Nutanix Volumes Storage の Volume Group の管理操作でも利用しますが、基本的に NDB での Volume Group の作成 / 接続 / 削除といった処理は自動化されています。


# 参考ドキュメント
