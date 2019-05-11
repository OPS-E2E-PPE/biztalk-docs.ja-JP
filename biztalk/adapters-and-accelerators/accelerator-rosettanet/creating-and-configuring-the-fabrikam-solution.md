---
title: Fabrikam ソリューションの構成の作成と |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, creating solutions
- double action tutorial, configuring solutions
ms.assetid: 463d55ef-12b6-49e1-a1b8-9081cfb0abed
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a1380b926583a6d352d0947949cd415056c8e42
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65284345"
---
# <a name="creating-and-configuring-the-fabrikam-solution"></a><span data-ttu-id="983ba-102">作成して、Fabrikam のソリューションを構成します。</span><span class="sxs-lookup"><span data-stu-id="983ba-102">Creating and Configuring the Fabrikam Solution</span></span>
<span data-ttu-id="983ba-103">チュートリアルのこのセクションでは、Fabrikam の組織に従う必要のある手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="983ba-103">This section of the tutorial details the steps that you have to follow for the Fabrikam organization.</span></span> <span data-ttu-id="983ba-104">Fabrikam 組織は、購入者を表し、ためプロセス PIP (Partner Interface) のすべての要求の発信側として機能します。</span><span class="sxs-lookup"><span data-stu-id="983ba-104">The Fabrikam organization represents the buyer and therefore acts as the initiator for all Partner Interface Process (PIP) requests.</span></span> <span data-ttu-id="983ba-105">このチュートリアルでパートナーを作成するには、4 つの Pip の契約と作成および配置する基幹業務 (LOB) ASP[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]特定の PIP の種類に基づいて Contoso のコンピューターに要求を送信するアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="983ba-105">In this tutorial, you create partner agreements for four PIPs, and build and deploy a line-of-business (LOB) ASP[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] application to send a request to the Contoso computer based on a certain PIP type.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="983ba-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="983ba-106">In This Section</span></span>  
  
-   [<span data-ttu-id="983ba-107">ステップ 1: Fabrikam ホーム組織の作成</span><span class="sxs-lookup"><span data-stu-id="983ba-107">Step 1: Creating the Fabrikam Home Organization</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-1-creating-the-fabrikam-home-organization.md)  
  
-   [<span data-ttu-id="983ba-108">手順 2:Contoso 取引先組織の作成</span><span class="sxs-lookup"><span data-stu-id="983ba-108">Step 2: Creating the Contoso Partner Organization</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-the-contoso-partner-organization.md)  
  
-   [<span data-ttu-id="983ba-109">ステップ 3:Fabrikam 0C2 取引先契約の作成</span><span class="sxs-lookup"><span data-stu-id="983ba-109">Step 3: Creating the Fabrikam 0C2 Trading Partner Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-creating-the-fabrikam-0c2-trading-partner-agreement.md)  
  
-   [<span data-ttu-id="983ba-110">手順 4:Fabrikam 0C4 取引先契約の作成</span><span class="sxs-lookup"><span data-stu-id="983ba-110">Step 4: Creating the Fabrikam 0C4 Trading Partner Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-4-creating-the-fabrikam-0c4-trading-partner-agreement.md)  
  
-   [<span data-ttu-id="983ba-111">手順 5:Fabrikam 3A2 取引先契約の作成</span><span class="sxs-lookup"><span data-stu-id="983ba-111">Step 5: Creating the Fabrikam 3A2 Trading Partner Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-5-creating-the-fabrikam-3a2-trading-partner-agreement.md)  
  
-   [<span data-ttu-id="983ba-112">手順 6:Fabrikam 3A4 取引先契約の作成</span><span class="sxs-lookup"><span data-stu-id="983ba-112">Step 6: Creating the Fabrikam 3A4 Trading Partner Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-6-creating-the-fabrikam-3a4-trading-partner-agreement.md)  
  
-   [<span data-ttu-id="983ba-113">手順 7:LOBWebApplication SDK サンプルのビルドと展開</span><span class="sxs-lookup"><span data-stu-id="983ba-113">Step 7: Building and Deploying the LOBWebApplication SDK Sample</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-7-building-and-deploying-the-lobwebapplication-sdk-sample.md)