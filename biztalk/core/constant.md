---
title: 定数 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0af49bf5-e7de-41da-ac27-70301b8ee4d4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba1da4a690ca37a5012f5abb2e31f1229cb1b4bb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354649"
---
# <a name="constant"></a>定数
1 つの定数値をスタックにプッシュします。  
  
## <a name="syntax"></a>構文  
  
```  
  
<ic:Operation Name="Constant">  
  <ic:Argument>val</ic:Argument>  
</ic:Operation>  
```  
  
#### <a name="parameters"></a>パラメーター  
 定数値。  
  
## <a name="pushed-value"></a>プッシュされた値  
 定数の値を表す文字列です。  
  
## <a name="remarks"></a>コメント  
  
## <a name="example"></a>例  
 次のサンプルのフィルター式を使用して、**定数**でを使用して値をプッシュする操作、 **Equals**操作が現在のアクティビティ名が"FoodAndDrinksPolicy"であることを確認します。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>FoodAndDrinksPolicy</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
  </ic:Expression>  
</ic:Filter>  
```  
  
 これは、一般的な使用パターン、**定数**操作。  
  
## <a name="see-also"></a>参照  
 [インターセプターの操作](../core/interceptor-operations.md)