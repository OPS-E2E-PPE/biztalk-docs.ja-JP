---
title: レッスン 4:注文テーブルに対して挿入操作の実行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 66fc64c5-a3da-4014-8545-f34e6577bd73
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8da95d9e06c2aadfa293e54d1fb7c71321577d5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368793"
---
# <a name="lesson-4-perform-an-insert-operation-on-the-purchase-order-table"></a>レッスン 4:注文テーブルに対して挿入操作を実行します。
[レッスン 3。従業員の新規追加を選択するストアド プロシージャの実行](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md)、実行する、 **UPDATE_EMPLOYEE**ストアド プロシージャと、新しく挿入された従業員レコードの詳細を含む応答メッセージを受信します。 このレッスンでは、前のレッスンで作成し、次の手順を実行するオーケストレーションを更新します。  
  
1.  挿入操作を実行するメッセージの構築、オーケストレーション内で、 **Purchase_Order**テーブル。 この手順はのような[手順 1。UPDATE_EMPLOYEE の要求メッセージを作成するストアド プロシージャ](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-update-employee-stored-procedure.md)します。  
  
2.  応答メッセージをマップする要求メッセージを構築した後、 **UPDATE_EMPLOYEE**でストアド プロシージャ、挿入操作の要求メッセージを**Purchase_Order**テーブル。 メッセージをマップすることによって、挿入操作の要求メッセージに応答メッセージから受信した値を渡します。  
  
3.  内のレコードを挿入するメッセージを送信する、 **Purchase_Order**テーブルし、応答を受信します。  
  
4.  送信ポートに応答を送信します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [ステップ 1: Purchase_Order テーブルに対する挿入操作の要求メッセージを作成する](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-insert-operation-on-purchase-order-table.md)  
  
-   [手順 2:UPDATE_EMPLOYEE 応答メッセージを挿入操作要求メッセージにマップする](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md)  
  
-   [ステップ 3:要求メッセージを送信してレコードを挿入し、応答を受信する](../../adapters-and-accelerators/adapter-sql/step-3-send-the-request-message-to-insert-records-and-receive-a-response.md)  
  
-   [手順 4:プロジェクトをビルドする](../../adapters-and-accelerators/adapter-sql/step-4-build-the-project.md)