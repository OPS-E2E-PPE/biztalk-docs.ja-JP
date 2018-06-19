---
title: 受信メッセージ図形にフィルターを使用して |Microsoft ドキュメント
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
ms.openlocfilehash: 1434e9704e073cfef1503ef550409e6d6414bb7c
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2018
ms.locfileid: "22287882"
---
# <a name="using-filters-with-the-receive-message-shape"></a>受信メッセージ図形にフィルターを使用します。
フィルター式は、"アクティブ化" プロパティに対して値 True を指定するオーケストレーションの受信図形に適用できる、オプションのパラメーターです。 フィルター式が指定された場合、受信メッセージがフィルター式で指定された条件に一致する場合にのみ、オーケストレーションがアクティブ化されます。 フィルター式が指定されていない場合は、オーケストレーションがサブスクライブする受信メッセージによって、オーケストレーションがアクティブ化されます。  
  
 フィルター式を作成するには、式の左側にある受信メッセージのプロパティを式の右側にある定数と比較します。 複数の式に AND および OR 演算子を適用することによって、複合式を作成することもできます。 フィルター式を空のままにすることもできます。この場合、すべてのメッセージが受け入れられます。  
  
 フィルター式は以下のようになります。  
  
```  
InvoiceSchema.Quantity >= 1000  
```  
  
 この例では、受信メッセージはオーケストレーションに提示されます。 オーケストレーションがアクティブ化 **受信** 図形 (、 **アクティブ化** にプロパティが設定されている **True** 、オーケストレーションを実行すると、特定のメッセージを受信できるように) に適用される前のフィルター式を使用します。 名前空間に Quantity という名前のプロパティを持つ受信メッセージが期待どおり **InvoiceSchema**します。 このオーケストレーションは、1000 以上のアイテムに対する請求書のみ受け付けるため、ランタイム エンジンは実行する前に受信メッセージを確認します。  
  
 次の表に、フィルター式で使用可能な演算子を示します。  
  
|演算子|Description|例|  
|--------------|-----------------|-------------|  
|==|等しい|ReqMsg(Total) == 100|  
|!=|等しくないです。|ReqMsg(Total) != 100|  
|<|小さい|ReqMsg(Total) \< 100|  
|>|大きい|ReqMsg(Total) > 100|  
|<=|以下に|ReqMsg(Total) \<100 を =|  
|>=|大きいまたは等しい|ReqMsg(Total) > = 100|  
|存在する|存在する|ReqMsg(Description) exists|  
  
> [!NOTE]
>  フィルター式の文字列値が次に例を引用符で囲まれた: reqmsg (description) =「注文書の状態」です。 フィルター式では文字値を使用できません。  
  
> [!NOTE]
>  アクティブ化受信が直接バインド ポートに関連付けられており、その後、フィルターでテストされたプロパティに対する同じ値を持つ同じ種類のメッセージを送信する場合、無限ループが作成されます。 メッセージはメッセージ ボックスに送られますが、フィルター条件に一致するため、そこで再度取得されます。 これを避けるには、別のプロパティに対してフィルター処理を行い、別の種類のメッセージを送信するか、同じ種類のメッセージを送信する前にプロパティの値を変更する必要があります。  
  
## <a name="see-also"></a>参照  
 [受信図形を構成する方法](../core/how-to-configure-the-receive-shape.md)   
 [オーケストレーションでの相関関係の使用](../core/using-correlations-in-orchestrations.md)   
 [識別フィールドおよびプロパティ フィールドの使用](../core/using-distinguished-fields-and-property-fields.md)   
 [オーケストレーションでメッセージの使用](../core/using-messages-in-orchestrations.md)