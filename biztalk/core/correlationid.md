---
title: CorrelationID | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4faf210-7e7f-450d-8bb1-84d3d31c3022
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 374ae165d48e1d91bc60d83a285df3b0f3594357
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354424"
---
# <a name="correlationid"></a>CorrelationID
`CorrelationID`要素を使用して、メッセージの相関 ID を指定します。  
  
## <a name="format"></a>形式  
 `CorrelationID`要素から成る、 `Expression` 1 つまたは複数を使用する要素`Operation`相関 ID として使用する文字列を指定する要素  
  
```  
<ic:CorrelationID>  
  <ic:Expression>  
    <!-- Operations -->  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
## <a name="remarks"></a>コメント  
 次の一般的な操作は、関連付け ID 式では使用できません。  
  
-   And  
  
-   [等しい]  
  
## <a name="example"></a>例  
 次の Workflow Foundation (WF) インターセプタ サンプルの構成ブロックは、相関関係を確立するには、"OrderNum"の id。 WF と一般的な操作を使用して、ワークフローの ID を適切な相関関係を構築する高度な式を構築できます。  
  
```  
<ic:CorrelationID>  
  <ic:Expression>  
    <wf:Operation Name="GetWorkflowProperty">  
      <wf:Argument>OrderNum</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
 Windows Communication Foundation (WCF) アプリケーションの場合は、相関 ID を作成するのに WCF 固有および共通の操作を使用できます。 次のサンプルは、 **XPath**操作と XPath を関連付け ID として使用するためのメッセージからクレジット_カード番号を取得します。  
  
```  
<ic:CorrelationID>  
  <ic:Expression>  
    <wcf:Operation Name ="XPath">  
      <wcf:Argument>//s:Body/creditCard:CreditCardNumber</wcf:Argument>  
    </wcf:Operation>  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
## <a name="see-also"></a>参照  
 [インターセプター OnEvent 要素](../core/interceptor-onevent-element.md)