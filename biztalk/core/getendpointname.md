---
title: "GetEndpointName |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c5a06850-ff6d-4fe4-9834-61d14b117391
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1567f0b4bceb756381c4033f3243ac7a58fda366
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="getendpointname"></a>GetEndpointName
現在のインターセプタ エンドポイントの名前をスタックにプッシュします。  
  
## <a name="syntax"></a>構文  
  
```  
  
<wcf:Operation Name="GetEndpointName" />  
```  
  
#### <a name="parameters"></a>パラメーター  
 [なし] :  
  
## <a name="pushed-value"></a>プッシュされた値  
 現在のインターセプタ エンドポイント名を含む文字列。  
  
## <a name="remarks"></a>解説  
 クライアント アプリケーションおよびサーバー アプリケーションは、App.config ファイルで指定されている同じエンドポイント名に対して異なる名前を返します。  
  
 クライアント アプリケーションの場合、GetEndPointName 操作で取得されるエンドポイント名はバインド名で、その後にアンダースコアとコントラクト名が続きます。  
  
 たとえば、ServiceEndpoint の Name プロパティが設定されていないバインドが設定されている場合は、名前に設定されます\<*バインディング*> _\<*コントラクト*>。  
  
 バインディングと名前が設定されていない場合、Name プロパティに設定されます\<*コントラクト*>。  
  
 サーバー アプリケーションの場合、App.config ファイルで指定されているエンドポイント名が取得されます。  
  
## <a name="example"></a>例  
 次に例示するフィルタ式では、PurchaseOrder_EP エンドポイントの ServiceRequest コントラクト呼び出しポイントについて、受信操作のインターセプタを定義します。 これは、次のような論理的な手順によって実行します。  
  
1.  現在の操作名を "Receive" と比較し、結果 ("true" または "false") をスタックにプッシュします。  
  
2.  現在のサービス コントラクト呼び出しポイントを "ServiceRequest" と比較し、結果 ("true" または "false") をスタックにプッシュします。 この段階で、スタックには 2 つのブール値が存在します。  
  
3.  ブール値を使用して、上記の手順の結果を比較**と**操作と、スタックにプッシュ結果。 この段階で、スタックには 1 つのブール値が存在します。  
  
4.  現在のエンドポイントを "PurchaseOrder_EP" と比較し、結果 ("true" または "false") をスタックにプッシュします。 この段階で、スタックには 2 つのブール値が存在します。  
  
5.  最後に、ブール値を使用して、スタック上の 2 つのブール値を比較**と**操作と、結果をスタックにプッシュします。 これにより、ブール値に対してエンドポイント比較の結果がチェックされ、操作名とコントラクト呼び出しポイントが一致すれば true、それ以外の場合は false が返されます。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wcf:Operation Name="GetOperationName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>Receive</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wcf:Operation Name="GetServiceContractCallPoint" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>ServiceRequest</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wcf:Operation Name="GetEndpointName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>PurchaseOrder_EP</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
## <a name="see-also"></a>参照  
 [Windows Communication Foundation での操作](../core/operations-in-windows-communication-foundation.md)