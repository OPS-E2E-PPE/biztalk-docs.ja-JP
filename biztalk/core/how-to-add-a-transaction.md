---
title: "トランザクションを追加する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adding, transactions
- transactions, adding
ms.assetid: 25385c20-3025-4cf1-bc1f-ef266e081bad
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24c67a9c76ae87f2355bb0ea4638d3bd156cda6e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-transaction"></a>トランザクションを追加する方法
以下の手順に従ってトランザクションを追加します。  
  
### <a name="to-add-a-transaction"></a>トランザクションを追加するには  
  
1.  クリックして、**トランザクション**タブです。  
  
2.  をクリックして**追加トランザクション**です。  
  
3.  をクリックして**新しい値を追加**です。 次の情報を入力し、クリックして**追加**です。  
  
    1.  **ノード名:**これは、ことを確認して**MSEXTERNAL**です。  
  
    2.  **トランザクションの種類:**これは、ことを確認して**Outbound Asynchronous**です。  
  
    3.  **要求メッセージ:**入力`LOCATION_SYNC`です。  
  
    4.  **要求メッセージのバージョン:**入力`VERSION_1`です。  
  
     ![](../core/media/psadapter-38-task-gatewayaddtransaction.gif "PSAdapter_38_Task_GatewayAddTransaction")  
  
4.  **Transaction Detail**  タブで、次の設定を確認してください。  
  
    1.  **状態:**アクティブです。  
  
    2.  **ルーティング:**暗黙の型。  
  
     ![](../core/media/psadapter-39-task-gatewaytransdetail.gif "PSAdapter_39_Task_GatewayTransDetail")  
  
5.  **[保存]**をクリックします。  
  
6.  クリックして、 **Return to Transaction List**リンクします。  
  
     トランザクションの一覧に、トランザクションが表示されます。  
  
## <a name="see-also"></a>参照  
 [PeopleSoft HTTP ホストおよびポートを作成します。](../core/creating-a-peoplesoft-http-host-and-port.md)