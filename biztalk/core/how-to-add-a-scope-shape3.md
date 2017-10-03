---
title: "スコープ Shape3 を追加する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Scope shapes, adding
ms.assetid: 8068ce97-4409-4c88-89e8-6505b56cefc5
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8231dfed1ea84ba5c11e0352f789b92cc38d0f83
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-scope-shape"></a>スコープ図形を追加する方法
スコープ図形を追加するには、次の操作を行います。  
  
### <a name="to-add-a-scope-shape"></a>スコープ図形を追加するには  
  
1.  下の矢印を右クリックし、**受信**ポートでは、順にポイント**図形の挿入**、し、**スコープ**です。  
  
     ![](../core/media/siebeladapter-18-exceptionhandling-insertscope.gif "SiebelAdapter_18_ExceptionHandling_InsertScope")  
  
     **スコープ**図形、エラーが発生する操作を設定します。  
  
     たとえば、SQLExecute オーケストレーションに送信ポート、受信ポート、さらに送信ポートを追加します。 この例では、SERVER にメッセージを送信します。 SERVER は応答して、 オーケストレーションの残りの部分を実行し、outFile ポートに情報を返します。  
  
2.  **スコープ**図形は、設定、**トランザクション**に**None**です。  
  
3.  内部を右クリックし、**スコープ**図形、および選択**新しい例外ハンドラー**です。  
  
     ![](../core/media/siebeladapter-19-exceptionhandling-newexception.gif "SiebelAdapter_19_ExceptionHandling_NewException")  
  
     これを作成、**例外のキャッチ**ブロックします。 内でキャッチこれは、バックエンド システムから例外が発生した場合、**例外のキャッチ**ブロックします。  
  
4.  **例外のキャッチ**ブロック、ロジックを追加する必要があります。  
  
     この場合、設定する必要がある最も重要なロジックは、受信するエラー メッセージの種類についてです。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server 例外処理の使用](../core/using-biztalk-server-exception-handling1.md)