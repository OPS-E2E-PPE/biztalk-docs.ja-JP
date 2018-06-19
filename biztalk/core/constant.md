---
title: 定数 |Microsoft ドキュメント
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
ms.openlocfilehash: 674307acea439bc260399cc01da4165eedaa2da5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237794"
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
 定数値が含まれた文字列。  
  
## <a name="remarks"></a>解説  
  
## <a name="example"></a>例  
 次のサンプル フィルター式を使用して、**定数**で使用される、値をプッシュする操作、 **Equals**操作が現在のアクティビティ名が"FoodAndDrinksPolicy"であることを確認します。  
  
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
  
 これは、一般的な使用パターン、**定数**操作します。  
  
## <a name="see-also"></a>参照  
 [インターセプタの操作](../core/interceptor-operations.md)