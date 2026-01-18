# 4-3. API

# NAIの利用

NAI自体の操作についてのREST APIは公開されていません。
ただし、NAIで作成されるモデルとエンドポイント（InferenceService）については、kubectlでも操作できます。

# エンドポイントの利用

NAIで作成した推論サービス エンドポイントは、OpenAI 互換クライアントから利用できます。クライアントには、エンドポイントのURLと、NAIで発行したAPIキーが必要です。

OpenAI APIのうち、下記に対応しています。

/v1/images/generations
https://platform.openai.com/docs/api-reference/images/create

/v1/chat/completions
https://platform.openai.com/docs/api-reference/chat

/v1/models
https://platform.openai.com/docs/api-reference/models

v1/embeddings
https://platform.openai.com/docs/api-reference/embeddings/create

# 参考ドキュメント
https://portal.nutanix.com/page/documents/details?targetId=Nutanix-Enterprise-AI-v2_5:top-nai-access-open-ai-clients-t.html
