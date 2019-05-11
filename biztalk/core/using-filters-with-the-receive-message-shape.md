---
title: フィルターと受信メッセージ図形の使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- filters, receive messages
- messages, filters
ms.assetid: 5310039b-6719-4971-933a-2da0573fb5e7
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58c0ed34645fc7b576a76092c676d4eb4c390020
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65246420"
---
# <a name="using-filters-with-the-receive-message-shape"></a>受信メッセージ図形にフィルターを使用します。
フィルター式は、受信のアクティブ化プロパティの値を指定する図形をオーケストレーションに適用できるオプションのパラメーターです。 フィルター式が指定されている場合、受信メッセージがフィルター式で指定された条件と一致する場合とし、オーケストレーションはアクティブのみです。 フィルター式が指定されていない場合、オーケストレーションがサブスクライブしているすべての受信メッセージはオーケストレーション アクティブ化されます。  
  
 フィルター式を作成するには、式の右側にある定数式の左側にある着信メッセージのプロパティを比較します。 AND を適用することで、複合式を作成することもできます。 および OR 演算子を 2 つまたは複数の式。 できますも空白のままに、フィルター式では、すべてのメッセージを受け入れられる場合。  
  
 フィルター式は、次のようになります。  
  
```  
InvoiceSchema.Quantity >= 1000  
```  
  
 この例では、オーケストレーションに受信メッセージが表示されます。 オーケストレーションがアクティブ化**受信**図形 (、**アクティベーション**プロパティに設定されて**True**できるように、特定のメッセージの受信、オーケストレーションを実行すると、) を適用前のフィルター式で。 名前空間に Quantity という名前のプロパティを持つ受信メッセージが期待どおり**InvoiceSchema**します。 オーケストレーションは、実行前に、ランタイム エンジンが受信メッセージをチェックしますので 1000 以上の項目に対する請求書のみを受け入れます。  
  
 次の表では、フィルター式で使用できる演算子を示します。  
  
|演算子|説明|例|  
|--------------|-----------------|-------------|  
|==|等しい|ReqMsg(Total) == 100|  
|!=|等しくないです。|ReqMsg(Total) != 100|  
|<|小さい|ReqMsg(Total) \< 100|  
|>|大きい|ReqMsg(Total) > 100|  
|<=|等しいまたはそれよりも小さい|ReqMsg(Total) \<= 100|  
|>=|大きいまたは等しい|ReqMsg(Total) >= 100|  
|存在します。|存在します。|ReqMsg(Description) exists|  
  
> [!NOTE]
>  フィルター式の文字列値は、たとえば、引用符で囲まれました。Reqmsg (description) =「発注書のステータス」。 フィルター式の文字の値を使用することはできません。  
  
> [!NOTE]
>  アクティブ化受信である場合は、直接バインド ポートに関連付けられて、その後、フィルターでテストされたプロパティの値が同じで、同じ型のメッセージを送信しては、無限ループを作成します。 メッセージは、場所は再度選択、フィルター条件に一致するため、メッセージ ボックスに移動します。 これを回避するには、する必要があります別のプロパティでフィルター処理、別の種類のメッセージを送信するか、同じ種類のメッセージを送信する前に、プロパティの値を変更してください。  
  
## <a name="see-also"></a>参照  
 [受信図形を構成する方法](../core/how-to-configure-the-receive-shape.md)   
 [オーケストレーションでの相関関係の使用](../core/using-correlations-in-orchestrations.md)   
 [識別フィールドとプロパティ フィールドの使用](../core/using-distinguished-fields-and-property-fields.md)   
 [オーケストレーションでのメッセージの使用](../core/using-messages-in-orchestrations.md)