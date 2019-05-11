---
title: 連結 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e21a773d-a9cc-4a6f-b548-46badcd92aab
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d47db49e60b95071b48393735b3b4b0e7cee528
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391629"
---
# <a name="concatenate"></a>連結
スタックから上位 2 項目を削除し、その 2 つの項目を連結して、結果をスタックにプッシュします。  
  
## <a name="syntax"></a>構文  
  
```  
  
<ic:Operation Name="Concatenate" />  
```  
  
#### <a name="parameters"></a>パラメーター  
 スタックの上位 2 項目。  
  
## <a name="pushed-value"></a>プッシュされた値  
 連結操作の結果の文字列。  
  
## <a name="remarks"></a>コメント  
  
## <a name="example"></a>例  
 次に示す更新された式の例では、定数文字列 "Start:" が "EventTime" コンテキスト プロパティの値と連結され、データベース列 NewOrderCreateTime に保存されます。  
  
```  
<ic:Update DataItemName="NewOrderCreateTime" Type="NVARCHAR">  
  <ic:Expression>  
    <ic:Operation Name="Constant">  
      <ic:Argument>Start:</ic:Argument>  
    </ic:Operation>  
    <wf:Operation Name="GetContextProperty">  
      <wf:Argument>EventTime</wf:Argument>  
    </wf:Operation>  
    <ic:Operation Name="Concatenate" />  
  </ic:Expression>  
</ic:Update>  
```  
  
## <a name="see-also"></a>参照  
 [インターセプターの操作](../core/interceptor-operations.md)