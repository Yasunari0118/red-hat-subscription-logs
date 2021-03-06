# 第9章 Web コンソールを使用したクラスターの管理

## クラスター管理の実行

Web コンソールを使用してクラスター管理を実行できるようになる。

### Web コンソールの説明

- Home

ダッシュボードには、健全性メトリクス、リソース数、イベント (マシン更新やポッドの障害など) のストリーミングリストといったクラスターの概要が表示されます。

[Home] → [Search] ページに移動して、あらゆるタイプのリソースを検索または作成できます。また、このページはメニュー内に専用のナビゲーションを持たないリソース (Groups など) に移動する際の始点として役立ちます。

[Home] → [Events] ページは、クラスター内で生じるイベントのフィルタリング可能なストリームを表示するため、トラブルシューティングに役立つ開始点となります。 


- Operators

OperatorHub を使用して、Red Hat によって管理されるオペレーターを検索およびインストールし、[Installed Operators] ページに移動してオペレーターを管理します。 


- Workloads、Networking、Storage

デプロイ、サービス、永続ボリュームなどの一般的なリソースを管理します。トラブルシューティングで特に重要なのは、ポッドログを表示してターミナルに接続できることです。 


- Builds

ビルド設定、ビルド、およびイメージストリームを管理します。 


- Monitoring

アラートを表示し、アドホック Prometheus クエリーを実行します。 


- Compute

ノード、マシン、マシン自動スケーラーなどの計算リソースを表示および管理します。 


- Administration

クラスター更新、クラスターオペレーター、CRD、ロールバインディング、リソースクォータなど、クラスター管理者にとって特に重要なさまざまな設定を表示および管理します。 


## OpenShift Web コンソールへのアクセス

Openshift Web コンソールは **openshift-console プロジェクトのポッド**として実行され、**openshift-console-operator プロジェクト**で実行されるオペレーターによって管理されます。

実稼働以外のシステムでは、一般的に HTTPS エンドポイントに自己署名証明書が使用されます。初めて Web コンソールに移動すると、Web ブラウザーに証明書についての警告が表示され、セキュリティの例外を追加する必要があります。 


## プロジェクトの作成

Red Hat では、マルチテナントクラスターを担当する管理者がリソースクォータと制限範囲 (総プロジェクト制限と総コンテナー制限をそれぞれ適用する) を設定することを推奨しています。

[Administration] → [Resource Quotas] または [Administration] → [Limit Ranges] に移動して、これらの制限を設定できる適切な YAML エディターにアクセスします。 


## 制限について

OpenShift Web コンソールは、OpenShift クラスターをグラフィカルに管理できる強力なツールですが、**一部の管理タスクは現在 Web コンソールでは利用できません。**

たとえば、ノードログを表示してノードデバッグセッションを実行するには、oc コマンドラインツールが必要です。 