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
# <a name="step-4-on-premises-create-the-sql-server-table"></a><span data-ttu-id="8b9a6-102">手順 4 (オンプレミス): SQL Server テーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="8b9a6-102">Step 4 (On Premises): Create the SQL Server Table</span></span>
<span data-ttu-id="8b9a6-103">ビジネス シナリオの一環として、販売注文メッセージが Contoso により Northwind に送信されるメッセージ X12 最後に挿入する必要がで、 **SalesOrder**テーブル、注文数量が 100 より大きい場合。</span><span class="sxs-lookup"><span data-stu-id="8b9a6-103">As part of the business scenario, the message X12 sales order message sent by Contoso to Northwind must finally be inserted in a **SalesOrder** table, if the quantity ordered is greater than 100.</span></span> <span data-ttu-id="8b9a6-104">このトピックでは、作成する方法の説明、 **SalesOrder**収納内部設置型である SQL Server データベース インスタンス内のテーブルです。</span><span class="sxs-lookup"><span data-stu-id="8b9a6-104">This topic provides instructions on how to create the **SalesOrder** table within a SQL Server database instance that is housed on-premises.</span></span>  
  
### <a name="to-create-the-salesorder-table"></a><span data-ttu-id="8b9a6-105">SalesOrder テーブルを作成するには</span><span class="sxs-lookup"><span data-stu-id="8b9a6-105">To create the SalesOrder table</span></span>  
  
1.  <span data-ttu-id="8b9a6-106">SQL Server Management Studio を開き、テーブルの作成先となるデータベースに対して次のクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="8b9a6-106">Open SQL Server Management Studio and run the following query against the database where you want to create the table.</span></span>  
  
2.  <span data-ttu-id="8b9a6-107">次のクエリを作成する実行、 **SalesOrder**テーブル。</span><span class="sxs-lookup"><span data-stu-id="8b9a6-107">Run the following query to create the **SalesOrder** table:</span></span>  
  
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
  
3.  <span data-ttu-id="8b9a6-108">対象データベースにテーブルが作成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8b9a6-108">Verify that the table is created in the target database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b9a6-109">参照</span><span class="sxs-lookup"><span data-stu-id="8b9a6-109">See Also</span></span>  
 [<span data-ttu-id="8b9a6-110">チュートリアル 4: BizTalk Server 2013 を使用するハイブリッド アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="8b9a6-110">Tutorial 4: Creating a Hybrid Application Using BizTalk Server 2013</span></span>](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)