---
title: ビジネス プロセス管理ソリューションの開発 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- developing, process management solution tutorial
- process management solution tutorial, developing
ms.assetid: 3b590533-2b18-4e78-b9e5-88f4a680532f
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60632efe6cfc8d48d395d20949012354874c7e46
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239642"
---
# <a name="developing-a-business-process-management-solution"></a><span data-ttu-id="c5423-102">ビジネス プロセス管理ソリューションの開発</span><span class="sxs-lookup"><span data-stu-id="c5423-102">Developing a Business Process Management Solution</span></span>
<span data-ttu-id="c5423-103">このセクションでは、このソリューションの設計に関係する基本的なパターン、および、パターンを BizTalk コンポーネントや構造に変換する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c5423-103">This section describes the basic patterns involved in the design of the solution and how those patterns translate into BizTalk components and structures.</span></span> <span data-ttu-id="c5423-104">ここでは、ソリューションでの処理を通じた注文メッセージを扱い、追加実装の詳細、ソリューションのバージョン管理とサイズ調整、およびメッセージとファイル参照についても説明します。</span><span class="sxs-lookup"><span data-stu-id="c5423-104">It also follows an order message through processing in the solution, provides additional implementation details, tells you how to version and scale the solution, and provides message and file references.</span></span> <span data-ttu-id="c5423-105">ソリューションとその設計の背後にあるビジネス要件に関する詳細については、「ビジネス要件」を参照してください[ビジネス プロセス管理ソリューションを理解する](../core/understanding-the-business-process-management-solution.md)です。</span><span class="sxs-lookup"><span data-stu-id="c5423-105">For more information about the solution and the business requirements behind its design, see "Business Requirements" in [Understanding the Business Process Management Solution](../core/understanding-the-business-process-management-solution.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c5423-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c5423-106">In This Section</span></span>  
  
-   [<span data-ttu-id="c5423-107">ビジネス プロセス管理ソリューションのパターン</span><span class="sxs-lookup"><span data-stu-id="c5423-107">Patterns in the Business Process Management Solution</span></span>](../core/patterns-in-the-business-process-management-solution.md)  
  
-   [<span data-ttu-id="c5423-108">ビジネス プロセス管理ソリューションのコンポーネント</span><span class="sxs-lookup"><span data-stu-id="c5423-108">Components of the Business Process Management Solution</span></span>](../core/components-of-the-business-process-management-solution.md)  
  
-   [<span data-ttu-id="c5423-109">ビジネス プロセス管理ソリューションでの処理</span><span class="sxs-lookup"><span data-stu-id="c5423-109">Processing in the Business Process Management Solution</span></span>](../core/processing-in-the-business-process-management-solution.md)  
  
-   [<span data-ttu-id="c5423-110">ビジネス プロセス管理ソリューションの実装の要点</span><span class="sxs-lookup"><span data-stu-id="c5423-110">Implementation Highlights of the Business Process Management Solution</span></span>](../core/implementation-highlights-of-the-business-process-management-solution.md)  
  
-   [<span data-ttu-id="c5423-111">BAM によるビジネス プロセス管理ソリューションの監視</span><span class="sxs-lookup"><span data-stu-id="c5423-111">Monitoring the Business Process Management Solution with BAM</span></span>](../core/monitoring-the-business-process-management-solution-with-bam.md)  
  
-   [<span data-ttu-id="c5423-112">ビジネス プロセス管理ソリューションのバージョン管理</span><span class="sxs-lookup"><span data-stu-id="c5423-112">Versioning the Business Process Management Solution</span></span>](../core/versioning-the-business-process-management-solution.md)  
  
-   [<span data-ttu-id="c5423-113">ビジネス プロセス管理ソリューション リファレンス</span><span class="sxs-lookup"><span data-stu-id="c5423-113">Business Process Management Solution Reference</span></span>](../core/business-process-management-solution-reference.md)