# 7-2. Nutanix Cloud Controller Manager（CCM）

Kubernetesがプロビジョニングされるインフラ特有の設定などを管理するCloud Controller Manager（CCM）として、Nutanix Cloud Controller Managerがインストールされます。主な役割として、Kubernetesノードにトポロジ情報のラベルを付与します。

仮想マシンのPrism配置ベースのトポロジ検出により、デフォルトではノード仮想マシンをホストするPrism ElementとPrism Centralを検出してノードのラベルを決定しており、Prism Centralはリージョン、Prism Elementはゾーンとして設定されます。この機能は、CSI DriverやNDKの前提となっています。

# 参考ドキュメント

https://github.com/nutanix-cloud-native/cloud-provider-nutanix
