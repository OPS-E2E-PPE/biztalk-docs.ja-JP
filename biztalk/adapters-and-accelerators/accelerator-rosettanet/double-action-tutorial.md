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
ms.openlocfilehash: 84d1e143385b55a1891255e96ec97974f4bdca89
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283784"
---
# <a name="double-action-tutorial"></a><span data-ttu-id="d1b65-102">ダブル アクション チュートリアル</span><span class="sxs-lookup"><span data-stu-id="d1b65-102">Double Action Tutorial</span></span>
<span data-ttu-id="d1b65-103">このチュートリアルの内容 Microsoft® を使用して、エンド ツー エンド ソリューション[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="d1b65-103">This tutorial covers an end-to-end solution using Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span></span> <span data-ttu-id="d1b65-104">このチュートリアルには、2 つの架空の会社間の取引パートナー シナリオを作成して、RosettaNet 準拠のソリューションを実装するために従う必要のある手順が詳しく説明します。Contoso、サプライヤーの組織と Fabrikam の購入者組織の場合は。</span><span class="sxs-lookup"><span data-stu-id="d1b65-104">The tutorial details the steps that you have to follow to implement a RosettaNet-compliant solution by creating a trading partner scenario between two fictitious companies: Contoso, the supplier organization, and Fabrikam, the buyer organization.</span></span>  
  
 <span data-ttu-id="d1b65-105">このチュートリアルでは、次の 4 つ異なる Partner Interface Process (Pip) を使用します。</span><span class="sxs-lookup"><span data-stu-id="d1b65-105">This tutorial uses four different Partner Interface Processes (PIPs):</span></span>  
  
- <span data-ttu-id="d1b65-106">0c2 - 非同期テスト要求</span><span class="sxs-lookup"><span data-stu-id="d1b65-106">0C2 - Asynchronous Test Request</span></span>  
  
- <span data-ttu-id="d1b65-107">0 C 4 - クエリの同期のテスト</span><span class="sxs-lookup"><span data-stu-id="d1b65-107">0C4 - Synchronous Test Query</span></span>  
  
- <span data-ttu-id="d1b65-108">3 a 2 - Request Price and Availability</span><span class="sxs-lookup"><span data-stu-id="d1b65-108">3A2 - Request Price and Availability</span></span>  
  
- <span data-ttu-id="d1b65-109">3A4 - 注文書の要求</span><span class="sxs-lookup"><span data-stu-id="d1b65-109">3A4 - Request Purchase Order</span></span>  
  
  <span data-ttu-id="d1b65-110">このチュートリアルのアドレスの処理など、RosettaNet ベースのソリューションのいくつかの異なる領域、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]管理コンソールで、基幹業務 (LOB) アプリケーションを作成して、統合に使用できるカスタム オーケストレーションの作成エンタープライズ リソース プランニング (ERP) システムです。</span><span class="sxs-lookup"><span data-stu-id="d1b65-110">This tutorial addresses several distinct areas of a RosettaNet-based solution, including working with the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Management Console, creating line-of-business (LOB) applications, and creating custom orchestrations that you can use to integrate Enterprise Resource Planning (ERP) systems.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d1b65-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d1b65-111">In This Section</span></span>  
  
-   [<span data-ttu-id="d1b65-112">ダブル アクション チュートリアルの準備</span><span class="sxs-lookup"><span data-stu-id="d1b65-112">Preparing for the Double Action Tutorial</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/preparing-for-the-double-action-tutorial.md)  
  
-   [<span data-ttu-id="d1b65-113">Contoso ソリューションの作成と構成</span><span class="sxs-lookup"><span data-stu-id="d1b65-113">Creating and Configuring the Contoso Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-and-configuring-the-contoso-solution.md)  
  
-   [<span data-ttu-id="d1b65-114">Fabrikam ソリューションの作成と構成</span><span class="sxs-lookup"><span data-stu-id="d1b65-114">Creating and Configuring the Fabrikam Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-and-configuring-the-fabrikam-solution.md)  
  
-   [<span data-ttu-id="d1b65-115">ダブル アクション チュートリアルのテスト</span><span class="sxs-lookup"><span data-stu-id="d1b65-115">Testing the Double Action Tutorial</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/testing-the-double-action-tutorial.md)