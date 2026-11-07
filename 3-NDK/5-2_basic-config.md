# 5-2. 基本設定

ここでは、NDKを利用するために、Nutanixクラスタを「StorageCluster」として登録します。
1. Prism CentralのUUIDを確認する
2. Prism ElementのUUIDを確認する
3. StorageClusterリソースを作成する

Prism CentralおよびPrism ElementのUUIDは、PCVMおよびCVMで「ncli cluster info」を実行して確認します。


確認したUUIDを指定して、Prism Elementに対応するStorageClusterリソースを作成します。API（dataservices.nutanix.com）からわかるように、これはNDK独自のKubernetesカスタム リソースです。

例：storage-cluster.yml

```
---
apiVersion: dataservices.nutanix.com/v1alpha1
kind: StorageCluster
metadata:
  name: st-cluster
spec:
  managementServerUuid: 16222475-b017-4c43-XXXX-XXXXXXXXXXXX
  storageServerUuid: 00063c9a-1efe-0a33-XXXX-XXXXXXXXXXXX
```

StorageClusterリソースは、kubectlでYAMLを適用して作成します。
```
$ kubectl apply -f storage-cluster.yml
storagecluster.dataservices.nutanix.com/st-cluster created
```

StorageClusterを作成したら、AVAILALE: true になることを確認します。
```
$ kubectl get storageclusters.dataservices.nutanix.com
NAME         AVAILABLE
st-cluster   true
```


# 参考ドキュメント

https://portal.nutanix.com/page/documents/details?targetId=Nutanix-Data-Services-for-Kubernetes-v2_0:top-dataservices-configs-k8s-c.html
