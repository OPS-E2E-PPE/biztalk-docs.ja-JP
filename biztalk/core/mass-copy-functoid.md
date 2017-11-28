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
# <a name="mass-copy-functoid"></a><span data-ttu-id="97aae-102">一括コピー Functoid</span><span class="sxs-lookup"><span data-stu-id="97aae-102">Mass Copy Functoid</span></span>
<span data-ttu-id="97aae-103">**一括コピー** functoid を含むスキーマを使用して、マップを有効に**任意**と**anyAttribute**要素。</span><span class="sxs-lookup"><span data-stu-id="97aae-103">The **Mass Copy** functoid enables your maps to use schemas that include **any** and **anyAttribute** elements.</span></span> <span data-ttu-id="97aae-104">これらの要素は、基本的に XML スキーマ定義言語に提供されているワイルドカードで、不明な構造や属性に一致します。</span><span class="sxs-lookup"><span data-stu-id="97aae-104">These elements are, in essence, wildcards provided in the XML Schema definition language to match unknown structures or attributes.</span></span>  
  
 <span data-ttu-id="97aae-105">不明な構造体を使用してデータを処理できることに加えて、**一括コピー** functoid では、スキーマ開発を簡略化することができます: 処理されるスキーマの部分のみを詳細に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97aae-105">In addition to handling data with unknown structure, the **Mass Copy** functoid enables you to simplify schema development: only the portions of a schema that will be processed need to be specified in detail.</span></span>  
  
 <span data-ttu-id="97aae-106">**一括コピー** functoid に接続されている送信元スキーマ ノードに対応する入力インスタンス メッセージ内の要素のコピー、**一括コピー** functoid です。</span><span class="sxs-lookup"><span data-stu-id="97aae-106">The **Mass Copy** functoid copies the element in the input instance message corresponding to the source schema node connected to the **Mass Copy** functoid.</span></span> <span data-ttu-id="97aae-107">また、Functoid はサブ構造体をすべてコピーして、送信先スキーマのリンク先ノードの出力インスタンス メッセージに再作成します。</span><span class="sxs-lookup"><span data-stu-id="97aae-107">The functoid also copies any and all of its substructure, and re-creates it in the output instance message at the linked node in the destination schema.</span></span> <span data-ttu-id="97aae-108">したがって、使用することも、**一括コピー** functoid を同一のサブ構造体を持つ送信元と送信先レコードをコピーします。</span><span class="sxs-lookup"><span data-stu-id="97aae-108">Thus, you can also use the **Mass Copy** functoid to copy any source and destination records having identical substructures.</span></span>  
  
 <span data-ttu-id="97aae-109">次の図に示しています、**一括コピー** functoid マップで使用します。</span><span class="sxs-lookup"><span data-stu-id="97aae-109">The following figure shows the **Mass Copy** functoid used in a map.</span></span>  
  
 <span data-ttu-id="97aae-110">![一括コピー functoid の使用方法を示すマップ](../core/media/masscopyfunctoid.gif "masscopyfunctoid")</span><span class="sxs-lookup"><span data-stu-id="97aae-110">![Map illustrating the use of the mass copy functoid](../core/media/masscopyfunctoid.gif "masscopyfunctoid")</span></span>  
<span data-ttu-id="97aae-111">一括コピー Functoid マップ</span><span class="sxs-lookup"><span data-stu-id="97aae-111">Mass Copy Functoid Map</span></span>  
  
 <span data-ttu-id="97aae-112">次のような入力インスタンス メッセージがあるとします。</span><span class="sxs-lookup"><span data-stu-id="97aae-112">Consider the following input instance message.</span></span>  
  
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
  
 <span data-ttu-id="97aae-113">このメッセージの処理に上の図に示したマップを使用すると、出力インスタンス メッセージは入力インスタンス メッセージと同一になります。</span><span class="sxs-lookup"><span data-stu-id="97aae-113">If the preceding map were used to process this message, the output instance message would be identical to the input instance message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97aae-114">参照</span><span class="sxs-lookup"><span data-stu-id="97aae-114">See Also</span></span>  
 <span data-ttu-id="97aae-115">[マップに一括コピー Functoid を追加する方法](../core/how-to-add-mass-copy-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="97aae-115">[How to Add Mass Copy Functoids to a Map](../core/how-to-add-mass-copy-functoids-to-a-map.md) </span></span>  
 <span data-ttu-id="97aae-116">[高度な Functoid](../core/advanced-functoids.md) </span><span class="sxs-lookup"><span data-stu-id="97aae-116">[Advanced Functoids](../core/advanced-functoids.md) </span></span>  
 <span data-ttu-id="97aae-117">[基本 Functoid](../core/basic-functoids.md) </span><span class="sxs-lookup"><span data-stu-id="97aae-117">[Basic Functoids](../core/basic-functoids.md) </span></span>  
 [<span data-ttu-id="97aae-118">リンクから、すべての要素および anyAttribute ノード</span><span class="sxs-lookup"><span data-stu-id="97aae-118">Links To and From the Any Element and anyAttribute Nodes</span></span>](../core/links-to-and-from-the-any-element-and-anyattribute-nodes.md)