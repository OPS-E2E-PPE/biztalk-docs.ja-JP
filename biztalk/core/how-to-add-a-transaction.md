---
title: トランザクションを追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adding, transactions
- transactions, adding
ms.assetid: 25385c20-3025-4cf1-bc1f-ef266e081bad
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3a4fcb1116e5b4a0cd3a8b62dc1283abc3215c6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009971"
---
# <a name="how-to-add-a-transaction"></a>トランザクションを追加する方法
以下の手順に従ってトランザクションを追加します。  
  
### <a name="to-add-a-transaction"></a>トランザクションを追加するには  
  
1. をクリックして、**トランザクション**タブ。  
  
2. クリックして**トランザクション追加**します。  
  
3. クリックして**新しい値を追加**します。 次の情報を入力し、クリックして**追加**します。  
  
   1. **ノード名:** はこのことを確認して**MSEXTERNAL**します。  
  
   2. **トランザクションの種類:** はこのことを確認して**Outbound Asynchronous**します。  
  
   3. **要求メッセージ:** 入力`LOCATION_SYNC`します。  
  
   4. **要求メッセージのバージョン:** 入力`VERSION_1`します。  
  
      ![](../core/media/psadapter-38-task-gatewayaddtransaction.gif "PSAdapter_38_Task_GatewayAddTransaction")  
  
4. **Transaction Detail**  タブで、次の設定を確認します。  
  
   1. **状態:** アクティブです。  
  
   2. **ルーティング:** 暗黙の型。  
  
      ![](../core/media/psadapter-39-task-gatewaytransdetail.gif "PSAdapter_39_Task_GatewayTransDetail")  
  
5. **[保存]** をクリックします。  
  
6. をクリックして、 **Return to Transaction List**リンク。  
  
    トランザクションの一覧に、トランザクションが表示されます。  
  
## <a name="see-also"></a>参照  
 [PeopleSoft の HTTP ホストとポートを作成する](../core/creating-a-peoplesoft-http-host-and-port.md)