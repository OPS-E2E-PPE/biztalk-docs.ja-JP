---
title: スコープ Shape1 を追加する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Scope shapes, adding
- Scope shapes, Catch Exception blocks
- Catch Exception blocks, Scope shapes
- adding, Scope shapes
ms.assetid: dfe039d1-4c4a-4e21-ae03-7ca534aafec3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 094f744f7d4d6d1c405ea50d222beb8c0a67920e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247186"
---
# <a name="how-to-add-a-scope-shape"></a>スコープ図形を追加する方法
以下の手順に従ってスコープ図形を追加します。  
  
### <a name="to-add-a-scope-shape"></a>スコープ図形を追加するには  
  
1.  下の矢印を右クリックし、 **ReceiveFromIn**ポートでは、順にポイント**図形の挿入**、クリックして**スコープ**です。  
  
     ![](../core/media/siebeladapter-18-exceptionhandling-insertscope.gif "SiebelAdapter_18_ExceptionHandling_InsertScope")  
  
     スコープ図形に、エラーが発生するような操作を設定します。  
  
     たとえば、SQLExecute オーケストレーションに送信ポート、受信ポート、さらに送信ポートを追加します。 この例では、DB2 にメッセージを送信しています。 DB2 は応答して、 オーケストレーションの残りの部分を実行し、OutFile ポートに情報を返します。  
  
2.  スコープ図形で、設定、**トランザクション**に**None**です。  
  
3.  スコープ図形の内側を右クリックし、選択**新しい例外ハンドラー**です。  
  
     ![](../core/media/siebeladapter-19-exceptionhandling-newexception.gif "SiebelAdapter_19_ExceptionHandling_NewException")  
  
     これにより、例外のキャッチ ブロックが作成されます。 例外がバックエンドから発生する場合、例外のキャッチ ブロック内でキャッチされます。  
  
4.  例外のキャッチ ブロックには、ロジックを追加する必要があります。  
  
     この場合、設定することが必要となる最も重要なロジックは、想定する種類のエラー メッセージに関するものになります。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server 例外処理の使用](../core/using-biztalk-server-exception-handling2.md)