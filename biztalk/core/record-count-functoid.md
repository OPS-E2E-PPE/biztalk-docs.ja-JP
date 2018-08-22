---
title: レコード カウント Functoid |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Max Occurs property
- Record Count functoids
ms.assetid: e6aab13f-afbe-4401-abbe-020570e2ff16
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87653709bf5d52c21537064bad286078ad625cf0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268746"
---
# <a name="record-count-functoid"></a><span data-ttu-id="aa4dc-102">レコード カウント Functoid</span><span class="sxs-lookup"><span data-stu-id="aa4dc-102">Record Count Functoid</span></span>
<span data-ttu-id="aa4dc-103">**レコード カウント**functoid は、入力インスタンス メッセージ内のレコードをカウントします。</span><span class="sxs-lookup"><span data-stu-id="aa4dc-103">The **Record Count** functoid counts records in the input instance message.</span></span>  
  
 <span data-ttu-id="aa4dc-104">**レコード カウント**functoid が 1 つの入力と 1 つの出力。</span><span class="sxs-lookup"><span data-stu-id="aa4dc-104">The **Record Count** functoid has one input and one output.</span></span> <span data-ttu-id="aa4dc-105">入力は、送信元スキーマのループ レコードからリンクになります。</span><span class="sxs-lookup"><span data-stu-id="aa4dc-105">The input is a link from a looping record in the source schema.</span></span> <span data-ttu-id="aa4dc-106">出力、**レコード カウント**functoid は、実際の入力インスタンス メッセージ内のループ レコードの数。</span><span class="sxs-lookup"><span data-stu-id="aa4dc-106">The output of the **Record Count** functoid is the count of the looping record in an actual input instance message.</span></span>  
  
 <span data-ttu-id="aa4dc-107">ループ レコードは、入力インスタンス メッセージ内にある、繰り返し回数が不明な要素に対応します。</span><span class="sxs-lookup"><span data-stu-id="aa4dc-107">Looping records correspond to elements that repeat an unpredictable number of times in an input instance message.</span></span> <span data-ttu-id="aa4dc-108">たとえば、発注書で、**項目**要素が何度も発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="aa4dc-108">For example, in a purchase order, the **Item** element might occur many times.</span></span> <span data-ttu-id="aa4dc-109">また、**項目**要素には、製品、説明、価格、および数量を含めることがあります。</span><span class="sxs-lookup"><span data-stu-id="aa4dc-109">And, the **Item** element might include products, descriptions, prices, and quantities.</span></span> <span data-ttu-id="aa4dc-110">次のコードは、このような注文書の簡単な例を示しています。</span><span class="sxs-lookup"><span data-stu-id="aa4dc-110">The following code is a simplified example of such a purchase order.</span></span>  
  
```  
<ns0:PurchaseOrder xmlns:ns0="http://RecordFunctoid.PurchaseOrder">  
    <From>Kevin F. Browne</From>  
    <To>Northwind Traders</To>  
    <LineItems>  
        <Item>  
            <Product>Laptop Computer</Product>  
            <Description>Thin profile laptop</Description>  
            <Price>1999.95</Price>  
            <Quantity>1</Quantity>  
        </Item>  
        <Item>  
            <Product>Monitor Swipes</Product>  
            <Description>Disposable monitor swipes</Description>  
            <Price>3.95</Price>  
            <Quantity>10</Quantity>  
        </Item>  
    </LineItems>  
</ns0:PurchaseOrder>  
```  
  
 <span data-ttu-id="aa4dc-111">**Max Occurs**プロパティを**項目**レコードが設定されているバインド解除済みとします。</span><span class="sxs-lookup"><span data-stu-id="aa4dc-111">The **Max Occurs** property for the **Item** record is set as unbounded.</span></span> <span data-ttu-id="aa4dc-112">これが示す、**項目**レコードがループ、および BizTalk マッパーは、このレコードをループとしてをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="aa4dc-112">This indicates that the **Item** record loops, and BizTalk Mapper compiles this record as a loop.</span></span>  
  
 <span data-ttu-id="aa4dc-113">合計数を検索すると仮定**項目**注文書入力インスタンスの要素がメッセージし、出力インスタンス メッセージ内のフィールドに結果を配置します。</span><span class="sxs-lookup"><span data-stu-id="aa4dc-113">Suppose you want to find the total number of **Item** elements in the purchase order input instance message and place the result in a field in the output instance message.</span></span>  
  
 <span data-ttu-id="aa4dc-114">次に示します、**レコード カウント**、受信する販売注文内の項目の数をカウントし、値を配置する functoid、 **ItemCount**フィールドで、 **SummedPO**出力インスタンス メッセージ。</span><span class="sxs-lookup"><span data-stu-id="aa4dc-114">The following figure shows a **Record Count** functoid that counts the number of items in an incoming purchase order and puts that value in the **ItemCount** field in the **SummedPO** output instance message.</span></span>  
  
 <span data-ttu-id="aa4dc-115">![レコード カウント functoid の使用方法を示すマップです。](../core/media/recordcountfunctoid.gif "recordcountfunctoid")</span><span class="sxs-lookup"><span data-stu-id="aa4dc-115">![Map showing the use of the record count functoid.](../core/media/recordcountfunctoid.gif "recordcountfunctoid")</span></span>  
<span data-ttu-id="aa4dc-116">レコード カウント Functoid のマップ</span><span class="sxs-lookup"><span data-stu-id="aa4dc-116">Record Count Functoid Map</span></span>  
  
 <span data-ttu-id="aa4dc-117">注意して、 **Max Occurs**プロパティを**項目**レコード**unbounded**です。</span><span class="sxs-lookup"><span data-stu-id="aa4dc-117">Notice that the **Max Occurs** property for the **Item** record would be **unbounded**.</span></span> <span data-ttu-id="aa4dc-118">これが示す、**項目**レコードがループ、および BizTalk マッパーは、このレコードをループとしてをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="aa4dc-118">This indicates that the **Item** record loops, and BizTalk Mapper compiles this record as a loop.</span></span>  
  
 <span data-ttu-id="aa4dc-119">上記サンプル購買注文のインスタンス メッセージが、これに含まれる 2 つ**項目**要素の値、 **ItemCount**フィールドが 2 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="aa4dc-119">For the preceding sample purchase order instance message, which contained two **Item** elements, the value of the **ItemCount** field will be set to 2.</span></span>  
  
```  
<ns0:SummedPO xmlns:ns0="http://RecordCountFunctoid.SummedPO">  
    <From>Kevin F. Browne</From>  
    <To>Northwind Traders</To>  
    <POTotal>2039.45</POTotal>  
    <ItemCount>2</ItemCount>  
</ns0:SummedPO>  
```  
  
> [!NOTE]
>  <span data-ttu-id="aa4dc-120">使用することも、**レコード カウント**フィールド要素の繰り返しをカウントする functoid です。</span><span class="sxs-lookup"><span data-stu-id="aa4dc-120">You can also use the **Record Count** functoid to count repeating field elements.</span></span> <span data-ttu-id="aa4dc-121">これは、レコードに制限されません。</span><span class="sxs-lookup"><span data-stu-id="aa4dc-121">It is not restricted to records.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa4dc-122">参照</span><span class="sxs-lookup"><span data-stu-id="aa4dc-122">See Also</span></span>  
 <span data-ttu-id="aa4dc-123">[マップにレコード カウント Functoid を追加する方法](../core/how-to-add-record-count-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="aa4dc-123">[How to Add Record Count Functoids to a Map](../core/how-to-add-record-count-functoids-to-a-map.md) </span></span>  
 <span data-ttu-id="aa4dc-124">[高度な Functoid](../core/advanced-functoids.md) </span><span class="sxs-lookup"><span data-stu-id="aa4dc-124">[Advanced Functoids](../core/advanced-functoids.md) </span></span>  
 <span data-ttu-id="aa4dc-125">[インデックス Functoid](../core/index-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="aa4dc-125">[Index Functoid](../core/index-functoid.md) </span></span>  
 <span data-ttu-id="aa4dc-126">[繰り返し Functoid](../core/iteration-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="aa4dc-126">[Iteration Functoid](../core/iteration-functoid.md) </span></span>  
 [<span data-ttu-id="aa4dc-127">ループ Functoid</span><span class="sxs-lookup"><span data-stu-id="aa4dc-127">Looping Functoid</span></span>](../core/looping-functoid.md)