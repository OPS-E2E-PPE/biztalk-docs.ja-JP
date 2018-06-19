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
# <a name="record-count-functoid"></a>レコード カウント Functoid
**レコード カウント**functoid は、入力インスタンス メッセージ内のレコードをカウントします。  
  
 **レコード カウント**functoid が 1 つの入力と 1 つの出力。 入力は、送信元スキーマのループ レコードからリンクになります。 出力、**レコード カウント**functoid は、実際の入力インスタンス メッセージ内のループ レコードの数。  
  
 ループ レコードは、入力インスタンス メッセージ内にある、繰り返し回数が不明な要素に対応します。 たとえば、発注書で、**項目**要素が何度も発生する可能性があります。 また、**項目**要素には、製品、説明、価格、および数量を含めることがあります。 次のコードは、このような注文書の簡単な例を示しています。  
  
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
  
 **Max Occurs**プロパティを**項目**レコードが設定されているバインド解除済みとします。 これが示す、**項目**レコードがループ、および BizTalk マッパーは、このレコードをループとしてをコンパイルします。  
  
 合計数を検索すると仮定**項目**注文書入力インスタンスの要素がメッセージし、出力インスタンス メッセージ内のフィールドに結果を配置します。  
  
 次に示します、**レコード カウント**、受信する販売注文内の項目の数をカウントし、値を配置する functoid、 **ItemCount**フィールドで、 **SummedPO**出力インスタンス メッセージ。  
  
 ![レコード カウント functoid の使用方法を示すマップです。] (../core/media/recordcountfunctoid.gif "recordcountfunctoid")  
レコード カウント Functoid のマップ  
  
 注意して、 **Max Occurs**プロパティを**項目**レコード**unbounded**です。 これが示す、**項目**レコードがループ、および BizTalk マッパーは、このレコードをループとしてをコンパイルします。  
  
 上記サンプル購買注文のインスタンス メッセージが、これに含まれる 2 つ**項目**要素の値、 **ItemCount**フィールドが 2 に設定されます。  
  
```  
<ns0:SummedPO xmlns:ns0="http://RecordCountFunctoid.SummedPO">  
    <From>Kevin F. Browne</From>  
    <To>Northwind Traders</To>  
    <POTotal>2039.45</POTotal>  
    <ItemCount>2</ItemCount>  
</ns0:SummedPO>  
```  
  
> [!NOTE]
>  使用することも、**レコード カウント**フィールド要素の繰り返しをカウントする functoid です。 これは、レコードに制限されません。  
  
## <a name="see-also"></a>参照  
 [マップにレコード カウント Functoid を追加する方法](../core/how-to-add-record-count-functoids-to-a-map.md)   
 [高度な Functoid](../core/advanced-functoids.md)   
 [インデックス Functoid](../core/index-functoid.md)   
 [繰り返し Functoid](../core/iteration-functoid.md)   
 [ループ Functoid](../core/looping-functoid.md)