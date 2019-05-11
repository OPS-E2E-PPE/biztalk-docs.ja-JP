---
title: 手順 3:SQL アダプタを使用する移行されたアプリケーションのテスト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 929ce2f3-94ed-4e12-b629-e229769f825a
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 95d0752426d30a9d4bd75ef1b34188c1b1fcbc83
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367712"
---
# <a name="step-3-test-the-migrated-application-that-uses-the-sql-adapter"></a>手順 3:SQL アダプタを使用する移行されたアプリケーションをテストします。
![ステップ 3/3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")  
  
 **所要時間:** 5 分  
  
 **目標:** この手順では、顧客テーブルに対する挿入操作を実行することによって移行済みのアプリケーションをテストします。 これを行うには、vPrev を使用して生成されたスキーマに準拠した要求メッセージをドロップ[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  
  
## <a name="prerequisites"></a>前提条件  
  
- BizTalk アプリケーションを構成するには、BizTalk オーケストレーションの論理ポートを BizTalk Server 管理コンソールで物理ポートにマッピングします。  
  
- WCF ベースの Wcf-custom 送信ポートを使用する BizTalk アプリケーションを構成する[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  
  
### <a name="to-test-the-migrated-application"></a>移行したアプリケーションをテストするには  
  
1. VPrev によって生成されたスキーマに準拠した XML 要求を作成する[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。 送信マップを使用して、Wcf-custom 送信ポートに変換します WCF ベースのスキーマに準拠するようにこの[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]SQL Server データベースに送信します。  
  
   ```  
   <Insert xmlns="http://SQLInsert">  
     <sync>  
       <after>  
         <CustomerTable Name="John" />  
       </after>  
     </sync>  
   </Insert>  
   ```  
  
2. 貼り付け、ファイルにマップされているフォルダーに要求メッセージの受信場所。  
  
3. オーケストレーションでは、要求メッセージを使用し、SQL Server データベースに送信します。 WCF ベースのスキーマに準拠するスキーマで、SQL Server データベースからの応答が受信した[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。 受信マップを使用して、Wcf-custom 送信ポートに変換しますこの vPrev 用のスキーマに[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。 SQL Server データベースからの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。 前の要求メッセージに対する応答は次のとおりです。  
  
   ```  
   <?xml version="1.0" encoding="utf-8" ?>   
   <InsertResponse xmlns="http://SQLInsert">  
     <Success>  
       <long xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">101</long>   
     </Success>  
   </InsertResponse>  
   ```  
  
    前の応答では、「101」は、顧客テーブルに挿入される id 列の値です。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 1:SQL アダプタを BizTalk プロジェクトを移行します。](../../adapters-and-accelerators/adapter-sql/tutorial-1-migrate-biztalk-projects-to-the-sql-adapter.md)