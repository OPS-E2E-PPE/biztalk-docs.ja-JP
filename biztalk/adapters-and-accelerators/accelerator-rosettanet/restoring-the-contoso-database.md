---
title: "Contoso データベースの復元 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- private process tutorial, restoring databases
- databases, restoring
ms.assetid: 291178c1-826e-49e0-a1d2-cbffee749659
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f77c242fe6477baac53b6a3e1b2fda545a7e4365
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="restoring-the-contoso-database"></a><span data-ttu-id="45dbf-102">Contoso データベースの復元</span><span class="sxs-lookup"><span data-stu-id="45dbf-102">Restoring the Contoso Database</span></span>
<span data-ttu-id="45dbf-103">ここでは、SQL Server Management Studio を使用して SQL スクリプトを実行し、Contoso データベースとそれに関連付けられたストアド プロシージャを復元します。</span><span class="sxs-lookup"><span data-stu-id="45dbf-103">In this step, you use SQL Server Management Studio to run a SQL script to restore the Contoso database and its associated stored procedures.</span></span> <span data-ttu-id="45dbf-104">また、データベース テーブルに準備データを追加します。</span><span class="sxs-lookup"><span data-stu-id="45dbf-104">You also populate the database tables with preliminary data.</span></span>  
  
### <a name="to-restore-the-contoso-database"></a><span data-ttu-id="45dbf-105">Contoso データベースを復元するには</span><span class="sxs-lookup"><span data-stu-id="45dbf-105">To restore the Contoso database</span></span>  
  
1.  <span data-ttu-id="45dbf-106">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft SQL Server 2008 R2**、順にクリック**SQL Server Management Studio**です。</span><span class="sxs-lookup"><span data-stu-id="45dbf-106">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="45dbf-107">サーバー ダイアログ ボックスへの接続で、 **SQL Server**ボックスで、クリックして**接続**です。</span><span class="sxs-lookup"><span data-stu-id="45dbf-107">In the Connect to Server dialog box, in the **SQL Server** box, click **Connect**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="45dbf-108">SQL Server エージェントが開始されていない場合を右クリックし、をクリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="45dbf-108">If the SQL Server Agent is not started, right-click it, and then click **Start**.</span></span>  
  
3.  <span data-ttu-id="45dbf-109">Microsoft SQL Server Management Studio でクリックして**新しいクエリ**です。</span><span class="sxs-lookup"><span data-stu-id="45dbf-109">In the Microsoft SQL Server Management Studio, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="45dbf-110">[クエリ] ペインで、次の SQL スクリプトをコピーし、[クエリ] ウィンドウに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="45dbf-110">In the Query pane, copy and paste the following SQL script into the Query window:</span></span>  
  
    ```  
    CREATE DATABASE Contoso  
    GO  
    USE Contoso  
    GO  
    CREATE TABLE Products (  
    [ProductID] [varchar] (255) NOT NULL ,  
    [Name] [varchar] (255) NOT NULL ,  
    [Description] [varchar] (800) NULL ,  
    [Price] [money] NULL ,  
    [NumberAvailable] [int] NOT NULL   
    ) ON [PRIMARY]  
    GO  
    INSERT INTO Products  
    VALUES( '12345678901234', 'ADM Line Card','',200.65,820 )  
    GO  
    INSERT INTO Products  
    VALUES( '12345678901235','Analog Line Card','',165.24,769 )  
    GO  
    INSERT INTO Products  
    VALUES( '12345678901236', 'Mapper/MUX','',150.54,948)  
    GO  
    CREATE TABLE StatusCodes (  
    [statusID] [int] NOT NULL ,  
    [statusCode] [nvarchar] (50) NOT NULL   
    ) ON [PRIMARY]  
    GO  
    CREATE PROCEDURE GetInventoryForProductID  
    @ProductID varchar(255),  
    @NumberAvailable INT OUTPUT,  
    @Price MONEY OUTPUT  
    AS  
    SET NOCOUNT ON  
    SELECT @NumberAvailable = NumberAvailable,  
     @Price = Price  
    FROM Products  
    WHERE  ProductID = @ProductID  
    RETURN(0)  
    GO  
    CREATE PROCEDURE SP_GetInventoryForProductID  
    @ProductID varchar(255)  
    AS  
    SET NOCOUNT ON  
    SELECT *  
    FROM Products  
    WHERE ProductID = @ProductID  
    for xml auto  
    RETURN(0)  
    ```  
  
5.  <span data-ttu-id="45dbf-111">**[実行]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="45dbf-111">Click **Execute**.</span></span>  
  
### <a name="to-set-permissions-on-the-contoso-database"></a><span data-ttu-id="45dbf-112">Contoso データベースにアクセス許可を設定するには</span><span class="sxs-lookup"><span data-stu-id="45dbf-112">To set permissions on the Contoso database</span></span>  
  
1.  <span data-ttu-id="45dbf-113">Microsoft SQL Server Management Studio の オブジェクト エクスプ ローラーで展開**データベース**、展開、 **Contoso**データベースを展開し、展開**セキュリティ**です。</span><span class="sxs-lookup"><span data-stu-id="45dbf-113">In the Object Explorer of the Microsoft SQL Server Management Studio, expand **Databases**, expand the **Contoso** database, and then expand **Security**.</span></span> <span data-ttu-id="45dbf-114">**[ユーザー]**を右クリックし、 **[新しいユーザー]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="45dbf-114">Right-click **Users**, and then click **New User**.</span></span>  
  
2.  <span data-ttu-id="45dbf-115">データベース ユーザー - 新規 ダイアログ ボックスの**ログイン名**、省略記号ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="45dbf-115">In the Database User - New dialog box, for **Login name**, click the ellipsis.</span></span>  
  
3.  <span data-ttu-id="45dbf-116">[ログインの選択] ダイアログ ボックスで、**参照**です。</span><span class="sxs-lookup"><span data-stu-id="45dbf-116">In the Select Login dialog box, click **Browse**.</span></span>  
  
4.  <span data-ttu-id="45dbf-117">オブジェクト ダイアログ ボックスの参照で、次のように選択します。 **BizTalk Application Users**、をクリックし、 **OK**です。</span><span class="sxs-lookup"><span data-stu-id="45dbf-117">In the Browse for Objects dialog box, select **BizTalk Application Users**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="45dbf-118">[ログインの選択] ダイアログ ボックスで、 **OK**です。</span><span class="sxs-lookup"><span data-stu-id="45dbf-118">In the Select Login dialog box, click **OK**.</span></span>  
  
6.  <span data-ttu-id="45dbf-119">データベース ユーザー - 新規 ダイアログ ボックスで、**データベース ロールのメンバーシップ**ペインで、 **db_datareader**と**db_datawriter**です。</span><span class="sxs-lookup"><span data-stu-id="45dbf-119">In the Database User - New dialog box, in the **Database role membership** pane, select **db_datareader** and **db_datawriter**.</span></span> <span data-ttu-id="45dbf-120">**ユーザー名**、入力**BizTalk Application Users**です。</span><span class="sxs-lookup"><span data-stu-id="45dbf-120">For **User name**, enter **BizTalk Application Users**.</span></span> <span data-ttu-id="45dbf-121">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="45dbf-121">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="45dbf-122">手順 1. ~ 6. を繰り返します**BizTalk Isolated Host Users**を選択すると、 **db_datareader**と**db_datawriter**の**データベース ロールのメンバーシップ**、」と入力して**BizTalk Isolated Host Users**の**ユーザー名**です。</span><span class="sxs-lookup"><span data-stu-id="45dbf-122">Repeat steps 1 through 6 for **BizTalk Isolated Host Users**, selecting **db_datareader** and **db_datawriter** for **Database role membership**, and entering **BizTalk Isolated Host Users** for **User name**.</span></span>  
  
8.  <span data-ttu-id="45dbf-123">手順 1. ~ 6. を繰り返します**BizTalk Server 管理者**を選択すると、 **db_owner**の**データベース ロールのメンバーシップ**、」と入力して**BizTalk Server管理者**の**ユーザー名**です。</span><span class="sxs-lookup"><span data-stu-id="45dbf-123">Repeat steps 1 through 6 for **BizTalk Server Administrators**, selecting **db_owner** for **Database role membership**, and entering **BizTalk Server Administrators** for **User name**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45dbf-124">参照</span><span class="sxs-lookup"><span data-stu-id="45dbf-124">See Also</span></span>  
 [<span data-ttu-id="45dbf-125">生成して、証明書の有効化</span><span class="sxs-lookup"><span data-stu-id="45dbf-125">Generating and Enabling Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/generating-and-enabling-certificates.md)