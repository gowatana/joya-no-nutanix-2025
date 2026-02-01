# 3-1. システム要件

## NDB Serverのリソース
NDB Serverの仮想アプライアンスを展開するNutanixクラスタを用意しておきます。NDBの管理サーバーの構成やリソース割り当ては、マルチクラスタ管理やHA機能の利用有無によって変わりますが、最小構成（マルチ クラスタ管理が無効で、NDB HAも無効）では、NDB Serverが1台だけ展開されます。この仮想マシンは、4 vCPU、16GBのメモリが割り当てられます。

NDB ServerはQCOW2ディスク イメージ、またはPrism Centralのマーケット プレイスから展開できます。ディスク イメージから展開する場合は、Nutanixクラスタ（Prism Element）があれば、仮想アプライアンスを展開可能です。


## サブネットの準備
NDB Serverの仮想アプライアンスを展開する際に、接続するサブネットを指定します。
そのため、Prism CentralまたはPrism Elementで、事前にサブネットを作成しておきます。このサブネットは、Prism CentralとPrism Elementに接続できるようにしておきます。


## iSCSI Data Services IPアドレスの設定
NDBではNutanix VolumesのVGを利用するため、事前にPrism Elementで、iSCSI Data Services IPアドレスを設定しておきます。


# 参考ドキュメント

https://portal.nutanix.com/page/documents/details?targetId=Nutanix-NDB-User-Guide-v2_9:top-vm-configuration-and-scale-r.html

https://portal.nutanix.com/page/documents/details?targetId=Nutanix-NDB-User-Guide-v2_9:top-db-network-requirements-r.html
