---
title: "条件付きループ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Looping functoids, conditional
- Equal functoids
- maps, conditional looping
ms.assetid: eb16efb8-b12c-47d6-afc9-579fc85ea59c
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5452f6b8768442b95ac6bddde0e84ba07f68c85
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="conditional-looping"></a>条件付きループ
条件を追加することができます、**ループ**functoid の出力リンクを**ループ**functoid と**論理**functoid 同じ送信先レコードを送信します。 論理条件が満たされている場合のみ、送信先レコードが作成されます。  
  
## <a name="conditional-looping-map"></a>条件付きループのマップ  
 ![条件付きループ functoid を示すをマップします。] (../core/media/loopingconditionalfunctoid.gif "loopingconditionalfunctoid")  
  
 上記の図では、最初**等しい**functoid を比較、**名**フィールド**FoodSurvey** "Wendy wheeler"です。 2 番目**等しい**functoid を比較、**名前**フィールド**FlowerSurvey** "Kelly focht"です。 したがって、先の作成、マップ**アドレス**レコードのみ、2 つの名前。 サンプル データを使用して、**ループ**functoid 例では、出力インスタンス メッセージは次のようです。  
  
```  
<ns0:MasterAddresses xmlns:ns0="http://ConditionalLoop.MasterAddresses">  
    <Address Name="Wendy Wheeler" Street="7890 Broadway" City="Columbus" State="OH" PostalCode="46290">  
    <Address Name="Kelly Focht" Street="456 1st Ave" City="Miami" State="FL" PostalCode="81406">  
</ns0:MasterAddresses>  
```  
  
## <a name="see-also"></a>参照  
 [マップにループ Functoid を追加する方法](../core/how-to-add-looping-functoids-to-a-map.md)   
 [高度な Functoid](../core/advanced-functoids.md)   
 [インデックス Functoid](../core/index-functoid.md)   
 [繰り返し Functoid](../core/iteration-functoid.md)   
 [ループ Functoid](../core/looping-functoid.md)   
 [レコード カウント Functoid](../core/record-count-functoid.md)