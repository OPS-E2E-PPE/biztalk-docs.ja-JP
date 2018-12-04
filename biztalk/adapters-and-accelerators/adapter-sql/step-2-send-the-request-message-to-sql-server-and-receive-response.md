---
title: '手順 2: SQL Server への要求メッセージの送信し、応答の受信 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 864d2174-d54b-4383-92bf-f6808a2a904b
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 55c2c6095c9e0c7bf88ec22a296ccc6483c62472
ms.sourcegitcommit: be6273d612669adfbb9dc9208aaae0a8437d4017
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/04/2018
ms.locfileid: "52826314"
---
# <a name="step-2-send-the-request-message-to-sql-server-and-receive-response"></a>手順 2: SQL Server に要求メッセージを送信し、応答を受信
![手順 2 の 2](../../adapters-and-accelerators/adapter-sql/media/step-2of2.gif "Step_2of2")  
  
 **所要時間:** 10 分  
  
 **目標:** を実行する要求メッセージを送信するこの手順で、 **UPDATE_EMPLOYEE**ストアド プロシージャと、応答を受信します。  
  
## <a name="prerequisites"></a>前提条件  
 完了する必要があります[手順 1: UPDATE_EMPLOYEE ストアド プロシージャの要求メッセージを作成](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-update-employee-stored-procedure.md)です。  
  
### <a name="to-send-the-request-message-and-receive-a-response"></a>要求メッセージを送信し、応答を受信するには  
  
1.  既存のオーケストレーションに下、**挿入**のブロック、**判断**図形を追加、**メッセージの割り当て**図形。 ツールボックスからドラッグして、**メッセージの割り当て**領域に図形が示されます。  
  
    > [!NOTE]
    >  ドロップすると、**メッセージの割り当て**オーケストレーション デザイナー、デザイン画面に図形を作成、それを囲む**メッセージの構築**図形。  
  
2.  デザイン サーフェイスを右クリックし、 **ConstructMessage_1**図形をクリックして**プロパティ ウィンドウ**します。  
  
3.  **プロパティ**のウィンドウ、 **ConstructMessage_1**図形で次の値を指定します。  
  
    |このプロパティを設定します。|この値を|  
    |-----------------------|-------------------|  
    |**構築メッセージ**|更新|  
    |**名前**|ConstructRequestMessage|  
  
4.  ダブルクリックして、 **MessageAssignment**  図形を**BizTalk 式エディタ**します。  
  
5.  **BizTalk 式エディタ**以下を追加します。  
  
    ```  
    UpdateEmployee = UpdateEmployeeMessageCreator.UpdateEmployeeMessageCreator.XMLMessageCreator();  
    UpdateEmployee(WCF.Action) = "TypedProcedure/dbo/UPDATE_EMPLOYEE";  
    ```  
  
     ここでは、**更新**で作成したメッセージは、[手順 2: BizTalk オーケストレーションのメッセージの作成](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md)要求メッセージを送信するため**UPDATE_EMPLOYEE**格納されています。プロシージャです。 **MessageAssignment**図形を呼び出す、 **UpdateEmployeeMessageCreator**要求メッセージを作成するクラス。 また、要求メッセージの WCF アクションを設定します。  
  
6.  次の図形 オーケストレーションを追加、**メッセージの割り当て**図形。  
  
    |図形|図形の種類|[プロパティ]|  
    |-----------|----------------|----------------|  
    |SendUpdateMessage|Send|-設定**メッセージ**に*更新*<br />-設定**名前**に*SendUpdateMessage*|  
    |ReceiveUpdateResponse|Receive|-設定**アクティブ**に*False*<br />-設定**メッセージ**に*UpdateEmployeeResponse*<br />-設定**名前**に*ReceiveUpdateResponse*|  
  
7.  要求-応答の送信ポートをオーケストレーションに追加します。 SQL Server に要求メッセージを送信し、応答を受信するにはこのポートを使用します。 次のポートのプロパティを設定します。  
  
    |このプロパティを設定します。|この値を|  
    |-----------------------|-------------------|  
    |**通信方向**|送信 - 受信|  
    |**通信方式**|要求-応答|  
    |**[Identifier]**|SQLOutboundPort|  
  
     また、変更操作名に Operation_1 **UpdateEmp**します。  
  
8.  アクション図形にポートを接続します。 オーケストレーション デザイナのデザイン画面で、アクション図形の緑、対応するポート ハンドルのために、緑色の矢印ハンドルをドラッグします。  
  
    > [!NOTE]
    >  このステップでは、ドラッグ アンド ドロップを使用して、アクション図形にポートを接続します。 アクション図形の操作プロパティを使用して、アクション図形をポートに接続することもできます。  
  
     次のように、ポートとアクション図形を接続します。  
  
    -   接続、 **SendUpdateMessage**アクション図形を**要求**の処理、 **SQLOutboundPort**します。  
  
    -   接続、 **ReceiveUpdateResponse**アクション図形を**応答**の処理、 **SQLOutboundPort**します。  
  
9. 次の図は、実行中のオーケストレーションを示します。  
  
     ![メッセージを送信するオーケストレーションを更新](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-04-update-msg-orch.gif "sql_adap_tut_04_update_msg_orch")  
  
## <a name="what-did-i-just-do"></a>でしただけ何か。  
 この手順で追加して、オーケストレーションを更新した、 **MessageAssignment**図形、**送信**と**受信**図形とポート。 図形を接続して、UPDATE_EMPLOYEE を実行する要求メッセージを送信するポートが要求メッセージと応答を受信します。  
  
## <a name="next-steps"></a>次の手順  
 次の手順でに対して挿入操作を呼び出すオーケストレーション図形を追加、 **Purchase_Order** 」の説明に従って、テーブル[レッスン 4: 注文テーブルに対して挿入操作を実行](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)します。  
  
## <a name="see-also"></a>参照  
 [手順 1: UPDATE_EMPLOYEE の要求メッセージを作成するストアド プロシージャ](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-update-employee-stored-procedure.md)   
 [レッスン 3: ストアド プロシージャを実行して、追加された新しい従業員を選択する](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md)
