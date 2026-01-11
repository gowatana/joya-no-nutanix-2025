# 2-2. 前提となるNutanix製品

## Prism Element

NDBでは、DBサーバーの仮想マシンやProtection Domainを使用しています。NDB Serverには、Prism Element（Nutanixクラスタ）を登録します。

## Prism Central
NDB Serverはディスク イメージからデプロイできますが、Prism Centralのマーケット プレイスでのデプロイも可能です。（ただしバージョンは古めで、複数回のアップデートが必要）

## Nutanix Volumes Storage

データベースやトランザクション ログのストレージとして、Nutanix VolumesによるiSCSIブロック デバイスを使用します。
そのため、Prism Elementでは、NDB Serverと連携する前にData Services IPアドレスを設定しておきます。

# 参考ドキュメント
