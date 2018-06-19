---
title: EDI メッセージの構造体 |Microsoft ドキュメント
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
ms.openlocfilehash: 9395ed5e0b03bda48e19d6413f95ca2e74a3f1e1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239634"
---
# <a name="edi-message-structure"></a>EDI メッセージの構造
EDI メッセージは、1 つのエンベロープと階層型の一連の構造体要素で構成されます。 エンベロープにはヘッダーとトレーラーのセットが含まれ、各セットは構造体要素を記述および格納します。 この構造体要素には、次のものがあります。  
  
```  
Interchange  
   Group  
      Transaction set/message  
         Segment  
            Data Element  
               Sub Element  
```  
  
 EDI メッセージの階層構造により、トランザクション セット/メッセージおよびグループをバッチ処理できます。 インターチェンジに 1 つのトランザクション セット/メッセージと 1 つのグループのみが含まれる場合でも、そのインターチェンジは、バッチ処理された場合と同じ基本的な構造体要素を使用して構造化されます。ただし、複数のトランザクション セット/メッセージまたはグループ要素がある場合を除きます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [EDI ヘッダーとトレーラー](../core/edi-headers-and-trailers.md)  
  
-   [EDI インターチェンジの構造体要素](../core/edi-interchange-structural-element.md)  
  
-   [EDI グループの構造体要素](../core/edi-group-structural-element.md)  
  
-   [EDI トランザクション セット メッセージの構造体要素](../core/edi-transaction-set-message-structural-element.md)  
  
-   [EDI セグメントの構造体要素](../core/edi-segment-structural-element.md)  
  
-   [EDI データ要素の構造体要素](../core/edi-data-element-structural-element.md)