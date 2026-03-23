# 3-1. システム要件

NKPでは、Kubernetesクラスタの種類ごと（管理クラスタと管理対象クラスタそれぞれ）に、リソースの最小要件があります。

最小要件を満たしていない場合、管理クラスタの作成直後にはリソースに余裕がありますが、Pro/Ultimateのライセンス キーを適用するとCPU/メモリといったリソースが枯渇します。

また、ドキュメントにあるリソース要件は、要件のノード数を満たした状態でのCPU/メモリ割り当てです。つまり、シングル ノードなどに台数を減らして展開する場合は、ノード当たりのリソース割り当てを増やして要件を満たす必要があります。

# 参考ドキュメント

https://portal.nutanix.com/page/documents/details?targetId=Nutanix-Kubernetes-Platform-v2_17-ja-JP:top-resource-req-pro-and-ultimate-cluster-min-r.html
