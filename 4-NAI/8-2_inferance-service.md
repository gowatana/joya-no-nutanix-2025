# 8-2. 推論サービス

NAIでは、AIモデルからAPIでアクセスできる推論サービスを起動して、エンドポイント（URL）を提供できます。このような処理は、一般的にサービングと呼ばれています。

NAIの推論サービスでは、KServeによるInferenceServiceリソースを利用しており、HTTPSでアクセス可能なREST APIを公開します。そしてInferenceServiceの入口となるGatewayリソースを提供するために、Envoy Gatewayが利用されています。


# 参考ドキュメント

https://kserve.github.io/website/docs/intro

https://portal.nutanix.com/page/documents/details?targetId=Nutanix-Enterprise-AI-v2_6:top-nai-endpoints-page-c.html
