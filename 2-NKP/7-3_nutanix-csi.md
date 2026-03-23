# 7-3. Nutanix CSI Driver

Kubernetesでは、コンテナの削除後もデータを保持するために永続ボリューム（PV）を利用します。そして、ストレージをPVとして扱うための仕組みとして、Container Storage Interrace（CSI）が用意されています。

NutanixからはNutanix CSI Driverが提供されており、Nutanixのストレージサービスと連携した、PVのプロビジョニング、スナップショット取得、クローンなどに対応しています。Nutanix VolumesからはVolume GroupによるiSCSIブロックデバイス、Nutanix FilesからはNFS共有をPVとして提供でき、PersistentVolumeClaim（PVC）の作成に合わせてPVを作成する動的プロビジョニングにも対応しています。

NKPでAHVにプロビジョニングされたKubernetesノードでは、Nutanix CSI DriverとVolume Group接続に必要なiSCSIイニシエーターがインストールされた状態になります。


# 参考ドキュメント

https://portal.nutanix.com/page/documents/details?targetId=CSI-Volume-Driver-v3_3:CSI-Volume-Driver-v3_3
