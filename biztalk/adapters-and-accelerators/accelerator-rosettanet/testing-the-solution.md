---
title: "ソリューションのテスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- testing solutions
- private process tutorial, testing solutions
ms.assetid: 90faf959-bac6-4695-8cb7-ecabe52baf1a
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4692035aed17f8432eb2bb515fa75df61be8047f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="testing-the-solution"></a><span data-ttu-id="1da67-102">ソリューションをテストします。</span><span class="sxs-lookup"><span data-stu-id="1da67-102">Testing the Solution</span></span>
<span data-ttu-id="1da67-103">ここでは、完成したソリューションをテストします。</span><span class="sxs-lookup"><span data-stu-id="1da67-103">In this section, you test your complete solution.</span></span> <span data-ttu-id="1da67-104">Fabrikam ソリューションで作成した LOBWebApplication ツールを使用して、Contoso LOB アプリケーションに 3A2 PIP 要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="1da67-104">You use the LOBWebApplication tool created in the Fabrikam solution to submit 3A2 PIP requests to the Contoso LOB application.</span></span> <span data-ttu-id="1da67-105">作成した Contoso のプライベート オーケストレーションは、SQL Adapter for [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] を使用して、Contoso ベースの 3A2 Price and Availability 要求を ERP システムに送信します。</span><span class="sxs-lookup"><span data-stu-id="1da67-105">The Contoso private orchestration that you created then submits a Contoso based 3A2 Price and Availability request to the ERP system using the SQL adapter for [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)].</span></span> <span data-ttu-id="1da67-106">ERP システムからの応答を受信すると、オーケストレーションはビジネス ルール エンジンを呼び出し、作成した緊急時に必要なビジネス ポリシーを実行します。</span><span class="sxs-lookup"><span data-stu-id="1da67-106">When the response is received from the ERP system, the orchestration calls the Business Rule Engine to enforce the emergency needs business policy that you created.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1da67-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="1da67-107">In This Section</span></span>  
  
-   [<span data-ttu-id="1da67-108">Fabrikam サンプルを使用して Price and Availability Request の作成</span><span class="sxs-lookup"><span data-stu-id="1da67-108">Creating a Price and Availability Request with the Fabrikam Sample</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-a-price-and-availability-request-with-the-fabrikam-sample.md)