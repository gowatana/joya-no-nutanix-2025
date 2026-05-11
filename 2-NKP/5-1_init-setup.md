# 5-1. 初期展開

まずは、AHVのNutanixクラスタでのセットアップについて説明します。


## ブートストラップ用マシンの用意

Cluster APIで管理クラスタを展開する際に、一時的にブートストラップ クラスタが作成されます。NKPでは、このクラスタの作成にkind（Kubernetes in Docker）が利用されます。そのため、NKPでKubernetesクラスタを作成するためにnkpコマンドを実行するマシンには、DockerまたはPodmanのインストールが必要です。なお、kindについてはnkpコマンドに組み込まれているため、単独でのインストールは不要です。

## 管理クラスタの展開

NKPの管理クラスタは、NKP CLI（nkpコマンド）で展開できます。nkpコマンドでは、TUIを起動してフォーム入力による展開ができますが、CLIにオプションを指定して実行することも可能です。管理クラスタを展開すると、自動的にNKP Dashboardも起動されます。

# 参考ドキュメント

https://portal.nutanix.com/page/documents/details?targetId=Nutanix-Kubernetes-Platform-v2_17-ja-JP:top-nutanix-infrastructure-options-t.html
