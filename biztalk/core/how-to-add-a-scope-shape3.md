---
title: スコープ Shape3 を追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Scope shapes, adding
ms.assetid: 8068ce97-4409-4c88-89e8-6505b56cefc5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 85b022dc0335ccd3b247c5c2fcad0553fad2ede4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387339"
---
# <a name="how-to-add-a-scope-shape"></a>スコープ図形を追加する方法
スコープ図形を追加するのにには、次の手順を使用します。  
  
### <a name="to-add-a-scope-shape"></a>スコープ図形を追加するには  
  
1.  下の矢印を右クリックし、**受信**ポートをポイントして、**図形の挿入**、し、**スコープ**します。  
  
     ![](../core/media/siebeladapter-18-exceptionhandling-insertscope.gif "SiebelAdapter_18_ExceptionHandling_InsertScope")  
  
     **スコープ**図形、エラーが発生する操作を設定します。  
  
     たとえば、SQLExecute オーケストレーション、送信ポート、受信と送信ポートを追加します。 この例では、サーバーにメッセージを送信します。 サーバーは応答して、 これにより、オーケストレーションの残りの部分を実行し、outFile ポートに情報を返します。  
  
2.  **スコープ**図形は、設定、**トランザクション**に**None**します。  
  
3.  内側を右クリックし、**スコープ**図形、および選択**新しい例外ハンドラー**します。  
  
     ![](../core/media/siebeladapter-19-exceptionhandling-newexception.gif "SiebelAdapter_19_ExceptionHandling_NewException")  
  
     これを作成、**例外のキャッチ**ブロックします。 内でキャッチされますが、バックエンド システムから例外が発生した場合、**例外のキャッチ**ブロックします。  
  
4.  **例外のキャッチ**ブロックのロジックを追加する必要があります。  
  
     設定する必要がある最も重要なロジックは、受信するエラー メッセージの種類です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server 例外処理の使用](../core/using-biztalk-server-exception-handling1.md)