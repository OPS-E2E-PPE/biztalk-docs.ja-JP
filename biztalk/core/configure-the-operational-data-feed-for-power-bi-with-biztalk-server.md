---
title: "オペレーション データを BizTalk Server で Power BI にフィードの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fe6d3a97-c7c0-4147-baa9-ee12f93248eb
caps.latest.revision: "11"
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: 09b1b1fd7f350e168b2bb13d6bee2e45c12d49cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-operational-data-feed-for-power-bi-with-biztalk-server"></a>BizTalk Server で Power BI にフィード オペレーション データを構成します。
OData フィードによって提供されるオペレーション データを読み取る[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]です。 

**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**追跡を指定すると、Power BI テンプレートを使用して Power BI に送信します。 または、独自に作成します。 

## <a name="what-is-operational-data"></a>オペレーション データとは
オペレーション データは、インスタンスおよび経由でやり取りされるメッセージに関する情報、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]環境。 オペレーション データ フィードは、同じデータのグループ ハブを見ることの取得、[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]コンソールです。 データにアクセスできるし、Power BI を含む視覚化ツールを使用してクエリを実行します。 

フィードには、次のデータ テーブルが含まれています。
* アプリケーション データ
* AS2 状態レコード
* バッチ処理の情報
* インスタンス情報
* インターチェンジの集計レコード
* インターチェンジの状態レコード
* メッセージ
* サブスクリプション
* 追跡イベント
* トランザクションのレポート
* トランザクション セット

> [!TIP]
> [PowerBI.com](http://powerbi.microsoft.com)を理解し、Power BI の詳細です。

## <a name="prerequisites"></a>前提条件
* ダウンロードしてインストール[Power BI Desktop](https://powerbi.microsoft.com/desktop/)ネットワーク アクセス権を持つ任意のコンピューターで、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]
* インストール[機能パック 1](https://www.microsoft.com/download/details.aspx?id=55100)で、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]
* IIS をインストール、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]です。 ほとんどの[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]環境では、IIS が既にインストールされています。 参照してください[Hardware and Software Requirements for BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)です。 

## <a name="enable-operational-data-feed"></a>運用上のデータ フィードを有効にします。

1. Windows PowerShell を管理者として実行 (**開始**メニューで、「 **PowerShell**、右クリックし、、選択**管理者として実行**)。 
2. フォルダーを参照場所[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]がインストールされている**Program Files (x86)/microsoft BizTalk Server 2016**
3. 次のコマンドを実行します。 更新してください、 `website`、 `domain\user`、 `password`、および`domain\group`実際の値にします。 

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service operationaldata -WebSiteName '<Default Web Site>' -ApplicationPool <operationalDataServiceAppPool> -ApplicationPoolUser <domain>\<user> -ApplicationPoolUserPassword <password> -AuthorizationRoles '<domain>\<group1>, <domain>\<group2>'
    ```
4. スクリプトを実行した後は、新しい IIS アプリケーションを参照してください。  
    1. Web ブラウザーを開きます
    2. 移動して**http://localhost/BizTalkOperationalDataService**

## <a name="use-the-power-bi-template"></a>Power BI テンプレートを使用します。
Power BI テンプレート ファイルにアクセスし、Microsoft から提供されている視覚エフェクトを使用するには、次の手順を使用します。

1. ダウンロードしてインストール、 [Power BI Desktop](https://powerbi.microsoft.com/desktop/)です。
2. BizTalk Server フォルダーの下を参照**%program Files (x86) \Microsoft BizTalk Server 2016\OperationalDataService**です。
3. 開く、 **BizTalkOperationalData.pbit**ファイル。
4. Power BI からメッセージが表示されたら、貼り付け、 **http://localhost/\<yourWebSite\>**  OData フィード用に作成した URL です。 たとえば、入力**http://localhost/OperationalDataService**です。 

    URL は、次のようにはなります。 
    
    ![Power BI テンプレート ファイルへの OData URL を貼り付けます](../core/media/pasteurltopowerbitempaltefile.PNG)

5. 選択**ロード**Power BI レポート内のフィールドに入力します。 
6. テンプレート ファイルでは、OData フィードから、情報と使用可能なテーブルが自動的に生成されます。

オペレーション データ、コンピューターによって公開されることができますアクセスおよび権限に基づいて他のアプリケーションによって実行されます。 

Power BI、およびレポート オンライン ジャンプを公開する方法の詳細について[PowerBI.com](http://powerbi.microsoft.com)

## <a name="see-also"></a>参照

[Power BI を詳細します。](https://www.powerbi.com)  
[この機能パックを構成します。](../core/configure-the-feature-pack.md)