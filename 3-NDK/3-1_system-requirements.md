# 3-1. システム要件

NKPで利用するケースにおいて、ソフトウェア互換性の考慮が必要なものは次のものです。
* AOS
* AHV
* Prism Central
* Helm
* Nutanix CSI Driver（NKPのバージョンと紐づきあり）
* Nutanix Kubernetes Platform
* Nutanix Konnector

NDKのインストール前に、下記をセットアップしておく必要があります。
* Prism Element（Nutanixクラスタ）
* Prism Central（Prism Elementを登録しておく）
* NKPクラスタ（Nutanix CSI Driverは自動インストールされる）

# 参考ドキュメント
https://portal.nutanix.com/page/documents/details?targetId=Nutanix-Data-Services-for-Kubernetes-v2_0:top-prerequisites-k8s-c.html
