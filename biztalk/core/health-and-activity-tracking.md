---
title: 状態と動作状況の追跡 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0c5d7415-38da-47b5-8dbc-0a2ea74548d9
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 116f55c0824d66017e2fb1264cc3a27f388e9a85
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344390"
---
# <a name="health-and-activity-tracking"></a><span data-ttu-id="4dada-102">状態と動作状況の追跡</span><span class="sxs-lookup"><span data-stu-id="4dada-102">Health and Activity Tracking</span></span>
<span data-ttu-id="4dada-103">**状態と動作状況の追跡 (HAT)** ツールでは削除されました[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]2009 です。</span><span class="sxs-lookup"><span data-stu-id="4dada-103">The **Health and Activity Tracking (HAT)** tool was removed in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2009.</span></span>  <span data-ttu-id="4dada-104">HAT ツールの役割は追跡および live に関連する情報を表示することでしたし、履歴メッセージ データが BizTalk 追跡データベースに格納します。</span><span class="sxs-lookup"><span data-stu-id="4dada-104">The role of the HAT tool was to track and display information relating to live and historical message data stored in the BizTalk Tracking database.</span></span>  <span data-ttu-id="4dada-105">ツールでは、順次表示経由でメッセージのフローを表示すること、およびオーケストレーション フローのデバッグを許可します。</span><span class="sxs-lookup"><span data-stu-id="4dada-105">The tool allowed debugging of the flow of an orchestration and the ability to view the flow of a message through a sequential display.</span></span>  <span data-ttu-id="4dada-106">クエリ ビルダーでは、追跡データの標準とカスタム クエリを許可します。</span><span class="sxs-lookup"><span data-stu-id="4dada-106">A Query Builder allowed standard and custom queries of the tracking data.</span></span>  
  
 <span data-ttu-id="4dada-107">正常性の動作状況の追跡ツールはから直接呼び出されません中に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メニューで、その追跡機能が直接境内に存在、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。</span><span class="sxs-lookup"><span data-stu-id="4dada-107">While the Health Activity Tracking tool is no longer invoked directly from the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] menu, its tracking functionality still indirectly exists from within the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span>  <span data-ttu-id="4dada-108">状態と動作状況の情報は、統合の機能強化を利用し、追加の BizTalk Server 管理コンソールの [グループ ハブ] ページ内のクエリを追跡します。</span><span class="sxs-lookup"><span data-stu-id="4dada-108">Health and activity information is available through improved integration and additional tracking queries within the Group Hub page in the BizTalk Server Administration console.</span></span>  
  
 <span data-ttu-id="4dada-109">大部分の関連したドキュメント追跡状態と動作状況のデータをご覧ください[追跡メッセージを表示し、インスタンス データ](../core/viewing-tracked-message-and-instance-data.md)。</span><span class="sxs-lookup"><span data-stu-id="4dada-109">A majority of documentation surrounding tracking health and activity data can be found at [Viewing Tracked Message and Instance Data](../core/viewing-tracked-message-and-instance-data.md).</span></span>  <span data-ttu-id="4dada-110">このセクションの情報の一部が含まれています[メッセージとインスタンス データ追跡のベスト プラクティス](../core/best-practices-for-message-and-instance-data-tracking.md)、[データの追跡について](../core/understanding-tracked-data.md)、[履歴の表示と追跡データ](../core/viewing-historical-and-tracked-data.md)、[メッセージ フローを表示する](../core/viewing-message-flow.md)、および[オーケストレーションのデバッグ](../core/debugging-an-orchestration.md)します。</span><span class="sxs-lookup"><span data-stu-id="4dada-110">Some of the information in this section includes [Best Practices for Message and Instance Data Tracking](../core/best-practices-for-message-and-instance-data-tracking.md), [Understanding Tracked Data](../core/understanding-tracked-data.md), [Viewing Historical and Tracked Data](../core/viewing-historical-and-tracked-data.md), [Viewing Message Flow](../core/viewing-message-flow.md), and [Debugging an Orchestration](../core/debugging-an-orchestration.md).</span></span>  
  
 <span data-ttu-id="4dada-111">強化された機能とこのページに追加のクエリの詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4dada-111">For additional information on the improvements and the additional queries to this page, refer to the following topics:</span></span>  
  
-   [<span data-ttu-id="4dada-112">グループ ハブ ページの使用</span><span class="sxs-lookup"><span data-stu-id="4dada-112">Using the Group Hub Page</span></span>](../core/using-the-group-hub-page.md)  
  
-   <span data-ttu-id="4dada-113">[管理コンソールの [クエリ] タブの使用](../core/using-the-administration-console-query-tab.md)</span><span class="sxs-lookup"><span data-stu-id="4dada-113">[Using the Administration Console Query Tab](../core/using-the-administration-console-query-tab.md)</span></span>  
  
-   [<span data-ttu-id="4dada-114">追跡メッセージ イベントを検索する方法</span><span class="sxs-lookup"><span data-stu-id="4dada-114">How to Search for Tracked Message Events</span></span>](../core/how-to-search-for-tracked-message-events.md)  
  
-   [<span data-ttu-id="4dada-115">追跡サービス インスタンスを検索する方法</span><span class="sxs-lookup"><span data-stu-id="4dada-115">How to Search for Tracked Service Instances</span></span>](../core/how-to-search-for-tracked-service-instances.md)