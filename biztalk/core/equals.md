---
title: 等しい |Microsoft ドキュメント
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
ms.openlocfilehash: 2b82ac5c779dc6b4d3624b48cebe9df1bc3d1966
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239818"
---
# <a name="equals"></a>[等しい]
スタックから上位 2 項目を削除し、その 2 つの項目を比較して、結果をスタックにプッシュします。  
  
## <a name="syntax"></a>構文  
  
```  
  
<ic:Operation Name="Equals" />  
```  
  
#### <a name="parameters"></a>パラメーター  
 スタックの上位 2 項目。  
  
## <a name="pushed-value"></a>プッシュされた値  
 比較演算の結果の文字列。  
  
## <a name="remarks"></a>解説  
  
## <a name="example"></a>例  
 次の例のフィルタ式を使用して、 **Equals**定数"CheckPO"には、現在のアクティビティ名を比較する操作。 両者が等しい場合、式は `true` に評価されます。  
  
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
  
 比較の実行時に C# でステートメントを作成する場合と同様に、フィルタ式を作成することがあります。 たとえば、3 つの値を比較する場合、C# では次のようなステートメントを作成します。  
  
```  
bool res = a == b == c;  
```  
  
 ただし、このステートメントは、フィルタ式のモデルとしては不十分です。 その代わりに、次のように修正した (同等の) ステートメントを使用します。  
  
```  
Bool res = (a == b) && (a == c);  
```  
  
 こちらの方が、比較を実行するときに使用するフィルタ式により近くなっています。 詳細および例に、次を参照してください。[と](../core/and.md)です。  
  
## <a name="see-also"></a>参照  
 [インターセプタの操作](../core/interceptor-operations.md)