---
title: ネットワーク負荷分散 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Network Load Balancing
- NLB
- deploying, network configuration
ms.assetid: 27dc95be-8069-4cbf-b7b0-77657ce22189
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e3bf3e2aba5d02fd6424ebb95493b798de1546c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377250"
---
# <a name="network-load-balancing"></a><span data-ttu-id="b7c79-102">ネットワーク負荷分散</span><span class="sxs-lookup"><span data-stu-id="b7c79-102">Network Load Balancing</span></span>
<span data-ttu-id="b7c79-103">A4SWIFT の分散デプロイでは、メッセージング、オーケストレーションでは、SharePoint サーバーのホストの MRSR サイト、または SQL Server データベースへの BizTalk Server コンピューターを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="b7c79-103">A distributed A4SWIFT deployment may contain BizTalk Server computers for messaging, orchestration, SharePoint Servers to host MRSR site, or SQL Server databases.</span></span> <span data-ttu-id="b7c79-104">場合は、使用状況のプロファイルとビジネス ニーズは非常には、ネットワーク負荷分散 (NLB) の 2 つ BizTalk HTTP フロント エンド (MRSR サイト サーバーまたは複数) の 2 つ以上の BizTalk メッセージング サーバーを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7c79-104">If your usage profile and business needs are great enough, you may need to set up network load balancing (NLB) for two or more BizTalk HTTP front-end (MRSR site) servers or two or more BizTalk messaging servers.</span></span> <span data-ttu-id="b7c79-105">ネットワーク負荷分散が必要な複数のサーバーの例は、「完全な A4SWIFT 展開の例」ダイアグラムを参照してください。[物理図](../../adapters-and-accelerators/accelerator-swift/physical-diagram.md)します。</span><span class="sxs-lookup"><span data-stu-id="b7c79-105">For an example of multiple servers in need of network load balancing, see the "Example of a full A4SWIFT deployment" diagram in [Physical Diagram](../../adapters-and-accelerators/accelerator-swift/physical-diagram.md).</span></span>  
  
 <span data-ttu-id="b7c79-106">ネットワーク負荷分散の詳細については、BizTalk Server の展開ガイドを参照してくださいと[手順 2。サーバーに NLB を構成する](../../adapters-and-accelerators/accelerator-swift/step-2-configuring-nlb-on-the-servers.md)します。</span><span class="sxs-lookup"><span data-stu-id="b7c79-106">For more information on network load balancing, see the BizTalk Server Deployment Guide, and [Step 2: Configuring NLB on the Servers](../../adapters-and-accelerators/accelerator-swift/step-2-configuring-nlb-on-the-servers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7c79-107">参照</span><span class="sxs-lookup"><span data-stu-id="b7c79-107">See Also</span></span>  
 [<span data-ttu-id="b7c79-108">手順 2:サーバー上での NLB の構成</span><span class="sxs-lookup"><span data-stu-id="b7c79-108">Step 2: Configuring NLB on the Servers</span></span>](../../adapters-and-accelerators/accelerator-swift/step-2-configuring-nlb-on-the-servers.md)