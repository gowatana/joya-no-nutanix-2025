# 4-2. CLI

## NKP CLI
NKPでは、管理クラスタのデプロイや、クラスタのライフサイクル管理などで、NKP CLI（nkpコマンド）を使用します。

NKP CLIには、KubernetesノードのOSイメージを作成するNutanix Image BuilderとKonvy Image Builderも組み込まれています。

また、NKP Catalogむけのアプリケーション パッケージの作成でも、NKP CLIを使用します。

## kubectl
NKPの管理クラスタおよび管理対象クラスタでも、一般的なKubernetesクラスタと同様にkubectlコマンドを利用します。

## Helm
NKPのアプリケーション管理の対象は、NKP独自のカタログ バンドル化されたものです。NKPカタログの形式にパッケージングされていないアプリケーションのインストールでは、Helmを利用するケースもあります。

# 参考ドキュメント
