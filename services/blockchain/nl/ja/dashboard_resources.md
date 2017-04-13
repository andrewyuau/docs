---

copyright:
  years: 2017

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:pre: .pre}

# リソース
{: #dashboard_resources}
最終更新日: 2017 年 3 月 16 日
{: .last-updated}

この画面には、ブロックチェーン・コンポーネントの重要なネットワーク詳細とリアルタイム状況情報が含まれています。それらのコンポーネントとしては、ピア、CA、およびオーダー・ノードがあります。各コンポーネントには、**「名前」**、**「URL」**、**「状況」**、および**「アクション」**というそれぞれ異なる 4 つのヘッダーがあります。
{:shortdesc}

**図 1** に、ネットワーク・コンポーネントを表示する初期ダッシュボード画面を示します。

![ブロックチェーン・ネットワーク](images/myresources.png "マイ・リソース")
*図 1. マイ・リソース*

#### 名前

「名前」ヘッダーでは、コンポーネントの正式なシステム・レベル名が表示されます。コンポーネントの名前が `order01`、`peer01`、および `ca01` であることが分かります。  

#### URL

「URL」ヘッダーでは、各コンポーネントの API エンドポイントが表示されます。クライアント・サイド・アプリケーションから特定のネットワーク・コンポーネントをターゲットとするために、これらのエンドポイントが必要であり、その定義は通常、アプリに付随する JSON モデルの構成ファイルに存在します。自分の組織に属していないピアからの承認を必要とするアプリケーションをカスタマイズしている場合は、関連する管理者からアウト・オブ・バンド操作でそれらの IP アドレスを取得することが必要になります。クライアントは、応答を返してもらう必要のあるすべてのピアに接続できなければなりません。

#### 状況

「状況」ヘッダーでは、各コンポーネントの現在のネットワーク状態 (例えば「実行中」または「停止」など) が表示されます。

#### アクション

「アクション」ヘッダーには、コンポーネントを開始または停止するためのボタンがあります。また、コンポーネント・ログにリンクするドロップダウン・ボックスも含まれています。ログは、さまざまなネットワーク・コンポーネント間で発生するリモート・プロシージャー・コールを明らかにするもので、デバッグおよびトラブルシューティングに役立つことが分かっています。ピアを停止して、それをトランザクションでターゲットにしてみてください。gRPC 接続エラーが表示されます。今度はピアを再始動して、トランザクションを再試行すると、接続が成功します。長期間にわたってピアをダウン状態のままにすることもできます。チャネルがトランザクション処理を続行するためです。ピアが再び稼働したときに、gossip プロトコルを通じて台帳が同期化されることが分かります。ピアが完全に台帳を同期化すると、通常の呼び出しおよび照会を実行できるようになります。  

#### サービス資格情報

この画面の右上に、「サービス資格情報」タブがあります。このタブをクリックすると、各コンポーネントの低レベルのネットワーク情報 (例えば CA 用の enrollID/enrollSecret) を含む JSON ファイルが表示されます。これが、アプリケーション用に必要となる構成情報の全体です。ただし、このファイルには、自分のピア IP のみが含まれています。追加のピアをターゲットとする必要がある場合、それらのエンドポイントを取得することが必要になります。   