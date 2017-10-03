---
title: "一括コピー Functoid |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- anyAttribute node
- Mass Copy functoids, about Mass Copy functoids
- any node
- Mass Copy functoids
ms.assetid: 228ff569-2e21-4e81-b564-6936241cdf6b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2fe0a9bc65369327a17591fb6adecb6bd6105333
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="mass-copy-functoid"></a>一括コピー Functoid
**一括コピー** functoid を含むスキーマを使用して、マップを有効に**任意**と**anyAttribute**要素。 これらの要素は、基本的に XML スキーマ定義言語に提供されているワイルドカードで、不明な構造や属性に一致します。  
  
 不明な構造体を使用してデータを処理できることに加えて、**一括コピー** functoid では、スキーマ開発を簡略化することができます: 処理されるスキーマの部分のみを詳細に指定する必要があります。  
  
 **一括コピー** functoid に接続されている送信元スキーマ ノードに対応する入力インスタンス メッセージ内の要素のコピー、**一括コピー** functoid です。 また、Functoid はサブ構造体をすべてコピーして、送信先スキーマのリンク先ノードの出力インスタンス メッセージに再作成します。 したがって、使用することも、**一括コピー** functoid を同一のサブ構造体を持つ送信元と送信先レコードをコピーします。  
  
 次の図に示しています、**一括コピー** functoid マップで使用します。  
  
 ![一括コピー functoid の使用方法を示すマップ](../core/media/masscopyfunctoid.gif "masscopyfunctoid")  
一括コピー Functoid マップ  
  
 次のような入力インスタンス メッセージがあるとします。  
  
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
  
 このメッセージの処理に上の図に示したマップを使用すると、出力インスタンス メッセージは入力インスタンス メッセージと同一になります。  
  
## <a name="see-also"></a>参照  
 [マップに一括コピー Functoid を追加する方法](../core/how-to-add-mass-copy-functoids-to-a-map.md)   
 [高度な Functoid](../core/advanced-functoids.md)   
 [基本 Functoid](../core/basic-functoids.md)   
 [リンクから、すべての要素および anyAttribute ノード](../core/links-to-and-from-the-any-element-and-anyattribute-nodes.md)