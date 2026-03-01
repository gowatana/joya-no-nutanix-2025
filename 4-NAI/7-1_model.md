# 7-1. モデル

NAIでは、Hugging Face HubまたはNVIDIA NGC Catalogから、モデルを直接インポートできます。

あらかじめNutanixが選択したモデルが、NAIのモデルカタログに登録されており、NAIのGUIからインポート可能です。

それぞれのモデル リポジトリからインポートするには、Hugging Face Hubであればアクセス トークン、NGCであればパーソナル トークンを、NAIに登録しておく必要があります。

モデル ページにあるモデルをダウンロードすると、自動的に作成されたKubernetes PV（NFS）に保存されます。KubernetesのStorageClassは次のように設定しておきます。
* Nutanix FilesのNFSサーバーを使用する
* ReadWirteMany（RWX）
* PVは動的にプロビジョニング
* PVCを作成したら、PVを即時（Immediate）バインドする

また、カスタム モデルのインポートも可能です。カスタム モデルについては、Nutanix ObjectsのBucketに保存されます。

なお、NAIが提供するのはモデル ストアであり、ファイン チューニングなどでモデルをカスタマイズする機能は持っていません。ただし、NAIとは別のツールでカスタマイズしたモデルを、NAIにインポートすることは可能です。


# 参考ドキュメント

https://portal.nutanix.com/page/documents/details?targetId=Nutanix-Enterprise-AI-v2_5:top-nai-models-c.html
