---
title: BAM を SQL Server Reporting Services と統合する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e2d66b7-c8eb-4871-8a47-544955ccd51e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3cba4a9fe610167105f9bf2b89c78f3a4b0ced0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336949"
---
# <a name="how-to-integrate-bam-with-sql-server-reporting-services"></a><span data-ttu-id="2405c-102">BAM を SQL Server Reporting Services と統合する方法</span><span class="sxs-lookup"><span data-stu-id="2405c-102">How to Integrate BAM with SQL Server Reporting Services</span></span>
<span data-ttu-id="2405c-103">レポートを作成するデータに基づく BAM インフラストラクチャの使用中の他の SQL Server データ ソースのレポートの作成に関連する一般的なタスク。</span><span class="sxs-lookup"><span data-stu-id="2405c-103">Creating a report based on data in the BAM infrastructure use the typical tasks associated with creating a report for any other SQL Server data source.</span></span> <span data-ttu-id="2405c-104">レポート デザイナーによるレポートの作成の詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=82437](http://go.microsoft.com/fwlink/?LinkId=82437)します。</span><span class="sxs-lookup"><span data-stu-id="2405c-104">For more information about creating a report with Report Designer, see [http://go.microsoft.com/fwlink/?LinkId=82437](http://go.microsoft.com/fwlink/?LinkId=82437).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2405c-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="2405c-105">Prerequisites</span></span>  
 <span data-ttu-id="2405c-106">レポートを作成するために必要なデータにアクセスするアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="2405c-106">You must have permissions to access the data necessary to create the report.</span></span>  
  
### <a name="how-to-create-a-report-in-bam-by-using-sql-server-reporting-service"></a><span data-ttu-id="2405c-107">SQL Server Reporting Service を使用して、BAM でレポートを作成する方法</span><span class="sxs-lookup"><span data-stu-id="2405c-107">How to Create a Report in BAM by Using SQL Server Reporting Service</span></span>  
  
1.  <span data-ttu-id="2405c-108">レポートの作成元となるデータ ソースを選択します。</span><span class="sxs-lookup"><span data-stu-id="2405c-108">Select the data source from which to create the report.</span></span>  
  
     <span data-ttu-id="2405c-109">BAM では、Reporting Services をポイントできます 2 つのデータ ソースを提供します。</span><span class="sxs-lookup"><span data-stu-id="2405c-109">BAM provides two data sources to which Reporting Services can point.</span></span>  
  
    |<span data-ttu-id="2405c-110">[データ ソース]</span><span class="sxs-lookup"><span data-stu-id="2405c-110">Data Source</span></span>|<span data-ttu-id="2405c-111">説明</span><span class="sxs-lookup"><span data-stu-id="2405c-111">Description</span></span>|  
    |-----------------|-----------------|  
    |<span data-ttu-id="2405c-112">BAM プライマリ インポート データベース</span><span class="sxs-lookup"><span data-stu-id="2405c-112">BAM Primary Import database</span></span>|<span data-ttu-id="2405c-113">アクティビティのインスタンスとリアルタイム集計のビューが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2405c-113">Contains views on activity instances and real-time aggregations.</span></span> <span data-ttu-id="2405c-114">種類の選択 ="Microsoft SQL Server"、Connection String ="データ ソース =\<*サーバー名*\>;Initial Catalog =\<*データベース名*\>"ここで、 \<*サーバー名*\>と\<*データベース名前*\>は、Bam プライマリ インポート データベースのサーバーとデータベースの名前です。</span><span class="sxs-lookup"><span data-stu-id="2405c-114">Select Type=”Microsoft SQL Server” and Connection String=”Data Source=\<*server name*\>; Initial Catalog=\<*database name*\>”, where \<*server name*\> and \<*database name*\> are the server and database names of your Bam Primary Import database.</span></span>|  
    |<span data-ttu-id="2405c-115">BAM 分析データベース</span><span class="sxs-lookup"><span data-stu-id="2405c-115">BAM Analysis database</span></span>|<span data-ttu-id="2405c-116">分析キューブをクエリに使用されるデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2405c-116">Contains data that is used to query the analysis cube.</span></span> <span data-ttu-id="2405c-117">種類の選択 ="Microsoft SQL Server Analysis Server"、Connection String ="データ ソース =\<*サーバー名*\>;Initial Catalog =\<*データベース名*\>"ここで、 \<*サーバー名*\>と\<*データベース名前*\>は、BAM 分析データベースのサーバーとデータベースの名前です。</span><span class="sxs-lookup"><span data-stu-id="2405c-117">Select Type=”Microsoft SQL Server Analysis Server” and Connection String=”Data Source=\<*server name*\>; Initial Catalog=\<*database name*\>”, where \<*server name*\> and \<*database name*\> are the server and database names of your BAM Analysis database.</span></span>|  
  
2.  <span data-ttu-id="2405c-118">クエリをデザインします。</span><span class="sxs-lookup"><span data-stu-id="2405c-118">Design the query.</span></span> <span data-ttu-id="2405c-119">BAM プライマリ インポート データベースの場合は、2 種類のビューがあります。</span><span class="sxs-lookup"><span data-stu-id="2405c-119">For the BAM Primary Import database, there are two types of views:</span></span>  
  
    |<span data-ttu-id="2405c-120">ビュー名</span><span class="sxs-lookup"><span data-stu-id="2405c-120">View Name</span></span>|<span data-ttu-id="2405c-121">説明</span><span class="sxs-lookup"><span data-stu-id="2405c-121">Description</span></span>|  
    |---------------|-----------------|  
    |<span data-ttu-id="2405c-122">dbo.bam_\<*ビュー名*\>_\<*アクティビティ名*\>View_View します。</span><span class="sxs-lookup"><span data-stu-id="2405c-122">dbo.bam_\<*view name*\>_\<*activity name*\>View_View.</span></span>|<span data-ttu-id="2405c-123">このビューには、インスタンス データが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2405c-123">This view contains instance data.</span></span>|  
    |<span data-ttu-id="2405c-124">dbo.bam_\<*ビュー名*\>_\<*リアルタイム集計のピボット テーブル名*\>_RTAView</span><span class="sxs-lookup"><span data-stu-id="2405c-124">dbo.bam_\<*view name*\>_\<*real time aggregation pivot table name*\>_RTAView</span></span>|<span data-ttu-id="2405c-125">このビューには、リアルタイム集計で使用されるデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2405c-125">This view contains data used in real-time aggregations.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="2405c-126">入力することができます**選択\*ビューから**を目的の結果を取得する設定。</span><span class="sxs-lookup"><span data-stu-id="2405c-126">You can type **select \* from view** to return the desired result set.</span></span> <span data-ttu-id="2405c-127">BAM 分析データベースのクエリ ビルダーをクリックし、ディメンションとキューブをという名前のメジャーをドラッグ\<*ビュー名*\>を目的の結果を取得する設定。</span><span class="sxs-lookup"><span data-stu-id="2405c-127">For the BAM Analysis database, click the query builder and drag the dimensions and measures of the cube named \<*view name*\> to return the desired result set.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="2405c-128">次の手順</span><span class="sxs-lookup"><span data-stu-id="2405c-128">Next Steps</span></span>  
 <span data-ttu-id="2405c-129">存在して、データの表示方法をするデータを指定するレポート ウィザードの手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="2405c-129">Complete the steps in the Report Wizard to specify which data you are going to present and how the data is to be presented.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2405c-130">参照</span><span class="sxs-lookup"><span data-stu-id="2405c-130">See Also</span></span>  
 [<span data-ttu-id="2405c-131">BAM データベースの管理</span><span class="sxs-lookup"><span data-stu-id="2405c-131">Managing BAM Databases</span></span>](../core/managing-bam-databases.md)