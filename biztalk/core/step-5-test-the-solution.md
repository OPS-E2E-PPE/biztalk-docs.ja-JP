---
title: "手順 5: ソリューションのテスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a5ca5301-2ee4-4024-a90a-396ed681d12a
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ce7edd1c1f1f8a063e2787cc2acecb3b57cca2c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-5-test-the-solution"></a><span data-ttu-id="4b9da-102">手順 5: ソリューションをテストします。</span><span class="sxs-lookup"><span data-stu-id="4b9da-102">Step 5: Test the Solution</span></span>
<span data-ttu-id="4b9da-103">このソリューションの目的に通知を送信するプロセスを自動化する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]たびに、営業案件のステージを設定して Salesforce で新しい営業案件が閉じられた、 **Closed Won**です。</span><span class="sxs-lookup"><span data-stu-id="4b9da-103">This solution aims at automating the process of sending notifications to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], every time a new opportunity is closed in Salesforce by setting the stage of the opportunity as **Closed Won**.</span></span> <span data-ttu-id="4b9da-104">通知の受信後に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、営業案件に関連する製品詳細を取得する Salesforce にクエリを送信し、Salesforce から応答をという名前の SQL Server データベース テーブルに挿入**OrderDetails**.</span><span class="sxs-lookup"><span data-stu-id="4b9da-104">After the notification is received [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sends a query to Salesforce to retrieve product details related to the opportunity, and then inserts the response from Salesforce into a SQL Server database table called **OrderDetails**.</span></span> <span data-ttu-id="4b9da-105">そのため、このソリューションをテストするには更新に営業案件のステージ**Closed Won**結果として、関連レコードを Orders データベースの [OrderDetails] テーブルで挿入取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b9da-105">So, to test this solution, we will update the stage of an opportunity to **Closed Won** and as a result, relevant records must get inserted in the OrderDetails table in the Orders database.</span></span>  
  
### <a name="to-test-the-solution"></a><span data-ttu-id="4b9da-106">ソリューションをテストするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4b9da-106">To test the solution</span></span>  
  
1.  <span data-ttu-id="4b9da-107">Salesforce デベロッパーのログイン資格情報を使用して `https://login.salesforce.com/?lt=de` にログインします。</span><span class="sxs-lookup"><span data-stu-id="4b9da-107">Log in to `https://login.salesforce.com/?lt=de`, using the Salesforce developer login credentials.</span></span>  
  
2.  <span data-ttu-id="4b9da-108">ナビゲーション バーで、クリックして**機会**、順にクリック**顧客 1 との営業案件**です。</span><span class="sxs-lookup"><span data-stu-id="4b9da-108">In the navigation bar, click **Opportunities**, and then click **Opportunity with Customer 1**.</span></span> <span data-ttu-id="4b9da-109">この営業案件を作成した[手順 2: Salesforce システムのセットアップ](../core/step-2-set-up-the-salesforce-system.md)です。</span><span class="sxs-lookup"><span data-stu-id="4b9da-109">You had created this opportunity in [Step 2: Set up the Salesforce System](../core/step-2-set-up-the-salesforce-system.md).</span></span>  
  
3.  <span data-ttu-id="4b9da-110">**営業案件の詳細**セクションに関連付けられている製品のメモ、**製品 (標準)**セクションです。</span><span class="sxs-lookup"><span data-stu-id="4b9da-110">In the **Opportunity Detail** section, take a note of the associated products in the **Products (Standard)** section.</span></span> <span data-ttu-id="4b9da-111">このセクションにある値が最終的に SQL Server データベースに挿入されます。</span><span class="sxs-lookup"><span data-stu-id="4b9da-111">The values you under this section will finally get inserted into the SQL Server database.</span></span> <span data-ttu-id="4b9da-112">下にある、**営業案件の詳細** をクリック、**編集**ボタンをクリックしの値を変更**ステージ**フィールドを**Closed Won**です。</span><span class="sxs-lookup"><span data-stu-id="4b9da-112">Under the **Opportunity Detail** section click the **Edit** button and change the value of **Stage** field to **Closed Won**.</span></span> <span data-ttu-id="4b9da-113">**[保存]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4b9da-113">Click **Save**.</span></span>  
  
     <span data-ttu-id="4b9da-114">![既存の営業案件の編集](../core/media/bts-sf-edit-opp.jpg "BTS_SF_Edit_Opp")</span><span class="sxs-lookup"><span data-stu-id="4b9da-114">![Edit an existing opportunity](../core/media/bts-sf-edit-opp.jpg "BTS_SF_Edit_Opp")</span></span>  
  
4.  <span data-ttu-id="4b9da-115">SQL Server Management Studio でのクエリを実行、 **OrderDetails**テーブルのすべての行を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b9da-115">In SQL Server Management Studio, run a query on the **OrderDetails** table to select all rows.</span></span>  
  
     <span data-ttu-id="4b9da-116">![SQL Query 出力](../core/media/bts-sf-sql-query.jpg "BTS_SF_SQL_Query")</span><span class="sxs-lookup"><span data-stu-id="4b9da-116">![SQL Query output](../core/media/bts-sf-sql-query.jpg "BTS_SF_SQL_Query")</span></span>  
  
     <span data-ttu-id="4b9da-117">ステージを変更した営業案件に表示されていた製品の一覧が表示されることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4b9da-117">Notice that it lists the products that are listed in the opportunity for which you changed the stage.</span></span>  
  
     <span data-ttu-id="4b9da-118">![営業案件に製品を追加](../core/media/bts-sf-add-product.gif "BTS_SF_Add_Product")</span><span class="sxs-lookup"><span data-stu-id="4b9da-118">![Add products to an opportunity](../core/media/bts-sf-add-product.gif "BTS_SF_Add_Product")</span></span>  
  
 <span data-ttu-id="4b9da-119">レコードに入力したことを確認できます、 **OrderDetails**テーブルは、Salesforce での製品の指定されたセットの作成の営業案件に対応します。</span><span class="sxs-lookup"><span data-stu-id="4b9da-119">You can see that the records entered in the **OrderDetails** table correspond to the sales opportunity created in Salesforce for a given set of products.</span></span> <span data-ttu-id="4b9da-120">新しい営業案件を作成して、新しい製品を営業案件に関連付けることで、これらの手順を繰り返すことができます。</span><span class="sxs-lookup"><span data-stu-id="4b9da-120">You can repeat these steps by creating new opportunities and associating new products with the opportunity.</span></span>