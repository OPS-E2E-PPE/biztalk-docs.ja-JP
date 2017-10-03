---
title: "手順 3: テスト移行 Application6 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- migration, testing the migrated application (RFC)
- migration
ms.assetid: 1b1ee59c-a5a3-442d-af2c-0fc4817f3063
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3ebc175053b7afa1f3c360623b0230809db17bb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-test-the-migrated-application"></a>手順 3: 移行後のアプリケーションをテストします。
![手順 3 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")  
  
 **所要時間:** 5 分  
  
 **目標:**この手順では、SD_RFC_CUSTOMER_GET RFC を呼び出すことによって移行済みのアプリケーションをテストします。 これを行うには、vPrev SAP アダプターを使用して生成されたスキーマに準拠している要求メッセージをドロップします。  
  
## <a name="prerequisites"></a>前提条件  
  
-   BizTalk Server 管理コンソールで物理ポートを BizTalk オーケストレーションの論理ポートにマップして、BizTalk アプリケーションを構成します。  
  
-   WCF ベースの Wcf-custom 送信ポートを使用する BizTalk アプリケーションを構成する[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
### <a name="to-test-the-migrated-application"></a>移行したアプリケーションをテストするには  
  
1.  SAP_RFC_Migration フォルダーから Input.xml 要求メッセージをコピーします。 この要求メッセージは、vPrev SAP アダプターによって生成されたスキーマに準拠しています。 送信マップを使用して、Wcf-custom 送信ポートに変換 WCF ベースのスキーマに準拠するようにこの[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]SAP システムに送信します。  
  
    ```  
    <ns0:SD_RFC_CUSTOMER_GET_Request xmlns:ns0="http://schemas.microsoft.com/BizTalk/2003">  
      <KUNNR>0000001390</KUNNR>  
      <NAME1/>  
      <CUSTOMER_T/>  
    </ns0:SD_RFC_CUSTOMER_GET_Request>  
    ```  
  
2.  貼り付けをファイルにマップされているフォルダーに要求メッセージの受信場所。  
  
3.  オーケストレーションは、要求メッセージを使用して、SAP システムに送信します。 WCF ベースのスキーマに準拠するスキーマで、SAP システムからの応答が受信した[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。 受信マップを使用して、Wcf-custom 送信ポートに変換しますこの vPrev SAP アダプター用のスキーマにします。 SAP システムからの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。 前の要求メッセージに対する応答は次のとおりです。  
  
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
 [チュートリアル 2: SAP RFC の BizTalk プロジェクトを移行します。](../../adapters-and-accelerators/adapter-sap/tutorial-2-migrating-an-sap-rfc-biztalk-project.md)