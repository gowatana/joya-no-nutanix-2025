# 4-3. API

NKPでのKubernetesクラスタ管理を自動化する場合、Cluster APIによるKuberneteカスタム リソースとして扱います。

つまり、NKP独自のREST APIが公開されているのではなく、Kuberneteリソースのマニフェストでクラスタを宣言的に定義して、NKPの管理クラスタに適用します。

たとえば、Terraformを活用する場合には、Kuberneteを操作するためのTerraform Provider（hashcorp/kubernetes）を利用できます。

# 参考ドキュメント

https://www.nutanix.dev/2025/10/22/how-to-deploy-a-kubernetes-cluster-in-the-nutanix-kubernetes-platform-using-terraform/
