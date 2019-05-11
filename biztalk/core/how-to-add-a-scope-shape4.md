---
title: スコープ Shape4 を追加する方法 |Microsoft Docs
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
ms.assetid: 4ed56ada-a656-40b1-b34a-0c0803c01216
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce1e97c941de98c700b549dfe6307794ca38fb31
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343411"
---
# <a name="how-to-add-a-scope-shape"></a>スコープ図形を追加する方法
追加する次の手順に従って、**スコープ**図形。  
  
### <a name="to-add-a-scope-shape"></a>スコープ図形を追加するには  
  
1.  下の矢印を右クリックし、 **ReceiveFromIn**ポートをポイントして、**図形の挿入**、 をクリックし、**スコープ**。  
  
     スコープ図形では、エラーが発生する操作を設定します。  
  
     たとえば、SQLExecute オーケストレーション、送信、受信および送信ポートを追加します。 この例では、サーバーにメッセージを送信します。 サーバーは応答して、 これにより、オーケストレーションの残りの部分を実行し、OutFile ポートに情報を返します。  
  
2.  スコープ図形に、設定、**トランザクション**に**None**します。  
  
3.  スコープ図形の内部を右クリックし、選択**新しい例外ハンドラー**します。  
  
     これを作成、**例外のキャッチ**ブロックします。 バック エンドから例外が発生した、内でキャッチされます、**例外のキャッチ**ブロックします。  
  
4.  **例外のキャッチ**ブロックのロジックを追加する必要があります。  
    設定する必要がある最も重要なロジックは、受信するエラー メッセージの種類です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server 例外処理の使用](../core/using-biztalk-server-exception-handling4.md)