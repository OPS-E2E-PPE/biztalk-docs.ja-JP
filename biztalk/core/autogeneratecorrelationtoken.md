---
title: AutoGenerateCorrelationToken |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a24357c9-34e5-4caa-b41c-19551cfe81f9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf2b3fd5ea662af08cf5613570ba65c4fd1017f6
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528900"
---
# <a name="autogeneratecorrelationtoken"></a>AutoGenerateCorrelationToken
自動的に関連付けトークンを生成して、スタック上に配置します。  
  
## <a name="syntax"></a>構文  
  
```  
  
<wcf:Operation Name="AutoGenerateCorrelationToken" />  
```  
  
#### <a name="parameters"></a>パラメーター  
 [なし] :  
  
## <a name="pushed-value"></a>プッシュされた値  
 関連付けトークンが含まれた文字列です。  
  
## <a name="remarks"></a>コメント  
 この操作は、メッセージ内に関連付けトークンがないが、要求と応答からの情報を関連付ける必要がある場合に役立ちます。 この操作を行うと、クライアント側またはサービス側で特定の要求/応答を関連付けることができます。  
  
> [!NOTE]
>  クライアントとサービスの両方で要求と応答によって生成されるデータを関連付けるには (継続)、メッセージのデータ要素を使用する必要があります。  
  
## <a name="example"></a>例  
 次に示す関連付けの式の例は、`AutoGenerateCorrelationToken` によって関連付けトークンが生成されることを前提としています。  
  
```  
<ic:CorrelationID>  
  <ic:Expression>            
    <wcf:Operation Name="AutoGenerateCorrelationToken"/>  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
## <a name="see-also"></a>参照  
 [Windows Communication Foundation での操作](../core/operations-in-windows-communication-foundation.md)