# 6-6. NKPのアプリケーション

Kubernetesでユーザーワークロードを稼働させるには、ロードバランサー、モニタリング、監視といった、プラットフォームとして必要なアプリケーションが必要になります。NKPには、これらのアプリケーションが含まれています。

NKPにパッケージとして含まれるアプリケーションによって、次のような機能が提供されています。ただし、NKPエディションによって利用可能なものが異なります。
* マルチクラスタのライフサイクル操作
* ビルトインのマルチテナンシー
* GitOps
* オートスケーリングとセルフヒーリング
* カスタマイズ可能な可観測性と、ログ ダッシュボード
* GPU Operatorのサポート
* AI支援によるチャットボット
* アプリケーション カタログ
* コスト管理

# アプリケーションの種類
NKPでは、管理対象となるアプリケーションをいくつかの種類に分類しています。ただし、これらはドキュメントによって表現の揺らぎがあるようです。

## コア プラットフォームアプリケーション
Traefikとその依存アプリケーション

## プラットフォームアプリケーション（Proエディション以上で利用可能）
監視、ログ記録、バックアップまたは復元、ポリシー エージェント、外部 DNS、負荷分散、イングレス、SSO、サービス メッシュ。

## プラットフォームアプリケーション（Ultimateエディションで利用可能）
すべての Pro Platform アプリケーションに加え、追加のアクセス制御と集中コスト管理が含まれます。

## カタログ アプリケーション（Ultimateエディションで利用可能）
Kafka、Spark、ZooKeeper など、ユーザーワークロードに使用するためにデプロイされるアプリケーション。

## カスタム アプリケーション
プラットフォーム アプリケーション以外にも、カスタムアプリケーションとしてNKPカタログから提供可能です。

## その他
Nutanix Catalog Appを別に扱うケースもあります。（現状ではNAIとNDK）

# NKPのカタログ アプリケーションの仕組み
NKPのアプリケーション管理では、AppDeploymentというカスタム リソースが利用されています。これには内部的にFluxなどが利用されており、手動でリソース定義の変更やアップデートを実施しても、自動的にロールバックされてしまいます。そのため、設定変更や更新といった作業は、NKP DashboardなどNKPの作法に合わせて実施する必要があります。

# 参考ドキュメント

https://portal.nutanix.com/page/documents/details?targetId=Nutanix-Kubernetes-Platform-v2_17-ja-JP:top-applications-c.html

https://portal.nutanix.com/page/documents/details?targetId=Nutanix-Kubernetes-Platform-v2_17-ja-JP:top-appdeployment-resources-c.html

https://github.com/mesosphere/kommander-applications/tree/main/applications
