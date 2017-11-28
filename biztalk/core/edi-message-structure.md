---
title: "EDI メッセージの構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0c9a0447-447f-483c-825d-547c06ad691e
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9395ed5e0b03bda48e19d6413f95ca2e74a3f1e1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="edi-message-structure"></a><span data-ttu-id="93958-102">EDI メッセージの構造</span><span class="sxs-lookup"><span data-stu-id="93958-102">EDI Message Structure</span></span>
<span data-ttu-id="93958-103">EDI メッセージは、1 つのエンベロープと階層型の一連の構造体要素で構成されます。</span><span class="sxs-lookup"><span data-stu-id="93958-103">EDI messages consist of an envelope and a hierarchical series of structural elements.</span></span> <span data-ttu-id="93958-104">エンベロープにはヘッダーとトレーラーのセットが含まれ、各セットは構造体要素を記述および格納します。</span><span class="sxs-lookup"><span data-stu-id="93958-104">The envelope contains a set of headers and trailers, each set of which describes and contains a structural element.</span></span> <span data-ttu-id="93958-105">この構造体要素には、次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="93958-105">These structural elements are as follows:</span></span>  
  
```  
Interchange  
   Group  
      Transaction set/message  
         Segment  
            Data Element  
               Sub Element  
```  
  
 <span data-ttu-id="93958-106">EDI メッセージの階層構造により、トランザクション セット/メッセージおよびグループをバッチ処理できます。</span><span class="sxs-lookup"><span data-stu-id="93958-106">The hierarchical structure of an EDI message enables transaction sets/messages and groups to be batched.</span></span> <span data-ttu-id="93958-107">インターチェンジに 1 つのトランザクション セット/メッセージと 1 つのグループのみが含まれる場合でも、そのインターチェンジは、バッチ処理された場合と同じ基本的な構造体要素を使用して構造化されます。ただし、複数のトランザクション セット/メッセージまたはグループ要素がある場合を除きます。</span><span class="sxs-lookup"><span data-stu-id="93958-107">Even if an interchange contains only one transaction set/message and only one group, that interchange is structured with the same basic structural elements that it would have if it were batched, with the exception that there would not be multiple transaction set/message or group elements.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="93958-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="93958-108">In This Section</span></span>  
  
-   [<span data-ttu-id="93958-109">EDI ヘッダーとトレーラー</span><span class="sxs-lookup"><span data-stu-id="93958-109">EDI Headers and Trailers</span></span>](../core/edi-headers-and-trailers.md)  
  
-   [<span data-ttu-id="93958-110">EDI インターチェンジの構造体要素</span><span class="sxs-lookup"><span data-stu-id="93958-110">EDI Interchange Structural Element</span></span>](../core/edi-interchange-structural-element.md)  
  
-   [<span data-ttu-id="93958-111">EDI グループの構造体要素</span><span class="sxs-lookup"><span data-stu-id="93958-111">EDI Group Structural Element</span></span>](../core/edi-group-structural-element.md)  
  
-   [<span data-ttu-id="93958-112">EDI トランザクション セット メッセージの構造体要素</span><span class="sxs-lookup"><span data-stu-id="93958-112">EDI Transaction Set-Message Structural Element</span></span>](../core/edi-transaction-set-message-structural-element.md)  
  
-   [<span data-ttu-id="93958-113">EDI セグメントの構造体要素</span><span class="sxs-lookup"><span data-stu-id="93958-113">EDI Segment Structural Element</span></span>](../core/edi-segment-structural-element.md)  
  
-   [<span data-ttu-id="93958-114">EDI データ要素の構造体要素</span><span class="sxs-lookup"><span data-stu-id="93958-114">EDI Data Element Structural Element</span></span>](../core/edi-data-element-structural-element.md)