---
title: "Tutorial2 を使用する準備 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: end-to-end tutorial, pre-requisites
ms.assetid: 88e6c0b5-5f7d-4fee-a4de-7922cfba917f
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8688e84f7913dbc32a0629d21f29ed2578c43b1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="preparing-to-use-the-tutorial"></a>このチュートリアルを使用する準備をしています
チュートリアルを使用する前に、ADT^A03.txt ファイルを作成する必要があります。  
  
### <a name="to-create-the-adta03txt-file"></a>ADT^A03.txt ファイルを作成するには  
  
1.  メモ帳などのエディターを開き、次のテキストをエディターにコピーします。  
  
    ```  
    MSH|^~\&|Tutorial_ADTSystem|MCM|BTAHL7InterfaceEngine||199601121005||ADT^A03|000001|P|2.3.1  
    EVN|A03|199601121005||01||199601121000  
    PID|||191919^^^MYHOS^MR~123-45-6789^^^USSSA^SS|253763|SMITH^JOHN^Q||19560129|M|||  
        123MAIN^^BUFFALO^NY^98052^""||(123)555-0100||S|M|10199925^^^MYHOS^AN|123-45-6789  
    PD1|S|F|NormalString^A^+1^-1^ISO^simpletext&Test&HCD^GI^simpletext&NormalString&ISO^I|  
       NormalString^Test&Test^Test^Test^Test^Test^AE^simpletext^simpletext&Test&ISO^P  
       ^NormalString^M10^MC^simpletext&NormalString&HCD^A|N|simpletext|I|I|N|NormalString  
       ^+1^M11^simpletext&NormalString&L,M,N^RRI^simpletext&NormalString&HCD|NOVALUE^NormalString  
       ^Test^Test^NormalString^Test|N  
    PV1|1|I|2000^2012^01^hey&test&DNS^test^test^test^test^test||||004777^MILLER^CONNIE^A.|||SUR||||2|A0  
    ```  
  
    > [!NOTE]
    >  存在する必要があります、.txt で 5 つの行がファイルに 1 つずつ"MSH"、"EVN"、"PID"、"PD1"および"PV1"で始まります。 "PID"行と"PD1"の行でスペースを削除する必要があります。 必要に応じて、メモ帳での折り返しを無効にします。  
  
2.  ファイルに保存**ADT^A03.txt**で、 \<*ドライブ*\>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<バージョン\>HL7\SDK\End エンドツー エンド チュートリアル フォルダー、および終値のメモ帳のアクセラレータです。  
  
 進みます[手順 1: ヘッダーや受信確認スキーマ作成および展開](../../adapters-and-accelerators/accelerator-hl7/step-1-create-and-deploy-header-and-acknowledgment-schemas.md)です。