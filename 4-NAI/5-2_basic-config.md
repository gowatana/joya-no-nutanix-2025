# 5-2. 基本設定

Helmによる（nai-core）のインストールを実施した後に、Envoy GatewayのSSL/TLS証明書の発行と設定を実施します。
この証明書は、NAIのインストールによってnai-system Namespaceに作成されるGatewayリソースのIPアドレス（に対応するFQDN）に対して発行します。

NKP Dashboard にある Application 一覧に NAI のリンク ボタンを追加するには、NAI のインストール後に ConfigMap の設定を追加する必要があります。
これは、NAI UIに対応したConifgMapの、data.dashboardLinkとして、NAI UIのURLを手動で設定します。

# 参考ドキュメント
https://portal.nutanix.com/page/documents/details?targetId=Nutanix-Enterprise-AI-v2_5:top-NAI-on-NKP-c.html
