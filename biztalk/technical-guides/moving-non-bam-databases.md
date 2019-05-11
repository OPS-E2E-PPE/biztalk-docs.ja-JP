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
ms.openlocfilehash: 1f6d5c4555620b2ea51a176e153dc5acdcbfabd8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400186"
---
# <a name="moving-non-bam-databases"></a><span data-ttu-id="77bfd-102">非 BAM データベースの移動</span><span class="sxs-lookup"><span data-stu-id="77bfd-102">Moving Non-BAM Databases</span></span>
<span data-ttu-id="77bfd-103">この手順を使用すると、BizTalk Server のプライマリ データベースを別のサーバーに移動します。</span><span class="sxs-lookup"><span data-stu-id="77bfd-103">You can use this procedure to move the primary BizTalk Server databases to another server.</span></span> <span data-ttu-id="77bfd-104">これと同じ基本的な手順がリモート SQL Server または SQL Server クラスターにローカルの SQL Server から BizTalk Server データベースを移動することもできます。</span><span class="sxs-lookup"><span data-stu-id="77bfd-104">This same basic procedure can also be used to move the BizTalk Server databases from a local SQL Server to a remote SQL Server or to a SQL Server cluster.</span></span> <span data-ttu-id="77bfd-105">このセクションに移動する方法を説明します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]関連する BAM ではないデータベース。</span><span class="sxs-lookup"><span data-stu-id="77bfd-105">This section describes how to move the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases that are not BAM related.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="77bfd-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="77bfd-106">In This Section</span></span>  
 <span data-ttu-id="77bfd-107">データベースを非 BAM を移動するには、次のトピックの手順[、BizTalk Server データベースを移動する方法](http://go.microsoft.com/fwlink/?LinkId=210646)(<http://go.microsoft.com/fwlink/?LinkId=210646>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。</span><span class="sxs-lookup"><span data-stu-id="77bfd-107">To move the non BAM databases follow the steps in the topic [How to Move the BizTalk Server Databases](http://go.microsoft.com/fwlink/?LinkId=210646) (<http://go.microsoft.com/fwlink/?LinkId=210646>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] help.</span></span>  
  
 <span data-ttu-id="77bfd-108">このセクションでは、特定の移動後に従う必要がある手順について説明するトピックも含まれています。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。</span><span class="sxs-lookup"><span data-stu-id="77bfd-108">This section also contains a topic that describes procedures that must be followed after moving particular [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases.</span></span> <span data-ttu-id="77bfd-109">環境内の適切なトピックの手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="77bfd-109">Complete the steps in the topic as appropriate for your environment.</span></span>  
  
-   [<span data-ttu-id="77bfd-110">メッセージ ボックス データベースが移動されていない場合に、追跡データベースを移動する際の考慮事項</span><span class="sxs-lookup"><span data-stu-id="77bfd-110">Considerations When Moving the Tracking Database if the MessageBox Database Is Not Being Moved</span></span>](../technical-guides/before-you-move-the-tracking-database-if-messagebox-database-is-not-moving.md)