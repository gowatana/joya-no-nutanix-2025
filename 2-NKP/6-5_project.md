# 6-5. NKPのプロジェクト

NKPのプロジェクトは、ワークスペース内でのKubernetesクラスタを横断してNamespaceを活用するものです。

プロジェクトの実体は、管理クラスタ側で、ワークスペースに対応するNamespaceに作成されるKubernetesカスタムリソースです。そして、Prism Centralのもつ機能のひとつであるプロジェクトとは無関係のものです。

プロジェクトを作成すると、各ワークロードクラスタには対応するNamespaceが作成されます。これにより、ワークスペースに含まれるKubernetesクラスタを横断して、アプリを展開する際に有用なものです。
たとえば、Kubernetesクラスタをまたぐロールの割り当て、設定やレジストリ認証情報（ConfigMapやSecret）などの共有、ネットワークやセキュリティのポリシー適用、継続的デリバリー（CD）の実装などが実現できます。

また、NKPでは、アプリのインストールの対象指定でも、ワークスペースやプロジェクトを活用します。


# 参考ドキュメント

https://portal.nutanix.com/page/documents/details?targetId=Nutanix-Kubernetes-Platform-v2_17-ja-JP:top-projects-c.html
