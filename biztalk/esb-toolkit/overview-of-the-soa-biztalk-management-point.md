---
title: "SOA BizTalk の管理ポイントの概要 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d4c3a30-c50e-4c1c-9f59-d9a364078388
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60f73834a9bc02e371d4050115b1eccf5e88e02f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="overview-of-the-soa-biztalk-management-point"></a><span data-ttu-id="f046a-102">SOA BizTalk の管理ポイントの概要</span><span class="sxs-lookup"><span data-stu-id="f046a-102">Overview of the SOA BizTalk Management Point</span></span>
<span data-ttu-id="f046a-103">BizTalk 管理ポイントは、ネイティブ SOA サービス マネージャーとワークベンチの製品と統合されています。</span><span class="sxs-lookup"><span data-stu-id="f046a-103">The BizTalk Management Point natively integrates with SOA Service Manager and Workbench products.</span></span> <span data-ttu-id="f046a-104">一般的な Web サービスの管理ポイントとは異なりこの実装は、関連付けられている BizTalk Server として表現されている、Microsoft BizTalk Server 環境で提供されるサービスと受信場所とポートを送信します。</span><span class="sxs-lookup"><span data-stu-id="f046a-104">Unlike the typical Web Services Management Point, this implementation is associated with services provided by the Microsoft BizTalk Server environment, expressed in terms of BizTalk Server receive locations and send ports.</span></span> <span data-ttu-id="f046a-105">により、任意の性質は、受信場所と送信ポート (さまざまな BizTalk Server アダプターに対して構成されている)、これらのサービスが必ずしも、Web サービスに関連付けられていないが、それらは SOA サービス マネージャーの観点から Web サービスとして扱うことができますSOA ワークベンチです。</span><span class="sxs-lookup"><span data-stu-id="f046a-105">Because of the arbitrary nature of receive locations and send ports (configured against a variety of BizTalk Server adapters), these services are not necessarily associated with Web services, but they can be treated as Web services in terms of the SOA Service Manager and SOA Workbench.</span></span>  
  
 <span data-ttu-id="f046a-106">図 1 は、アプリケーションの例の Workbench ページを表示する SOA Service Manager の Web アプリケーションを示します。</span><span class="sxs-lookup"><span data-stu-id="f046a-106">Figure 1 shows the SOA Service Manager Web application displaying the Workbench page for an example application.</span></span> <span data-ttu-id="f046a-107">左側のツリー ビューでは、アプリケーションと BizTalk Server 内でインストールされているサービス内を移動するユーザーと、右側のウィンドウでは、ユーザーがアプリケーションの詳細、操作、アクセス ポート、カテゴリ、ルール、および監視情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="f046a-107">The left-side tree view allows users to navigate through the applications and services installed within BizTalk Server, and the right-side pane allows users to view application details, operations, access ports, categories, rules, and monitoring information.</span></span>  
  
 <span data-ttu-id="f046a-108">![Ch9 &#45;SOAServiceManager](../esb-toolkit/media/ch9-soaservicemanager.jpg "Ch9 SOAServiceManager")</span><span class="sxs-lookup"><span data-stu-id="f046a-108">![Ch9&#45;SOAServiceManager](../esb-toolkit/media/ch9-soaservicemanager.jpg "Ch9-SOAServiceManager")</span></span>  
  
 <span data-ttu-id="f046a-109">**図 1**</span><span class="sxs-lookup"><span data-stu-id="f046a-109">**Figure 1**</span></span>  
  
 <span data-ttu-id="f046a-110">**ワークベンチ ページで使用可能な監視機能を示す、SOA サービス マネージャー**</span><span class="sxs-lookup"><span data-stu-id="f046a-110">**The SOA Service Manager showing the monitoring features available on the Workbench page**</span></span>  
  
 <span data-ttu-id="f046a-111">すべてのアプリケーション (すべての送信ポートし、受信場所) 内の操作または特定の操作を監視します。ワークベンチの表示、選択したを通過するメッセージの一覧は、送信ポートと受信場所。</span><span class="sxs-lookup"><span data-stu-id="f046a-111">You can monitor all the operations within an application (all send ports and receive locations), or specific operations; the Workbench shows a list of the messages passing through the selected send ports and receive locations.</span></span> <span data-ttu-id="f046a-112">リスト内のメッセージをダブルクリックすると、ワークベンチは、(記録が有効な場合)、メッセージとそのコンテキスト プロパティの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="f046a-112">When you double-click a message in the list, the Workbench displays details of the message, and its context properties (if recording is enabled).</span></span> <span data-ttu-id="f046a-113">また、そのサービスを通過リアルタイムのメッセージでは、特定のサービスとモニターを選択できます。</span><span class="sxs-lookup"><span data-stu-id="f046a-113">Alternatively, you can select a specific service and monitor in real-time messages passing through that service.</span></span>