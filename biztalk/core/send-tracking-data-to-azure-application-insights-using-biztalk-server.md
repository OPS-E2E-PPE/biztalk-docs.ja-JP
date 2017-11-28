---
title: "Application Insights または Event Hubs へのデータの追跡 |Microsoft ドキュメント"
description: "Azure の Application Insights または BizTalk Server で Azure Event Hubs での追跡データの分析を有効にする feature pack をインストールします。"
ms.custom: fp1, fp2
ms.date: 11/16/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b3ff6cb9-44d0-46cd-9b4f-a346365afb7b
caps.latest.revision: "10"
author: tordgladnordahl
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a6fe0c50527f51b599bca5f51c7b8ed8fb7313e
ms.sourcegitcommit: f65e8ed2b8c18cded26b9d60868fb6a56bcc1205
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="send-biztalk-tracking-data-to-azure-application-insights-or-event-hubs"></a>BizTalk 追跡データを Azure の Application Insights または Event Hubs の送信します。

**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**を処理し、追跡データを Azure Application Insights に送信することができます。 
          
**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]Feature Pack 2**:

* Application Insights は、既定の SQL インスタンスと名前付きインスタンスの SQL サポートしています。
* プロセスおよび追跡データを Azure Event Hubs に送信できます。

受信ポート、送信ポート、およびオーケストレーションからのインスタンスを追跡するには、これらの Azure サービスを使用します。

## <a name="prerequisites"></a>前提条件
* 新しいインスタンスを作成する[Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-create-new-resource)です。 BizTalk Server を使用して、**インストルメンテーション キー**を認証します。
* 作成、 [Azure Event Hubs の名前空間とイベント ハブ](https://docs.microsoft.com/azure/event-hubs/event-hubs-create)です。 BizTalk Server では、SAS (名前空間レベル) またはイベント ハブ レベルのポリシーを使用して、認証します。
* インストール[Feature Pack 2](https://aka.ms/bts2016fp2)で、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]

## <a name="enable-analytics-for-your-environment"></a>環境の分析を有効にします。

1. 開く、 **BizTalk Server 管理コンソール**コンソールで、右クリックし、 **BizTalk グループ**を選択して**設定**です。 
2. 確認**グループ レベルの分析を有効にする**です。
3. **ターゲット型** **Application Insight**または**Event Hub**一覧からです。
    ![環境の分析を有効にします。](../core/media/environmentsettingapplicationinishgt.PNG)

4. **接続パラメーター**、select、**しています.**ボタン、および**サインイン**Azure アカウントにします。  

    **Application Insights 用**  
    選択、**サブスクリプション**、**リソース グループ**と、Application Insights インスタンス。

    ![環境の分析を有効にします。](../core/media/analytics-group-application-insights.png)

    **イベント ハブの**  
    選択、**サブスクリプション**、**リソース グループ**、Event Hub の名前空間、およびイベント ハブ。 認証の場合は、名前空間レベル、またはイベント ハブ レベルでもエンティティの署名でアクセス署名 (SAS) を使用できます。 使用可能なキーに問題が自動的に入力されます内で構成した値[Azure](https://portal.azure.com)です。

    ![環境の分析を有効にします。](../core/media/send-tracking-data-to-azure.png)

5. **[OK]** を選択して変更を保存します。 

有効にすると、 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] Azure リソースへのデータを送信する準備ができました。 次に、ポートやオーケストレーションに対する分析を有効にします。 

## <a name="enable-analytics-on-your-artifacts"></a>アイテムに対する分析を有効にします。

1. BizTalk Server 管理 を右クリックし、**受信ポート**、**送信ポート**または**オーケストレーション**を選択して**追跡**です。
2. **分析**、確認**Analytics を有効にする**次のようなです。 この設定は、追跡、および成果物から Azure リソースへのデータの送信を開始します。
    
    ![オーケストレーションの追跡データ](../core/media/orchestrationsettingsapplicationinsight.PNG)

3. **[OK]** を選択して変更を保存します。
4. 追跡ホスト インスタンスを再起動し、BizTalk アプリケーションが開始されたことを確認します。

> [!TIP]
> 組織のデータをさらに多くの把握するためには、他のシステムと、BizTalk Server の分析結果を接続します。

## <a name="view-your-data"></a>データを表示します。

#### <a name="use-application-insights"></a>Application Insights を使用します。
Application Insights にデータが送信されると、Azure 内で分析ツールを使用して、高度なクエリを作成し、データを分析できます。

1. サインイン、 [Azure ポータル](https://portal.azure.com)です。
2. Application Insights のリソースを開き、選択**メトリックス エクスプ ローラー**です。
3. 空のグラフが表示されます。 グラフでは、次のように選択します。**編集**です。 **メトリック****カスタム**使用の追跡対象のプロパティを表示します。 グラフに変更を表示するさまざまなオプションを選択します。 

    ![Azure の分析](../core/media/azure-stream-metrics-custom.png)

4. 戻り、Application Insights のリソースを選択して**Analytics**です。 **使用状況****実行**です。 サンプル クエリが実行され、結果がグラフに表示されます。  

> [!TIP]
> Azure の Application Insights は、強力なツールです。 Application Insights でのクエリを作成するのに役立つリソースがある[Application Insights で分析](https://docs.microsoft.com/azure/application-insights/app-insights-analytics)とで作業を開始する場合でも[Application Insights とは?](https://docs.microsoft.com/en-us/azure/application-insights/app-insights-overview)です。

#### <a name="use-event-hubs"></a>Event Hubs を使用します。
Event Hubs にデータが送信されると、複数のデータを表示する方法があります。 Event Hubs の多くのユーザーを使用しているイベント ハブをキャプチャしてストリーミング データを Azure に読み込みます。 目的は、フォーカス データ キャプチャではなく、データ処理をするのです。 [イベント ハブのキャプチャ](https://docs.microsoft.com/azure/event-hubs/event-hubs-capture-overview)しくみ、およびを設定する方法について説明します。

別のオプションでは、受信ポートと、イベント ハブのアダプターを使用して受信場所を作成します。 次に、フォルダーにデータを出力することができます。 この概念は、シナリオをテストする場合に最適な可能性があります。 [イベント ハブのアダプター](event-hubs-adapter.md) Event Hubs から BizTalk Server にメッセージを受信する手順について説明します。

## <a name="where-the-data-is-stored"></a>データの格納場所

Azure リソース内で、非常に早く (、数分以内)、追跡データが表示されます。 しない場合、追跡ホストの問題があります。 SQL Server で分析データは、TrackingData_2_ で、BizTalkMsgBoxDb データベースに格納*x*テーブル。 SQL Server Management Studio では、これら 4 つのテーブルで上位 1000 行を返します。 データが存在する場合、追跡ホストに移行しないデータ、BizTalkDTADb データベース。 

いくつか考えられる解決策:

1. 追跡ホストを再起動します。
2. 専用の追跡ホストを作成します。 追跡を有効にすることがあります BizTalk Server がインストールされているときに、 **BizTalk Server アプリケーション 1**ホストします。 通常、このアプリケーションは、メッセージの処理にも使用されます。 次の手順を使用して、専用の追跡ホストを作成します。 

    1. BizTalk Server 管理コンソールで、BizTalk Server アプリケーション 1 ホストのプロパティを開き、オフにして**ホストの追跡を許可する**です。 このホスト インスタンスを再起動します。

    2. という名前の新しいホストを作成する**追跡**、し確認**ホストの追跡を許可する**です。 ホスト インスタンスを作成し、それを開始します。

ここで、もう一度 BizTalkMsgBoxDb TrackingData_2_x テーブルを照会します。 テーブルが空の場合は、データは、移動され、Application Insights での表示を開始する必要があります。
    
## <a name="see-also"></a>参照
 [インストールして、機能パックを構成する.](../core/configure-the-feature-pack.md)