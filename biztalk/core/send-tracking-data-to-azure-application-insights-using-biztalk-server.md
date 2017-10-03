---
title: "BizTalk Server を使用して Azure Application Insights に追跡データを送信 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b3ff6cb9-44d0-46cd-9b4f-a346365afb7b
caps.latest.revision: "10"
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: f587c3049e191505c87ba456b5ddfd41011862c2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="send-tracking-data-to-azure-application-insights-using-biztalk-server"></a>BizTalk Server を使用して Azure Application Insights に追跡データを送信します。
送信[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]Azure アプリケーション Inisights にデータを追跡します。 

**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**を処理し、追跡データを Azure Application Insights に送信することができます。 Application Insights の機能を使用すると、受信ポート、送信ポート、およびオーケストレーションからのインスタンスを追跡できます。

## <a name="prerequisites"></a>前提条件
* 新しいインスタンスを作成する[Application Insights](https://docs.microsoft.com/en-us/azure/application-insights/app-insights-create-new-resource)
* インストール[機能パック 1](https://www.microsoft.com/download/details.aspx?id=55100)で、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]

## <a name="enable-analytics-for-your-environment"></a>環境の分析を有効にします。

1. 開く、 **BizTalk Server 管理コンソール**コンソールで、 **BizTalk 管理コンソール**を右クリックし、 **BizTalk グループ**を選択して**の設定**. 
2. 確認**グループ レベルの分析を有効にする**です。
3. **ターゲット型** **Application Insight**一覧からです。
4. **接続パラメーター**、入力、Application Insights **[インストルメンテーション キー](https://docs.microsoft.com/en-us/azure/application-insights/app-insights-create-new-resource)**  (Azure ポータルで使用可能)。

    グループの設定は、次のようになります。 

    ![環境の分析を有効にします。](../core/media/environmentsettingapplicationinishgt.PNG)

5. **[OK]** を選択して変更を保存します。 

有効にすると、 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] Application Insights にデータを送信する準備ができました。 次に、ポートやオーケストレーションに対する分析を有効にします。 

## <a name="enable-analytics-on-your-artifacts"></a>アイテムに対する分析を有効にします。

1. BizTalk Server 管理 を右クリックし、**受信ポート**、**送信ポート**または**オーケストレーション**を選択して**追跡**です。
2. **Analytics**、確認**Analytics を有効にする**です。 この設定は、追跡と Application Insights に成果物からのデータの送信を開始します。

    成果物の設定は、次のようになります。 
    
    ![オーケストレーションの追跡データ](../core/media/orchestrationsettingsapplicationinsight.PNG)

3. **[OK]** を選択して変更を保存します。

次に、データを見るための Application Insights 内のクエリを実行します。  

> [!TIP]
> 組織のデータをさらに多くの把握するためには、他のシステムと、BizTalk Server の分析結果を接続します。

## <a name="run-queries-on-your-data"></a>データに対するクエリを実行します。
Application Insights にデータが送信されると、Azure 内で分析ツールを使用して、高度なクエリを作成し、データを分析できます。

1. サインイン、 [Azure ポータル](https://portal.azure.com)です。
2. Application Insights のリソースを開き、選択**Analytics**です。
3. 選択**使用状況**、および指定したクエリを実行します。

    > [!TIP]
    > Application Insights でクエリを記述する方法の詳細について[Application Insights で分析](https://docs.microsoft.com/azure/application-insights/app-insights-analytics)です。
    
## <a name="see-also"></a>参照
 [この機能パックを構成します。](../core/configure-the-feature-pack.md)