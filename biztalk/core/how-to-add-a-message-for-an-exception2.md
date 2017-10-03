---
title: "Exception2 のメッセージを追加する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exceptions, adding messages
- messages, exceptions
- exception handling, adding messages
- fault messages, adding
ms.assetid: 9d8a3801-78cd-4c18-8deb-3fbe4a49a2f9
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b2c314684094e73cb6d663bcf2183ffc3eccae5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-message-for-an-exception"></a>例外のメッセージを追加する方法
最初に作成したバックエンド システムへのポートには、要求と応答が含まれています。 エラーに割り当てることができるように、メッセージを追加する必要があります。  
  
### <a name="to-add-a-fault-message"></a>エラー メッセージを追加するには  
  
1.  **オーケストレーション ビュー** ] ウィンドウを右クリックして**メッセージ**、し、[**新しいメッセージ**です。  
  
     これにより Message_3 が作成され、このエラーに割り当てることができます。  
  
2.  右クリック**Message_3**を選択して**プロパティ**です。  
  
3.  設定、**メッセージの種類**よう: 選択**.NET クラス**、し、 **System, String**  
  
 ![](../core/media/jdeoneworld-03-addscope.gif "JdeOneWorld_03_addscope")  
  
## <a name="see-also"></a>参照  
 [BizTalk Server 例外処理の使用](../core/using-biztalk-server-exception-handling1.md)