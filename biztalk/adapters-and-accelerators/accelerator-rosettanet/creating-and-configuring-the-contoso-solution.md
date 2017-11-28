---
title: "作成して、Contoso ソリューションの構成 |Microsoft ドキュメント"
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
ms.assetid: 25370624-b27f-4f6c-a813-801ac4f81b8f
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6cef247bff0c57bd39fbdda9d1a01710bcca0fab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="creating-and-configuring-the-contoso-solution"></a><span data-ttu-id="8a60b-102">作成して、Contoso ソリューションを構成します。</span><span class="sxs-lookup"><span data-stu-id="8a60b-102">Creating and Configuring the Contoso Solution</span></span>
<span data-ttu-id="8a60b-103">ここでは、Contoso 社側で従う必要のある手順の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="8a60b-103">This section of the tutorial details the steps that you have to follow for the Contoso organization.</span></span> <span data-ttu-id="8a60b-104">Contoso 社はメーカーであるため、受信したすべての PIP (Partner Interface Process) 要求への応答側として機能します。</span><span class="sxs-lookup"><span data-stu-id="8a60b-104">The Contoso organization represents the manufacturer and therefore acts as the Responder to all incoming Partner Interface Process (PIP) requests.</span></span> <span data-ttu-id="8a60b-105">このチュートリアルでは、4 つの PIP 用のパートナー アグリーメントを作成し、PIP の種類に基づいて適切な応答を送信するためのオーケストレーションを構築および展開します。</span><span class="sxs-lookup"><span data-stu-id="8a60b-105">In this tutorial, you create partner agreements for four PIPs and build and deploy an orchestration to send an appropriate response based on the PIP type.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8a60b-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8a60b-106">In This Section</span></span>  
  
-   [<span data-ttu-id="8a60b-107">手順 1: Contoso ホーム組織の作成</span><span class="sxs-lookup"><span data-stu-id="8a60b-107">Step 1: Creating the Contoso Home Organization</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-1-creating-the-contoso-home-organization.md)  
  
-   [<span data-ttu-id="8a60b-108">手順 2: Fabrikam パートナー組織の作成</span><span class="sxs-lookup"><span data-stu-id="8a60b-108">Step 2: Creating the Fabrikam Partner Organization</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-the-fabrikam-partner-organization.md)  
  
-   [<span data-ttu-id="8a60b-109">手順 3: Contoso 0 C 2 取引先アグリーメントの作成</span><span class="sxs-lookup"><span data-stu-id="8a60b-109">Step 3: Creating the Contoso 0C2 Trading Partner Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-creating-the-contoso-0c2-trading-partner-agreement.md)  
  
-   [<span data-ttu-id="8a60b-110">手順 4: Contoso 0 C 4 取引先アグリーメントの作成</span><span class="sxs-lookup"><span data-stu-id="8a60b-110">Step 4: Creating the Contoso 0C4 Trading Partner Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-4-creating-the-contoso-0c4-trading-partner-agreement.md)  
  
-   [<span data-ttu-id="8a60b-111">手順 5: Contoso 3 a 2 取引先アグリーメントの作成</span><span class="sxs-lookup"><span data-stu-id="8a60b-111">Step 5: Creating the Contoso 3A2 Trading Partner Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-5-creating-the-contoso-3a2-trading-partner-agreement.md)  
  
-   [<span data-ttu-id="8a60b-112">手順 6: Contoso 3A4 取引先アグリーメントの作成</span><span class="sxs-lookup"><span data-stu-id="8a60b-112">Step 6: Creating the Contoso 3A4 Trading Partner Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-6-creating-the-contoso-3a4-trading-partner-agreement.md)  
  
-   [<span data-ttu-id="8a60b-113">手順 7: ビルドと DoubleAction SDK サンプルの展開</span><span class="sxs-lookup"><span data-stu-id="8a60b-113">Step 7: Building and Deploying the DoubleAction SDK Sample</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-7-building-and-deploying-the-doubleaction-sdk-sample.md)