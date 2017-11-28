---
title: "BAM を SQL Server Reporting Services と統合する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6e2d66b7-c8eb-4871-8a47-544955ccd51e
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61478bde3dd224029a6e3d6fd7c73ee84554f93e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-integrate-bam-with-sql-server-reporting-services"></a><span data-ttu-id="6243a-102">BAM と SQL Server Reporting Services を統合する方法</span><span class="sxs-lookup"><span data-stu-id="6243a-102">How to Integrate BAM with SQL Server Reporting Services</span></span>
<span data-ttu-id="6243a-103">BAM インフラストラクチャに基づいてレポートを作成するには、SQL Server の他のデータ ソース用のレポートを作成するための一般的なタスクを使用します。</span><span class="sxs-lookup"><span data-stu-id="6243a-103">Creating a report based on data in the BAM infrastructure use the typical tasks associated with creating a report for any other SQL Server data source.</span></span> <span data-ttu-id="6243a-104">レポート デザイナーによるレポートの作成の詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=82437](http://go.microsoft.com/fwlink/?LinkId=82437)です。</span><span class="sxs-lookup"><span data-stu-id="6243a-104">For more information about creating a report with Report Designer, see [http://go.microsoft.com/fwlink/?LinkId=82437](http://go.microsoft.com/fwlink/?LinkId=82437).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6243a-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="6243a-105">Prerequisites</span></span>  
 <span data-ttu-id="6243a-106">レポートの作成に必要なデータへのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="6243a-106">You must have permissions to access the data necessary to create the report.</span></span>  
  
### <a name="how-to-create-a-report-in-bam-by-using-sql-server-reporting-service"></a><span data-ttu-id="6243a-107">SQL Server Reporting Services を使用して BAM でレポートを作成する方法</span><span class="sxs-lookup"><span data-stu-id="6243a-107">How to Create a Report in BAM by Using SQL Server Reporting Service</span></span>  
  
1.  <span data-ttu-id="6243a-108">レポートを作成するデータ ソースを選択します。</span><span class="sxs-lookup"><span data-stu-id="6243a-108">Select the data source from which to create the report.</span></span>  
  
     <span data-ttu-id="6243a-109">BAM には、Reporting Services から参照可能な 2 つのデータ ソースが用意されています。</span><span class="sxs-lookup"><span data-stu-id="6243a-109">BAM provides two data sources to which Reporting Services can point.</span></span>  
  
    |<span data-ttu-id="6243a-110">[データ ソース]</span><span class="sxs-lookup"><span data-stu-id="6243a-110">Data Source</span></span>|<span data-ttu-id="6243a-111">Description</span><span class="sxs-lookup"><span data-stu-id="6243a-111">Description</span></span>|  
    |-----------------|-----------------|  
    |<span data-ttu-id="6243a-112">BAM プライマリ インポート データベース</span><span class="sxs-lookup"><span data-stu-id="6243a-112">BAM Primary Import database</span></span>|<span data-ttu-id="6243a-113">アクティビティ インスタンスとリアルタイム集計に関するビューが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6243a-113">Contains views on activity instances and real-time aggregations.</span></span> <span data-ttu-id="6243a-114">種類を選択 ="Microsoft SQL Server"、Connection String ="データ ソース =\<*サーバー名*> です。Initial Catalog =\<*データベース名*>"ここで、 \<*サーバー名*> と\<*データベース名*> は、サーバーとデータベース、Bam プライマリ インポート データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="6243a-114">Select Type=”Microsoft SQL Server” and Connection String=”Data Source=\<*server name*>; Initial Catalog=\<*database name*>”, where \<*server name*> and \<*database name*> are the server and database names of your Bam Primary Import database.</span></span>|  
    |<span data-ttu-id="6243a-115">BAM 分析データベース</span><span class="sxs-lookup"><span data-stu-id="6243a-115">BAM Analysis database</span></span>|<span data-ttu-id="6243a-116">分析キューブに対してクエリを実行するために使用するデータが格納されています。</span><span class="sxs-lookup"><span data-stu-id="6243a-116">Contains data that is used to query the analysis cube.</span></span> <span data-ttu-id="6243a-117">種類を選択 ="Microsoft SQL Server Analysis Server"、Connection String ="データ ソース =\<*サーバー名*> です。Initial Catalog =\<*データベース名*>"ここで、 \<*サーバー名*> と\<*データベース名*> は、サーバーとデータベース、BAM 分析データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="6243a-117">Select Type=”Microsoft SQL Server Analysis Server” and Connection String=”Data Source=\<*server name*>; Initial Catalog=\<*database name*>”, where \<*server name*> and \<*database name*> are the server and database names of your BAM Analysis database.</span></span>|  
  
2.  <span data-ttu-id="6243a-118">クエリをデザインします。</span><span class="sxs-lookup"><span data-stu-id="6243a-118">Design the query.</span></span> <span data-ttu-id="6243a-119">BAM プライマリ インポート データベースでは、2 種類のビューがあります。</span><span class="sxs-lookup"><span data-stu-id="6243a-119">For the BAM Primary Import database, there are two types of views:</span></span>  
  
    |<span data-ttu-id="6243a-120">ビュー名</span><span class="sxs-lookup"><span data-stu-id="6243a-120">View Name</span></span>|<span data-ttu-id="6243a-121">Description</span><span class="sxs-lookup"><span data-stu-id="6243a-121">Description</span></span>|  
    |---------------|-----------------|  
    |<span data-ttu-id="6243a-122">dbo.bam_\<*ビュー名*> _\<*アクティビティ名*> View_View です。</span><span class="sxs-lookup"><span data-stu-id="6243a-122">dbo.bam_\<*view name*>_\<*activity name*>View_View.</span></span>|<span data-ttu-id="6243a-123">このビューにはインスタンス データが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6243a-123">This view contains instance data.</span></span>|  
    |<span data-ttu-id="6243a-124">dbo.bam_\<*ビュー名*> _\<*リアルタイム集計のピボット テーブル名*> _RTAView</span><span class="sxs-lookup"><span data-stu-id="6243a-124">dbo.bam_\<*view name*>_\<*real time aggregation pivot table name*>_RTAView</span></span>|<span data-ttu-id="6243a-125">このビューには、リアルタイム集計で使用するデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6243a-125">This view contains data used in real-time aggregations.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="6243a-126">入力することができます**選択\*ビューから**を目的の結果を返すに設定します。</span><span class="sxs-lookup"><span data-stu-id="6243a-126">You can type **select \* from view** to return the desired result set.</span></span> <span data-ttu-id="6243a-127">BAM 分析データベースのクエリ ビルダー をクリックし、ディメンションとキューブをという名前のメジャーをドラッグして\<*ビュー名*> を目的の結果を返すに設定します。</span><span class="sxs-lookup"><span data-stu-id="6243a-127">For the BAM Analysis database, click the query builder and drag the dimensions and measures of the cube named \<*view name*> to return the desired result set.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="6243a-128">次の手順</span><span class="sxs-lookup"><span data-stu-id="6243a-128">Next Steps</span></span>  
 <span data-ttu-id="6243a-129">レポート ウィザードの手順を実行して、表示するデータとそのデータの表示方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="6243a-129">Complete the steps in the Report Wizard to specify which data you are going to present and how the data is to be presented.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6243a-130">参照</span><span class="sxs-lookup"><span data-stu-id="6243a-130">See Also</span></span>  
 [<span data-ttu-id="6243a-131">BAM データベースの管理</span><span class="sxs-lookup"><span data-stu-id="6243a-131">Managing BAM Databases</span></span>](../core/managing-bam-databases.md)