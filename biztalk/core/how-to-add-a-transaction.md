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
ms.openlocfilehash: 2734828dad1a236fa6bd599588f5b34094cfeb13
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387285"
---
# <a name="how-to-add-a-transaction"></a>トランザクションを追加する方法
トランザクションを追加する次の手順に従います。  
  
### <a name="to-add-a-transaction"></a>トランザクションを追加するには  
  
1. をクリックして、**トランザクション**タブ。  
  
2. クリックして**トランザクション追加**します。  
  
3. クリックして**新しい値を追加**します。 次の情報を入力し、クリックして**追加**します。  
  
   1. **ノード名:** あることを確認**MSEXTERNAL**します。  
  
   2. **トランザクションの種類:** あることを確認**Outbound Asynchronous**します。  
  
   3. **要求メッセージ。** 入力`LOCATION_SYNC`します。  
  
   4. **要求メッセージのバージョン:** 入力`VERSION_1`します。  
  
      ![](../core/media/psadapter-38-task-gatewayaddtransaction.gif "PSAdapter_38_Task_GatewayAddTransaction")  
  
4. **Transaction Detail**  タブで、次の設定を確認します。  
  
   1. **状態:** アクティブ:  
  
   2. **ルーティング。** 暗黙の型。  
  
      ![](../core/media/psadapter-39-task-gatewaytransdetail.gif "PSAdapter_39_Task_GatewayTransDetail")  
  
5. **[保存]** をクリックします。  
  
6. をクリックして、 **Return to Transaction List**リンク。  
  
    トランザクションは、トランザクションの一覧に表示されます。  
  
## <a name="see-also"></a>参照  
 [PeopleSoft の HTTP ホストとポートを作成する](../core/creating-a-peoplesoft-http-host-and-port.md)