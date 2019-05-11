---
title: ソリューションのテスト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing solutions
- private process tutorial, testing solutions
ms.assetid: 90faf959-bac6-4695-8cb7-ecabe52baf1a
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b43ab300fefbe1916b58e9c606c2541dfd0a10e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280602"
---
# <a name="testing-the-solution"></a><span data-ttu-id="96d8a-102">ソリューションのテスト</span><span class="sxs-lookup"><span data-stu-id="96d8a-102">Testing the Solution</span></span>
<span data-ttu-id="96d8a-103">このセクションでは、完全なソリューションをテストします。</span><span class="sxs-lookup"><span data-stu-id="96d8a-103">In this section, you test your complete solution.</span></span> <span data-ttu-id="96d8a-104">Fabrikam ソリューションで作成した LOBWebApplication ツールを使用して、Contoso LOB アプリケーションに 3 a 2 PIP 要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="96d8a-104">You use the LOBWebApplication tool created in the Fabrikam solution to submit 3A2 PIP requests to the Contoso LOB application.</span></span> <span data-ttu-id="96d8a-105">作成した Contoso のプライベート オーケストレーションは、BizTalk Server の SQL アダプターを使用して、ERP システムに Contoso のに基づいて 3 a 2 Price and Availability 要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="96d8a-105">The Contoso private orchestration that you created then submits a Contoso based 3A2 Price and Availability request to the ERP system using the SQL adapter for BizTalk Server.</span></span> <span data-ttu-id="96d8a-106">ERP システムからの応答が受信されると、オーケストレーションを呼び出して、緊急にビジネス ルール エンジンでは、ビジネス ポリシーを作成する必要です。</span><span class="sxs-lookup"><span data-stu-id="96d8a-106">When the response is received from the ERP system, the orchestration calls the Business Rule Engine to enforce the emergency needs business policy that you created.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="96d8a-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="96d8a-107">In This Section</span></span>  
  
-   [<span data-ttu-id="96d8a-108">Fabrikam サンプルを使用した Price and Availability 要求の作成</span><span class="sxs-lookup"><span data-stu-id="96d8a-108">Creating a Price and Availability Request with the Fabrikam Sample</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-a-price-and-availability-request-with-the-fabrikam-sample.md)