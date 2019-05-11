---
title: エンジン制御関数 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rules Engine, functions
ms.assetid: a7900e59-c52c-4a6d-9ca3-ee4ec659f9b5
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7339462fb21b77bb16627c5671a6246a2eefc4db
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65349461"
---
# <a name="engine-control-functions"></a><span data-ttu-id="6ab96-102">エンジン制御関数</span><span class="sxs-lookup"><span data-stu-id="6ab96-102">Engine Control Functions</span></span>
<span data-ttu-id="6ab96-103">このセクションでは、アプリケーションまたはポリシーをルール エンジンの作業メモリ内のファクトを制御できるようにするいくつかのビジネス ルール エンジン制御関数に関連する動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="6ab96-103">This section explains the behaviors associated with several Business Rule engine control functions that allow an application or policy to control the facts in the rule engine's working memory.</span></span> <span data-ttu-id="6ab96-104">作業メモリ内のファクトの存在はドライブは、評価する条件、および実行されるアクションです。</span><span class="sxs-lookup"><span data-stu-id="6ab96-104">The presence of facts in the working memory drives the conditions that are evaluated and the actions that are executed.</span></span>  
  
 <span data-ttu-id="6ab96-105">ここでは、 **Assert**、 **Retract**、 **RetractByType**、**再アサート**、および**Update**異なるファクト関数: .NET オブジェクト、 **TypedXmlDocument**、 **DataConnection**、および**TypedDataTable**します。</span><span class="sxs-lookup"><span data-stu-id="6ab96-105">This section examines the **Assert**, **Retract**, **RetractByType**, **Reassert**, and **Update** functions for different facts: .NET objects, **TypedXmlDocument**, **DataConnection**, and **TypedDataTable**.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6ab96-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6ab96-106">In This Section</span></span>  
  
-   [<span data-ttu-id="6ab96-107">Filter</span><span class="sxs-lookup"><span data-stu-id="6ab96-107">Assert</span></span>](../core/assert.md)  
  
-   [<span data-ttu-id="6ab96-108">Retract</span><span class="sxs-lookup"><span data-stu-id="6ab96-108">Retract</span></span>](../core/retract.md)  
  
-   [<span data-ttu-id="6ab96-109">RetractByType</span><span class="sxs-lookup"><span data-stu-id="6ab96-109">RetractByType</span></span>](../core/retractbytype.md)  
  
-   [<span data-ttu-id="6ab96-110">Reassert</span><span class="sxs-lookup"><span data-stu-id="6ab96-110">Reassert</span></span>](../core/reassert.md)  
  
-   [<span data-ttu-id="6ab96-111">Update</span><span class="sxs-lookup"><span data-stu-id="6ab96-111">Update</span></span>](../core/update1.md)  
  
-   [<span data-ttu-id="6ab96-112">Halt</span><span class="sxs-lookup"><span data-stu-id="6ab96-112">Halt</span></span>](../core/halt.md)