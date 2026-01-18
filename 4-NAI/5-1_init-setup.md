# 5-1. 初期展開

NKPにNAIをインストールする事前準備としては、つぎのものが挙げられます。
1. NKPクラスタの用意（AHV、Prism Central、NKPクラスタ）
2. Nutainx FilesによるNFSサーバーの用意
3. 作業環境の用意（NKP展開時の環境を流用可能）
4. NKPクラスタでのGPUノード プール追加
5. NKPクラスタでのNFSサーバー用StorageClass作成
6. 関連ソフトウェアのインストール（GPU-Operator、Envoy Gateway、KServe）

ここでは、カスタム モデルのインポートで利用するNutainx Objectsの用意は省略しています。

NAIのインストールは、下記の方式があります。ここでは、Helmによるインストールについて説明します。
* Helmによるインストール
* NKPカタログでのインストール

HelmによるNAIのインストールは、つぎの手順となります。

1. Nutanix Docker Hub トークンの入手
2. Nutanix Helm Repo の登録
3. nai-core のインストール


# 参考ドキュメント
https://portal.nutanix.com/page/documents/details?targetId=Nutanix-Enterprise-AI-v2_5:top-NAI-on-NKP-c.html
