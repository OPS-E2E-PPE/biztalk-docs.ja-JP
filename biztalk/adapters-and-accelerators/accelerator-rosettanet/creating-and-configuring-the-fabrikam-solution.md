---
title: "Fabrikam ソリューションの構成の作成と |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- double action tutorial, creating solutions
- double action tutorial, configuring solutions
ms.assetid: 463d55ef-12b6-49e1-a1b8-9081cfb0abed
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 923e5fb3ba8e50f87538c77b354434cac952d9d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="creating-and-configuring-the-fabrikam-solution"></a><span data-ttu-id="cfa86-102">作成して、Fabrikam のソリューションを構成します。</span><span class="sxs-lookup"><span data-stu-id="cfa86-102">Creating and Configuring the Fabrikam Solution</span></span>
<span data-ttu-id="cfa86-103">ここでは、Fabrikam の組織側で従う必要のある手順の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="cfa86-103">This section of the tutorial details the steps that you have to follow for the Fabrikam organization.</span></span> <span data-ttu-id="cfa86-104">Fabrikam 組織は購入者であるため、すべての PIP (Partner Interface Process) 要求の開始側として機能します。</span><span class="sxs-lookup"><span data-stu-id="cfa86-104">The Fabrikam organization represents the buyer and therefore acts as the initiator for all Partner Interface Process (PIP) requests.</span></span> <span data-ttu-id="cfa86-105">このチュートリアルでは、4 つの PIP 用のパートナー アグリーメントを作成し、特定の PIP の種類に基づいて Contoso のコンピューターに要求を送信するための基幹業務 (LOB) ASP[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] アプリケーションを構築して展開します。</span><span class="sxs-lookup"><span data-stu-id="cfa86-105">In this tutorial, you create partner agreements for four PIPs, and build and deploy a line-of-business (LOB) ASP[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] application to send a request to the Contoso computer based on a certain PIP type.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cfa86-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="cfa86-106">In This Section</span></span>  
  
-   [<span data-ttu-id="cfa86-107">手順 1: Fabrikam ホーム組織の作成</span><span class="sxs-lookup"><span data-stu-id="cfa86-107">Step 1: Creating the Fabrikam Home Organization</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-1-creating-the-fabrikam-home-organization.md)  
  
-   [<span data-ttu-id="cfa86-108">手順 2: Contoso パートナー組織の作成</span><span class="sxs-lookup"><span data-stu-id="cfa86-108">Step 2: Creating the Contoso Partner Organization</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-the-contoso-partner-organization.md)  
  
-   [<span data-ttu-id="cfa86-109">手順 3: Fabrikam 0 C 2 取引先アグリーメントの作成</span><span class="sxs-lookup"><span data-stu-id="cfa86-109">Step 3: Creating the Fabrikam 0C2 Trading Partner Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-creating-the-fabrikam-0c2-trading-partner-agreement.md)  
  
-   [<span data-ttu-id="cfa86-110">手順 4: Fabrikam 0 C 4 取引先アグリーメントの作成</span><span class="sxs-lookup"><span data-stu-id="cfa86-110">Step 4: Creating the Fabrikam 0C4 Trading Partner Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-4-creating-the-fabrikam-0c4-trading-partner-agreement.md)  
  
-   [<span data-ttu-id="cfa86-111">手順 5: Fabrikam 3 a 2 取引先アグリーメントの作成</span><span class="sxs-lookup"><span data-stu-id="cfa86-111">Step 5: Creating the Fabrikam 3A2 Trading Partner Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-5-creating-the-fabrikam-3a2-trading-partner-agreement.md)  
  
-   [<span data-ttu-id="cfa86-112">手順 6: Fabrikam 3A4 取引先アグリーメントの作成</span><span class="sxs-lookup"><span data-stu-id="cfa86-112">Step 6: Creating the Fabrikam 3A4 Trading Partner Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-6-creating-the-fabrikam-3a4-trading-partner-agreement.md)  
  
-   [<span data-ttu-id="cfa86-113">手順 7: ビルドと LOBWebApplication SDK サンプルの展開</span><span class="sxs-lookup"><span data-stu-id="cfa86-113">Step 7: Building and Deploying the LOBWebApplication SDK Sample</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-7-building-and-deploying-the-lobwebapplication-sdk-sample.md)