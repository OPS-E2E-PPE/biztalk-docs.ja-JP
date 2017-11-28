---
title: "エンジン制御関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Business Rules Engine, functions
ms.assetid: a7900e59-c52c-4a6d-9ca3-ee4ec659f9b5
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 033a4213a6552319f44a98e23562d7e8703fdd42
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="engine-control-functions"></a><span data-ttu-id="065d9-102">エンジン制御関数</span><span class="sxs-lookup"><span data-stu-id="065d9-102">Engine Control Functions</span></span>
<span data-ttu-id="065d9-103">このセクションでは、アプリケーションまたはポリシーがルール エンジンの作業メモリ内のファクトを制御できるようにするビジネス ルール エンジンの制御関数に関連する動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="065d9-103">This section explains the behaviors associated with several Business Rule engine control functions that allow an application or policy to control the facts in the rule engine's working memory.</span></span> <span data-ttu-id="065d9-104">作業メモリ内に存在するファクトによって、評価される条件と実行されるアクションが決まります。</span><span class="sxs-lookup"><span data-stu-id="065d9-104">The presence of facts in the working memory drives the conditions that are evaluated and the actions that are executed.</span></span>  
  
 <span data-ttu-id="065d9-105">このセクションの内容を調べ、 **Assert**、 **Retract**、 **RetractByType**、 **Reassert**、および**更新**異なるファクト関数: .NET オブジェクト、 **TypedXmlDocument**、 **DataConnection**、および**TypedDataTable**です。</span><span class="sxs-lookup"><span data-stu-id="065d9-105">This section examines the **Assert**, **Retract**, **RetractByType**, **Reassert**, and **Update** functions for different facts: .NET objects, **TypedXmlDocument**, **DataConnection**, and **TypedDataTable**.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="065d9-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="065d9-106">In This Section</span></span>  
  
-   [<span data-ttu-id="065d9-107">Filter</span><span class="sxs-lookup"><span data-stu-id="065d9-107">Assert</span></span>](../core/assert.md)  
  
-   [<span data-ttu-id="065d9-108">取り消し</span><span class="sxs-lookup"><span data-stu-id="065d9-108">Retract</span></span>](../core/retract.md)  
  
-   [<span data-ttu-id="065d9-109">RetractByType</span><span class="sxs-lookup"><span data-stu-id="065d9-109">RetractByType</span></span>](../core/retractbytype.md)  
  
-   [<span data-ttu-id="065d9-110">再アサート</span><span class="sxs-lookup"><span data-stu-id="065d9-110">Reassert</span></span>](../core/reassert.md)  
  
-   [<span data-ttu-id="065d9-111">Update</span><span class="sxs-lookup"><span data-stu-id="065d9-111">Update</span></span>](../core/update1.md)  
  
-   [<span data-ttu-id="065d9-112">停止</span><span class="sxs-lookup"><span data-stu-id="065d9-112">Halt</span></span>](../core/halt.md)