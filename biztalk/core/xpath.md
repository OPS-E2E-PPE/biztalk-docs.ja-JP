---
title: "XPath |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 444b5eb9-0c00-4225-918e-b973532c67d0
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ee46838596a55512df5d1476f2c3ba34b1f5cb9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="xpath"></a>XPath
XPath ステートメントで指定された値をプッシュします。  
  
## <a name="syntax"></a>構文  
  
```  
  
<wcf:Operation Name="XPath">  
  <wcf:Argument>//po:POID</wcf:Argument>  
</wcf:Operation>  
```  
  
#### <a name="parameters"></a>パラメーター  
 有効な XPath ステートメント。  
  
## <a name="pushed-value"></a>プッシュされた値  
 XPath ステートメントの実行によって見つかった文字列値。  
  
## <a name="remarks"></a>解説  
 有効な XPath ステートメントを使用する必要があります。  
  
 一致する値が複数見つかった場合は、最初に見つかった値だけが使用されます。  
  
## <a name="example"></a>例  
 次に示す式の例では、現在のメッセージに含まれる注文書 ID に定数 "C_" を連結することにより、関連付けの値を生成します。 注文書 ID は、XPath 操作を使用して取得されます。  
  
```  
<ic:CorrelationID>  
  <ic:Expression>  
    <ic:Operation Name="Constant">  
      <ic:Argument>C_</ic:Argument>  
    </ic:Operation>  
    <wcf:Operation Name="XPath">  
      <wcf:Argument>//po:POID</wcf:Argument>  
    </wcf:Operation>  
    <ic:Operation Name="Concatenate" />  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
## <a name="see-also"></a>参照  
 [Windows Communication Foundation での操作](../core/operations-in-windows-communication-foundation.md)