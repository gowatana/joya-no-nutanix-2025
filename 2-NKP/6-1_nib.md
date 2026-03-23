# 6-1. Nutanix Image Builder

Cluster APIによるKubernetesクラスタ展開には、Cluster API用に準備したOSイメージが必要です。CAPXでは、OSディスクイメージをPrism Centralのイメージサービスに登録しておきます。

OSとしては、Rocky Linux、Ubuntu、RHELなどが利用でき、Nutanixからは、Rocky LinuxとUbuntuのイメージが提供されています。ただし、NKP Starterでは、そのうちのRocky Linuxのイメージのみが利用可能です。

ディスクイメージはSupport & Insight Portalで提供されていますが、それ以外のOSや、GPUドライバ追加などのカスタマイズイメージが必要な場合は、ディスクイメージのビルドが必要です。

NKPでKubernetesクラスタをプロビジョニングするコンポーネントは、Konvoyとよばれています。

AHVで利用するOSイメージはNutanix Image Builder（NIB）、それ以外のプラットフォーム用のイメージについてはKonvoy Image Builder（KIB）と呼ばれるCLIで作成します。NIBはnkp CLIに組み込まれており、KIBは独立したバイナリとして提供されています。

NIBおよびKIBでは、AHV用のディスクイメージの作成にはコンテナ環境（DockerまたはPodman）とPacker 、Cluster API用のパッケージ追加や設定にはAnsible が内部的に利用されています。そのため、nkpコマンドでイメージを作成する環境としてもDockerまたはPodmanをインストールしておく必要があります。

# 参考ドキュメント

https://portal.nutanix.com/page/documents/details?targetId=Nutanix-Kubernetes-Platform-v2_17-ja-JP:top-nutanix_image_builder-c.html
