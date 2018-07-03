---
title: 非 BAM データベースの移動 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9e548e72-db0e-4f07-a07a-8d210425dfa5
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b9038e443784ae0f2839c2656f62131e9a0fdfa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011379"
---
# <a name="moving-non-bam-databases"></a><span data-ttu-id="6a8ea-102">非 BAM データベースの移動</span><span class="sxs-lookup"><span data-stu-id="6a8ea-102">Moving Non-BAM Databases</span></span>
<span data-ttu-id="6a8ea-103">この手順を使用すると、BizTalk Server のプライマリ データベースを別のサーバーに移動します。</span><span class="sxs-lookup"><span data-stu-id="6a8ea-103">You can use this procedure to move the primary BizTalk Server databases to another server.</span></span> <span data-ttu-id="6a8ea-104">これと同じ基本的な手順がリモート SQL Server または SQL Server クラスターにローカルの SQL Server から BizTalk Server データベースを移動することもできます。</span><span class="sxs-lookup"><span data-stu-id="6a8ea-104">This same basic procedure can also be used to move the BizTalk Server databases from a local SQL Server to a remote SQL Server or to a SQL Server cluster.</span></span> <span data-ttu-id="6a8ea-105">このセクションに移動する方法を説明します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]関連する BAM ではないデータベース。</span><span class="sxs-lookup"><span data-stu-id="6a8ea-105">This section describes how to move the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases that are not BAM related.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6a8ea-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6a8ea-106">In This Section</span></span>  
 <span data-ttu-id="6a8ea-107">データベースを非 BAM を移動するには、次のトピックの手順[、BizTalk Server データベースを移動する方法](http://go.microsoft.com/fwlink/?LinkId=210646)(<http://go.microsoft.com/fwlink/?LinkId=210646>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。</span><span class="sxs-lookup"><span data-stu-id="6a8ea-107">To move the non BAM databases follow the steps in the topic [How to Move the BizTalk Server Databases](http://go.microsoft.com/fwlink/?LinkId=210646) (<http://go.microsoft.com/fwlink/?LinkId=210646>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] help.</span></span>  
  
 <span data-ttu-id="6a8ea-108">このセクションでは、特定の移動後に従う必要がある手順について説明するトピックも含まれています。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。</span><span class="sxs-lookup"><span data-stu-id="6a8ea-108">This section also contains a topic that describes procedures that must be followed after moving particular [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases.</span></span> <span data-ttu-id="6a8ea-109">環境内の適切なトピックの手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="6a8ea-109">Complete the steps in the topic as appropriate for your environment.</span></span>  
  
-   [<span data-ttu-id="6a8ea-110">メッセージ ボックス データベースが移動されていない場合に、追跡データベースを移動する際の考慮事項</span><span class="sxs-lookup"><span data-stu-id="6a8ea-110">Considerations When Moving the Tracking Database if the MessageBox Database Is Not Being Moved</span></span>](../technical-guides/before-you-move-the-tracking-database-if-messagebox-database-is-not-moving.md)