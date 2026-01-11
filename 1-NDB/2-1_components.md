# 2-1. 主要コンポーネント

NDBは、仮想アプライアンスとして提供されるNDB Serverで管理します。

NDB Serverには、Nutanix クラスタ（Prism Element）を登録します。

AHVホスト障害時には、NDB Serverは、一般的な仮想マシンと同様にNutanixクラスタのHA機能で自動再起動できます。NDB Serverを高可用性構成（NDB HA）にすることで、冗長化も可能ですが、この場合はNDB Serverを分散配置するため、Nutanixクラスタが3つ必要になります。

# 参考ドキュメント

https://portal.nutanix.com/page/documents/details?targetId=Nutanix-NDB-User-Guide-v2_9:top-ndb-architecture-c.html
