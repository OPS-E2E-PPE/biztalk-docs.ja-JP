---
title: "ビジネスの実装の重要なポイント プロセス管理ソリューション |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: process management solution tutorial, implementing
ms.assetid: 3558db0e-d7f6-4c10-bd58-1601bd44e73f
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: decad6f68398cca2d0b88c4904d3e63c075749b3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="implementation-highlights-of-the-business-process-management-solution"></a><span data-ttu-id="67d0c-102">ビジネス プロセス管理ソリューションの実装の要点</span><span class="sxs-lookup"><span data-stu-id="67d0c-102">Implementation Highlights of the Business Process Management Solution</span></span>
<span data-ttu-id="67d0c-103">このセクションでは、企業間取引ソリューションの実装関連の要素を詳細に説明します。</span><span class="sxs-lookup"><span data-stu-id="67d0c-103">This section describes the implementation-related elements of the solution in greater detail.</span></span> <span data-ttu-id="67d0c-104">これらの要素にビジネス ルール フレームワーク、処理ステージの数は、方法、 **OrderManager**処理ステージの使用と通信する、 **OrderHandler**オブジェクト、方法アプリケーションでは、Ops アダプタを使用します。</span><span class="sxs-lookup"><span data-stu-id="67d0c-104">These elements include the Business Rules Framework, the number of processing stages, how the **OrderManager** communicates with the processing stages, the use of the **OrderHandler** object, and how the application uses the Ops Adapter.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="67d0c-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="67d0c-105">In This Section</span></span>  
  
-   [<span data-ttu-id="67d0c-106">ビジネス ルールによる検証</span><span class="sxs-lookup"><span data-stu-id="67d0c-106">Validation with Business Rules</span></span>](../core/validation-with-business-rules.md)  
  
-   [<span data-ttu-id="67d0c-107">処理ステージの数</span><span class="sxs-lookup"><span data-stu-id="67d0c-107">Number of Processing Stages</span></span>](../core/number-of-processing-stages.md)  
  
-   [<span data-ttu-id="67d0c-108">逆のパートナーの直接バインド</span><span class="sxs-lookup"><span data-stu-id="67d0c-108">Inverse Direct Partner Binding</span></span>](../core/inverse-direct-partner-binding.md)  
  
-   [<span data-ttu-id="67d0c-109">OrderBroker と OrderManager 間の通信</span><span class="sxs-lookup"><span data-stu-id="67d0c-109">Communication between OrderBroker and OrderManager</span></span>](../core/communication-between-orderbroker-and-ordermanager.md)  
  
-   [<span data-ttu-id="67d0c-110">ビジネス プロセス管理ソリューションで SSO の効率的な使用</span><span class="sxs-lookup"><span data-stu-id="67d0c-110">Using SSO Efficiently in the Business Process Management Solution</span></span>](../core/using-sso-efficiently-in-the-business-process-management-solution.md)  
  
-   [<span data-ttu-id="67d0c-111">Order Handler オブジェクトを使用して、バックエンド システムと通信するには</span><span class="sxs-lookup"><span data-stu-id="67d0c-111">Using the Order Handler Object to Communicate with Backend Systems</span></span>](../core/using-the-order-handler-object-to-communicate-with-backend-systems.md)  
  
-   [<span data-ttu-id="67d0c-112">XML ドキュメントのマージ</span><span class="sxs-lookup"><span data-stu-id="67d0c-112">Merging XML Documents</span></span>](../core/merging-xml-documents.md)  
  
-   [<span data-ttu-id="67d0c-113">Ops アダプタ</span><span class="sxs-lookup"><span data-stu-id="67d0c-113">The Ops Adapter</span></span>](../core/the-ops-adapter.md)  
  
-   [<span data-ttu-id="67d0c-114">Recaller オブジェクト</span><span class="sxs-lookup"><span data-stu-id="67d0c-114">The Recaller Object</span></span>](../core/the-recaller-object.md)