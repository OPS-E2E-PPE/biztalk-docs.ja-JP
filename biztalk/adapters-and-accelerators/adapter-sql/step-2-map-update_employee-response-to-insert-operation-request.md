---
title: "手順 2: マップ操作の要求メッセージを挿入する UPDATE_EMPLOYEE 応答メッセージ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8d12014a-0147-4227-88fa-0b290eff4cce
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 29a7cef00860f32aa2a493cc401e5d49d223ad3a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-map-the-updateemployee-response-message-to-insert-operation-request-message"></a>手順 2: マップ操作の要求メッセージを挿入する UPDATE_EMPLOYEE 応答メッセージ
![手順 4 2](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")  
  
 **所要時間:** 10 分  
  
 **目標:**挿入操作を実行する要求メッセージを作成するこの手順で、 **Purchase_Order**テーブルし、の応答メッセージをマップし、 **UPDATE_EMPLOYEE**格納されています。挿入操作の要求メッセージにプロシージャです。 これによりに挿入される応答メッセージの値を渡す、 **Purchase_Order**テーブル。  
  
## <a name="prerequisites"></a>前提条件  
 完了する必要があります[手順 1: Purchase_Order テーブルに対する挿入操作の要求メッセージを作成する](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-insert-operation-on-purchase-order-table.md)です。  
  
### <a name="to-map-the-messages"></a>メッセージにマップするには  
  
1.  既存のオーケストレーションで、**挿入**のブロック、**判断**図形の下にある、 **ReceiveUpdateResponse**図形を追加、**メッセージの割り当て**図形です。 ツールボックスからドラッグして、**メッセージの割り当て**スペースに図形が示されます。  
  
    > [!NOTE]
    >  ドロップすると、**メッセージの割り当て**オーケストレーション デザイナー、デザイン サーフェイスに図形を作成、外側にある**メッセージの構築**図形です。  
  
2.  デザイン サーフェイスを右クリックし、 **ConstructMessage_1**図形をクリックして**プロパティ ウィンドウ**します。  
  
3.  **プロパティ**のウィンドウ、 **ConstructMessage_1**図形で次の値を指定します。  
  
    |このプロパティを設定します。|この値を|  
    |-----------------------|-------------------|  
    |**構築メッセージ**|InsertPO|  
    |**名前**|ConstructInsertMessage|  
  
4.  ダブルクリックして、 **MessageAssignment**図形を開くには、 **BizTalk 式エディタ**です。  
  
5.  **BizTalk 式エディタ**以下を追加します。  
  
    ```  
    InsertPO = UpdatePOMessageCreator.UpdatePOMessageCreator.XMLMessageCreator();  
    InsertPO(WCF.Action) = "TableOp/Insert/dbo/Purchase_Order";  
    ```  
  
     ここでは、 **InsertPO**で作成したメッセージは、[手順 2: BizTalk オーケストレーションのメッセージの作成](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md)挿入操作の要求メッセージを送信するため、 **Purchase_Order**テーブル。 **MessageAssignment**図形を呼び出す、 **UpdatePOMessageCreator**要求メッセージを作成するクラス。 また、要求メッセージの WCF アクションを設定します。  
  
6.  内で、**メッセージの構築**図形後、**メッセージの割り当て**図形を追加、**変換**図形です。  
  
7.  **変換の構成** ダイアログ ボックスで、左側のペインから、**変換**ラベルをクリックして**ソース**です。  
  
8.  **送信元の変換**右側のボックスで、下の空白部分をクリックして、**変数名**、し、 **UpdateEmployeeResponse**です。  
  
     ![ソース スキーマのマッピングの選択](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-05-source-map.gif "sql_adap_tut_05_source_map")  
  
9. **変換の構成** ダイアログ ボックスで、左側のペインから、**変換**ラベルをクリックして**先**です。  
  
10. **送信先の変換**右側のボックスで、下の空白部分をクリックして、**変数名**、し、 **InsertPO**です。  
  
     ![変換先スキーマのマッピングの選択](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-05-dest-map.gif "sql_adap_tut_05_dest_map")  
  
11. **[OK]**をクリックします。 マップ ファイルを開きます。  
  
12. 送信元と送信先スキーマ内のノードを展開します。  
  
13. Employee_ID をマップし、両方のスキーマ内のフィールドの名前します。  
  
    -   マップ、 **Employee_ID**スキーマのノードに、ソース (UPDATE_EMPLOYEEResponse)、 **Employee_ID**送信先スキーマ (Insert) のノードです。  
  
    -   マップ、**名前**ソース スキーマのノードに、 **Employee_Name**送信先スキーマです。  
  
     次の図は、マップされているスキーマを示します。  
  
     ![送信元と送信先スキーマのマッピング](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-07-dest-map.gif "sql_adap_tut_07_dest_map")  
  
     保存して、マップを閉じます。  
  
14. 次の図では、実行中のオーケストレーションを示します。  
  
     ![変換図形をオーケストレーション](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-08-map-orch.gif "sql_adap_tut_08_map_orch")  
  
## <a name="what-did-i-just-do"></a>でしただけは何ですか。  
 このステップでレコードの挿入先のメッセージを作成した、 **Purchase_Order**テーブルからの応答メッセージをマップが表示され、 **UPDATE_EMPLOYEE** insert ストアド プロシージャ、要求メッセージを操作。  
  
## <a name="next-steps"></a>次の手順  
 挿入操作を実行する要求メッセージを送信する、 **Purchase_Order**テーブル応答を受信する、」の説明に従って[手順 3: 応答を挿入するレコードし受信要求メッセージの送信](../../adapters-and-accelerators/adapter-sql/step-3-send-the-request-message-to-insert-records-and-receive-a-response.md)です。  
  
## <a name="see-also"></a>参照  
 [手順 1: Purchase_Order テーブルに対する挿入操作の要求メッセージを作成します。](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-insert-operation-on-purchase-order-table.md)   
 [レッスン 4: Purchase Order テーブルで挿入操作を実行します。](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)