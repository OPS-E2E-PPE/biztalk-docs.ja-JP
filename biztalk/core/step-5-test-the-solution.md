---
title: 手順 5:ソリューションのテスト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a5ca5301-2ee4-4024-a90a-396ed681d12a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 010fc421a6de7f2c247e39907b923ddc14089065
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244386"
---
# <a name="step-5-test-the-solution"></a><span data-ttu-id="50287-102">手順 5:ソリューションをテストします。</span><span class="sxs-lookup"><span data-stu-id="50287-102">Step 5: Test the Solution</span></span>
<span data-ttu-id="50287-103">このソリューションに通知を送信するプロセスを自動化する目的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]たびに、営業案件のステージを設定して Salesforce で新しい営業案件を閉じた、 **Closed Won**します。</span><span class="sxs-lookup"><span data-stu-id="50287-103">This solution aims at automating the process of sending notifications to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], every time a new opportunity is closed in Salesforce by setting the stage of the opportunity as **Closed Won**.</span></span> <span data-ttu-id="50287-104">通知を受け取った後[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]に関連する営業案件、製品の詳細を取得する Salesforce にクエリを送信して、Salesforce からの応答をという名前の SQL Server データベース テーブルに挿入**OrderDetails**.</span><span class="sxs-lookup"><span data-stu-id="50287-104">After the notification is received [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sends a query to Salesforce to retrieve product details related to the opportunity, and then inserts the response from Salesforce into a SQL Server database table called **OrderDetails**.</span></span> <span data-ttu-id="50287-105">そのため、このソリューションをテストするには更新する営業案件のステージ**Closed Won**結果として、関連するレコードを Orders データベースの [OrderDetails] テーブルで挿入取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50287-105">So, to test this solution, we will update the stage of an opportunity to **Closed Won** and as a result, relevant records must get inserted in the OrderDetails table in the Orders database.</span></span>  
  
### <a name="to-test-the-solution"></a><span data-ttu-id="50287-106">ソリューションをテストするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="50287-106">To test the solution</span></span>  
  
1. <span data-ttu-id="50287-107">ログイン`https://login.salesforce.com/?lt=de`、Salesforce デベロッパーのログイン資格情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="50287-107">Log in to `https://login.salesforce.com/?lt=de`, using the Salesforce developer login credentials.</span></span>  
  
2. <span data-ttu-id="50287-108">ナビゲーション バーで、クリックして**機会**、順にクリックします**顧客 1 と営業案件**します。</span><span class="sxs-lookup"><span data-stu-id="50287-108">In the navigation bar, click **Opportunities**, and then click **Opportunity with Customer 1**.</span></span> <span data-ttu-id="50287-109">この営業案件を作成していた[手順 2。Salesforce システムを設定する](../core/step-2-set-up-the-salesforce-system.md)します。</span><span class="sxs-lookup"><span data-stu-id="50287-109">You had created this opportunity in [Step 2: Set up the Salesforce System](../core/step-2-set-up-the-salesforce-system.md).</span></span>  
  
3. <span data-ttu-id="50287-110">**営業案件の詳細**セクションで、ある関連商品をメモに取ります、**製品 (Standard)** セクション。</span><span class="sxs-lookup"><span data-stu-id="50287-110">In the **Opportunity Detail** section, take a note of the associated products in the **Products (Standard)** section.</span></span> <span data-ttu-id="50287-111">このセクションの SQL Server データベースに最後に挿入が値です。</span><span class="sxs-lookup"><span data-stu-id="50287-111">The values you under this section will finally get inserted into the SQL Server database.</span></span> <span data-ttu-id="50287-112">で、**営業案件の詳細** をクリック、**編集**ボタンをクリックしの値を変更**ステージ**フィールドを**Closed Won**します。</span><span class="sxs-lookup"><span data-stu-id="50287-112">Under the **Opportunity Detail** section click the **Edit** button and change the value of **Stage** field to **Closed Won**.</span></span> <span data-ttu-id="50287-113">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="50287-113">Click **Save**.</span></span>  
  
    <span data-ttu-id="50287-114">![既存の営業案件の編集](../core/media/bts-sf-edit-opp.jpg "BTS_SF_Edit_Opp")</span><span class="sxs-lookup"><span data-stu-id="50287-114">![Edit an existing opportunity](../core/media/bts-sf-edit-opp.jpg "BTS_SF_Edit_Opp")</span></span>  
  
4. <span data-ttu-id="50287-115">SQL Server Management studio でクエリを実行、 **OrderDetails**テーブルのすべての行を選択します。</span><span class="sxs-lookup"><span data-stu-id="50287-115">In SQL Server Management Studio, run a query on the **OrderDetails** table to select all rows.</span></span>  
  
    <span data-ttu-id="50287-116">![SQL クエリの出力](../core/media/bts-sf-sql-query.jpg "BTS_SF_SQL_Query")</span><span class="sxs-lookup"><span data-stu-id="50287-116">![SQL Query output](../core/media/bts-sf-sql-query.jpg "BTS_SF_SQL_Query")</span></span>  
  
    <span data-ttu-id="50287-117">ステージを変更した営業案件に記載されている製品一覧が表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="50287-117">Notice that it lists the products that are listed in the opportunity for which you changed the stage.</span></span>  
  
    <span data-ttu-id="50287-118">![営業案件に製品を追加](../core/media/bts-sf-add-product.gif "BTS_SF_Add_Product")</span><span class="sxs-lookup"><span data-stu-id="50287-118">![Add products to an opportunity](../core/media/bts-sf-add-product.gif "BTS_SF_Add_Product")</span></span>  
  
   <span data-ttu-id="50287-119">レコードの入力を参照してください、 **OrderDetails**テーブルは、製品の指定されたセットの Salesforce で作成された営業案件に対応します。</span><span class="sxs-lookup"><span data-stu-id="50287-119">You can see that the records entered in the **OrderDetails** table correspond to the sales opportunity created in Salesforce for a given set of products.</span></span> <span data-ttu-id="50287-120">新しい営業案件を作成し、営業案件と新しい製品を関連付ける、次の手順を繰り返すことができます。</span><span class="sxs-lookup"><span data-stu-id="50287-120">You can repeat these steps by creating new opportunities and associating new products with the opportunity.</span></span>