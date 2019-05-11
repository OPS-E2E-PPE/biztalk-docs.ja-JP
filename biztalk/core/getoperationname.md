---
title: GetOperationName |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f858269c-d412-43e3-85e1-398afa9375ab
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 92eba73898b08e89cd1c3c7cdbd5f65c14ba048f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387676"
---
# <a name="getoperationname"></a>GetOperationName
現在の操作の名前をスタックにプッシュします。  
  
## <a name="syntax"></a>構文  
  
```  
  
<wcf:Operation Name="GetOperationName" />  
```  
  
#### <a name="parameters"></a>パラメーター  
 [なし] :  
  
## <a name="pushed-value"></a>プッシュされた値  
 現在の操作の名前を格納している文字列。  
  
## <a name="remarks"></a>コメント  
 GetOperationName を使用するときは、アプリケーションで呼び出される操作名と比較してください。 たとえば、サービス コントラクトの name 属性を使用してカスタム名を割り当てると、クライアントは、メソッドのカスタム名を使用して生成された既定のプロキシを使用します。 しかし、サーバー アプリケーションは、name 属性で指定された名前ではなく、対応する操作の実際のメソッド名を使用します。  
  
## <a name="example"></a>例  
 次の例では、`GetOperationName` を使用して、"AuthorizePayment" という名前の操作をフィルタ処理する式を作成します。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wcf:Operation Name="GetOperationName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>AuthorizePayment</ic:Argument>  
    </ic:Operation>  
  </ic:Expression>  
</ic:Filter>  
```  
  
## <a name="see-also"></a>参照  
 [Windows Communication Foundation での操作](../core/operations-in-windows-communication-foundation.md)