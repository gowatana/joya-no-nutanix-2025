# 5-3. 利用開始

NDKには専用のGUIがなく、基本的にkubectlなど一般的なKubernetes管理ツールで操作します。

kubectlで、NDKをインストールしたKubernetesにアクセスする準備（kubeconfigファイルの配置など）を実施しておきます。この例では、下記のようにKubernetesクラスタにアクセスしてノード情報が取得できるようにしてあります。
```
$ kubectl get nodes
NAME                            STATUS   ROLES           AGE   VERSION
nkpndk-md-0-zv4pm-jkcdc-mz4mg   Ready    <none>          69m   v1.33.5
nkpndk-p82sm-twt5k              Ready    control-plane   70m   v1.33.5
```

このクラスタにはNDKがインストールされており、ndk-controller-managerのPodが起動されています。
```
$ kubectl get pods -n ntnx-system -l app.kubernetes.io/name=ndk
NAME                                      READY   STATUS    RESTARTS   AGE
ndk-controller-manager-754bcbf7d4-2jlhg   4/4     Running   0          2m10s
```

NDKのStorageClusterとして、Nutanixクラスタ（Prism Element）を登録してあります。
```
$ kubectl get storageclusters.dataservices.nutanix.com
NAME         AVAILABLE
st-cluster   true
```

# 参考ドキュメント
https://portal.nutanix.com/page/documents/details?targetId=Nutanix-Data-Services-for-Kubernetes-v2_0:top-storageclusters-set-up-cli-k8s-t.html
