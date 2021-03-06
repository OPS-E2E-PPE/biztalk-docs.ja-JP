---
title: 手順 1:通知を受信するオーケストレーション図形の追加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4e4c6fa5-81b7-4928-84d5-39533535f862
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 981ab324745840a4ba15e7d552af3f9ff965e3fa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367803"
---
# <a name="step-1-add-orchestration-shapes-to-receive-notification"></a>手順 1:通知を受信するオーケストレーション図形を追加します。
![ステップ 1/3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")  
  
 **所要時間:** 5 分  
  
 **目標:** この手順への変更の通知を受信するオーケストレーション図形を追加、**従業員**テーブル。  
  
## <a name="prerequisites"></a>前提条件  
 」の手順を完了する必要があります[レッスン 1。スキーマを生成し、メッセージを作成する](../../adapters-and-accelerators/adapter-sql/lesson-1-generate-schemas-and-create-messages.md)します。  
  
### <a name="to-receive-notification-messages"></a>通知メッセージを受信するには  
  
1.  BizTalk オーケストレーションを開いて**EmployeeOrch.odx**で追加した[手順 2。BizTalk オーケストレーションのメッセージを作成する](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md)します。  
  
2.  追加、**受信**オーケストレーションへの図形。 オーケストレーション ツールボックスからドラッグして、**受信**図形をオーケストレーション デザイン画面との間の領域にドロップ、**開始**(緑色の円) と**エンド**図形 (赤色の八角形)。  
  
    |このプロパティを設定します。|この値を|  
    |-----------------------|-------------------|  
    |**Activate**|True|  
    |**メッセージ**|NotifyReceive|  
    |**名前**|ReceiveNotification|  
  
3.  追加、一方向受信ポートをオーケストレーションにします。 SQL Server データベースから通知メッセージを受信するのににはこのポートを使用します。 次のポートのプロパティを設定します。  
  
    |このプロパティを設定します。|この値を|  
    |-----------------------|-------------------|  
    |**通信方向**|Receive|  
    |**通信方式**|一方向|  
    |**[Identifier]**|ReceiveNotification|  
  
     また、変更操作名に Operation_1**通知**します。  
  
4.  接続、 **ReceiveNotification**ポートを**ReceiveNotification**アクション図形。 オーケストレーション デザイナのデザイン画面で、アクション図形の緑、対応するポート ハンドルのために、緑色の矢印ハンドルをドラッグします。  
  
    > [!NOTE]
    >  この手順では、ドラッグ アンド ドロップを使用するポートをアクション図形に接続します。 アクション図形の操作のプロパティは、アクション図形をポートに接続するのに代わりに使用できます。  
  
5.  次の図は、実行中のオーケストレーションを示します。  
  
     ![通知メッセージを受信するオーケストレーション](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-01-receive-notification-orch.gif "sql_adap_tut_01_receive_notification_orch")  
  
## <a name="what-did-i-just-do"></a>でしただけ何か。  
 この手順では、オーケストレーション図形を追加し、受信ポート、SQL Server データベースから通知を受信します。  
  
## <a name="next-steps"></a>次の手順  
 式図形を追加する」の説明に従って、SQL Server データベースから受信した通知の種類を抽出するオーケストレーションに[手順 2。通知の種類を通知メッセージから抽出](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md)します。  
  
## <a name="see-also"></a>参照  
 [手順 2:通知メッセージからの通知の種類を抽出します。](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md)   
 [レッスン 2:通知を受信してフィルター処理する](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)