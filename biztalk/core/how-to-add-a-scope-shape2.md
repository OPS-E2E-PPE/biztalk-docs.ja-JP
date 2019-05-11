---
title: スコープ Shape2 を追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Scope shapes, adding
- adding, Scope shapes
ms.assetid: 9449210f-1f29-4b86-a14b-148caa06ac6b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be9f3aaab2843ad77a1103155239277e0ec72e4e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343615"
---
# <a name="how-to-add-a-scope-shape"></a>スコープ図形を追加する方法
追加する、次の手順を使用して、**スコープ**図形。  
  
### <a name="to-add-a-scope-shape"></a>スコープ図形を追加するには  
  
1.  下の矢印を右クリックし、 **ReceiveFromIn**ポートをポイントして、**図形の挿入**、選択と**スコープ**します。  
  
     **スコープ**図形、エラーが発生する操作を設定します。  
  
     たとえば、SQLExecute オーケストレーション、送信、受信および送信ポートを追加します。 この例では、サーバーにメッセージを送信します。 サーバーは応答して、 これにより、オーケストレーションの残りの部分を実行し、OutFile ポートに情報を返します。  
  
2.  **スコープ**図形は、設定、**トランザクションの種類**に**None**します。  
  
3.  内側を右クリックし、**スコープ**図形し、選択**新しい例外ハンドラー**します。  
  
     これを作成、**例外のキャッチ**ブロックします。 内でキャッチされますが、バックエンド システムから例外が発生した場合、**例外のキャッチ**ブロックします。  
  
4.  **例外のキャッチ**ブロックのロジックを追加する必要があります。  
  
     設定する必要がある最も重要なロジックは、受信するエラー メッセージの種類です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server 例外処理の使用](../core/using-biztalk-server-exception-handling3.md)