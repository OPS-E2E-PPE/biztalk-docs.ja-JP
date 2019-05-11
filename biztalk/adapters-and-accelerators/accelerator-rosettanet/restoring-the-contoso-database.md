---
title: Contoso データベースの復元 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, restoring databases
- databases, restoring
ms.assetid: 291178c1-826e-49e0-a1d2-cbffee749659
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d434d3817a8e00f01e458dd96850b1bff6bb79a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282401"
---
# <a name="restoring-the-contoso-database"></a><span data-ttu-id="9bcc6-102">Contoso データベースの復元</span><span class="sxs-lookup"><span data-stu-id="9bcc6-102">Restoring the Contoso Database</span></span>
<span data-ttu-id="9bcc6-103">この手順では、Contoso データベースとその関連付けられたストアド プロシージャを復元するのに SQL スクリプトを実行するのに SQL Server Management Studio を使用します。</span><span class="sxs-lookup"><span data-stu-id="9bcc6-103">In this step, you use SQL Server Management Studio to run a SQL script to restore the Contoso database and its associated stored procedures.</span></span> <span data-ttu-id="9bcc6-104">予備的なデータをデータベース テーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="9bcc6-104">You also populate the database tables with preliminary data.</span></span>  
  
### <a name="to-restore-the-contoso-database"></a><span data-ttu-id="9bcc6-105">Contoso データベースを復元するには</span><span class="sxs-lookup"><span data-stu-id="9bcc6-105">To restore the Contoso database</span></span>  
  
1.  <span data-ttu-id="9bcc6-106">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft SQL Server 2008 R2**、順にクリックします**SQL Server Management Studio**します。</span><span class="sxs-lookup"><span data-stu-id="9bcc6-106">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="9bcc6-107">サーバー] ダイアログ ボックスへの接続で、 **SQL Server**ボックスで、[ **Connect**します。</span><span class="sxs-lookup"><span data-stu-id="9bcc6-107">In the Connect to Server dialog box, in the **SQL Server** box, click **Connect**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9bcc6-108">SQL Server エージェントが開始されていない場合を右クリックし、順にクリックします**開始**します。</span><span class="sxs-lookup"><span data-stu-id="9bcc6-108">If the SQL Server Agent is not started, right-click it, and then click **Start**.</span></span>  
  
3.  <span data-ttu-id="9bcc6-109">Microsoft SQL Server Management Studio で次のようにクリックします。**新しいクエリ**します。</span><span class="sxs-lookup"><span data-stu-id="9bcc6-109">In the Microsoft SQL Server Management Studio, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="9bcc6-110">クエリ ウィンドウでコピーしてクエリ ウィンドウに次の SQL スクリプトを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="9bcc6-110">In the Query pane, copy and paste the following SQL script into the Query window:</span></span>  
  
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
  
5.  <span data-ttu-id="9bcc6-111">**[実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9bcc6-111">Click **Execute**.</span></span>  
  
### <a name="to-set-permissions-on-the-contoso-database"></a><span data-ttu-id="9bcc6-112">Contoso データベースにアクセス許可を設定するには</span><span class="sxs-lookup"><span data-stu-id="9bcc6-112">To set permissions on the Contoso database</span></span>  
  
1.  <span data-ttu-id="9bcc6-113">Microsoft SQL Server Management Studio の オブジェクト エクスプ ローラー**データベース**、展開、 **Contoso**データベースを展開し、展開**セキュリティ**します。</span><span class="sxs-lookup"><span data-stu-id="9bcc6-113">In the Object Explorer of the Microsoft SQL Server Management Studio, expand **Databases**, expand the **Contoso** database, and then expand **Security**.</span></span> <span data-ttu-id="9bcc6-114">**[ユーザー]** を右クリックし、 **[新しいユーザー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9bcc6-114">Right-click **Users**, and then click **New User**.</span></span>  
  
2.  <span data-ttu-id="9bcc6-115">データベース ユーザー - 新規 ダイアログ ボックスでの**ログイン名**、省略記号をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9bcc6-115">In the Database User - New dialog box, for **Login name**, click the ellipsis.</span></span>  
  
3.  <span data-ttu-id="9bcc6-116">ログインの選択] ダイアログ ボックスで、[**参照**します。</span><span class="sxs-lookup"><span data-stu-id="9bcc6-116">In the Select Login dialog box, click **Browse**.</span></span>  
  
4.  <span data-ttu-id="9bcc6-117">[参照] ダイアログ ボックスのオブジェクトで選択**BizTalk Application Users**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="9bcc6-117">In the Browse for Objects dialog box, select **BizTalk Application Users**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="9bcc6-118">ログインの選択] ダイアログ ボックスで、[ **OK**します。</span><span class="sxs-lookup"><span data-stu-id="9bcc6-118">In the Select Login dialog box, click **OK**.</span></span>  
  
6.  <span data-ttu-id="9bcc6-119">データベース ユーザー - 新規 ダイアログ ボックスで、**データベース ロールのメンバーシップ**ペインで、 **db_datareader**と**db_datawriter**します。</span><span class="sxs-lookup"><span data-stu-id="9bcc6-119">In the Database User - New dialog box, in the **Database role membership** pane, select **db_datareader** and **db_datawriter**.</span></span> <span data-ttu-id="9bcc6-120">**ユーザー名**、入力**BizTalk Application Users**します。</span><span class="sxs-lookup"><span data-stu-id="9bcc6-120">For **User name**, enter **BizTalk Application Users**.</span></span> <span data-ttu-id="9bcc6-121">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9bcc6-121">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="9bcc6-122">手順 1. ~ 6. を繰り返します**BizTalk 分離ホスト ユーザー**選択**db_datareader**と**db_datawriter**の**データベース ロールのメンバーシップ**、入力と**BizTalk 分離ホスト ユーザー**の**ユーザー名**します。</span><span class="sxs-lookup"><span data-stu-id="9bcc6-122">Repeat steps 1 through 6 for **BizTalk Isolated Host Users**, selecting **db_datareader** and **db_datawriter** for **Database role membership**, and entering **BizTalk Isolated Host Users** for **User name**.</span></span>  
  
8.  <span data-ttu-id="9bcc6-123">手順 1. ~ 6. を繰り返します**BizTalk Server 管理者**選択**db_owner**の**データベース ロールのメンバーシップ**、入力と**BizTalk Server管理者**の**ユーザー名**します。</span><span class="sxs-lookup"><span data-stu-id="9bcc6-123">Repeat steps 1 through 6 for **BizTalk Server Administrators**, selecting **db_owner** for **Database role membership**, and entering **BizTalk Server Administrators** for **User name**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bcc6-124">参照</span><span class="sxs-lookup"><span data-stu-id="9bcc6-124">See Also</span></span>  
 [<span data-ttu-id="9bcc6-125">証明書の生成と有効化</span><span class="sxs-lookup"><span data-stu-id="9bcc6-125">Generating and Enabling Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/generating-and-enabling-certificates.md)