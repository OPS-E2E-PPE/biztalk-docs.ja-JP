---
title: "災害からの復旧 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eefb036b-7254-407d-a203-66708c07f67d
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff6d7ba22180995d41fa536717804483931c7ad0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="recovering-from-a-disaster"></a><span data-ttu-id="94531-102">災害からの復旧</span><span class="sxs-lookup"><span data-stu-id="94531-102">Recovering from a Disaster</span></span>
<span data-ttu-id="94531-103">このセクションでは、運用操作を障害復旧サイトに転送する手順を詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="94531-103">This section details the steps to transfer production operations to the disaster recovery site.</span></span> <span data-ttu-id="94531-104">オンラインの実稼働システムはこのセクションの目的で、「ソース」システムと呼びます。</span><span class="sxs-lookup"><span data-stu-id="94531-104">For the purposes of this section, the online production system is referred to as the “source” system.</span></span> <span data-ttu-id="94531-105">障害復旧サイトは、"destination"システム"と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="94531-105">The disaster recovery site is referred to as the “destination” system.</span></span> <span data-ttu-id="94531-106">このセクションでは、障害復旧プロセスの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="94531-106">This section provides an overview of the disaster recovery process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="94531-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="94531-107">In This Section</span></span>  
  
-   [<span data-ttu-id="94531-108">BizTalk グループを復元します。</span><span class="sxs-lookup"><span data-stu-id="94531-108">Restoring the BizTalk Group</span></span>](../technical-guides/restoring-the-biztalk-group.md)  
  
-   [<span data-ttu-id="94531-109">ランタイム コンピューターを回復します。</span><span class="sxs-lookup"><span data-stu-id="94531-109">Recovering the Runtime Computers</span></span>](../technical-guides/recovering-the-runtime-computers.md)  
  
-   [<span data-ttu-id="94531-110">その他のアプリケーションを回復します。</span><span class="sxs-lookup"><span data-stu-id="94531-110">Recovering Additional Applications</span></span>](../technical-guides/recovering-additional-applications.md)  
  
-   [<span data-ttu-id="94531-111">ログ配布のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="94531-111">Troubleshooting Log Shipping</span></span>](../technical-guides/troubleshooting-log-shipping.md)