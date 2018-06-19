---
title: フィルター |Microsoft ドキュメント
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
ms.openlocfilehash: efa69998b1782f42d7730744fd88534d26a87835
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22245802"
---
# <a name="filter"></a>[フィルター]
`Filter` 要素には、`Expression` または `true` に評価される `false` が含まれています。これに基づいて、イベントは処理またはスキップされます。  
  
## <a name="format"></a>Format  
  
```  
<ic:Filter>  
</ic:Filter>  
```  
  
## <a name="remarks"></a>解説  
  
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
 [インターセプタ OnEvent 要素](../core/interceptor-onevent-element.md)