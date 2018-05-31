---
title: 'タスク 5: 構成変換 Shape2 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e92874e-9021-4cf6-bab6-d4173308c469
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 596afdecc38f25ef92dbeb368197d9c71adaffc5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279634"
---
# <a name="task-5-configure-the-transform-shape"></a>タスク 5: 変換図形を構成します。
変換図形を構成するには、次の手順に従います。  
  
### <a name="to-configure-the-transform-shape"></a>変換図形を構成するには  
  
1.  メッセージの構築図形を ReceiveBeginDocResponse の後へドラッグします。  
  
    -   **構築メッセージ:** editlinemsg  
  
    -   **[名前]:** ConstructEditLineMessageWithData  
  
    1.  中央で、選択を右クリックして**図形の挿入**、し、**変換**です。  
  
         ![変換図形の挿入](../core/media/insert-shape-transform.gif "insert_shape_transform")  
  
    2.  変換を使用して、送信データと受信データをマップします。  
  
     作業環境では、(BeginDoc の代わりに) ドキュメントを、すべてのメッセージを構築するために使用できるすべての値、BeginDoc、EditLine、および EndDoc と共に送信する場合があります。 ただし、この例ではハードコードされたデータが使用されています。  
  
2.  [Transform_1] をダブルクリックして開きます。  
  
    1.  ソースを選択し、下の追加行をクリックして**変数名**選択 **[begindocresponsemsg]** です。  
  
         ![ソース変換](../core/media/transform-source.gif "transform_source")  
  
    2.  選択**先**下にある行の追加 をクリック**変数名**を選択**editlinemsg**、 をクリック**ok**です。  
  
         ![変換先](../core/media/transform-destination.gif "transform_destination")  
  
3.  ソリューション エクスプ ローラーでダブルクリック **[transform_1.btm]** マッピング ツールを開きます。 次の 4 つのアイテムをリンクします。  
  
    -   mnCMJobNo  
  
    -   szCMComputerID  
  
    -   mnProcessID  
  
    -   mnTransactionID  
  
     ![変換マッピングの例](../core/media/example-transformmapping.gif "example_transformmapping")  
  
     使いやすいように、この例では値がハードコードされています。 送信先スキーマでアイテムをクリックし、次の値を設定します。  
  
     ![ハードコードされたマッピング](../core/media/hardcoded-mapping-example.gif "hardcoded_mapping_example")  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <ns0:F4211FSEditLine xmlns:ns0="http://schemas.microsoft.com/  
          [JDE://CSALES/B4200310]">  
       <ns0:cCMLineAction>A</ns0:cCMLineAction>  
       <ns0:cCMProcessEdits>1</ns0:cCMProcessEdits>  
       <ns0:cCMWriteToWFFlag>2</ns0:cCMWriteToWFFlag>  
       <ns0:szItemNo>210</ns0:szItemNo>  
       <ns0:mnQtyOrdered>1</ns0:mnQtyOrdered>  
       <ns0:cSalesTaxableYN>N</ns0:cSalesTaxableYN>  
       <ns0:szTransactionUOM>EA</ns0:szTransactionUOM>  
       <ns0:szCMProgramID>XMLInterop</ns0:szCMProgramID>  
       <ns0:szCMVersion>ZJDE0001</ns0:szCMVersion>  
    </ns0:F4211FSEditLine>  
    ```  
  
4.  メッセージの構築図形を [ReceiveEditLine] の後へドラッグします。  
  
    -   **構築メッセージ:** enddocmsg  
  
    -   **[名前]:** ConstructEndDocMessageWithData  
  
         クリックし、中央で右クリック**図形の挿入**、し、**変換**です。  
  
5.  [Transform_2] をダブルクリックして開きます。  
  
    1.  選択**ソース**下にある行の追加 をクリック**変数名**選択**begindocresponsemsg**です。  
  
    2.  選択**先**下にある行の追加 をクリック**変数名**を選択**enddocmsg**、 をクリック**ok**です。  
  
6.  ソリューション エクスプ ローラーでダブルクリック **[transform_2.btm]** マッピング ツールを開きます。 次の 4 つのアイテムをリンクします。  
  
    -   mnCMJobNo  
  
    -   szCMComputerID  
  
    -   mnProcessID  
  
    -   mnTransactionID  
  
     使いやすいように、この例では値がハードコードされています。 送信先スキーマでアイテムをクリックし、次の値を設定します。  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <ns0:F4211FSEndDoc xmlns:ns0="http://schemas.microsoft.com/  
        [JDE://CSALES/B4200310]">  
       <ns0:szCMProgramID>XMLInterop</ns0:szCMProgramID>  
       <ns0:szCMVersion>ZJDE0001</ns0:szCMVersion>  
       <ns0:cCMUseWorkFiles>2</ns0:cCMUseWorkFiles>  
    </ns0:F4211FSEndDoc>  
    ```  
  
## <a name="see-also"></a>参照  
 [タスク 1: ポートを作成します。](../core/task-1-create-the-ports1.md)   
 [タスク 2: メッセージを作成します。](../core/task-2-create-the-messages2.md)   
 [タスク 3: 送信、受信図形と構成](../core/task-3-configure-the-send-and-receive-shapes2.md)   
 [タスク 4: メッセージの構築図形を構成します。](../core/task-4-configure-the-construct-message-shape1.md)