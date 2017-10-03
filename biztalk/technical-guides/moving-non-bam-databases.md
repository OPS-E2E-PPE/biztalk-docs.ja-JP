---
title: "非 BAM データベースの移動 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9e548e72-db0e-4f07-a07a-8d210425dfa5
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c836840fef8b49cb907e7ac039612c68c1f6fd6c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="moving-non-bam-databases"></a><span data-ttu-id="3a18e-102">非 BAM データベースの移動</span><span class="sxs-lookup"><span data-stu-id="3a18e-102">Moving Non-BAM Databases</span></span>
<span data-ttu-id="3a18e-103">この手順を使用すると、BizTalk Server のプライマリ データベースを別のサーバーに移動します。</span><span class="sxs-lookup"><span data-stu-id="3a18e-103">You can use this procedure to move the primary BizTalk Server databases to another server.</span></span> <span data-ttu-id="3a18e-104">これと同じ基本的な手順は、データベースを移動する、BizTalk Server がローカルの SQL Server からリモートの SQL Server または SQL Server クラスターにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="3a18e-104">This same basic procedure can also be used to move the BizTalk Server databases from a local SQL Server to a remote SQL Server or to a SQL Server cluster.</span></span> <span data-ttu-id="3a18e-105">このセクションに移動する方法について説明、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]関連する BAM ではないデータベース。</span><span class="sxs-lookup"><span data-stu-id="3a18e-105">This section describes how to move the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases that are not BAM related.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3a18e-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="3a18e-106">In This Section</span></span>  
 <span data-ttu-id="3a18e-107">データベース以外の BAM を移動する、トピックの手順に従います[を BizTalk Server データベースを移動する方法](http://go.microsoft.com/fwlink/?LinkId=210646)(http://go.microsoft.com/fwlink/?LinkId=210646) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。</span><span class="sxs-lookup"><span data-stu-id="3a18e-107">To move the non BAM databases follow the steps in the topic [How to Move the BizTalk Server Databases](http://go.microsoft.com/fwlink/?LinkId=210646) (http://go.microsoft.com/fwlink/?LinkId=210646) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] help.</span></span>  
  
 <span data-ttu-id="3a18e-108">このセクションでは、特定の移動後に従う必要がある手順について説明するトピックも含まれています。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。</span><span class="sxs-lookup"><span data-stu-id="3a18e-108">This section also contains a topic that describes procedures that must be followed after moving particular [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases.</span></span> <span data-ttu-id="3a18e-109">環境に応じて適切なトピックの手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="3a18e-109">Complete the steps in the topic as appropriate for your environment.</span></span>  
  
-   [<span data-ttu-id="3a18e-110">メッセージ ボックス データベースが移動されていない場合に、追跡データベースを移動する際の考慮事項</span><span class="sxs-lookup"><span data-stu-id="3a18e-110">Considerations When Moving the Tracking Database if the MessageBox Database Is Not Being Moved</span></span>](../technical-guides/before-you-move-the-tracking-database-if-messagebox-database-is-not-moving.md)