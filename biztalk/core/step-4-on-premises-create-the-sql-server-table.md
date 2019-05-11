---
title: 手順 4 (オンプレミス):SQL Server のテーブルの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e7e253ac-8707-484f-8461-f098cc7ec7d8
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67981fed618f9214bf1d07c3140c7685fba3a727
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392511"
---
# <a name="step-4-on-premises-create-the-sql-server-table"></a><span data-ttu-id="9fb92-102">手順 4 (オンプレミス):SQL Server のテーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="9fb92-102">Step 4 (On Premises): Create the SQL Server Table</span></span>
<span data-ttu-id="9fb92-103">ビジネス シナリオの一環として、メッセージ X12 販売注文メッセージが Contoso により Northwind に送信する必要があります最後に挿入するを**SalesOrder**注文数量が 100 より大きい場合は、テーブルします。</span><span class="sxs-lookup"><span data-stu-id="9fb92-103">As part of the business scenario, the message X12 sales order message sent by Contoso to Northwind must finally be inserted in a **SalesOrder** table, if the quantity ordered is greater than 100.</span></span> <span data-ttu-id="9fb92-104">このトピックでは、手順を作成する方法には、 **SalesOrder**収納オンプレミスである SQL Server データベース インスタンス内のテーブル。</span><span class="sxs-lookup"><span data-stu-id="9fb92-104">This topic provides instructions on how to create the **SalesOrder** table within a SQL Server database instance that is housed on-premises.</span></span>  
  
### <a name="to-create-the-salesorder-table"></a><span data-ttu-id="9fb92-105">SalesOrder テーブルを作成するには</span><span class="sxs-lookup"><span data-stu-id="9fb92-105">To create the SalesOrder table</span></span>  
  
1.  <span data-ttu-id="9fb92-106">SQL Server Management Studio を開き、テーブルを作成するデータベースに対して次のクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="9fb92-106">Open SQL Server Management Studio and run the following query against the database where you want to create the table.</span></span>  
  
2.  <span data-ttu-id="9fb92-107">作成する次のクエリ実行、 **SalesOrder**テーブル。</span><span class="sxs-lookup"><span data-stu-id="9fb92-107">Run the following query to create the **SalesOrder** table:</span></span>  
  
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
  
3.  <span data-ttu-id="9fb92-108">ターゲット データベースのテーブルが作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="9fb92-108">Verify that the table is created in the target database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fb92-109">参照</span><span class="sxs-lookup"><span data-stu-id="9fb92-109">See Also</span></span>  
 [<span data-ttu-id="9fb92-110">チュートリアル 4: BizTalk Server 2013 を使用してハイブリッド アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="9fb92-110">Tutorial 4: Creating a Hybrid Application Using BizTalk Server 2013</span></span>](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)