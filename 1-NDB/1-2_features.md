# 1-2. 主要機能

NDB によって提供される主要な機能として、次のものがあります。
* 1-Click プロビジョニング
* コピー データ管理（CDM：Copy Data Management）
* DB 保護（バックアップ / リストア）
* 1-Click パッチ適用

Nutanix NDB は、Nutanix HCI 上での DB サーバ仮想マシンを管理対象とします。

つまり、Nutanix の外部で稼働している DB サーバは、物理マシン / 仮想マシンのいずれの場合も管理できません。
そのため既存の DB サーバを NDB で管理するためには、なんらかの方法で Nutanix HCI 上の仮想マシンとして移行する必要があります。

また、NDB の管理サーバ（NDB Server）も、Nutanix HCI 上で稼働している必要があります。


# 管理対象の DBMS

NDB では、次の DBMS を管理できます。

* PostgreSQL
* Oracle Database
* Microsoft SQL Server
* MySQL
* MariaDB
* MongoDB

# 参考ドキュメント

https://portal.nutanix.com/page/documents/details?targetId=Nutanix-NDB-User-Guide-v2_9:top-services-c.html
