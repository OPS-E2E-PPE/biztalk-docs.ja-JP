---
title: フィルター |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b8dad59d-4a47-4794-bbf9-cba02fe7f0bf
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5366385056383fd260fb80e2e6fa8b3f842ac48
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388001"
---
# <a name="filter"></a>Assert
`Filter` 要素には、`Expression` または `true` に評価される `false` が含まれています。これに基づいて、イベントは処理またはスキップされます。  
  
## <a name="format"></a>形式  
  
```  
<ic:Filter>  
</ic:Filter>  
```  
  
## <a name="remarks"></a>コメント  
  
## <a name="example"></a>例  
 次の例は、イベントに関連付けられたワークフローのユーザー キーが "DocumentUrl" と等しい場合に `true` に評価されるフィルタを定義します。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetUserKey" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>DocumentUrl</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
## <a name="see-also"></a>参照  
 [インターセプター OnEvent 要素](../core/interceptor-onevent-element.md)