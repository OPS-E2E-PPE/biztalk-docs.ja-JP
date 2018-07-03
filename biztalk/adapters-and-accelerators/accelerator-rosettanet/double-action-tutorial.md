---
title: ダブル アクション チュートリアル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tutorials, PIPs
- double action tutorial, about the tutorial
- trading partners, tutorials
- double action tutorial
- tutorials, trading partners
- PIPs, tutorials
- tutorials, double action tutorial
ms.assetid: b692c043-82ef-46f4-8683-7ae1fd6e4421
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 220f853788462d3c9b53b8fb043c65ac54872fd0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973979"
---
# <a name="double-action-tutorial"></a><span data-ttu-id="978c0-102">ダブル アクション チュートリアル</span><span class="sxs-lookup"><span data-stu-id="978c0-102">Double Action Tutorial</span></span>
<span data-ttu-id="978c0-103">このチュートリアルの内容 Microsoft® を使用して、エンド ツー エンド ソリューション[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="978c0-103">This tutorial covers an end-to-end solution using Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span></span> <span data-ttu-id="978c0-104">ここでは、RosettaNet 準拠のソリューションを実装するために従う必要のある手順について詳しく説明します。この手順では、Contoso 社 (サプライヤー組織) と Fabrikam 社 (購入者組織) という 2 つの架空の会社間の取引先シナリオを作成します。</span><span class="sxs-lookup"><span data-stu-id="978c0-104">The tutorial details the steps that you have to follow to implement a RosettaNet-compliant solution by creating a trading partner scenario between two fictitious companies: Contoso, the supplier organization, and Fabrikam, the buyer organization.</span></span>  
  
 <span data-ttu-id="978c0-105">このチュートリアルでは、以下の 4 種類の PIP (Partner Interface Process) を使用します。</span><span class="sxs-lookup"><span data-stu-id="978c0-105">This tutorial uses four different Partner Interface Processes (PIPs):</span></span>  
  
- <span data-ttu-id="978c0-106">0C2 - Asynchronous Test Request (非同期のテスト要求)</span><span class="sxs-lookup"><span data-stu-id="978c0-106">0C2 - Asynchronous Test Request</span></span>  
  
- <span data-ttu-id="978c0-107">0C4 - Synchronous Test Query (同期のテスト照会)</span><span class="sxs-lookup"><span data-stu-id="978c0-107">0C4 - Synchronous Test Query</span></span>  
  
- <span data-ttu-id="978c0-108">3A2 - Request Price and Availability (価格とアベイラビリティの要求)</span><span class="sxs-lookup"><span data-stu-id="978c0-108">3A2 - Request Price and Availability</span></span>  
  
- <span data-ttu-id="978c0-109">3A4 - Request Purchase Order (発注の要求)</span><span class="sxs-lookup"><span data-stu-id="978c0-109">3A4 - Request Purchase Order</span></span>  
  
  <span data-ttu-id="978c0-110">このチュートリアルは、RosettaNet ベースのソリューションの複数の異なる領域に対応しています。これらの領域には、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 管理コンソールを使用した作業、基幹業務 (LOB) アプリケーションの作成、エンタープライズ リソース計画 (ERP) システムを統合するために使用できるカスタム オーケストレーションの作成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="978c0-110">This tutorial addresses several distinct areas of a RosettaNet-based solution, including working with the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Management Console, creating line-of-business (LOB) applications, and creating custom orchestrations that you can use to integrate Enterprise Resource Planning (ERP) systems.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="978c0-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="978c0-111">In This Section</span></span>  
  
-   [<span data-ttu-id="978c0-112">ダブル アクション チュートリアルの準備</span><span class="sxs-lookup"><span data-stu-id="978c0-112">Preparing for the Double Action Tutorial</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/preparing-for-the-double-action-tutorial.md)  
  
-   [<span data-ttu-id="978c0-113">Contoso ソリューションの作成と構成</span><span class="sxs-lookup"><span data-stu-id="978c0-113">Creating and Configuring the Contoso Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-and-configuring-the-contoso-solution.md)  
  
-   [<span data-ttu-id="978c0-114">Fabrikam ソリューションの作成と構成</span><span class="sxs-lookup"><span data-stu-id="978c0-114">Creating and Configuring the Fabrikam Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-and-configuring-the-fabrikam-solution.md)  
  
-   [<span data-ttu-id="978c0-115">ダブル アクション チュートリアルのテスト</span><span class="sxs-lookup"><span data-stu-id="978c0-115">Testing the Double Action Tutorial</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/testing-the-double-action-tutorial.md)