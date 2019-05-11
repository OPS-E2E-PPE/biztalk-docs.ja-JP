---
title: Application Insights や Event Hubs にデータを追跡 |Microsoft Docs
description: Azure Application Insights または BizTalk Server で Azure Event Hubs を使用して、追跡データの分析を有効にする feature pack をインストールします。
ms.custom: fp1, fp2
ms.date: 11/16/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b3ff6cb9-44d0-46cd-9b4f-a346365afb7b
caps.latest.revision: 10
author: tordgladnordahl
ms.author: mandia
manager: anneta
ms.openlocfilehash: 981fc1222b2a9b63c8d87cf6ac35bb82b954c857
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254458"
---
# <a name="send-biztalk-tracking-data-to-azure-application-insights-or-event-hubs"></a>BizTalk の追跡、Azure Application Insights や Event Hubs にデータを送信します。

**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** を処理し、追跡データを Azure Application Insights に送信することができます。 
          
**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]Feature Pack 2**:

* Application Insights は、SQL の既定のインスタンス、および名前付きインスタンスの SQL サポートしています。
* 処理し、追跡データを Azure Event Hubs に送信することができます。

受信ポート、送信ポート、およびオーケストレーションからのインスタンスを追跡するには、次の Azure サービスを使用します。

## <a name="prerequisites"></a>前提条件
* 新しいインスタンスを作成[Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-create-new-resource)します。 BizTalk Server を使用して、**インストルメンテーション キー**を認証します。
* 作成、 [Azure Event Hubs 名前空間とイベント ハブ](https://docs.microsoft.com/azure/event-hubs/event-hubs-create)します。 BizTalk Server は、認証に SAS (名前空間レベル) またはイベント ハブのレベルのポリシーを使用します。
* インストール[Feature Pack 2](https://aka.ms/bts2016fp2)で、 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]

## <a name="enable-analytics-for-your-environment"></a>環境の分析を有効にします。

1. 開く、 **BizTalk Server 管理**コンソールで、右クリックし、 **BizTalk グループ**を選択し、**設定**します。 
2. 確認**グループ レベルの分析を有効にする**します。
3. **ターゲットの種類**を選択します**Application Insight**または**Event Hub**一覧から。
    ![環境の分析を有効にします。](../core/media/environmentsettingapplicationinishgt.PNG)

4. **接続パラメーター**を選択、 **.** ボタン、および**サインイン**Azure アカウントにします。  

    **Application Insights には**  
    選択、**サブスクリプション**、**リソース グループ**、し、Application Insights インスタンス。

    ![環境の分析を有効にします。](../core/media/analytics-group-application-insights.png)

    **イベント ハブの**  
    選択、**サブスクリプション**、**リソース グループ**、イベント ハブ名前空間とイベント ハブ。 認証の場合は、名前空間のレベル、またはイベント ハブのレベルでのエンティティの署名でアクセス署名 (SAS) を使用できます。 使用できるキーで自動的に設定されますは内で以前に構成値を持つ[Azure](https://portal.azure.com)します。

    ![環境の分析を有効にします。](../core/media/send-tracking-data-to-azure.png)

5. **[OK]** を選択して変更を保存します。 

有効にすると、 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] Azure リソースにデータを送信する準備ができました。 次に、ポート、およびオーケストレーションでの分析を有効にします。 

## <a name="enable-analytics-on-your-artifacts"></a>アーティファクトで analytics を有効にします。

1. BizTalk Server 管理コンソールを右クリックし、**受信ポート**、**送信ポート**または**オーケストレーション**、選択と**追跡**します。
2. **Analytics**、確認**Analytics を有効にする**次のような。 この設定は、追跡、および成果物から Azure リソースへのデータの送信を開始します。
    
    ![オーケストレーションの追跡データ](../core/media/orchestrationsettingsapplicationinsight.PNG)

3. **[OK]** を選択して変更を保存します。
4. 追跡ホスト インスタンスを再起動し、BizTalk アプリケーションの起動を確認します。

> [!TIP]
> 組織のデータのさらに多くの洞察を得るには、他のシステムと BizTalk Server の分析を接続します。

## <a name="view-your-data"></a>データを表示します

#### <a name="use-application-insights"></a>Application Insights を使用します。
Application Insights にデータが送信されるは、Azure 内での分析ツールを使用して、高度なクエリを作成して、データを分析します。

1. サインイン、 [Azure Portal](https://portal.azure.com)します。
2. Application Insights リソースを開き、選択**メトリックス エクスプ ローラー**します。
3. 空のグラフが表示されます。 グラフでは、次のように選択します。**編集**します。 **メトリック**を選択します**カスタム**に利用可能な追跡対象プロパティを参照してください。 グラフに変更を表示するさまざまなオプションを選択します。 

    ![Azure の分析](../core/media/azure-stream-metrics-custom.png)

4. 戻って、Application Insights リソースを選択して**Analytics**します。 **使用状況**、**実行**します。 サンプル クエリを実行して、結果をグラフに表示されます。  

> [!TIP]
> Azure Application Insights は、強力なツールです。 Application Insights でのクエリの作成に役立つリソースがある[Application Insights の Analytics の](https://docs.microsoft.com/azure/application-insights/app-insights-analytics)とに開始する場合にも[Application Insights とは何ですか?](https://docs.microsoft.com/azure/application-insights/app-insights-overview)。

#### <a name="use-event-hubs"></a>Event Hubs を使用します。
Event Hubs にデータが送信されると、複数のデータを表示する方法があります。 Event Hubs の多くのユーザーは、Event Hubs Capture を使用するは、Azure にストリーミング データを読み込みます。 目的は、データ キャプチャではなく、データの処理に注力するのです。 [Event Hubs Capture](https://docs.microsoft.com/azure/event-hubs/event-hubs-capture-overview)しくみ、およびように設定する方法について説明します。

別のオプションでは、受信ポートとイベント ハブのアダプターを使用して受信場所を作成します。 次に、フォルダーにデータを出力できます。 このアイデアは、シナリオをテストする場合に最適な可能性があります。 [Event Hubs アダプター](event-hubs-adapter.md) Event Hubs から BizTalk Server にメッセージを受信する手順について説明します。

## <a name="where-the-data-is-stored"></a>データが格納されています。

Azure リソース内で迅速に進める (数分) 内、追跡データが表示されます。 場合は、追跡ホストの問題があります。 は、TrackingData_2_、BizTalkMsgBoxDb データベースの SQL Server で、分析データが格納されている*x*テーブル。 SQL Server Management studio では、これら 4 つのテーブルの上位 1000 行を返します。 データが存在する場合、追跡ホストはデータを移動しない、BizTalkDTADb データベースに。 

いくつかの考えられる解決策:

1. 追跡ホストを再起動します。
2. 専用の追跡ホストを作成します。 追跡を有効にすることがあります BizTalk Server がインストールされている場合、 **BizTalk Server アプリケーション 1**ホスト。 通常、このアプリケーションは、メッセージの処理にも使用されます。 次の手順を使用して専用の追跡ホストを作成します。 

    1. BizTalk Server 管理コンソールで、BizTalk Server アプリケーション 1 のホストのプロパティを開き、オフにします**ホストの追跡を許可する**します。 このホスト インスタンスを再起動します。

    2. という名前の新しいホストを作成する**追跡**、確認と**ホストの追跡を許可する**します。 ホスト インスタンスを作成し、開始します。

ここで、もう一度 BizTalkMsgBoxDb TrackingData_2_x テーブルを照会します。 テーブルが空の場合、データは、移動され、Application Insights での表示を開始する必要があります。
    
## <a name="see-also"></a>関連項目
 [インストールして、Feature Pack を構成するには.](../core/configure-the-feature-pack.md)