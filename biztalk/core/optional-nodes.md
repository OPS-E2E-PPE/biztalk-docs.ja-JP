---
title: "省略可能なノード |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- testing, BizTalk Mapper
- maps, testing
- testing, maps
- BizTalk Mapper, testing
- maps, optional nodes
ms.assetid: 7dcd203e-fb23-438a-87d1-42323acd87cc
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96cf7d8b22ee8469a7e52dba7bbad899209c5274
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="optional-nodes"></a><span data-ttu-id="ba800-102">省略可能なノード</span><span class="sxs-lookup"><span data-stu-id="ba800-102">Optional Nodes</span></span>
<span data-ttu-id="ba800-103">省略可能なノードを使用すると、マップをテストしたときに警告が生成されます。</span><span class="sxs-lookup"><span data-stu-id="ba800-103">Using optional nodes will produce a warning when you test your map.</span></span> <span data-ttu-id="ba800-104">送信元ノードが省略可能であると見なされる条件には、次の 2 つがあります。</span><span class="sxs-lookup"><span data-stu-id="ba800-104">There are two conditions in which a source node may be considered optional:</span></span>  
  
-   <span data-ttu-id="ba800-105">実際のレコードまたはフィールドが省略可能である。</span><span class="sxs-lookup"><span data-stu-id="ba800-105">The actual record or field is optional.</span></span>  
  
-   <span data-ttu-id="ba800-106">送信元のレコードまたはフィールドは必須であるが、親、先祖、それより上位の階層が省略可能である。</span><span class="sxs-lookup"><span data-stu-id="ba800-106">The source record or field is required, but a parent, grandparent, and farther up the hierarchy is optional.</span></span>  
  
 <span data-ttu-id="ba800-107">たとえば、送信元スキーマに省略可能なレコードやフィールドがあり、送信先スキーマに対応するレコードまたはフィールドが必要な場合などが考えられます。</span><span class="sxs-lookup"><span data-stu-id="ba800-107">You may have situations when you have records and fields in a source schema that are optional, but the destination schema requires the corresponding records or fields.</span></span>  
  
 <span data-ttu-id="ba800-108">可能な条件の両方で、マップのテストで警告を生成、**出力**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="ba800-108">In both of the possible conditions, testing your map produces a warning in the **Output** window.</span></span> <span data-ttu-id="ba800-109">また、出力データは対象ノードには取り込まれません。</span><span class="sxs-lookup"><span data-stu-id="ba800-109">In addition, the output data will not include the target node.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba800-110">参照</span><span class="sxs-lookup"><span data-stu-id="ba800-110">See Also</span></span>  
 [<span data-ttu-id="ba800-111">マップのテスト</span><span class="sxs-lookup"><span data-stu-id="ba800-111">Testing Maps</span></span>](../core/testing-maps.md)