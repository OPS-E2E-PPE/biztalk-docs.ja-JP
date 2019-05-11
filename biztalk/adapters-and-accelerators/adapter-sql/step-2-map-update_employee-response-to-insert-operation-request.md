---
title: 手順 2:操作要求メッセージを挿入する UPDATE_EMPLOYEE 応答メッセージのマップ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8d12014a-0147-4227-88fa-0b290eff4cce
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 825eea8ba60d6b7767f9ea9b7536f8ed65470928
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367793"
---
# <a name="step-2-map-the-updateemployee-response-message-to-insert-operation-request-message"></a>手順 2:操作要求メッセージを挿入する UPDATE_EMPLOYEE 応答メッセージをマップします。
![手順 4 2](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")  

 **所要時間:** 10 分  

 **目標:** この手順で、挿入操作を実行する要求メッセージを作成する、 **Purchase_Order**テーブルし、の応答メッセージをマップし、 **UPDATE_EMPLOYEE**ストアド プロシージャを要求する挿入操作のメッセージ。 これにより、挿入する応答メッセージの値で渡す、 **Purchase_Order**テーブル。  

## <a name="prerequisites"></a>前提条件  
 完了する必要があります[手順 1。Purchase_Order テーブルに対する挿入操作の要求メッセージを作成](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-insert-operation-on-purchase-order-table.md)です。  

### <a name="to-map-the-messages"></a>メッセージにマップするには  

1. 既存のオーケストレーションで、**挿入**のブロック、**判断**図形の下、 **ReceiveUpdateResponse**図形を追加、 **メッセージの割り当て**図形。 ツールボックスからドラッグして、**メッセージの割り当て**領域に図形が示されます。  

   > [!NOTE]
   >  ドロップすると、**メッセージの割り当て**オーケストレーション デザイナー、デザイン画面に図形を作成、それを囲む**メッセージの構築**図形。  

2. デザイン サーフェイスを右クリックし、 **ConstructMessage_1**図形をクリックして**プロパティ ウィンドウ**します。  

3. **プロパティ**のウィンドウ、 **ConstructMessage_1**図形で次の値を指定します。  


   |    このプロパティを設定します。     |     この値を      |
   |--------------------------|------------------------|
   | **構築メッセージ** |        InsertPO        |
   |         **名前**         | ConstructInsertMessage |


4. ダブルクリックして、 **MessageAssignment**  図形を**BizTalk 式エディタ**します。  

5. **BizTalk 式エディタ**以下を追加します。  

   ```  
   InsertPO = UpdatePOMessageCreator.UpdatePOMessageCreator.XMLMessageCreator();  
   InsertPO(WCF.Action) = "TableOp/Insert/dbo/Purchase_Order";  
   ```  

    ここでは、 **InsertPO**で作成したメッセージは、[手順 2。BizTalk オーケストレーションのメッセージを作成する](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md)挿入操作の要求メッセージを送信するため、 **Purchase_Order**テーブル。 **MessageAssignment**図形を呼び出す、 **UpdatePOMessageCreator**要求メッセージを作成するクラス。 また、要求メッセージの WCF アクションを設定します。  

6. 内で、**メッセージの構築**図形以降、**メッセージの割り当て**図形を追加、**変換**図形。  

7. **変換の構成**] ダイアログ ボックスで、左側のウィンドウから、**変換**ラベルで、[**ソース**します。  

8. **送信元の変換**右側のボックスに、下の空白部分をクリックして、**変数名**、し、 **UpdateEmployeeResponse**します。  

    ![ソース スキーマのマッピングの選択](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-05-source-map.gif "sql_adap_tut_05_source_map")  

9. **変換の構成** ダイアログ ボックスで、左側のウィンドウから、**変換**ラベルで、をクリックして**先**します。  

10. **送信先の変換**右側のボックスに、下の空白部分をクリックして、**変数名**、し、 **InsertPO**します。  

     ![変換先スキーマのマッピングの選択](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-05-dest-map.gif "sql_adap_tut_05_dest_map")  

11. **[OK]** をクリックします。 マップ ファイルが開きます。  

12. 元と送信先スキーマ内のノードを展開します。  

13. Employee_ID をマップし、両方のスキーマのフィールドの名前します。  

    - マップ、 **Employee_ID**をソース スキーマ (UPDATE_EMPLOYEEResponse) 内のノード、 **Employee_ID**送信先スキーマ (挿入) 内のノード。  

    - マップ、**名前**ソース スキーマのノードに、 **Employee_Name**送信先スキーマです。  

      次の図は、マップされたスキーマを示します。  

      ![マップ元と送信先スキーマ](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-07-dest-map.gif "sql_adap_tut_07_dest_map")  

      保存して、マップを閉じます。  

14. 次の図は、実行中のオーケストレーションを示します。  

     ![変換図形をオーケストレーション](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-08-map-orch.gif "sql_adap_tut_08_map_orch")  

## <a name="what-did-i-just-do"></a>でしただけ何か。  
 この手順では、レコードの挿入先のメッセージを作成、 **Purchase_Order**テーブルし、からの応答メッセージをマップし、 **UPDATE_EMPLOYEE**挿入ストアド プロシージャ、要求メッセージを操作です。  

## <a name="next-steps"></a>次の手順  
 挿入操作を実行する要求メッセージを送信する、 **Purchase_Order**テーブルし、」の説明に従って、応答を受信[手順 3。レコードを挿入し、応答を受信する要求メッセージの送信](../../adapters-and-accelerators/adapter-sql/step-3-send-the-request-message-to-insert-records-and-receive-a-response.md)します。  

## <a name="see-also"></a>参照  
 [ステップ 1: Purchase_Order テーブルに対する挿入操作の要求メッセージを作成します。](../../adapters-and-accelerators/adapter-sql/step-1-create-the-request-message-for-insert-operation-on-purchase-order-table.md)   
 [レッスン 4:注文テーブルに対して挿入操作を実行する](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)