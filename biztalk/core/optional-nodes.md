---
title: 省略可能なノード |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing, BizTalk Mapper
- maps, testing
- testing, maps
- BizTalk Mapper, testing
- maps, optional nodes
ms.assetid: 7dcd203e-fb23-438a-87d1-42323acd87cc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bbab14a66f0ac88f32e945bf7b9c738eb419b654
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323402"
---
# <a name="optional-nodes"></a><span data-ttu-id="a0ac5-102">省略可能なノード</span><span class="sxs-lookup"><span data-stu-id="a0ac5-102">Optional Nodes</span></span>
<span data-ttu-id="a0ac5-103">省略可能なノードを使用して、マップをテストするときに警告が生成されます。</span><span class="sxs-lookup"><span data-stu-id="a0ac5-103">Using optional nodes will produce a warning when you test your map.</span></span> <span data-ttu-id="a0ac5-104">省略可能な見なすことがソース ノードを 2 つの条件があります。</span><span class="sxs-lookup"><span data-stu-id="a0ac5-104">There are two conditions in which a source node may be considered optional:</span></span>  
  
- <span data-ttu-id="a0ac5-105">実際のレコードまたはフィールドは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="a0ac5-105">The actual record or field is optional.</span></span>  
  
- <span data-ttu-id="a0ac5-106">ソースのレコードまたはフィールドが必要ですが、親、親の親、およびそれより上位の階層は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="a0ac5-106">The source record or field is required, but a parent, grandparent, and farther up the hierarchy is optional.</span></span>  
  
  <span data-ttu-id="a0ac5-107">場合は、レコードと省略可能な送信元スキーマ内のフィールドがあるときにする必要がありますが、送信先スキーマは、対応するレコードまたはフィールドが必要です。</span><span class="sxs-lookup"><span data-stu-id="a0ac5-107">You may have situations when you have records and fields in a source schema that are optional, but the destination schema requires the corresponding records or fields.</span></span>  
  
  <span data-ttu-id="a0ac5-108">可能な条件の両方で、マップのテストで警告を生成、**出力**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="a0ac5-108">In both of the possible conditions, testing your map produces a warning in the **Output** window.</span></span> <span data-ttu-id="a0ac5-109">さらに、出力データは、ターゲット ノードは含まれません。</span><span class="sxs-lookup"><span data-stu-id="a0ac5-109">In addition, the output data will not include the target node.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0ac5-110">参照</span><span class="sxs-lookup"><span data-stu-id="a0ac5-110">See Also</span></span>  
 [<span data-ttu-id="a0ac5-111">マップのテスト</span><span class="sxs-lookup"><span data-stu-id="a0ac5-111">Testing Maps</span></span>](../core/testing-maps.md)