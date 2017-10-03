---
title: "ネットワーク負荷分散 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Network Load Balancing
- NLB
- deploying, network configuration
ms.assetid: 27dc95be-8069-4cbf-b7b0-77657ce22189
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66147720f810fb4ec8b8c4b0d387073f188ec844
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="network-load-balancing"></a><span data-ttu-id="2446b-102">ネットワーク負荷分散</span><span class="sxs-lookup"><span data-stu-id="2446b-102">Network Load Balancing</span></span>
<span data-ttu-id="2446b-103">A4SWIFT の分散デプロイでは、メッセージング、オーケストレーションでは、SharePoint サーバーのホスト MRSR サイト、または SQL Server データベースへの BizTalk Server コンピューターを含めることがあります。</span><span class="sxs-lookup"><span data-stu-id="2446b-103">A distributed A4SWIFT deployment may contain BizTalk Server computers for messaging, orchestration, SharePoint Servers to host MRSR site, or SQL Server databases.</span></span> <span data-ttu-id="2446b-104">使用量プロファイルとビジネスのニーズが非常に場合は、ネットワーク負荷分散 (NLB) の 2 つ BizTalk HTTP フロント エンド (MRSR サイト サーバーまたは複数) または 2 つ以上の BizTalk メッセージング サーバーを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2446b-104">If your usage profile and business needs are great enough, you may need to set up network load balancing (NLB) for two or more BizTalk HTTP front-end (MRSR site) servers or two or more BizTalk messaging servers.</span></span> <span data-ttu-id="2446b-105">ネットワーク負荷分散が必要な複数のサーバーの例で「A4SWIFT の完全展開の使用例」図を参照してください。[物理図](../../adapters-and-accelerators/accelerator-swift/physical-diagram.md)です。</span><span class="sxs-lookup"><span data-stu-id="2446b-105">For an example of multiple servers in need of network load balancing, see the "Example of a full A4SWIFT deployment" diagram in [Physical Diagram](../../adapters-and-accelerators/accelerator-swift/physical-diagram.md).</span></span>  
  
 <span data-ttu-id="2446b-106">ネットワーク負荷分散の詳細については、BizTalk Server の展開ガイド 』 を参照してください。 および[手順 2: サーバー上の NLB の構成](../../adapters-and-accelerators/accelerator-swift/step-2-configuring-nlb-on-the-servers.md)です。</span><span class="sxs-lookup"><span data-stu-id="2446b-106">For more information on network load balancing, see the BizTalk Server Deployment Guide, and [Step 2: Configuring NLB on the Servers](../../adapters-and-accelerators/accelerator-swift/step-2-configuring-nlb-on-the-servers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2446b-107">参照</span><span class="sxs-lookup"><span data-stu-id="2446b-107">See Also</span></span>  
 [<span data-ttu-id="2446b-108">手順 2: サーバーで NLB を構成します。</span><span class="sxs-lookup"><span data-stu-id="2446b-108">Step 2: Configuring NLB on the Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/step-2-configuring-nlb-on-the-servers.md)