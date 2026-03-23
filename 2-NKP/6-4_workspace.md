# 6-4. NKPのワークスペース

NKPでは、Kubernetesクラスタの集合である「フリート」の管理において「ワークスペース」「プロジェクト」という管理単位を用います。これらは、管理クラスタに作成されるNKP独自のKubernetesリソースであり、NKP DashboradやCLI（nkpまたは kubectl）で管理できます。

ワークスペースは、Kubernetesクラスタをグループ化して、クラスタのアップデートやアプリケーションインストールの対象管理などで利用できます。IDプロバイダーについてもワークスペース単位で設定可能であり、NKPをマルチテナントで利用する場合には、テナントの分割に利用できます。
ワークスペースを作成すると、管理クラスタではそれに対応するNamespaceが作成されます。そして、ワークスペースにワークロードクラスタを作成すると、対応するClusterリソースはこのNamespaceに作成されます。

# 参考ドキュメント

https://portal.nutanix.com/page/documents/details?targetId=Nutanix-Kubernetes-Platform-v2_17-ja-JP:top-workspaces-c.html
