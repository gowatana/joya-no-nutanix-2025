# 前提となるNutanix製品

## Nutanix Kubernetes Platform
NDKの主なインストール先。ただし、ほかにもEKSとOpenShiftに対応している。
NDKの、NKPのカタログ アプリケーションも公開されている。（調査中）

## Prism Element
NDKが、StorageClusterとして扱う。

## Prism Central
NDKがPrism EementをStorageClusterとして扱う際、管理のための接続先はPrism Centralになる。
DRの機能（Recovery Pointなど）も利用されている。


## Nutanix Cloud Controller Manager
NKPのクラスタには、Kubernetesがプロビジョニングされるインフラ特有の設定などを管理するCloud Controller Manager（CCM）として、Nutanix Cloud Controller Manager がインストールされる。
主な役割として、Kubernetesノードにトポロジ情報のラベルを付与します。仮想マシンのPrism配置ベースのトポロジ検出により、デフォルトではノード仮想マシンをホストするPrism ElementとPrism Centralを検出してノードのラベルを決定しており、Prism Centralはリージョン、Prism Elementはゾーンとして設定されます。


# 連携するNutanix製品

## NK
Prism CentralにKubernetesクラスタを登録する。

調査中

## Cloud Native AOS
AOSがない環境（EKSやベアメタルKubernetesなど）でNDKを使用する際に、AOSをKubernetes Podとして起動するソリューション。
ただし、いまのところEKSのみ対応。


# 参考ドキュメント
