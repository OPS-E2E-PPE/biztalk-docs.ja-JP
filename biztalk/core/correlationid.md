---
title: CorrelationID |Microsoft ドキュメント
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
ms.openlocfilehash: 1192de4a49c300220ce0b297bbc1ee02ce64c6dc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237770"
---
# <a name="correlationid"></a>CorrelationID
`CorrelationID` 要素は、メッセージの関連付け ID を指定するために使用します。  
  
## <a name="format"></a>Format  
 `CorrelationID` 要素は、関連付け ID として使用する文字列を指定するために 1 つまたは複数の `Expression` 要素を使用する `Operation` 要素で構成されています。  
  
```  
<ic:CorrelationID>  
  <ic:Expression>  
    <!-- Operations -->  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
## <a name="remarks"></a>解説  
 次の一般的な演算は、関連付け ID 式では許可されていません。  
  
-   And  
  
-   [等しい]  
  
## <a name="example"></a>例  
 次の Workflow Foundation (WF) インターセプタ サンプルの構成ブロックは、"OrderNum" を使用して関連付け ID を確立しています。 WF と一般的な演算により、高度な式を構築してワークフローに適した関連付け ID を作成できます。  
  
```  
<ic:CorrelationID>  
  <ic:Expression>  
    <wf:Operation Name="GetWorkflowProperty">  
      <wf:Argument>OrderNum</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
 Windows Communication Foundation (WCF) アプリケーションについては、WCF 固有の演算と一般的な演算を使用して、関連付け ID を作成できます。 次のサンプルは、 **XPath**操作と XPath 相関 ID として使用するためのメッセージからクレジット_カード番号を取得します。  
  
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
 [インターセプタ OnEvent 要素](../core/interceptor-onevent-element.md)