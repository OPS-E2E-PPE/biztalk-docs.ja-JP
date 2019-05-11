---
title: スコープ Shape5 を追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adding, Scope shapes
- Scope shape, adding
ms.assetid: 1e16eda1-c4bd-4428-a477-78c453aeb1aa
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35301e9e3cd66ab26d06208501c535b73305f5a6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343396"
---
# <a name="how-to-add-a-scope-shape"></a>スコープ図形を追加する方法
追加する次の手順に従って、**スコープ**図形。  
  
### <a name="to-add-a-scope-shape"></a>スコープ図形を追加するには  
  
1.  下の矢印を右クリックし、 **ReceiveFromIn**ポートをポイントして、**図形の挿入**、 をクリックし、**スコープ**。  
  
     **スコープ**図形、エラーが発生する操作を設定します。  
  
     たとえば、SQLExecute オーケストレーション、送信、受信および送信ポートを追加します。 この例では、サーバーにメッセージを送信します。 サーバーは応答して、 これにより、オーケストレーションの残りの部分を実行し、OutFile ポートに情報を返します。  
  
2.  **スコープ**図形は、設定、**トランザクションの種類**に**None**します。  
  
3.  内側を右クリックし、**スコープ**図形し、選択**新しい例外ハンドラー**します。  
  
     これを作成、`Catch Exception`ブロックします。 バック エンドから例外が発生した、内でキャッチされます、`Catch Exception`ブロックします。  
  
4.  `Catch Exception`ブロックのロジックを追加する必要があります。  
  
     設定する必要がある最も重要なロジックは、受信するエラー メッセージの種類です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server 例外処理の使用](../core/using-biztalk-server-exception-handling5.md)