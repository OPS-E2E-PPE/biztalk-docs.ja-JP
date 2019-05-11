---
title: フォールト メッセージ 2 を追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- fault messages, adding
- messages, fault messages
ms.assetid: 8f1b40af-2c75-4167-8b62-a86b791907c9
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8835098f95c34b506714306afd4c5e7fc42d1b63
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387360"
---
# <a name="how-to-add-a-fault-message"></a>エラー メッセージを追加する方法
バックエンド システムへのポートを作成するときに、要求と応答が含まれます。 エラーに割り当てることができますようにメッセージを追加する必要があります。  
  
### <a name="to-add-a-fault-message"></a>エラー メッセージを追加するには  
  
1.  **オーケストレーション**ウィンドウで、右クリック**メッセージ**を選択し、**新しいメッセージ**。  
  
     これには、エラーに割り当てることができる Message_3 が作成されます。  
  
2.  Message_3 を右クリックして**プロパティ**します。  
  
3.  **プロパティ**ダイアログ ボックスで、セット、**メッセージの種類**します。  
  
     選択 **.NET クラス**選び **[systemstring]** します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server 例外処理の使用](../core/using-biztalk-server-exception-handling3.md)