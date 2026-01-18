# 3-1. システム要件

NAIをNKPにインストールする場合の、システム要件について説明します。

## ソフトウェア要件の考慮点
NAIには、インストール先のKubernetesや多くの関連OSSとのソフトウェア要件があります。NKPにインストールする場合は、まず互換性のあるバージョンのNKPを選定することで、多く関連OSSのバージョンを決定できます。NKPに含まれているOSSはNKPのカタログからインストールし、含まれていないOSSの利用バージョンを選定います。

NKPを利用する場合には、おもに下記のソフトウェアについてバージョン選定が必要です。

* Nutanix製品
  - Nutanix Files
  - Nutanix Objects 
* OSS
  - KServe
  - Envoy Gateway

## ハードウェア要件の考慮点

NAIでは、LLMを利用するソリューションなので、サポート対象のGPUもNutainxから指定されています。

NAI 2.5では、次のGPUがサポート対象です。
* NVIDIA Ada Lovelace L40S
* NVIDIA Hopper H100
* NVIDIA Hopper H100-NVL
* NVIDIA Ampere A100
* NVIDIA Hopper H200
* NVIDIA RTX PRO 6000 Blackwell Server Edition


# 参考ドキュメント

https://portal.nutanix.com/page/documents/details?targetId=Nutanix-Enterprise-AI-v2_5:top-nai-requirements-c.html

https://portal.nutanix.com/page/documents/details?targetId=Release-Notes-Nutanix-Enterprise-AI-v2_5:rel-nai-software_requirements-r.html

※要ログイン
