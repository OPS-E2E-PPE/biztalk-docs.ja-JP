---
title: '|Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 80bd8f1f-edae-476d-b488-78e6c5ee70bf
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 676940dfa5cbc23d0c8127923d292e382a4e3cad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230018"
---
# <a name="and"></a>And
ブール値を実行する、スタックから上位 2 項目を削除**AND**の項目、および結果をスタックにプッシュし、2 つです。  
  
## <a name="syntax"></a>構文  
  
```  
  
<ic:Operation Name="And" />  
```  
  
#### <a name="parameters"></a>パラメーター  
 スタックの上位 2 項目。  
  
## <a name="pushed-value"></a>プッシュされた値  
 ブール型の結果の文字列**AND**操作します。  
  
## <a name="remarks"></a>解説  
  
## <a name="example"></a>例  
 **と**操作は、複数のステートメントを評価する必要がある場合に便利です。 次の例のフィルタ式を確認するかどうか、アクティビティ名が"CheckPO"を使用してアクティビティ イベントが閉じられる、**と**操作します。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>CheckPO</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <wf:Operation Name="GetActivityEvent"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <ic:Operation Name="And"/>  
  </ic:Expression>  
</ic:Filter>  
```  
  
 この例では**と**式の最後の操作は、比較の結果に依存しています (および比較の実行にスタックからポップ) ためです。 実行するには、この概念を拡張する**と**3 つ以上のアイテムに対して操作します。 たとえば、条件 A、条件 B、および条件 C が True の場合、次のような式を使用します。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>CheckPO</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <wf:Operation Name="GetActivityEvent"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <wf:Operation Name="GetActivityType"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyType</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <ic:Operation Name="And"/>  
    <ic:Operation Name="And"/>  
  </ic:Expression>  
</ic:Filter>   
```  
  
## <a name="see-also"></a>参照  
 [インターセプタの操作](../core/interceptor-operations.md)