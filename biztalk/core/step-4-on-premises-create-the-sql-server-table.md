---
title: "手順 4 (オンプレミス): SQL Server テーブルの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e7e253ac-8707-484f-8461-f098cc7ec7d8
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6a6934a98ccd101003519486388b09504b5f0ab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-4-on-premises-create-the-sql-server-table"></a>手順 4 (オンプレミス): SQL Server テーブルを作成します。
ビジネス シナリオの一環として、販売注文メッセージが Contoso により Northwind に送信されるメッセージ X12 最後に挿入する必要がで、 **SalesOrder**テーブル、注文数量が 100 より大きい場合。 このトピックでは、作成する方法の説明、 **SalesOrder**収納内部設置型である SQL Server データベース インスタンス内のテーブルです。  
  
### <a name="to-create-the-salesorder-table"></a>SalesOrder テーブルを作成するには  
  
1.  SQL Server Management Studio を開き、テーブルの作成先となるデータベースに対して次のクエリを実行します。  
  
2.  次のクエリを作成する実行、 **SalesOrder**テーブル。  
  
    ```  
    CREATE TABLE [dbo].[SalesOrder] (  
        [SalesOrderID] int IDENTITY(1,1) NOT NULL,  
        [PartNum] int  NOT NULL,  
        [DateRequested] datetime  NULL,  
        [CompanyCode] varchar(3)  NOT NULL,  
        [Qty] int  NOT NULL,  
        [UnitAskPrice] float  NULL,  
        [ShipDate] datetime  NOT NULL,  
        [SellToAddress] varchar(255)  NULL,  
        [BillToAddress] varchar(255)  NOT NULL,  
        [PartnerContact] varchar(128)  NULL,  
        [CustomerComments] varchar(500)  NULL,  
        [RFQStatuesId] smallint  NULL  
    );  
    GO  
    ```  
  
3.  対象データベースにテーブルが作成されていることを確認します。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 4: BizTalk Server 2013 を使用するハイブリッド アプリケーションを作成します。](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)