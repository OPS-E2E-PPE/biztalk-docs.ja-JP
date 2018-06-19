---
title: GetServiceContractCallPoint |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: be03d100-0cba-4b80-8056-b582a2cd74ce
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e291bcf733129991f6d3b5000ca8e9bc1353057
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246410"
---
# <a name="getservicecontractcallpoint"></a>GetServiceContractCallPoint
現在のサービス コントラクト呼び出しポイントの名前をスタックにプッシュします。  
  
## <a name="syntax"></a>構文  
  
```  
  
<wcf:Operation Name="GetServiceContractCallPoint" />  
```  
  
#### <a name="parameters"></a>パラメーター  
 [なし] :  
  
## <a name="pushed-value"></a>プッシュされた値  
 現在のコントラクト呼び出しポイントを表す文字列です。  
  
## <a name="remarks"></a>解説  
 Windows Communication Framework のサービスは、サービス コントラクトの有効期間中のさまざまなポイントで傍受できます。 これらのポイントは、`System.BizTalk.Bam.Interceptors.Wcf.ContractCallPoint` 列挙体によって定義されます。  
  
|コントラクト呼び出しポイント|Description|  
|-------------------------|-----------------|  
|ClientReply|クライアント応答呼び出しポイントです。|  
|ClientRequest|クライアント要求呼び出しポイントです。|  
|ClientFault|クライアント違反ポイントです。|  
|ServiceReply|サービス応答呼び出しポイントです。|  
|ServiceRequest|サービス要求呼び出しポイントです。|  
|ServiceFault|サービス違反ポイントです。|  
|CallbackRequest|コールバック要求呼び出しポイントです。|  
|CallbackReply|コールバック応答呼び出しポイントです。|  
|CallbackFault|コールバック違反ポイントです。|  
  
## <a name="example"></a>例  
 次のサンプルには、クライアント応答状態にある特定の操作 ("Receive") を検出するように構成されたイベント フィルタ式が含まれています。 この処理は、`GetOperationName`、`GetServiceContractCallPoint`、論理演算などの演算の組み合わせを使用して実行されます。  
  
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
      <ic:Argument>ClientReply</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
## <a name="see-also"></a>参照  
 [Windows Communication Foundation での操作](../core/operations-in-windows-communication-foundation.md)