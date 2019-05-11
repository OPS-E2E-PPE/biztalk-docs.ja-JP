---
title: MQSeries アダプターの展開オプション |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, deploying
- deploying, MQSeries adapters
ms.assetid: d9380aff-40ea-419b-88e2-1e2ec3f023cb
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18d2791b62478b1927772149f3f5d54f3cb5f618
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65264416"
---
# <a name="mqseries-adapter-deployment-options"></a><span data-ttu-id="ce1b7-102">MQSeries アダプターの展開オプション</span><span class="sxs-lookup"><span data-stu-id="ce1b7-102">MQSeries Adapter Deployment Options</span></span>
<span data-ttu-id="ce1b7-103">MQSeries アダプターでは、ハードウェアの構成で優れた柔軟性を提供します。</span><span class="sxs-lookup"><span data-stu-id="ce1b7-103">The MQSeries adapter gives you great flexibility in configuring your hardware.</span></span> <span data-ttu-id="ce1b7-104">これには少なくとも 3 つの主な使用パターンがあります。</span><span class="sxs-lookup"><span data-stu-id="ce1b7-104">There are at least three main patterns of use:</span></span>  
  
-   <span data-ttu-id="ce1b7-105">BizTalk Server、アダプター、および MQSeries Server for Windows を同じコンピューターにします。</span><span class="sxs-lookup"><span data-stu-id="ce1b7-105">BizTalk Server, the adapter, and MQSeries Server for Windows on the same computer.</span></span>  
  
-   <span data-ttu-id="ce1b7-106">BizTalk Server と MQSeries Server を実行している 1 つまたは複数の追加コンピューターに接続する 2 番目のコンピューター上の 1 台のコンピューターと MQSeries Server for Windows (MQSAgent を含む) のアダプター。</span><span class="sxs-lookup"><span data-stu-id="ce1b7-106">BizTalk Server and the adapter on one computer, and MQSeries Server for Windows (including the MQSAgent) on a second computer, which connects to one or more additional computers that are running MQSeries Server.</span></span>  
  
-   <span data-ttu-id="ce1b7-107">別のコンピューター グループとアダプター、MQSeries Server が (MQSAgent を含む) に複数の BizTalk Server インストールします。</span><span class="sxs-lookup"><span data-stu-id="ce1b7-107">Multiple BizTalk Server installations in a group and the adapter, and MQSeries Server (including MQSAgent) on a separate computer.</span></span>  
  
-   <span data-ttu-id="ce1b7-108">MQSeries Server と MQSeries キュー マネージャーをクラスター化する場合、アダプターが正しく機能します。</span><span class="sxs-lookup"><span data-stu-id="ce1b7-108">The adapter functions correctly if you cluster MQSeries Server and the MQSeries Queue Managers.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ce1b7-109">MQSAgent COM + アプリケーションは、ここでクラスター化する必要がありますされません。</span><span class="sxs-lookup"><span data-stu-id="ce1b7-109">The MQSAgent COM+ application should not be clustered in this case.</span></span> <span data-ttu-id="ce1b7-110">代わりに、クラスターの両方のノードでは、MQSAgent COM + アプリケーションをインストールおよび構成されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="ce1b7-110">Instead, both nodes of the cluster should have the MQSAgent COM+ application installed and configured.</span></span> <span data-ttu-id="ce1b7-111">このシナリオで、MQSAgent COM + アプリケーションが停止した場合、クライアントから次の呼び出しを再起動します。</span><span class="sxs-lookup"><span data-stu-id="ce1b7-111">In this scenario, if the MQSAgent COM+ application stops, the next call from the client will restart it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce1b7-112">参照</span><span class="sxs-lookup"><span data-stu-id="ce1b7-112">See Also</span></span>  
 [<span data-ttu-id="ce1b7-113">MQSeries アダプターの使用</span><span class="sxs-lookup"><span data-stu-id="ce1b7-113">Using the MQSeries Adapter</span></span>](../core/using-the-mqseries-adapter.md)