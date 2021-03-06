---
title: 一括コピー Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- anyAttribute node
- Mass Copy functoids, about Mass Copy functoids
- any node
- Mass Copy functoids
ms.assetid: 228ff569-2e21-4e81-b564-6936241cdf6b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ffd3cb15f74bef774a9794d0fa6dbe910971f1b3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380041"
---
# <a name="mass-copy-functoid"></a>一括コピー Functoid
**一括コピー**により、マップが含まれるスキーマを使用して、functoid**任意**と**anyAttribute**要素。 これらの要素は、基本的に XML スキーマ定義言語に提供されているワイルドカードで、不明な構造や属性に一致します。  
  
 不明な構造を使用してデータを処理できることに加えて、**一括コピー** functoid では、スキーマ開発を簡略化することができます: 処理されるスキーマの部分のみが詳細で指定する必要があります。  
  
 **一括コピー** functoid に接続されている送信元スキーマ ノードに対応する入力インスタンス メッセージ内の要素のコピー、**一括コピー** functoid。 Functoid は、サブ構造体をすべてコピーし、送信先スキーマのリンク先ノードに、出力インスタンス メッセージで再作成します。 そのため、使用することも、**一括コピー** functoid を同一のサブ構造体を持つ送信元と送信先レコードをコピーします。  
  
 次に示します、**一括コピー** functoid のマップで使用します。  
  
 ![一括コピー functoid の使用方法を示すマップ](../core/media/masscopyfunctoid.gif "masscopyfunctoid")  
一括コピー Functoid マップ  
  
 次の入力インスタンス メッセージを検討してください。  
  
```  
<ns0:Root xmlns:ns0="http://MassCopy.ComplexDocument">  
    <PurchaseOrder>  
        <From>Kevin F. Browne</From>  
        <To>Northwind Traders</To>  
        <LineItems>  
            <Item>  
                <Product>Laptop Computer</Product>  
                <Description>Thin profile laptop</Description>  
                <Price>1999.95</Price>  
                <Quantity>1</Quantity>  
            </Item>  
        </LineItems>  
    </PurchaseOrder>  
</ns0:Root>  
```  
  
 図に示したマップ、このメッセージの処理に使用されていた場合、出力インスタンス メッセージは、入力インスタンス メッセージを同一になります。  
  
## <a name="see-also"></a>参照  
 [マップに一括コピー Functoid を追加する方法](../core/how-to-add-mass-copy-functoids-to-a-map.md)   
 [高度な Functoid](../core/advanced-functoids.md)   
 [基本 Functoid](../core/basic-functoids.md)   
 [anyElement ノードおよび anyAttribute ノード間のリンク](../core/links-to-and-from-the-any-element-and-anyattribute-nodes.md)