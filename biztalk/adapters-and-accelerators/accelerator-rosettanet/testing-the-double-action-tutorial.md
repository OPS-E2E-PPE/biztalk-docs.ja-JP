---
title: ダブル アクション チュートリアルのテスト |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, testing solutions
- testing solutions
ms.assetid: e5bc66e6-333e-4d94-ae1e-345ab45c83e5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 807308623780e029fff571a36dc703de0f79460d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207050"
---
# <a name="testing-the-double-action-tutorial"></a><span data-ttu-id="02674-102">ダブル アクション チュートリアルのテスト</span><span class="sxs-lookup"><span data-stu-id="02674-102">Testing the Double Action Tutorial</span></span>
<span data-ttu-id="02674-103">ここでは、これまでのセクションで作成した Contoso と Fabrikam のソリューションを使用して、0C2、0C4、3A2、3A4 という 4 つの異なる PIP (Partner Interface Process) をテストします。</span><span class="sxs-lookup"><span data-stu-id="02674-103">In this section, you use the Contoso and Fabrikam solutions that you created in the earlier sections to test four different Partner Interface Processes (PIPs): 0C2, 0C4, 3A2 and 3A4.</span></span> <span data-ttu-id="02674-104">Fabrikam のコンピューターで LOBWebApplication を使用して、要求を行います。</span><span class="sxs-lookup"><span data-stu-id="02674-104">You use the LOBWebApplication on the Fabrikam computer to make the request.</span></span> <span data-ttu-id="02674-105">システムは、拡張された通信チャネルを使用して、Contoso のコンピューターに要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="02674-105">The system will send the request using an enhanced communication channel to the Contoso computer.</span></span> <span data-ttu-id="02674-106">ダブル アクション オーケストレーションでは、使用する PIP に基づいた適切な応答が生成されます。</span><span class="sxs-lookup"><span data-stu-id="02674-106">The Double Action orchestration will generate an appropriate response based on the PIP you use.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="02674-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="02674-107">In This Section</span></span>  
  
-   [<span data-ttu-id="02674-108">手順 1: a 0 C の送信要求します。</span><span class="sxs-lookup"><span data-stu-id="02674-108">Step 1: Submitting a 0C2 Request</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-1-submitting-a-0c2-request.md)  
  
-   [<span data-ttu-id="02674-109">手順 2: 送信 a 0 C 4 クエリします。</span><span class="sxs-lookup"><span data-stu-id="02674-109">Step 2: Submitting a 0C4 Query</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-2-submitting-a-0c4-query.md)  
  
-   [<span data-ttu-id="02674-110">手順 3: 3 a 2 要求の送信</span><span class="sxs-lookup"><span data-stu-id="02674-110">Step 3: Submitting a 3A2 Request</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-submitting-a-3a2-request.md)  
  
-   [<span data-ttu-id="02674-111">手順 4: 3A4 要求の送信</span><span class="sxs-lookup"><span data-stu-id="02674-111">Step 4: Submitting a 3A4 Request</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-4-submitting-a-3a4-request.md)