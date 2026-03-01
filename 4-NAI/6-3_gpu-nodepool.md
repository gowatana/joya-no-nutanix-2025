# 6-3. GPUノード プール

Kubernetesクラスタのうち、NAIでのGPUコンテナ起動が必要になるのは、ワーカーノードです。
推論サービスのPodを起動するためのGPUを搭載したワーカー ノードは、NKPでは、GPUのノード プールとして追加します。

GPUを必要とするPodは、GPU Operatorに含まれる機能により、自動的にGPUワーカー ノードで起動されます。

さらに、Kubernetesクラスタでのスケジューリングを次のように調整することで、GPUを使用しないPodがGPUノードで起動されることを防止できます。
* nvidia.com/gpuキーを持つGPUノードを、NoScheduleでTaint。
* 推論エンドポイントのPodでは、この条件に対するTolerationを指定することで、Taintされたワーカーノードでスケジュール可能にする。


# 参考ドキュメント

https://portal.nutanix.com/page/documents/details?targetId=Nutanix-Enterprise-AI-v2_5:top-nai-requirements-c.html
