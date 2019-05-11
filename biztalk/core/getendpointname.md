---
title: GetEndpointName |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c5a06850-ff6d-4fe4-9834-61d14b117391
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e39dc97a5d1b12b2e9978f3833092355a47b0623
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345086"
---
# <a name="getendpointname"></a>GetEndpointName
スタックに現在のインターセプタ エンドポイントの名前をプッシュします。  
  
## <a name="syntax"></a>構文  
  
```  
  
<wcf:Operation Name="GetEndpointName" />  
```  
  
#### <a name="parameters"></a>パラメーター  
 [なし] :  
  
## <a name="pushed-value"></a>プッシュされた値  
 現在のインターセプタ エンドポイント名を表す文字列です。  
  
## <a name="remarks"></a>コメント  
 クライアントとサーバー アプリケーションの App.config ファイルで指定された同じエンドポイント名ごとに異なる名前が返されることに注意してください。 重要です。  
  
 クライアント アプリケーションは、GetEndPointName 操作によって取得されるエンドポイント名は、バインディング名がアンダー スコアとコントラクト名。  
  
 たとえば、バインディングが設定されているサービス エンドポイントの名前プロパティが設定されていない場合、名前が設定\<*バインド*\>_\<*コントラクト*\>.  
  
 バインディングと名前が設定されていない場合、Name プロパティに設定されます\<*コントラクト*\>します。  
  
 サービスの場合は、取得した名前は、App.config ファイルで指定されたエンドポイント名前です。  
  
## <a name="example"></a>例  
 次のフィルター式の例では、PurchaseOrder_EP エンドポイントの ServiceRequest コントラクト呼び出しポイントの受信操作のインターセプタを定義します。 これは、次の論理手順で行います。  
  
1.  現在の操作名を"Receive"を比較し、結果 (true または false) をスタックにプッシュします。  
  
2.  現在のサービス コントラクト呼び出しポイントを"ServiceRequest"を比較し、結果 (true または false) をスタックにプッシュします。 スタック上に 2 つのブール値はようになりました。  
  
3.  ブール値を使用して、前の手順の結果を比較**と**操作と、スタックにプッシュの結果。 これにより、1 つのブール値がスタックに残ります。  
  
4.  現在のエンドポイントを"PurchaseOrder_EP"を比較し、結果 (true または false) をスタックにプッシュします。 スタック上に 2 つのブール値はようになりました。  
  
5.  最後に、ブール値を使用して、スタック上の 2 つのブール値を比較**と**操作と、結果をスタックにプッシュします。 コントラクトと操作の名前、ポイントが正常に呼び出す場合は true であるブール値に対してエンドポイント比較の結果が一致すると、およびそれ以外の場合は false、これを確認します。  
  
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