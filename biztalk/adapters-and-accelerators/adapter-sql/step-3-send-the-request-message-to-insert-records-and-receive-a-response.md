---
title: '手順 3: レコードを挿入し、応答を受信する要求メッセージの送信 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a8a8906-7c7d-437c-9f04-345ad4ac460e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db97afa0de19e15e5005e5647279365ea6ba023b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224090"
---
# <a name="step-3-send-the-request-message-to-insert-records-and-receive-a-response"></a>手順 3: レコードを挿入し、応答を受信する要求メッセージを送信します。
![手順 4 の 3](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")  
  
 **所要時間:** 10 分  
  
 **目標:** にレコードを挿入する要求メッセージを送信するこの手順で、 **Purchase_Order**テーブルが表示され、応答を受信します。  
  
## <a name="prerequisites"></a>前提条件  
 完了する必要があります[手順 2: 挿入操作の要求メッセージに UPDATE_EMPLOYEE 応答メッセージをマップ](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md)です。  
  
### <a name="to-send-the-request-message-and-receive-a-response"></a>要求メッセージの送信し、応答を受信するには  
  
1.  次の図形 オーケストレーションを追加、**メッセージの構築**図形です。  
  
    |図形|図形の種類|[プロパティ]|  
    |-----------|----------------|----------------|  
    |SendInsertMessage|Send|-設定**メッセージ**に*InsertPO*<br />-設定**名前**に*SendInsertMessage*|  
    |ReceiveInsertResponse|Receive|-設定**アクティブ**に*False*<br />-設定**メッセージ**に*InsertPOResponse*<br />-設定**名前**に*ReceiveInsertResponse*|  
    |SaveInsertResponse|Send|-設定**メッセージ**に*InsertPOResponse*<br />-設定**名前**に*SaveInsertResponse*|  
  
2.  変更、 **SQLOutboundPort**で作成した[手順 2: SQL Server と応答の受信要求メッセージを送信](../../adapters-and-accelerators/adapter-sql/step-2-send-the-request-message-to-sql-server-and-receive-response.md)です。  
  
    1.  オーケストレーション デザイナーでポートを右クリックし、をクリックして**新しい操作**です。 新しい操作を追加するポートの形状変更**Operation_1**です。  
  
    2.  をクリックして**Operation_1**プロパティ ウィンドウで、識別子の値を変更して**InsertPO**です。  
  
3.  一方向の送信ポートをオーケストレーションに追加します。 挿入操作の応答メッセージを送信するのににはこのポートを使用します。 ポートの次のプロパティを設定します。  
  
    |このプロパティを設定します。|この値を|  
    |-----------------------|-------------------|  
    |**通信方向**|Send|  
    |**通信方式**|一方向|  
    |**[Identifier]**|SaveResponsePort|  
  
     また、"operation_1"にから、操作名を変更**InsertPO**です。  
  
4.  アクション図形にポートを接続します。 オーケストレーション デザイナーでのデザイン画面で、アクション図形のポートを対応する緑色のハンドルの緑色の矢印の形のハンドルをドラッグします。  
  
    > [!NOTE]
    >  このステップでは、ドラッグ アンド ドロップを使用して、アクション図形にポートを接続します。 アクション図形の操作プロパティを使用して、アクション図形をポートに接続することもできます。  
  
     次のようにポートとアクション図形を接続します。  
  
    -   接続、 **SendInsertMessage**にアクション図形、**要求**のハンドル、 **InsertPO**の操作、 **SQLOutboundPort**です。  
  
    -   接続、 **ReceiveInsertResponse**にアクション図形、**応答**のハンドル、 **InsertPO**の操作、 **SQLOutboundPort**です。  
  
    -   接続、 **SaveInsertResponse**にアクション図形、**要求**のハンドル、 **SaveResponsePort**です。  
  
5.  次の図では、実行中のオーケストレーションを示します。  
  
     ![完成したオーケストレーション](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-09-comp-orch.gif "sql_adap_tut_09_comp_orch")  
  
## <a name="what-did-i-just-do"></a>でしただけは何ですか。  
 レコードの挿入要求を送信する、 **Purchase_Order**テーブルが表示され、応答を受信します。  
  
## <a name="next-steps"></a>次の手順  
 」の説明に従って、プロジェクトをビルドする[手順 4: プロジェクトをビルド](../../adapters-and-accelerators/adapter-sql/step-4-build-the-project.md)です。  
  
## <a name="see-also"></a>参照  
 [手順 2: マップ操作の要求メッセージを挿入する UPDATE_EMPLOYEE 応答メッセージ](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md)   
 [手順 4: プロジェクトをビルドします](../../adapters-and-accelerators/adapter-sql/step-4-build-the-project.md)   
 [レッスン 4: Purchase Order テーブルで挿入操作を実行します。](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)