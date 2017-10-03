---
title: "手順 3: SQL アダプターを使用する移行されたアプリケーションのテスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 929ce2f3-94ed-4e12-b629-e229769f825a
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2eaf57c08157ffb9785f591016793c4c416704bf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-test-the-migrated-application-that-uses-the-sql-adapter"></a>手順 3: SQL アダプターを使用する移行されたアプリケーションをテストします。
![手順 3 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")  
  
 **所要時間:** 5 分  
  
 **目標:**この手順では、顧客テーブルに挿入操作を実行することによって移行済みのアプリケーションをテストします。 これを行う、vPrev を使用して生成されたスキーマに準拠した要求メッセージをドロップする[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
## <a name="prerequisites"></a>前提条件  
  
-   BizTalk Server 管理コンソールで物理ポートを BizTalk オーケストレーションの論理ポートにマップして、BizTalk アプリケーションを構成します。  
  
-   WCF ベースの Wcf-custom 送信ポートを使用する BizTalk アプリケーションを構成する[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
### <a name="to-test-the-migrated-application"></a>移行したアプリケーションをテストするには  
  
1.  要求、vPrev によって生成されたスキーマに準拠した XML を作成する[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。 送信マップを使用して、Wcf-custom 送信ポートに変換 WCF ベースのスキーマに準拠するようにこの[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]し、SQL Server データベースに送信します。  
  
    ```  
    <Insert xmlns="http://SQLInsert">  
      <sync>  
        <after>  
          <CustomerTable Name="John" />  
        </after>  
      </sync>  
    </Insert>  
    ```  
  
2.  貼り付けをファイルにマップされているフォルダーに要求メッセージの受信場所。  
  
3.  オーケストレーションは、要求メッセージを使用して、SQL Server データベースに送信します。 WCF ベースのスキーマに準拠するスキーマで、SQL Server データベースからの応答が受信した[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。 受信マップを使用して、Wcf-custom 送信ポートに変換しますこの、vPrev 用のスキーマに[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。 SQL Server データベースからの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。 上記の要求メッセージに対する応答は次のとおりです。  
  
    ```  
    \<?xml version="1.0" encoding="utf-8" ?>   
    <InsertResponse xmlns="http://SQLInsert">  
      <Success>  
        <long xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">101</long>   
      </Success>  
    </InsertResponse>  
    ```  
  
     前の応答では、「101」は、Customer テーブルに挿入された identity 列の値です。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 1: SQL アダプタを BizTalk プロジェクトを移行します。](../../adapters-and-accelerators/adapter-sql/tutorial-1-migrate-biztalk-projects-to-the-sql-adapter.md)