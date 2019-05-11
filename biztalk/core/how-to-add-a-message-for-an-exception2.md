---
title: Exception2 のメッセージを追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exceptions, adding messages
- messages, exceptions
- exception handling, adding messages
- fault messages, adding
ms.assetid: 9d8a3801-78cd-4c18-8deb-3fbe4a49a2f9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 166d3ef5817d4da9ea6b79bc9174b3a9117c086d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387379"
---
# <a name="how-to-add-a-message-for-an-exception"></a>例外のメッセージを追加する方法
最初にバックエンド システムへのポートを作成するときは、要求と応答を格納します。 エラーに割り当てることができますようにメッセージを追加する必要があります。  
  
### <a name="to-add-a-fault-message"></a>エラー メッセージを追加するには  
  
1. **オーケストレーション**ウィンドウで、右クリック**メッセージ**、し、**新しいメッセージ**。  
  
    これには、エラーに割り当てることができる Message_3 が作成されます。  
  
2. 右クリック**Message_3**、選び**プロパティ**します。  
  
3. 設定、**メッセージの種類**よう: 選択 **.NET クラス**、し、 **System, String**  
  
   ![](../core/media/jdeoneworld-03-addscope.gif "JdeOneWorld_03_addscope")  
  
## <a name="see-also"></a>参照  
 [BizTalk Server 例外処理の使用](../core/using-biztalk-server-exception-handling1.md)