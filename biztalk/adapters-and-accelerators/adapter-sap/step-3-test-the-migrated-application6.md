---
title: 手順 3:テスト移行 Application6 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migration, testing the migrated application (RFC)
- migration
ms.assetid: 1b1ee59c-a5a3-442d-af2c-0fc4817f3063
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ab38d728eeb5c947dbda1fd38706d0ac5257002
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372783"
---
# <a name="step-3-test-the-migrated-application"></a>手順 3:移行したアプリケーションをテストします。
![ステップ 3/3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")  
  
 **所要時間:** 5 分  
  
 **目標:** この手順では、SD_RFC_CUSTOMER_GET RFC を呼び出すことによって、移行済みのアプリケーションをテストします。 これを行うには、vPrev SAP アダプターを使用して生成されたスキーマに準拠した要求メッセージをドロップします。  
  
## <a name="prerequisites"></a>前提条件  
  
- BizTalk アプリケーションを構成するには、BizTalk オーケストレーションの論理ポートを BizTalk Server 管理コンソールで物理ポートにマッピングします。  
  
- WCF ベースの Wcf-custom 送信ポートを使用する BizTalk アプリケーションを構成する[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
### <a name="to-test-the-migrated-application"></a>移行したアプリケーションをテストするには  
  
1. SAP_RFC_Migration フォルダーから Input.xml 要求メッセージをコピーします。 この要求メッセージは、vPrev SAP アダプターによって生成されたスキーマに準拠しています。 送信マップを使用して、Wcf-custom 送信ポートに変換します WCF ベースのスキーマに準拠するようにこの[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]SAP システムに送信します。  
  
   ```  
   <ns0:SD_RFC_CUSTOMER_GET_Request xmlns:ns0="http://schemas.microsoft.com/BizTalk/2003">  
     <KUNNR>0000001390</KUNNR>  
     <NAME1/>  
     <CUSTOMER_T/>  
   </ns0:SD_RFC_CUSTOMER_GET_Request>  
   ```  
  
2. 貼り付け、ファイルにマップされているフォルダーに要求メッセージの受信場所。  
  
3. オーケストレーションでは、要求メッセージを使用し、SAP システムに送信します。 WCF ベースのスキーマに準拠するスキーマでの SAP システムからの応答が受信した[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。 受信マップを使用して、Wcf-custom 送信ポートに変換しますこの vPrev SAP アダプター用のスキーマにします。 SAP システムからの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。 前の要求メッセージに対する応答は次のとおりです。  
  
   ```  
   <?xml version="1.0" encoding="utf-8" ?>   
   <ns0:SD_RFC_CUSTOMER_GET_Response xmlns:ns0="http://schemas.microsoft.com/BizTalk/2003">  
     <CUSTOMER_T>  
       <KUNNR>0000001390</KUNNR>   
       <ANRED>Firma</ANRED>   
       <NAME1>Contoso, Ltd.</NAME1>   
       <PFACH />   
       <STRAS>Strasse 4567</STRAS>   
       <PSTLZ>50000</PSTLZ>   
       <ORT01>Aachen</ORT01>   
       <TELF1>0123-45678</TELF1>   
       <TELFX>0123-56789</TELFX>   
     </CUSTOMER_T>  
   </ns0:SD_RFC_CUSTOMER_GET_Response>  
   ```  
  
## <a name="see-also"></a>参照  
 [チュートリアル 2: SAP の RFC BizTalk プロジェクトを移行する](../../adapters-and-accelerators/adapter-sap/tutorial-2-migrating-an-sap-rfc-biztalk-project.md)