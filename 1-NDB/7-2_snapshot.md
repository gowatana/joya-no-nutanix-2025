# 7-2. スナップショットの取得

NDBでは、データベースのリストアやクローンの前提として、タイムマシンにてスナップショットを取得しておく必要があります。


## 手動でのスナップショット取得

NDBのスナップショットは、ソースDBに割り当てられたタイムマシンで取得します。


## 自動でのスナップショット取得

定期的なスナップショットの自動取得は、NDBのSLAで設定します。SLAでは、スナップショットの取得間隔（頻度）と、保存期間を設定できます。


## サニタイズされたスナップショットの取得

NDBでは、サニタイズされたスナップショットを取得して、そこから機密情報を消去したクローンDBを作成できます。この機能では、クローンDBでデータをサニタイズする、ポスト スクリプトを用意する必要があります。


# 参考ドキュメント

https://portal.nutanix.com/page/documents/details?targetId=Nutanix-NDB-User-Guide-v2_9:top-manual-snapshots-create-t.html

https://portal.nutanix.com/page/documents/details?targetId=Nutanix-NDB-User-Guide-v2_9:top-sanitized-snapshots-c.html

https://portal.nutanix.com/page/documents/details?targetId=Nutanix-NDB-User-Guide-v2_9:top-sanitised-snapshot-create-t.html

https://portal.nutanix.com/kb/17478
