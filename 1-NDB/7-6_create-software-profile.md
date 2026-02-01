# 7-6. ソフトウェア プロファイルの作成

NDBでは、Oracle DatabaseやSQL ServerにはOOBのソフトウェア プロファイルが用意されていません。

ソフトウェア プロファイルを作成するには、まずDBMSがインストールされたDBサーバーVMを用意し、NDBに登録してそこからソフトウェア プロファイルを作成します。

つまり、NDBによるDB管理を開始するには、基本的には最初に手作業でDBサーバを構築する必要があります。

当然ながら、各DBMSの全てのバージョンがサポートされるわけではないため、NDBのドキュメントなどで、DBMSごとにサポート対象バージョンを確認する必要があります。
また、Oracle DatabaseとSQL Serverについては、DBMSバージョンごとにサポートされるOSがドキュメントに記載されています。

> - [Blog] NDB で PostgreSQL DB をプロビジョニングしてみる。（OOB 編）  
>   https://blog.ntnx.jp/entry/2022/12/08/233530
> - [Blog] Nutanix の NDB と Oracle Database。  
>   https://blog.ntnx.jp/entry/2022/12/07/235802
> - [Blog] NDB で DB をプロビジョニングしてみる。（Oracle CDB）  
>   https://blog.ntnx.jp/entry/2022/12/15/030326
> - [Blog] NDB での DB / DB サーバの削除の様子。（Oracle）  
>   https://blog.ntnx.jp/entry/2022/12/14/231934
> - [Blog] Nutanix の NDB と Oracle Database。補足編（DB Server と DB の同時登録）  
>   https://blog.ntnx.jp/entry/2023/05/03/154512


# 参考ドキュメント
