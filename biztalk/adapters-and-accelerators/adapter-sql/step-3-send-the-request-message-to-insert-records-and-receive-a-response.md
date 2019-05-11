---
title: 手順 3:レコードを挿入し、応答を受信する要求メッセージの送信 |Microsoft Docs
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
ms.openlocfilehash: f0db2560d1ef8db10e68b67eeb34e6531e03afd6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367691"
---
# <a name="step-3-send-the-request-message-to-insert-records-and-receive-a-response"></a>手順 3:レコードを挿入し、応答を受信する要求メッセージを送信します。
![手順 4 の 3](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")  
  
 **所要時間:** 10 分  
  
 **目標:** レコードを挿入する要求メッセージを送信するこの手順で、 **Purchase_Order**テーブルし、応答を受信します。  
  
## <a name="prerequisites"></a>前提条件  
 完了する必要があります[手順 2。操作要求メッセージを挿入する UPDATE_EMPLOYEE 応答メッセージにマップ](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md)します。  
  
### <a name="to-send-the-request-message-and-receive-a-response"></a>要求メッセージを送信し、応答を受信するには  
  
1.  次の図形 オーケストレーションを追加、**メッセージの構築**図形。  
  
    |図形|図形の種類|プロパティ|  
    |-----------|----------------|----------------|  
    |SendInsertMessage|Send|-設定**メッセージ**に*InsertPO*<br />-設定**名前**に*SendInsertMessage*|  
    |ReceiveInsertResponse|Receive|-設定**アクティブ**に*False*<br />-設定**メッセージ**に*InsertPOResponse*<br />-設定**名前**に*ReceiveInsertResponse*|  
    |SaveInsertResponse|Send|-設定**メッセージ**に*InsertPOResponse*<br />-設定**名前**に*SaveInsertResponse*|  
  
2.  変更、 **SQLOutboundPort**で作成した[手順 2。SQL Server への要求メッセージの送信し、応答受信](../../adapters-and-accelerators/adapter-sql/step-2-send-the-request-message-to-sql-server-and-receive-response.md)します。  
  
    1.  オーケストレーション デザイナでポートを右クリックし、をクリックし、**新しい操作**します。 ポート シェイプの変更、新しい操作を追加する**Operation_1**します。  
  
    2.  クリックして**Operation_1**プロパティ ウィンドウで変更する識別子の値と**InsertPO**します。  
  
3.  一方向の送信ポートをオーケストレーションに追加します。 挿入操作の応答メッセージを送信するのににはこのポートを使用します。 次のポートのプロパティを設定します。  
  
    |このプロパティを設定します。|この値を|  
    |-----------------------|-------------------|  
    |**通信方向**|Send|  
    |**通信方式**|一方向|  
    |**[Identifier]**|SaveResponsePort|  
  
     また、変更操作名に Operation_1 **InsertPO**します。  
  
4.  アクション図形にポートを接続します。 オーケストレーション デザイナのデザイン画面で、アクション図形の緑、対応するポート ハンドルのために、緑色の矢印ハンドルをドラッグします。  
  
    > [!NOTE]
    >  この手順では、ドラッグ アンド ドロップを使用するポートをアクション図形に接続します。 アクション図形の操作のプロパティは、アクション図形をポートに接続するのに代わりに使用できます。  
  
     次のように、ポートとアクション図形を接続します。  
  
    -   接続、 **SendInsertMessage**アクション図形を**要求**の処理、 **InsertPO**の操作、 **SQLOutboundPort**します。  
  
    -   接続、 **ReceiveInsertResponse**アクション図形を**応答**の処理、 **InsertPO**の操作、 **SQLOutboundPort**します。  
  
    -   接続、 **SaveInsertResponse**アクション図形を**要求**の処理、 **SaveResponsePort**します。  
  
5.  次の図は、実行中のオーケストレーションを示します。  
  
     ![完成したオーケストレーション](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-09-comp-orch.gif "sql_adap_tut_09_comp_orch")  
  
## <a name="what-did-i-just-do"></a>でしただけ何か。  
 レコードを挿入する要求を送信した、 **Purchase_Order**テーブルし、応答を受信します。  
  
## <a name="next-steps"></a>次の手順  
 」の説明に従って、プロジェクトをビルドする[手順 4。プロジェクトをビルド](../../adapters-and-accelerators/adapter-sql/step-4-build-the-project.md)します。  
  
## <a name="see-also"></a>参照  
 [手順 2:操作要求メッセージを挿入する UPDATE_EMPLOYEE 応答メッセージをマップします。](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md)   
 [手順 4:プロジェクトをビルドします](../../adapters-and-accelerators/adapter-sql/step-4-build-the-project.md)   
 [レッスン 4:注文テーブルに対して挿入操作を実行する](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)