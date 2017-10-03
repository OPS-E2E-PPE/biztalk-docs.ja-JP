---
title: "フォールト メッセージ 2 を追加する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- fault messages, adding
- messages, fault messages
ms.assetid: 8f1b40af-2c75-4167-8b62-a86b791907c9
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6dee8a1fca0e30a96b6a714b5c717c0638bc8144
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-fault-message"></a>エラー メッセージを追加する方法
作成したバックエンド システムへのポートには、要求と応答が含まれています。 エラーに割り当てることができるように、メッセージを追加する必要があります。  
  
### <a name="to-add-a-fault-message"></a>エラー メッセージを追加するには  
  
1.  **オーケストレーション**ウィンドウを右クリックして**メッセージ**を選択し、**新しいメッセージ**です。  
  
     これにより Message_3 が作成され、このエラーに割り当てることができます。  
  
2.  Message_3 を右クリックし **プロパティ**です。  
  
3.  **プロパティ**ダイアログ ボックスで、設定、**メッセージの種類**です。  
  
     選択**.NET クラス**し、 **SystemString**です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server 例外処理の使用](../core/using-biztalk-server-exception-handling3.md)