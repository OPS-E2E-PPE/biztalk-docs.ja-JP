---
title: 手順 3:Oracle データベース アダプターに移行したアプリケーションのテスト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 495efc4f-9d9e-450f-a03a-628bb54e658f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51a4c635e00a9c8107e62f67d4b844cb9f1d0ec2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375974"
---
# <a name="step-3-test-the-migrated-application-to-oracle-database-adapter"></a>手順 3:Oracle データベース アダプターに移行したアプリケーションをテストします。
![ステップ 3/3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")  
  
 **所要時間:** 5 分  
  
 **目標:** この手順では、SCOTT に対して、挿入操作を実行することによって移行済みのアプリケーションをテストします。CUSTOMER テーブル。 これを行うには、vPrev Oracle データベース アダプターを使用して生成されたスキーマに準拠した要求メッセージをドロップします。  
  
## <a name="prerequisites"></a>前提条件  
  
- BizTalk アプリケーションを構成するには、BizTalk オーケストレーションの論理ポートを BizTalk Server 管理コンソールで物理ポートにマッピングします。  
  
- WCF ベースの Wcf-custom 送信ポートを使用する BizTalk アプリケーションを構成する[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。  
  
### <a name="to-test-the-migrated-application"></a>移行したアプリケーションをテストするには  
  
1. Oracle_Migration フォルダーから OracleInsert.xml 要求メッセージをコピーします。 この要求メッセージは、vPrev Oracle データベース アダプターによって生成されたスキーマに準拠しています。 送信マップを使用して、Wcf-custom 送信ポートに変換します WCF ベースのスキーマに準拠するようにこの[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]Oracle データベースに送信します。  
  
   ```  
   <ns0:Insert xmlns:ns0="http://schemas.microsoft.com/[OracleDb://ADAPTER/SCOTT/Tables/CUSTOMER]">  
     <ns0:Rows>  
       <ns0:InsertRecord>  
         <ns0:NAME>Customer_1</ns0:NAME>  
         <ns0:STREET>Street_1</ns0:STREET>  
         <ns0:CITY>City_1</ns0:CITY>  
       </ns0:InsertRecord>  
       <ns0:InsertRecord>  
         <ns0:NAME>Customer_2</ns0:NAME>  
         <ns0:STREET>Street_2</ns0:STREET>  
         <ns0:CITY>City_2</ns0:CITY>  
       </ns0:InsertRecord>  
     </ns0:Rows>  
   </ns0:Insert>  
   ```  
  
2. 貼り付け、ファイルにマップされているフォルダーに要求メッセージの受信場所。  
  
3. オーケストレーションでは、要求メッセージを使用し、Oracle データベースに送信します。 WCF ベースのスキーマに準拠するスキーマで、Oracle データベースからの応答が受信した[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。 受信マップを使用して、Wcf-custom 送信ポートに変換しますこの vPrev Oracle データベース アダプター用のスキーマにします。 Oracle データベースからの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。 前の要求メッセージに対する応答は次のとおりです。  
  
   ```  
   <?xml version="1.0" encoding="utf-8"?>  
   <ns0:InsertResponse xmlns:ns0="http://schemas.microsoft.com/[OracleDb://ADAPTER/SCOTT/Tables/CUSTOMER]"></ns0:InsertResponse>  
   ```  
  
## <a name="see-also"></a>参照  
 [チュートリアル: BizTalk プロジェクトの移行](https://msdn.microsoft.com/library/dd788186(v=bts.80).aspx)