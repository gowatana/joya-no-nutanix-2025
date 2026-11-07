# 5-1. 初期展開

NDKのインストールの流れは、次のような手順になります。

## 事前準備

1. インストール先の準備（Prism Central、NKP クラスタなど）
2. kubectlとhelmを実行するマシンの用意
3. Nutanix DockerHubトークンの生成
4. CSI DriverとStorageClassの準備

NDKをインストールするKubernetesクラスタには、事前にNutanix CSI Driverをインストールして、StorageClassが作成された状態にしておきます。どちらも、NKPによるKubernetesクラスタであれば、デフォルトで準備された状態になっています。
```
$ kubectl get sc
NAME                       PROVISIONER       RECLAIMPOLICY   VOLUMEBINDINGMODE      ALLOWVOLUMEEXPANSION   AGE
nutanix-volume (default)   csi.nutanix.com   Delete          WaitForFirstConsumer   true                   13m
```

## NDKのインストール

1. Nutanix Helm Repoの追加
2. HDKのインストール

# 1. Nutanix Helm Repo の追加

Nutanix の Helm Repo は、次のように helm コマンドで追加します。
```
helm repo add ntnx-charts https://nutanix.github.io/helm-releases/
```

登録された Repo は、helm repo list で確認できます。
```
$ helm repo list
NAME            URL
ntnx-charts     https://nutanix.github.io/helm-releases/
```

この Repo には、NDK 以外にも Nutanix 製品の Chart が含まれています。
```
$ helm search repo
NAME                                            CHART VERSION   APP VERSION     DESCRIPTION
ntnx-charts/aiops                               1.0.16          1.0.0           An Umbrella Helm chart representing the Intelli...
ntnx-charts/aiops-base                          0.1.3           1.0.0           An helm chart representing the Intelligent Oper...
ntnx-charts/aiops-ui                            1.0.149         1.0.2           A Helm chart for AIOPs UI Deployment
ntnx-charts/altinity-clickhouse-operator        1.0.4           0.24.2          Helm chart to deploy [altinity-clickhouse-opera...
ntnx-charts/cfs                                 1.0.2           1.0.0           A Helm chart for Collector Framework Service (Cfs)
ntnx-charts/chakr-db-ext4                       0.0.9           1.0.0           Helm Chart for chakrdb service.
ntnx-charts/cisco-device-connector              7.5.0           1.16.1          A Helm chart for Kubernetes
ntnx-charts/clickhouse-keeper                   1.0.1           24.8.8.17       A Helm chart for SMSP
ntnx-charts/clickhouse-server                   1.0.1           24.8.8.17       A Helm chart for Clickhouse Cluster
ntnx-charts/cluster-mgmt                        1.0.19          1.0.0           A Helm chart for cluster-mgmt service.
ntnx-charts/cpaas-nats                          1.0.6           2.10.25-alpine  A Helm chart for the NATS.io High Speed Cloud N...
ntnx-charts/cpaas-ncm-schema                    1.0.4           0.1.1           A Helm chart for Clickhouse schema migration
ntnx-charts/dcis                                1.0.24          1.0.0           A Helm chart for config ingestion service in ku...
ntnx-charts/dmis                                1.0.4           1.0.0           A Helm chart for metrics ingestion service in k...
ntnx-charts/dpm                                 1.0.18          0.0.1           Helm chart for dpm service
ntnx-charts/ergon                               0.1.11          0.1.8           A Helm chart for deployment of Ergon containeri...
ntnx-charts/external-notifications-service      1.0.11          1.0.9           A Helm chart for Kubernetes
ntnx-charts/flux                                1.1.0           1.1.0           A Helm chart for Flux Service
ntnx-charts/ikat                                0.0.1736671716  0.0.1736671716  A Helm chart for Ikat Proxy and Ikat control plane
ntnx-charts/insights-collector                  0.1.61          1.0.0           A Helm chart for Insights Collector
ntnx-charts/insights-server-chakr               0.0.13          1.0.0           Helm Chart for IDF service.
ntnx-charts/ltss                                1.3.0           1.0.0           A Helm chart for Kubernetes
ntnx-charts/mercury                             0.0.1737106335  0.0.1737106335  A Helm chart for Kubernetes
ntnx-charts/msp-prometheus-collector            1.0.4           1.0.0           A Helm chart for MSP Prometheus Collector service.
ntnx-charts/nai-core                            2.5.0           0.1.0           A Helm chart for NAI core components
ntnx-charts/nai-knative-istio-controller        1.13.1          1.13.1          A Helm chart for the Knative Istio controller w...
ntnx-charts/nai-knative-serving                 1.13.1          1.13.1          A Helm chart for Knative serving
ntnx-charts/nai-knative-serving-crds            1.13.1          1.13.1          A Helm chart for installing Knative Serving CRDs
ntnx-charts/nai-operators                       2.5.0           0.1.0           A Helm chart for CRDs and Operators required by...
ntnx-charts/nc-cpaas                            1.0.3           1.0.0           An Umbrella Helm chart for CPaaS components
ntnx-charts/ncm-adonis-service                  25.1.23         25.1.23         Helm charts for NCM Adonis service.
ntnx-charts/ncm-backup                          1.0.22          1.0.19          A Helm chart for ncm-backup
ntnx-charts/ncm-base                            1.0.47          1.0.0           An Umbrella Helm chart representing the NCM bas...
ntnx-charts/ncm-calm                            1.0.89          1.0.0           Helm Chart for deploying calm service on SMSP c...
ntnx-charts/ncm-common                          1.0.83          1.0.0           An Umbrella Helm chart representing the NCM Com...
ntnx-charts/ncm-common-base                     1.0.0           1.0.0           An Helm chart representing the NCM Common Platf...
ntnx-charts/ncm-data-processor                  1.0.14          1.16.0          A Helm chart for Kubernetes
ntnx-charts/ncm-dbal-dedupe                     1.0.7           1.0.3           A Helm chart for dbal dedupe service in kubernetes
ntnx-charts/ncm-epsilon                         2.0.89          1.0.0           A Helm chart for Kubernetes
ntnx-charts/ncm-migration                       1.0.19          1.0.0           A Helm chart for Kubernetes
ntnx-charts/ncm-policy                          1.0.85          1.0.0           Helm Chart for deploying Policy Service on SMSP...
ntnx-charts/ncm-post-processor                  1.0.5           1.16.0          A Helm chart for NCM Post Processor
ntnx-charts/ncm-postgres                        1.0.1           0.0.1           Helm Chart for deploying postgres service on Mi...
ntnx-charts/ncm-release-meta                    1.5.30          1.0.0           An Helm chart used for providing NCM release me...
ntnx-charts/ncm-self-service                    1.0.20          1.0.0           An Umbrella Helm chart representing the NCM Sel...
ntnx-charts/ncm-tunnel-server                   1.0.88          1.0.0           Helm Chart for deploying NCM Tunnel Server on S...
ntnx-charts/ncs-app-aws                         1.0.0                           An Umbrella Helm Chart representing the NCS app
ntnx-charts/ncs-manifest                        1.0.0           1.0.0           A Helm chart for ncs-manifest
ntnx-charts/ndk                                 2.0.0           2.0.0           Helm chart for Nutanix Data Services for Kubern...
ntnx-charts/neuron                              1.0.16          1.0.0           Helm chart for neuron service.
ntnx-charts/nutanix-central                     1.7.0           1.0.0           An umbrella Helm chart for deployment of Nutani...
ntnx-charts/nutanix-csi-snapshot                6.3.3           6.3.3           Snapshot components required for CSI snapshotti...
ntnx-charts/nutanix-csi-storage                 3.3.9           3.3.9           Nutanix Container Storage Interface (CSI) Driver
ntnx-charts/nutanix-infra-data-receiver         1.0.25          1.16.0          A Helm chart for Kubernetes
ntnx-charts/nutanix-infrastructure-manager      7.5.0           7.5.0           Helm charts for Nutanix Infrastructure Manager ...
ntnx-charts/nutanix-k8s-agent                   1.0.426         1.0.426         A Helm chart for onboarding a Kubernetes cluste...
ntnx-charts/onboarding-svc                      1.0.11          1.0.0           A Helm chart for onboarding service.
ntnx-charts/otel-collector                      1.0.1           1.0.0           A Helm chart for OpenTelemetry Collector
ntnx-charts/pc-app-aws                          7.5.9                           An Umbrella Helm chart representing the PC Plat...
ntnx-charts/pc-app-azure                        7.5.9                           An Umbrella Helm chart representing the PC Plat...
ntnx-charts/pc-app-gcp                          7.5.1                           An Umbrella Helm chart representing the PC Plat...
ntnx-charts/pc-app-onprem                       7.5.36                          An Umbrella Helm chart representing the PC Plat...
ntnx-charts/pc-registration-config              1.0.2           1.0.0           A Helm chart for node proxy configuration on PC.
ntnx-charts/reports                             1.0.11          1.0.0           A Helm chart for reporting service.
ntnx-charts/search                              1.0.24          1.0.0           A Helm chart for Search Service.
ntnx-charts/signals-manager                     1.0.16          1.0.1           Helm chart for signals-manager service.
ntnx-charts/sizer                               1.0.0           1.0.0           Helm chart for neuron sizer service.
ntnx-charts/smsp-registration-config            1.0.1           1.0.0           A Helm chart for node proxy configuration on S-MSP
ntnx-charts/sqlserver                           0.0.29          0.0.1           A Helm chart for aiops sqlserver collector
ntnx-charts/statsgw                             1.0.18          1.0.0           A Helm chart for Stats Gateway Kubernetes
ntnx-charts/uda                                 1.0.25          1.0.24          Helm chart for uda engine service.
ntnx-charts/vcenter                             0.0.29          0.0.1           A Helm chart for aiops vcenter collector
ntnx-charts/vulcan                              1.0.9           1.0.0           Helm chart for vulcan service.
ntnx-charts/zeus-collector                      1.0.5           1.0.0           A Helm chart for Zeus Collector
ntnx-charts/zookeeper                           0.0.6           1.0.0           Helm Chart for Zookeeper service.
```

NDKのChartは、下記のように確認できます。なお、最新以外のバージョンも表示したい場合は、「--versions」オプションで実行します。
```
$ helm search repo ntnx-charts/ndk
NAME            CHART VERSION   APP VERSION     DESCRIPTION
ntnx-charts/ndk 2.0.0           2.0.0           Helm chart for Nutanix Data Services for Kubern...
```

NDKのChartは、次のようになっています。
```
$ helm show chart ntnx-charts/ndk
annotations:
  artifacthub.io/changes: |
    - Initial release
  artifacthub.io/containsSecurityUpdates: "true"
  artifacthub.io/displayName: NDK
  artifacthub.io/maintainers: |
    - name: Nutanix Cloud Native Team
      email: cloudnative@nutanix.com
apiVersion: v2
appVersion: 2.0.0
description: Helm chart for Nutanix Data Services for Kubernetes (NDK). NDK provides
  for application-centric data management services for containerized workloads managed
  by Kubernetes.
home: https://github.com/nutanix-core/k8s-juno
icon: https://avatars2.githubusercontent.com/u/6165865?s=200&v=4
keywords:
- Nutanix
- Storage
- Volumes
- Files
- StorageClass
- RedHat
- CentOS
- Ubuntu
- Snapshot
- AppProtection
kubeVersion: '>= 1.26.0-0'
maintainers:
- email: cloudnative@nutanix.com
  name: nutanix-cloud-native-bot
name: ndk
type: application
version: 2.0.0
```

# 2. NDK のインストール

NDKは、次のようにhelm installコマンドでインストールできます。imageCredentialsで指定するレジストリのログイン情報は、Nutanix Support & Insights PortalのNDKのダウンロード ページで入手できます。
```
helm install ndk ntnx-charts/ndk \
--version 2.0.0 \
-n ntnx-system \
--set config.secret.name=nutanix-csi-credentials \
--set imageCredentials.credentials.username=$DOCKER_USERNAME \
--set imageCredentials.credentials.password=$DOCKER_PASSWORD \
--set tls.server.enable=false
```

インストール コマンドを実行したら、下記のようにndk-controller-managerのPodがRunningになるまで待ちます。
```
$ kubectl -n ntnx-system get pod -l app.kubernetes.io/name=ndk
NAME                                      READY   STATUS    RESTARTS   AGE
ndk-controller-manager-754bcbf7d4-dnctw   4/4     Running   0          2m25s
```

そして、LoadBalancer Serviceとして「ndk-intercom-service」が作成されます。このロード バランサーは、デフォルトではMetalLBが使用されます。
```
$ kubectl get svc -n ntnx-system ndk-intercom-service
NAME                   TYPE           CLUSTER-IP      EXTERNAL-IP    PORT(S)          AGE
ndk-intercom-service   LoadBalancer   10.105.122.58   172.22.5.222   2021:31787/TCP   130m
```

なお、NDKのアンインストールでも、helmコマンドを使用します。
```
$ helm uninstall ndk -n ntnx-system
release "ndk" uninstalled
```

# 参考ドキュメント
https://portal.nutanix.com/page/documents/details?targetId=Nutanix-Data-Services-for-Kubernetes-v2_0:top-install-ndk-nonairgap-t.html
