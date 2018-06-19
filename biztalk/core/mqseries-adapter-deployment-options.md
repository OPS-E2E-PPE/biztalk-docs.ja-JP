---
title: MQSeries アダプターの展開オプション |Microsoft ドキュメント
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
ms.openlocfilehash: b88fa674c38df8b31c1954234846fd3939ed8568
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263018"
---
# <a name="mqseries-adapter-deployment-options"></a><span data-ttu-id="64118-102">MQSeries アダプターの展開オプション</span><span class="sxs-lookup"><span data-stu-id="64118-102">MQSeries Adapter Deployment Options</span></span>
<span data-ttu-id="64118-103">MQSeries アダプターを使用すると、ハードウェアを非常に柔軟に構成できます。</span><span class="sxs-lookup"><span data-stu-id="64118-103">The MQSeries adapter gives you great flexibility in configuring your hardware.</span></span> <span data-ttu-id="64118-104">その主な使用法には、少なくとも次の 3 つのパターンがあります。</span><span class="sxs-lookup"><span data-stu-id="64118-104">There are at least three main patterns of use:</span></span>  
  
-   <span data-ttu-id="64118-105">BizTalk Server、MQSeries アダプター、MQSeries Server for Windows を同一のコンピューターで実行します。</span><span class="sxs-lookup"><span data-stu-id="64118-105">BizTalk Server, the adapter, and MQSeries Server for Windows on the same computer.</span></span>  
  
-   <span data-ttu-id="64118-106">BizTalk Server および MQSeries アダプターを 1 台のコンピューターで実行し、MQSeries Server for Windows (MQSAgent を含む) を 2 台目のコンピューターで実行します。2 台目のコンピューターは、MQSeries Server を実行している 1 台以上の別のコンピューターに接続します。</span><span class="sxs-lookup"><span data-stu-id="64118-106">BizTalk Server and the adapter on one computer, and MQSeries Server for Windows (including the MQSAgent) on a second computer, which connects to one or more additional computers that are running MQSeries Server.</span></span>  
  
-   <span data-ttu-id="64118-107">グループ内の複数の BizTalk Server インストールと MQSeries アダプター、MQSeries Server (MQSAgent を含む) を別個のコンピューターで実行します。</span><span class="sxs-lookup"><span data-stu-id="64118-107">Multiple BizTalk Server installations in a group and the adapter, and MQSeries Server (including MQSAgent) on a separate computer.</span></span>  
  
-   <span data-ttu-id="64118-108">MQSeries Server と MQSeries キュー マネージャーをクラスター化しても、アダプターは正常に機能します。</span><span class="sxs-lookup"><span data-stu-id="64118-108">The adapter functions correctly if you cluster MQSeries Server and the MQSeries Queue Managers.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="64118-109">この場合、MQSAgent COM+ アプリケーションはクラスター化しないでください。</span><span class="sxs-lookup"><span data-stu-id="64118-109">The MQSAgent COM+ application should not be clustered in this case.</span></span> <span data-ttu-id="64118-110">その代わり、クラスターのいずれのノードにも、MQSAgent COM+ アプリケーションをインストールおよび構成してください。</span><span class="sxs-lookup"><span data-stu-id="64118-110">Instead, both nodes of the cluster should have the MQSAgent COM+ application installed and configured.</span></span> <span data-ttu-id="64118-111">こうしておくことで、MQSAgent COM+ アプリケーションが停止した場合、クライアントから次の呼び出しがあったときに再起動します。</span><span class="sxs-lookup"><span data-stu-id="64118-111">In this scenario, if the MQSAgent COM+ application stops, the next call from the client will restart it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64118-112">参照</span><span class="sxs-lookup"><span data-stu-id="64118-112">See Also</span></span>  
 [<span data-ttu-id="64118-113">MQSeries アダプタの使用</span><span class="sxs-lookup"><span data-stu-id="64118-113">Using the MQSeries Adapter</span></span>](../core/using-the-mqseries-adapter.md)