---
title: "手順 1: 通知を受信するオーケストレーション図形の追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4e4c6fa5-81b7-4928-84d5-39533535f862
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a33693a09d89acc5d1ad9e4514c7907b789cc75
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-add-orchestration-shapes-to-receive-notification"></a>手順 1: 通知を受信するオーケストレーション図形を追加します。
![手順 1/3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")  
  
 **所要時間:** 5 分  
  
 **目標:**への変更の通知を受信するオーケストレーション図形を追加するこの手順で、**従業員**テーブル。  
  
## <a name="prerequisites"></a>前提条件  
 内の手順を完了する必要があります[レッスン 1: スキーマの生成とメッセージの作成](../../adapters-and-accelerators/adapter-sql/lesson-1-generate-schemas-and-create-messages.md)です。  
  
### <a name="to-receive-notification-messages"></a>通知メッセージを受信するには  
  
1.  、BizTalk オーケストレーションを開いて**EmployeeOrch.odx**、で追加する[手順 2: BizTalk オーケストレーションのメッセージの作成](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md)です。  
  
2.  追加、**受信**オーケストレーションへの図形です。 オーケストレーション ツールボックスからドラッグして、**受信**図形をオーケストレーション デザイン画面との間の領域にドロップ、**開始**(緑色の円) と**終了**図形 (赤色の八角形)。  
  
    |このプロパティを設定します。|この値を|  
    |-----------------------|-------------------|  
    |**Activate**|True|  
    |**メッセージ**|NotifyReceive|  
    |**名前**|ReceiveNotification|  
  
3.  追加、一方向受信ポートをオーケストレーションにします。 SQL Server データベースから通知メッセージを受信するのににはこのポートを使用します。 ポートの次のプロパティを設定します。  
  
    |このプロパティを設定します。|この値を|  
    |-----------------------|-------------------|  
    |**通信方向**|Receive|  
    |**通信方式**|一方向|  
    |**[Identifier]**|ReceiveNotification|  
  
     また、"operation_1"にから、操作名を変更**通知**です。  
  
4.  接続、 **ReceiveNotification**ポートを**ReceiveNotification**アクション図形。 オーケストレーション デザイナーでのデザイン画面で、アクション図形のポートを対応する緑色のハンドルの緑色の矢印の形のハンドルをドラッグします。  
  
    > [!NOTE]
    >  このステップでは、ドラッグ アンド ドロップを使用して、アクション図形にポートを接続します。 アクション図形の操作プロパティを使用して、アクション図形をポートに接続することもできます。  
  
5.  次の図では、実行中のオーケストレーションを示します。  
  
     ![通知メッセージを受信するオーケストレーション](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-01-receive-notification-orch.gif "sql_adap_tut_01_receive_notification_orch")  
  
## <a name="what-did-i-just-do"></a>でしただけは何ですか。  
 このステップでは、オーケストレーション図形を追加し、SQL Server データベースから通知を受信する受信ポート。  
  
## <a name="next-steps"></a>次の手順  
 」の説明に従って、SQL Server データベースから受信した通知の種類を抽出するオーケストレーションの式図形を追加する[手順 2: 通知メッセージから通知の種類を抽出](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md)です。  
  
## <a name="see-also"></a>参照  
 [手順 2: 通知メッセージからの通知の種類を抽出します。](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md)   
 [レッスン 2: 表示され、通知をフィルター処理](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)