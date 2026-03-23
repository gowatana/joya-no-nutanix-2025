# 4-1. GUI

ここでは、NKPの管理で利用する主要なGUIを紹介します。

## NKP Dashboard
NKP Dashboardは、NKPの管理クラスタが提供するWeb UIです。Kubernetesクラスタのライフサイクル管理や、アプリケーションの管理が可能です。

## Prism Central
NKPを展開する環境の準備や、運用（監視、トラブルシュートなど）で利用します。場合によってはPrism Elementも使用しますが、NKPからはPrism Centralを介してNutanixクラスタと連携するため、基本的に管理者もPrism Centralを利用することになります。

## Grafana Dashboard
NKPのアプリとして提供され、NKP DashboardやPrism Centralよりも詳細なメトリックの確認などに利用できます。

## Kubernetes Dashboard
NKPのアプリケーションとして、Kubernetes Dashboardも提供されています。

ただし、Kubernetes DashboardのGitHubリポジトリは2026年1月にアーカイブされ、開発が停止しています。Dashboardのリポジトリでは、代替としてHeadlampが案内されています。

# 参考ドキュメント

https://github.com/kubernetes-retired/dashboard
