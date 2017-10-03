---
title: "手順 2: SQL Server に要求メッセージを送信し、応答を受信 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 864d2174-d54b-4383-92bf-f6808a2a904b
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce820ab6a1914e44239313588eaaefeb696e61d6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-send-the-request-message-to-sql-server-and-receive-response"></a>手順 2: SQL Server に要求メッセージを送信し、応答を受信
![手順 2 の 2](../../adapters-and-accelerators/adapter-sql/media/step-2of2.gif "Step_2of2")  
  
 **所要時間:** 10 分  
  
 **目標:**を実行する要求メッセージを送信するこの手順で、 **UPDATE_EMPLOYEE**ストアド プロシージャと、応答を受信します。  
  
## <a name="prerequisites"></a>前提条件  
 完了する必要があります[手順 1: UPDATE_EMPLOYEE ストアド プロシージャ用の要求メッセージを作成する](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-update-employee-stored-procedure.md)です。  
  
### <a name="to-send-the-request-message-and-receive-a-response"></a>要求メッセージの送信し、応答を受信するには  
  
1.  既存のオーケストレーションを下にある、**挿入**のブロック、**判断**図形を追加、**メッセージの割り当て**図形です。 ツールボックスからドラッグして、**メッセージの割り当て**スペースに図形が示されます。  
  
    > [!NOTE]
    >  ドロップすると、**メッセージの割り当て**オーケストレーション デザイナー、デザイン サーフェイスに図形を作成、外側にある**メッセージの構築**図形です。  
  
2.  デザイン サーフェイスを右クリックし、 **ConstructMessage_1**図形をクリックして**プロパティ ウィンドウ**します。  
  
3.  **プロパティ**のウィンドウ、 **ConstructMessage_1**図形で次の値を指定します。  
  
    |このプロパティを設定します。|この値を|  
    |-----------------------|-------------------|  
    |**構築メッセージ**|更新|  
    |**名前**|ConstructRequestMessage|  
  
4.  ダブルクリックして、 **MessageAssignment**図形を開くには、 **BizTalk 式エディタ**です。  
  
5.  **BizTalk 式エディタ**以下を追加します。  
  
    ```  
    UpdateEmployee = UpdateEmployeeMessageCreator.UpdateEmployeeMessageCreator.XMLMessageCreator();  
    UpdateEmployee(WCF.Action) = "TypedProcedure/dbo/UPDATE_EMPLOYEE";  
    ```  
  
     ここでは、**更新**で作成したメッセージは、[手順 2: BizTalk オーケストレーションのメッセージの作成](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md)要求メッセージを送信するため**UPDATE_EMPLOYEE**格納されています。プロシージャです。 **MessageAssignment**図形を呼び出す、 **UpdateEmployeeMessageCreator**要求メッセージを作成するクラス。 また、要求メッセージの WCF アクションを設定します。  
  
6.  次の図形 オーケストレーションを追加、**メッセージの割り当て**図形です。  
  
    |図形|図形の種類|[プロパティ]|  
    |-----------|----------------|----------------|  
    |SendUpdateMessage|Send|-設定**メッセージ**に*更新*<br />-設定**名前**に*SendUpdateMessage*|  
    |ReceiveUpdateResponse|Receive|-設定**アクティブ**に*False*<br />-設定**メッセージ**に*UpdateEmployeeResponse*<br />-設定**名前**に*ReceiveUpdateResponse*|  
  
7.  要求-応答送信ポートをオーケストレーションに追加します。 SQL Server に要求メッセージを送信し、応答を受信するにはこのポートを使用します。 ポートの次のプロパティを設定します。  
  
    |このプロパティを設定します。|この値を|  
    |-----------------------|-------------------|  
    |**通信方向**|送信 - 受信|  
    |**通信方式**|要求-応答|  
    |**[Identifier]**|SQLOutboundPort|  
  
     また、"operation_1"にから、操作名を変更**UpdateEmp**です。  
  
8.  アクション図形にポートを接続します。 オーケストレーション デザイナーでのデザイン画面で、アクション図形のポートを対応する緑色のハンドルの緑色の矢印の形のハンドルをドラッグします。  
  
    > [!NOTE]
    >  このステップでは、ドラッグ アンド ドロップを使用して、アクション図形にポートを接続します。 アクション図形の操作プロパティを使用して、アクション図形をポートに接続することもできます。  
  
     次のようにポートとアクション図形を接続します。  
  
    -   接続、 **SendUpdateMessage**にアクション図形、**要求**のハンドル、 **SQLOutboundPort**です。  
  
    -   接続、 **ReceiveUpdateResponse**にアクション図形、**応答**のハンドル、 **SQLOutboundPort**です。  
  
9. 次の図では、実行中のオーケストレーションを示します。  
  
     ![更新メッセージを送信するオーケストレーションを更新](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-04-update-msg-orch.gif "sql_adap_tut_04_update_msg_orch")  
  
## <a name="what-did-i-just-do"></a>でしただけは何ですか。  
 この手順で追加することによって、オーケストレーションを更新した、 **MessageAssignment**図形、**送信**と**受信**図形、およびポートです。 図形を接続して、UDPATE_EMPLOYEE を実行する要求メッセージを送信ポートが要求メッセージと応答を受信します。  
  
## <a name="next-steps"></a>次の手順  
 次の手順でに対して挿入操作を呼び出すオーケストレーション図形を追加する、 **Purchase_Order** 」の説明に従っての表に、[レッスン 4: Purchase Order テーブルに対して挿入操作を実行](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)です。  
  
## <a name="see-also"></a>参照  
 [手順 1: UPDATE_EMPLOYEE の要求メッセージを作成するストアド プロシージャ](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-update-employee-stored-procedure.md)   
 [レッスン 3: 追加された新しい従業員を選択するストアド プロシージャを実行します。](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md)