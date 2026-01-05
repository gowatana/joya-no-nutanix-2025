# 前提となるNutanix製品

## Prism Central
NKPがAHV上のKubernetesクラスタのライフサイクルを管理する場合、Prism Centralと連携します。
nkp CLIによる管理クラスタのプロビジョニングの時点で、Prism Centralを登録する必要があります。
NKPの管理クラスタは、Prism Centralのマーケット プレイスにも登録されています。

## CAPX
AHVにKubernetesノードをプロビジョニングする、Cluster API（CAPI）のNutanix（X）Provider。

## Cluster API Runtime Extensions - Nutanix （CAREN）

調査中
* ClusterClassでのHelm Chartのバージョンなどを定義していそう。
* Nutanix Providerだけでなく、ほかのAWS Providerなどでも利用される。

https://nutanix-cloud-native.github.io/cluster-api-runtime-extensions-nutanix/


# 連携するNutanix製品

## Nutanix Cloud Controller Manager
NKPのクラスタには、Kubernetesがプロビジョニングされるインフラ特有の設定などを管理するCloud Controller Manager（CCM）として、Nutanix Cloud Controller Manager がインストールされる。
主な役割として、Kubernetesノードにトポロジ情報のラベルを付与します。仮想マシンのPrism配置ベースのトポロジ検出により、デフォルトではノード仮想マシンをホストするPrism ElementとPrism Centralを検出してノードのラベルを決定しており、Prism Centralはリージョン、Prism Elementはゾーンとして設定されます。この機能は、CSI DriverやNDKの前提となっています。

## Nutanix CSI Driver
Nutanix Volumes StorageおよびNutanix Files Storageと連携するためのCSI Driver。

## Nutanix COSI Driver
Nutanix ObjectsのS3互換のバケットを利用するためのNutanix COSI Driver。これはNKPでプロビジョニングしたKubernetesクラスタにはデフォルトでインストールされていないため、必要に応じてNKPカタログからインストールすることになります。

調査中

## Nutanix Flow CNI
調査中


# Nutanix以外の関連製品

## DockerまたはPodman
管理クラスタをプロビジョニングする際に、ブートストラップ クラスタを作成するために必要。
なお、ブートストラップ クラスタは、NKP内蔵のkind（Kubernetes in Docker）で作成されるので、kindのインストールは不要。


# 参考ドキュメント

https://portal.nutanix.com/page/documents/details?targetId=CSI-Volume-Driver-v3_3:CSI-Volume-Driver-v3_3

https://github.com/nutanix-cloud-native/cloud-provider-nutanix

https://github.com/nutanix-cloud-native/cosi-driver-nutanix

