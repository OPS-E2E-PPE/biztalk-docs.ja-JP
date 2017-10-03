---
title: "スコープ Shape2 を追加する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Scope shapes, adding
- adding, Scope shapes
ms.assetid: 9449210f-1f29-4b86-a14b-148caa06ac6b
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ef67618c553702ae32cd0a88f6d2f77eb1ff053
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-scope-shape"></a>スコープ図形を追加する方法
追加する、次の手順を使用して、**スコープ**図形です。  
  
### <a name="to-add-a-scope-shape"></a>スコープ図形を追加するには  
  
1.  下の矢印を右クリックし、 **ReceiveFromIn**ポートでは、順にポイント**図形の挿入**を選択して**スコープ**です。  
  
     **スコープ**図形、エラーが発生する操作を設定します。  
  
     たとえば、SQLExecute オーケストレーションで、送信、受信および送信ポートを追加します。 この例では、SERVER にメッセージを送信します。 SERVER は応答して、 オーケストレーションの残りの部分を実行し、OutFile ポートに情報を返します。  
  
2.  **スコープ**図形は、設定、**トランザクション タイプ**に**なし**です。  
  
3.  内部を右クリックし、**スコープ**の整形し、選択**新しい例外ハンドラー**です。  
  
     これを作成、**例外のキャッチ**ブロックします。 内でキャッチこれは、バックエンド システムから例外が発生した場合、**例外のキャッチ**ブロックします。  
  
4.  **例外のキャッチ**ブロック、ロジックを追加する必要があります。  
  
     この場合、設定する必要がある最も重要なロジックは、受信するエラー メッセージの種類についてです。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server 例外処理の使用](../core/using-biztalk-server-exception-handling3.md)