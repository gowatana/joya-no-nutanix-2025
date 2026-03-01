# 8-3. 推論エンジン

NAIの推論サービスでは、モデルに合わせた推論エンジンを利用します。モデルごとに、CPU・メモリ・GPUのリソース要件が異なります。

Hugging Face Hubからインポートしたモデルでは、推論エンジンとしてvLLMを利用します。
以前のバージョンのNAIではTGI（Text Generation Inference）も使用していましたが、TGIの開発がメンテナンス モードに移行されたため、今後はvLLMを利用するようです。

NVIDIA NGC Catalogからインポートしたモデルでは、推論エンジンとしてNVIDIA NIMを利用します。


# 参考ドキュメント

https://portal.nutanix.com/page/documents/details?targetId=Nutanix-Enterprise-AI-v2_5:top-nai-requirements-c.html

https://portal.nutanix.com/page/documents/details?targetId=Nutanix-Enterprise-AI-v2_6:top-nai-requirements-c.html
