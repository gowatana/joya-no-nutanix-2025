# 3-2. ラボ環境

NAIのシステム要件では、CPU/メモリが大容量必要であり、GPUも必要とされています。

ただし、NAIのUI確認などの用途であれば、GPUが搭載されていないNKPクラスタにHelmでインストール可能です。この場合、UI設定やモデルのインポートは可能ですが、エンドポイントは作成できません。

NAI（nai-core）自体はあまり多くのリソースを必要としませんが、前提となるNKP Pro/Ultimateのリソース要件が大きいため、結局のところ、リソース割り当ての大きなKubernetesクラスタが必要となります。

# 参考ドキュメント
https://portal.nutanix.com/page/documents/details?targetId=Nutanix-Enterprise-AI-v2_5:top-nai-requirements-c.html
