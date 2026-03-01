# 8-4. エンドポイントのAPI

NAIの提供する推論サービス エンドポイントのREST APIは、OpenAI APIのものと互換性があります。
たとえばAIアプリからNAIのエンドポイントにアクセスする場合には、OpenAIのサービスと同様に、Pythonのopenaiモジュールなどが利用できます。

NAI 2.6では、下記のURLがサポートされています。これらのURLは、モデルの種類によって使い分けることになります。

* [/v1/chat/completions](https://developers.openai.com/api/reference/chat-completions/overview)
* [/v1/models](https://developers.openai.com/api/reference/resources/models)
* [/v1/embeddings](https://developers.openai.com/api/reference/resources/embeddings/methods/create)
* [/v1/images/generations](https://developers.openai.com/api/reference/resources/images)
* [/v1/audio/transcriptions](https://developers.openai.com/api/reference/resources/audio/subresources/transcriptions/methods/create)
* [/v1/audio/translations](https://developers.openai.com/api/reference/resources/audio/subresources/translations/methods/create)

# 参考ドキュメント

https://portal.nutanix.com/page/documents/details?targetId=Nutanix-Enterprise-AI-v2_6:top-nai-access-open-ai-clients-t.html
