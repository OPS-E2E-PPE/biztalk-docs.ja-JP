---
title: "スコープ Shape4 を追加する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adding, Scope shapes
- Scope shape, adding
ms.assetid: 4ed56ada-a656-40b1-b34a-0c0803c01216
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a81bb85412784616d185b64ee39f1e777d19fea3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-scope-shape"></a>スコープ図形を追加する方法
次の手順を追加するに従って、**スコープ**図形です。  
  
### <a name="to-add-a-scope-shape"></a>スコープ図形を追加するには  
  
1.  下の矢印を右クリックし、 **ReceiveFromIn**ポートでは、順にポイント**図形の挿入**、クリックして**スコープ**です。  
  
     スコープ図形に、エラーが発生するような操作を設定します。  
  
     たとえば、SQLExecute オーケストレーションで、送信、受信および送信ポートを追加します。 この例では、SERVER にメッセージを送信します。 SERVER は応答して、 オーケストレーションの残りの部分を実行し、OutFile ポートに情報を返します。  
  
2.  スコープ図形で、設定、**トランザクション**に**None**です。  
  
3.  スコープ図形の内部を右クリックし、選択**新しい例外ハンドラー**です。  
  
     これを作成、**例外のキャッチ**ブロックします。 内でキャッチこれは、例外がバックエンドから発生する場合、**例外のキャッチ**ブロックします。  
  
4.  **例外のキャッチ**ブロック、ロジックを追加する必要があります。  
    この場合、設定する必要がある最も重要なロジックは、受信するエラー メッセージの種類についてです。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server 例外処理の使用](../core/using-biztalk-server-exception-handling4.md)