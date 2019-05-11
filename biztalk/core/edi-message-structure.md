---
title: EDI メッセージの構造 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0c9a0447-447f-483c-825d-547c06ad691e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8584f0c002fac052f5ed6a0cb2b8885587821e8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389207"
---
# <a name="edi-message-structure"></a><span data-ttu-id="be3a9-102">EDI メッセージの構造</span><span class="sxs-lookup"><span data-stu-id="be3a9-102">EDI Message Structure</span></span>
<span data-ttu-id="be3a9-103">EDI メッセージは、エンベロープと階層的な一連の構造体要素で構成されます。</span><span class="sxs-lookup"><span data-stu-id="be3a9-103">EDI messages consist of an envelope and a hierarchical series of structural elements.</span></span> <span data-ttu-id="be3a9-104">エンベロープには、一連のヘッダーとトレーラー、各セットが含まれていますがについて説明しますと、構造体の要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="be3a9-104">The envelope contains a set of headers and trailers, each set of which describes and contains a structural element.</span></span> <span data-ttu-id="be3a9-105">これらの構造体の要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="be3a9-105">These structural elements are as follows:</span></span>  
  
```  
Interchange  
   Group  
      Transaction set/message  
         Segment  
            Data Element  
               Sub Element  
```  
  
 <span data-ttu-id="be3a9-106">EDI メッセージの階層構造では、トランザクション セット/メッセージとバッチ処理するグループを使用できます。</span><span class="sxs-lookup"><span data-stu-id="be3a9-106">The hierarchical structure of an EDI message enables transaction sets/messages and groups to be batched.</span></span> <span data-ttu-id="be3a9-107">インターチェンジが、同じ基本的な構造体要素をバッチ処理された場合に構造化されたインターチェンジに 1 つのみのトランザクション セット/メッセージと 1 つだけのグループが含まれる場合でも、例外のことがない複数のトランザクション セット/メッセージまたはグループの要素。</span><span class="sxs-lookup"><span data-stu-id="be3a9-107">Even if an interchange contains only one transaction set/message and only one group, that interchange is structured with the same basic structural elements that it would have if it were batched, with the exception that there would not be multiple transaction set/message or group elements.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="be3a9-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="be3a9-108">In This Section</span></span>  
  
-   [<span data-ttu-id="be3a9-109">EDI ヘッダーとトレーラー</span><span class="sxs-lookup"><span data-stu-id="be3a9-109">EDI Headers and Trailers</span></span>](../core/edi-headers-and-trailers.md)  
  
-   [<span data-ttu-id="be3a9-110">EDI のインターチェンジ構造体要素</span><span class="sxs-lookup"><span data-stu-id="be3a9-110">EDI Interchange Structural Element</span></span>](../core/edi-interchange-structural-element.md)  
  
-   [<span data-ttu-id="be3a9-111">EDI のグループ構造体要素</span><span class="sxs-lookup"><span data-stu-id="be3a9-111">EDI Group Structural Element</span></span>](../core/edi-group-structural-element.md)  
  
-   [<span data-ttu-id="be3a9-112">EDI トランザクション セット/メッセージの構造体要素</span><span class="sxs-lookup"><span data-stu-id="be3a9-112">EDI Transaction Set-Message Structural Element</span></span>](../core/edi-transaction-set-message-structural-element.md)  
  
-   [<span data-ttu-id="be3a9-113">EDI セグメントの構造要素</span><span class="sxs-lookup"><span data-stu-id="be3a9-113">EDI Segment Structural Element</span></span>](../core/edi-segment-structural-element.md)  
  
-   [<span data-ttu-id="be3a9-114">EDI データ要素の構造体要素</span><span class="sxs-lookup"><span data-stu-id="be3a9-114">EDI Data Element Structural Element</span></span>](../core/edi-data-element-structural-element.md)