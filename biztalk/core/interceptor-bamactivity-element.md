---
title: インターセプター BamActivity 要素 |Microsoft Docs
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
ms.openlocfilehash: 07d9929e1122f00ede80c1d3e7c9efff5a2f3fff
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382061"
---
# <a name="interceptor-bamactivity-element"></a>インターセプタ BamActivity 要素
**BamActivity**要素が 1 つの BAM アクティビティを定義します。  
  
## <a name="format"></a>形式  
 `BamActivity`要素が含まれています、**名前**属性し、1 つ以上含む`OnEvent`要素。  
  
```  
<ic:BamActivity Name="PurchaseOrder">  
  <!-- One or more OnEvent elements -->  
</ic:BamActivity>   
```  
  
### <a name="attributes"></a>属性  
  
|属性名|説明|  
|--------------------|-----------------|  
|名前|BAM アクティビティのユーザー定義名。|  
  
## <a name="example"></a>例  
 次の例には、"myorderworkflow"、単一の OnEvent とサンプル BamActivity にはが含まれています。  
  
```  
<ic:BamActivity Name="MyOrderWorkflow">  
  <ic:OnEvent Name="MyActivityEvent"  Source="OrderWorkflow">  
    …  
  </ic:OnEvent>  
</ic:BamActivity>  
```  
  
## <a name="see-also"></a>参照  
 [インターセプター EventSource 要素](../core/interceptor-eventsource-element.md)   
 [インターセプター OnEvent 要素](../core/interceptor-onevent-element.md)