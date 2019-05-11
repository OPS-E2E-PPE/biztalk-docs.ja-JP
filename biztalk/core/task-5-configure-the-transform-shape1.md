---
title: タスク 5:変換図形の 1 の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93a73fd2-0f34-4681-8aed-7d54d69c86d3
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1cf1be22c9a42da6cb82cb4d2303bcbc45038180
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65299839"
---
# <a name="task-5-configure-the-transform-shape"></a>タスク 5:変換図形を構成します。
変換図形を構成するのにには、次の手順を使用します。  
  
### <a name="to-configure-the-transform-shape"></a>変換図形を構成するには  
  
1. メッセージの構築図形を ReceiveBeginDocResponse の後へドラッグします。  
  
   - **構築メッセージ:** EditLineMsg  
  
   - **名:** ConstructEditLineMessageWithData  
  
     右クリックし、真ん中の**図形の挿入**、し、**変換**します。  
  
     ![](../core/media/jde-insert-shape-transform.gif "JDE_insert_shape_transform")  
  
     変換を使用して送信されるデータを送信するデータからデータをマップします。  
  
     作業環境にはドキュメントを送信する (BeginDoc) ではなくすべての値を持つことのすべての可能なメッセージ、BeginDoc、EditLine、および EndDoc を構築することができます。 この例では、ただし、データがあるのみハード コード化されました。  
  
2. ダブルクリック**変換 _ 1**を開きます。  
  
   1.  ソースを選択し、下の追加行をクリックして**変数名**選択**BeginDocResponseMsg**します。  
  
        ![](../core/media/jde-transform-source.gif "JDE_transform_source")  
  
   2.  選択**先**行の追加 をクリック**変数名**を選択します**EditLineMsg**、 をクリック**ok**します。  
  
        ![](../core/media/jde-transform-destination.gif "JDE_transform_destination")  
  
3. ソリューション エクスプ ローラーでダブルクリック **[transform_1.btm]** マッピング ツールを開きます。 次の 4 つの項目をリンクするには。  
  
   - mnCMJobNo  
  
   - szCMComputerID  
  
   - mnProcessID  
  
   - mnTransactionID  
  
     ![](../core/media/jde-example-transformmapping.gif "JDE_example_transformmapping")  
  
     この例では、使いやすさのハードコーディングされた値があります。 送信先スキーマ内の項目をクリックし、次の値を設定します。  
  
     ![](../core/media/jde-hardcoded-mapping-example.gif "JDE_hardcoded_mapping_example")  
  
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
  
4. ReceiveEditLine の後に、メッセージの構築をドラッグします。  
  
   - **構築メッセージ:** EndDocMsg  
  
   - **名:** ConstructEndDocMessageWithData  
  
     クリックし、中央で右クリックして**図形の挿入**、し、**変換**します。  
  
5. ダブルクリック **[transform_2]** を開きます。  
  
   1.  選択**ソース**[行の追加] をクリック**変数名**選択と**BeginDocResponseMsg**します。  
  
   2.  選択**先**行の追加 をクリック**変数名**を選択します**EndDocMsg**、 をクリック**ok**します。  
  
6. ソリューション エクスプ ローラーでダブルクリック **[transform_2.btm]** マッピング ツールを開きます。 次の 4 つの項目をリンクするには。  
  
   - mnCMJobNo  
  
   - szCMComputerID  
  
   - mnProcessID  
  
   - mnTransactionID  
  
     この例では、使いやすさのハードコーディングされた値があります。 送信先スキーマ内の項目をクリックし、次の値を設定します。  
  
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
 [タスク 1:ポートを作成します。](../core/task-1-create-the-ports2.md)   
 [タスク 2:メッセージを作成します。](../core/task-2-create-the-messages1.md)   
 [タスク 3:受信図形と送信の構成](../core/task-3-configure-the-send-and-receive-shapes1.md)   
 [タスク 4:メッセージの構築図形を構成します。](../core/task-4-configure-the-construct-message-shape2.md)