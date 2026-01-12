# 3-2. ラボ環境

ラボ環境を構成する際の考慮点です。
* Nutanixクラスタは、1ノード構成でもNDKはインストール可能。ただし、NKPノードの仮想マシンを起動できるリソースは必要。
* Prism Centralも1ノード構成でNDKはインストール可能。レプリケーションを試すには、NKPクラスタを複数作成する。
* NKPクラスタは、コントロール プレーン ノード 1台、ワーカー ノード1台の最小構成でも展開可能。ただし、NKPカタログでのNDKインストールを試す場合は、NKP Ultimateが必要になるので、NKPの要件に従ったリソースが必要になる。
* Nutanix CSI DriverのバージョンにNDKの互換性がない場合は、NKPクラスタでCSI Driver単体のバージョンアップも可能。しかし、基本的にはNKPごとバージョンアップする。

# 参考ドキュメント
https://portal.nutanix.com/page/documents/details?targetId=Nutanix-Data-Services-for-Kubernetes-v2_0:top-prerequisites-k8s-c.html
