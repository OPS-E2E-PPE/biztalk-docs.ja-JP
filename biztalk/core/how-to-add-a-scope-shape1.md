---
title: スコープ図形の 1 を追加する方法 |Microsoft Docs
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
ms.openlocfilehash: faabba82196f7e595427f36c0d07d66769bafd18
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387320"
---
# <a name="how-to-add-a-scope-shape"></a>スコープ図形を追加する方法
スコープ図形を追加するこれらの手順に従います。  
  
### <a name="to-add-a-scope-shape"></a>スコープ図形を追加するには  
  
1.  下の矢印を右クリックし、 **ReceiveFromIn**ポートをポイントして、**図形の挿入**、 をクリックし、**スコープ**。  
  
     ![](../core/media/siebeladapter-18-exceptionhandling-insertscope.gif "SiebelAdapter_18_ExceptionHandling_InsertScope")  
  
     スコープ図形では、エラーが発生する操作を設定します。  
  
     たとえば、SQLExecute オーケストレーション、送信ポート、受信と送信ポートを追加します。 この例では、DB2 にメッセージを送信しました。 DB2 は応答です。 これにより、オーケストレーションの残りの部分を実行し、OutFile ポートに情報を返します。  
  
2.  スコープ図形に、設定、**トランザクション**に**None**します。  
  
3.  スコープ図形内で右クリックして**新しい例外ハンドラー**します。  
  
     ![](../core/media/siebeladapter-19-exceptionhandling-newexception.gif "SiebelAdapter_19_ExceptionHandling_NewException")  
  
     これは、例外のキャッチ ブロックを作成します。 バック エンドから例外が発生した場合は、例外のキャッチ ブロック内でキャッチされます。  
  
4.  例外のキャッチ ブロックでは、ロジックを追加する必要があります。  
  
     最も重要なロジックを設定する必要がありますが、予期したエラー メッセージの種類です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server 例外処理の使用](../core/using-biztalk-server-exception-handling2.md)