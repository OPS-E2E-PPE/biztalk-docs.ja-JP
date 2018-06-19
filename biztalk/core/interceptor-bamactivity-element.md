---
title: インターセプタ BamActivity 要素 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6dee61b4-83cd-4a22-b8a6-1c1a7ea3648b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd43869922e46187c8b2e06155d525e428edd905
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257066"
---
# <a name="interceptor-bamactivity-element"></a>インターセプタ BamActivity 要素
**BamActivity**要素は、1 つの BAM アクティビティを定義します。  
  
## <a name="format"></a>Format  
 `BamActivity`要素が含まれています、**名前**属性を 1 つ以上含む`OnEvent`要素。  
  
```  
<ic:BamActivity Name="PurchaseOrder">  
  <!-- One or more OnEvent elements -->  
</ic:BamActivity>   
```  
  
### <a name="attributes"></a>属性  
  
|属性名|Description|  
|--------------------|-----------------|  
|名前|BAM アクティビティのユーザー定義名です。|  
  
## <a name="example"></a>例  
 次の例には、単一の OnEvent を持つ、"MyOrderWorkflow" というサンプルの BamActivity が含まれています。  
  
```  
<ic:BamActivity Name="MyOrderWorkflow">  
  <ic:OnEvent Name="MyActivityEvent"  Source="OrderWorkflow">  
    …  
  </ic:OnEvent>  
</ic:BamActivity>  
```  
  
## <a name="see-also"></a>参照  
 [インターセプタ EventSource 要素](../core/interceptor-eventsource-element.md)   
 [インターセプタ OnEvent 要素](../core/interceptor-onevent-element.md)