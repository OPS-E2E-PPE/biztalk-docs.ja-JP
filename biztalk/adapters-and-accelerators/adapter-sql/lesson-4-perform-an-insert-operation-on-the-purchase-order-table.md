---
title: "レッスン 4: Purchase Order テーブルで挿入操作の実行 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 66fc64c5-a3da-4014-8545-f34e6577bd73
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c966e3c10f18424b2cfb1fde0235caedbb5f58f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="lesson-4-perform-an-insert-operation-on-the-purchase-order-table"></a>レッスン 4: Purchase Order テーブルで挿入操作を実行します。
[レッスン 3: 追加された新しい従業員を選択するストアド プロシージャの実行](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md)、実行する、 **UPDATE_EMPLOYEE**ストアド プロシージャとの詳細を含む応答メッセージを受信して、新しく従業員のレコードを挿入します。 このレッスンでは、前のレッスンで作成し、オーケストレーションを更新する、次の手順を実行します。  
  
1.  挿入操作を実行するメッセージの構築、オーケストレーション内で、 **Purchase_Order**テーブル。 この手順はのような[手順 1: UPDATE_EMPLOYEE ストアド プロシージャ用の要求メッセージを作成する](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-update-employee-stored-procedure.md)です。  
  
2.  応答メッセージをマップする要求メッセージを構築した後、 **UPDATE_EMPLOYEE**でストアド プロシージャの挿入操作の要求メッセージを**Purchase_Order**テーブル。 メッセージをマップすることによって、挿入操作の要求メッセージに応答メッセージから受信した値を渡します。  
  
3.  内のレコードを挿入するメッセージを送信する、 **Purchase_Order**テーブルが表示され、応答を受信します。  
  
4.  送信ポートに応答を送信します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [手順 1: Purchase_Order テーブルに対する挿入操作の要求メッセージを作成します。](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-insert-operation-on-purchase-order-table.md)  
  
-   [手順 2: マップ操作の要求メッセージを挿入する UPDATE_EMPLOYEE 応答メッセージ](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md)  
  
-   [手順 3: レコードを挿入し、応答を受信する要求メッセージを送信します。](../../adapters-and-accelerators/adapter-sql/step-3-send-the-request-message-to-insert-records-and-receive-a-response.md)  
  
-   [手順 4: プロジェクトをビルドします](../../adapters-and-accelerators/adapter-sql/step-4-build-the-project.md)