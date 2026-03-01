# 7-3. エンドポイントのハイバネート

NAIの推論サービス エンドポイントは、ハイバネートにより一時的に停止できます。

CPUとは異なり、PodにGPUを割り当てると、そのPodが占有してしまいます。エンドポイントをハイバネート状態にすること、エンドポイントの設定やAPIキーの割り当てはそのまま残りますが、推論ポッドが削除された状態になります。使用していないCPUとメモリだけでなくGPUも開放でき、そのぶんGPUを必要とするほかのエンドポイントを起動できるようになります。

# 参考ドキュメント

https://portal.nutanix.com/page/documents/details?targetId=Nutanix-Enterprise-AI-v2_5:top-nai-endpoint-hibernation-c.html
