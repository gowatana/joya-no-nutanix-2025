# 8-1. NAIの前提となるOSS

NAIをNKPのKubernetesクラスタにインストールするには、NKPにバンドルされいているもの以外にもOSSを利用します。必要なOSSはNAIのバージョン アップによって変更されることがありますが、NAI 2.4以降は次のソフトウェアが必要です。
* Envoy Gateway：KServeの前提として必要になるGatewayリソースを提供します。
* KServe：NAIの推論サービス エンドポイントの実体となるInferenceServiceリソースを提供します。


# 参考ドキュメント

https://portal.nutanix.com/page/documents/details?targetId=Release-Notes-Nutanix-Enterprise-AI-v2_6:rel-nai-software_requirements-r.html
