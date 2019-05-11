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
# <a name="edi-message-structure"></a>EDI メッセージの構造
EDI メッセージは、エンベロープと階層的な一連の構造体要素で構成されます。 エンベロープには、一連のヘッダーとトレーラー、各セットが含まれていますがについて説明しますと、構造体の要素が含まれています。 これらの構造体の要素は次のとおりです。  
  
```  
Interchange  
   Group  
      Transaction set/message  
         Segment  
            Data Element  
               Sub Element  
```  
  
 EDI メッセージの階層構造では、トランザクション セット/メッセージとバッチ処理するグループを使用できます。 インターチェンジが、同じ基本的な構造体要素をバッチ処理された場合に構造化されたインターチェンジに 1 つのみのトランザクション セット/メッセージと 1 つだけのグループが含まれる場合でも、例外のことがない複数のトランザクション セット/メッセージまたはグループの要素。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [EDI ヘッダーとトレーラー](../core/edi-headers-and-trailers.md)  
  
-   [EDI のインターチェンジ構造体要素](../core/edi-interchange-structural-element.md)  
  
-   [EDI のグループ構造体要素](../core/edi-group-structural-element.md)  
  
-   [EDI トランザクション セット/メッセージの構造体要素](../core/edi-transaction-set-message-structural-element.md)  
  
-   [EDI セグメントの構造要素](../core/edi-segment-structural-element.md)  
  
-   [EDI データ要素の構造体要素](../core/edi-data-element-structural-element.md)