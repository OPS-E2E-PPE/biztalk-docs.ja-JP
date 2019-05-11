---
title: SOA BizTalk 管理ポイントの概要 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0d4c3a30-c50e-4c1c-9f59-d9a364078388
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17a6631135272d2e58571ebdf8c4afed95f967ce
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400035"
---
# <a name="overview-of-the-soa-biztalk-management-point"></a><span data-ttu-id="daf37-102">SOA BizTalk 管理ポイントの概要</span><span class="sxs-lookup"><span data-stu-id="daf37-102">Overview of the SOA BizTalk Management Point</span></span>
<span data-ttu-id="daf37-103">BizTalk 管理ポイントは、ネイティブ SOA サービス マネージャー、Workbench の製品と統合します。</span><span class="sxs-lookup"><span data-stu-id="daf37-103">The BizTalk Management Point natively integrates with SOA Service Manager and Workbench products.</span></span> <span data-ttu-id="daf37-104">一般的な Web サービスの管理ポイントとは異なりこの実装に関連付けられている BizTalk Server の観点から表される、Microsoft BizTalk Server 環境によって提供されるサービスの場所の受信し、送信ポート。</span><span class="sxs-lookup"><span data-stu-id="daf37-104">Unlike the typical Web Services Management Point, this implementation is associated with services provided by the Microsoft BizTalk Server environment, expressed in terms of BizTalk Server receive locations and send ports.</span></span> <span data-ttu-id="daf37-105">任意のため、これらのサービスが、Web サービスに必ずしも関連付けられていないが、SOA サービス マネージャーの観点から Web サービスとして扱えるの性質は、受信場所と送信ポート (さまざまな BizTalk Server アダプターに対して構成されている)SOA Workbench。</span><span class="sxs-lookup"><span data-stu-id="daf37-105">Because of the arbitrary nature of receive locations and send ports (configured against a variety of BizTalk Server adapters), these services are not necessarily associated with Web services, but they can be treated as Web services in terms of the SOA Service Manager and SOA Workbench.</span></span>  
  
 <span data-ttu-id="daf37-106">図 1 は、アプリケーションの例の Workbench ページを表示する SOA Service Manager Web アプリケーションを示します。</span><span class="sxs-lookup"><span data-stu-id="daf37-106">Figure 1 shows the SOA Service Manager Web application displaying the Workbench page for an example application.</span></span> <span data-ttu-id="daf37-107">左側のツリー ビューにより、ユーザーがアプリケーションと、BizTalk Server 内にインストールされているサービスを移動して、右側のペインは、アプリケーションの詳細、操作、アクセス ポート、カテゴリ、ルール、および監視情報を表示するユーザー。</span><span class="sxs-lookup"><span data-stu-id="daf37-107">The left-side tree view allows users to navigate through the applications and services installed within BizTalk Server, and the right-side pane allows users to view application details, operations, access ports, categories, rules, and monitoring information.</span></span>  
  
 <span data-ttu-id="daf37-108">![Ch9&#45;SOAServiceManager](../esb-toolkit/media/ch9-soaservicemanager.jpg "Ch9 SOAServiceManager")</span><span class="sxs-lookup"><span data-stu-id="daf37-108">![Ch9&#45;SOAServiceManager](../esb-toolkit/media/ch9-soaservicemanager.jpg "Ch9-SOAServiceManager")</span></span>  
  
 <span data-ttu-id="daf37-109">**図 1**</span><span class="sxs-lookup"><span data-stu-id="daf37-109">**Figure 1**</span></span>  
  
 <span data-ttu-id="daf37-110">**Workbench のページで使用可能な監視機能を示す、SOA サービス マネージャー**</span><span class="sxs-lookup"><span data-stu-id="daf37-110">**The SOA Service Manager showing the monitoring features available on the Workbench page**</span></span>  
  
 <span data-ttu-id="daf37-111">すべての (すべての送信ポートし、受信場所)、アプリケーション内の操作や特定の操作を監視することができます。Workbench の表示、選択した通過するメッセージの一覧は、送信ポートと受信場所。</span><span class="sxs-lookup"><span data-stu-id="daf37-111">You can monitor all the operations within an application (all send ports and receive locations), or specific operations; the Workbench shows a list of the messages passing through the selected send ports and receive locations.</span></span> <span data-ttu-id="daf37-112">リスト内のメッセージをダブルクリックすると、Workbench は、(記録を有効になっている) 場合、メッセージとそのコンテキスト プロパティの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="daf37-112">When you double-click a message in the list, the Workbench displays details of the message, and its context properties (if recording is enabled).</span></span> <span data-ttu-id="daf37-113">または、そのサービスを通過するリアルタイムのメッセージでは、特定のサービスとモニターを選択できます。</span><span class="sxs-lookup"><span data-stu-id="daf37-113">Alternatively, you can select a specific service and monitor in real-time messages passing through that service.</span></span>