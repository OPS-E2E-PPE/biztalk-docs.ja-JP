---
title: "状態と動作状況の追跡 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0c5d7415-38da-47b5-8dbc-0a2ea74548d9
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35b1720535b58a50fe0c5bd3478bc9b9ec90d0d8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="health-and-activity-tracking"></a><span data-ttu-id="a74f1-102">状態と動作状況の追跡</span><span class="sxs-lookup"><span data-stu-id="a74f1-102">Health and Activity Tracking</span></span>
<span data-ttu-id="a74f1-103">**状態と動作状況の追跡 (HAT)**でツールが削除されて[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]2009 です。</span><span class="sxs-lookup"><span data-stu-id="a74f1-103">The **Health and Activity Tracking (HAT)** tool was removed in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2009.</span></span>  <span data-ttu-id="a74f1-104">追跡および live に関連する情報を表示する、HAT ツールの役割、履歴メッセージ データが BizTalk 追跡データベースに格納されています。</span><span class="sxs-lookup"><span data-stu-id="a74f1-104">The role of the HAT tool was to track and display information relating to live and historical message data stored in the BizTalk Tracking database.</span></span>  <span data-ttu-id="a74f1-105">オーケストレーションのフローをデバッグすることや、メッセージを連続表示してフローを確認することができました。</span><span class="sxs-lookup"><span data-stu-id="a74f1-105">The tool allowed debugging of the flow of an orchestration and the ability to view the flow of a message through a sequential display.</span></span>  <span data-ttu-id="a74f1-106">クエリ ビルダーでは、追跡データの標準クエリおよびカスタム クエリを実行できました。</span><span class="sxs-lookup"><span data-stu-id="a74f1-106">A Query Builder allowed standard and custom queries of the tracking data.</span></span>  
  
 <span data-ttu-id="a74f1-107">状態と動作状況の追跡ツールは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] メニューから直接起動はされないようになりましたが、その追跡機能は引き続き間接的に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境内に存在しています。</span><span class="sxs-lookup"><span data-stu-id="a74f1-107">While the Health Activity Tracking tool is no longer invoked directly from the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] menu, its tracking functionality still indirectly exists from within the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span>  <span data-ttu-id="a74f1-108">状態と動作状況の情報は、BizTalk Server 管理コンソールの [グループ ハブ] ページ内で、強化された統合と追加の追跡クエリを通じて利用できます。</span><span class="sxs-lookup"><span data-stu-id="a74f1-108">Health and activity information is available through improved integration and additional tracking queries within the Group Hub page in the BizTalk Server Administration console.</span></span>  
  
 <span data-ttu-id="a74f1-109">大半の関連したドキュメント追跡状態と動作状況のデータはあります[追跡メッセージを表示し、インスタンス データ](../core/viewing-tracked-message-and-instance-data.md)です。</span><span class="sxs-lookup"><span data-stu-id="a74f1-109">A majority of documentation surrounding tracking health and activity data can be found at [Viewing Tracked Message and Instance Data](../core/viewing-tracked-message-and-instance-data.md).</span></span>  <span data-ttu-id="a74f1-110">このセクションの情報の一部が含まれています[メッセージとインスタンス データ追跡のベスト プラクティス](../core/best-practices-for-message-and-instance-data-tracking.md)、[について追跡データ](../core/understanding-tracked-data.md)、[履歴の表示と追跡データ](../core/viewing-historical-and-tracked-data.md)、[メッセージ フローを表示する](../core/viewing-message-flow.md)、および[オーケストレーションのデバッグ](../core/debugging-an-orchestration.md)です。</span><span class="sxs-lookup"><span data-stu-id="a74f1-110">Some of the information in this section includes [Best Practices for Message and Instance Data Tracking](../core/best-practices-for-message-and-instance-data-tracking.md), [Understanding Tracked Data](../core/understanding-tracked-data.md), [Viewing Historical and Tracked Data](../core/viewing-historical-and-tracked-data.md), [Viewing Message Flow](../core/viewing-message-flow.md), and [Debugging an Orchestration](../core/debugging-an-orchestration.md).</span></span>  
  
 <span data-ttu-id="a74f1-111">このページに対する強化点と追加クエリの詳細については、以下のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a74f1-111">For additional information on the improvements and the additional queries to this page, refer to the following topics:</span></span>  
  
-   [<span data-ttu-id="a74f1-112">グループ ハブ ページを使用します。</span><span class="sxs-lookup"><span data-stu-id="a74f1-112">Using the Group Hub Page</span></span>](../core/using-the-group-hub-page.md)  
  
-   <span data-ttu-id="a74f1-113">[管理コンソールの [クエリ] タブを使用します。](../core/using-the-administration-console-query-tab.md)</span><span class="sxs-lookup"><span data-stu-id="a74f1-113">[Using the Administration Console Query Tab](../core/using-the-administration-console-query-tab.md)</span></span>  
  
-   [<span data-ttu-id="a74f1-114">追跡メッセージ イベントを検索する方法</span><span class="sxs-lookup"><span data-stu-id="a74f1-114">How to Search for Tracked Message Events</span></span>](../core/how-to-search-for-tracked-message-events.md)  
  
-   [<span data-ttu-id="a74f1-115">追跡サービス インスタンスを検索する方法</span><span class="sxs-lookup"><span data-stu-id="a74f1-115">How to Search for Tracked Service Instances</span></span>](../core/how-to-search-for-tracked-service-instances.md)