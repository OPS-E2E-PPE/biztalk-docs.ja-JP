---
title: 等しい |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ac93031a-9d18-443d-9e38-71ef9edd5a30
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e376445e8349663ab6196e99f9f31df8e5c1e139
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530732"
---
# <a name="equals"></a>[等しい]
スタックから上位 2 項目を削除、2 つの項目を比較し、その結果をスタックにプッシュします。  
  
## <a name="syntax"></a>構文  
  
```  
  
<ic:Operation Name="Equals" />  
```  
  
#### <a name="parameters"></a>パラメーター  
 スタックの上位 2 項目。  
  
## <a name="pushed-value"></a>プッシュされた値  
 比較演算の結果を文字列します。  
  
## <a name="remarks"></a>コメント  
  
## <a name="example"></a>例  
 次の例のフィルタ式を使用して、 **Equals**定数"CheckPO"には、現在のアクティビティ名を比較する操作。 2 つが等しい場合は、式の評価が`true`します。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>CheckPO</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
  </ic:Expression>  
</ic:Filter>  
```  
  
 まったく同じで、ステートメントを記述すると、式の作成をしたくなる場合がありますC#比較を実行するときにします。 3 つの値を比較する例。C#ように記述します。  
  
```  
bool res = a == b == c;  
```  
  
 ただし、フィルタ式のモデルとして少し短くなります。 代わりに、変更された (ただし、同等) のステートメントを検討してください。  
  
```  
Bool res = (a == b) && (a == c);  
```  
  
 これには、フィルター式、比較を実行に使用するものより密接と一致します。 詳細と例では、次を参照してください。[と](../core/and.md)します。  
  
## <a name="see-also"></a>参照  
 [インターセプターの操作](../core/interceptor-operations.md)