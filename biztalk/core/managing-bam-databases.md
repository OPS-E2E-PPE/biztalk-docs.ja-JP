---
title: BAM データベースの管理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [BAM], databases
- databases [BAM], managing
- databases, BAM
ms.assetid: ce3c472e-2da1-4d67-816a-befe4ded20d9
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1dbe8cdb2c7806ab62b67db80c4741d64560fba9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262578"
---
# <a name="managing-bam-databases"></a><span data-ttu-id="23381-102">BAM データベースの管理</span><span class="sxs-lookup"><span data-stu-id="23381-102">Managing BAM Databases</span></span>
<span data-ttu-id="23381-103">管理者は、BAM 管理ユーティリティ (bm.exe) を使用して、BAM データベースを設定、管理、および更新できます。</span><span class="sxs-lookup"><span data-stu-id="23381-103">Administrators use the BAM Management utility (bm.exe) to set up, manage, and update the BAM databases.</span></span> <span data-ttu-id="23381-104">このセクションでは、BAM 管理ユーティリティを使用して BAM データベースの一般的な管理者タスクを実行する方法について説明します。以下に示す表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23381-104">This section shows you how to use the BAM Management utility to perform these common administrator tasks for the BAM databases, which are described in the following table.</span></span>  
  
 <span data-ttu-id="23381-105">バックアップして、BAM データベースの復元については、次を参照してください。[をバックアップおよび復元する BAM](../core/backing-up-and-restoring-bam.md)です。</span><span class="sxs-lookup"><span data-stu-id="23381-105">For information about backing up and restoring the BAM databases, see [Backing Up and Restoring BAM](../core/backing-up-and-restoring-bam.md).</span></span>  
  
|<span data-ttu-id="23381-106">データベース</span><span class="sxs-lookup"><span data-stu-id="23381-106">Database</span></span>|<span data-ttu-id="23381-107">既定のデータベース名</span><span class="sxs-lookup"><span data-stu-id="23381-107">Default database name</span></span>|<span data-ttu-id="23381-108">Description</span><span class="sxs-lookup"><span data-stu-id="23381-108">Description</span></span>|  
|--------------|---------------------------|-----------------|  
|<span data-ttu-id="23381-109">BAM プライマリ インポート データベース</span><span class="sxs-lookup"><span data-stu-id="23381-109">BAM Primary Import database</span></span>|<span data-ttu-id="23381-110">BAMPrimaryImport</span><span class="sxs-lookup"><span data-stu-id="23381-110">BAMPrimaryImport</span></span>|<span data-ttu-id="23381-111">BAM が未処理の追跡データを収集する場所。</span><span class="sxs-lookup"><span data-stu-id="23381-111">Where BAM collects raw tracking data.</span></span>|  
|<span data-ttu-id="23381-112">BAM Notification Services アプリケーション データベース</span><span class="sxs-lookup"><span data-stu-id="23381-112">BAM Notification Services Application database</span></span>|<span data-ttu-id="23381-113">BAMAlertsApplication</span><span class="sxs-lookup"><span data-stu-id="23381-113">BAMAlertsApplication</span></span>|<span data-ttu-id="23381-114">BAM 通知に関する警告情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="23381-114">Contains alert information for BAM notifications.</span></span> <span data-ttu-id="23381-115">たとえば、BAM ポータルを使用して警告を作成すると、警告に関連する条件とイベントを指定するエントリに加え、警告に関するその他のサポート データ項目がデータベースに挿入されます。</span><span class="sxs-lookup"><span data-stu-id="23381-115">For example, when you create an alert using the BAM portal, entries are inserted in the database specifying the conditions and events to which the alert pertains, as well as other supporting data items for the alert.</span></span>|  
|<span data-ttu-id="23381-116">BAM Notification Services インスタンス データベース</span><span class="sxs-lookup"><span data-stu-id="23381-116">BAM Notification Services Instance database</span></span>|<span data-ttu-id="23381-117">BAMAlertsNSMain</span><span class="sxs-lookup"><span data-stu-id="23381-117">BAMAlertsNSMain</span></span>|<span data-ttu-id="23381-118">BAM で監視しているシステムに Notification Services が接続する方法を指定するインスタンス情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="23381-118">Contains instance information specifying how the notification services connect to the system that BAM is monitoring.</span></span>|  
|<span data-ttu-id="23381-119">BAM スター スキーマ データベース</span><span class="sxs-lookup"><span data-stu-id="23381-119">BAM Star Schema database</span></span>|<span data-ttu-id="23381-120">BAMStarSchema</span><span class="sxs-lookup"><span data-stu-id="23381-120">BAMStarSchema</span></span>|<span data-ttu-id="23381-121">段階テーブル、メジャー テーブル、およびディメンション テーブルを格納します。</span><span class="sxs-lookup"><span data-stu-id="23381-121">Contains the staging table, and the measure and dimension tables.</span></span>|  
|<span data-ttu-id="23381-122">BAM 分析データベース</span><span class="sxs-lookup"><span data-stu-id="23381-122">BAM Analysis database</span></span>|<span data-ttu-id="23381-123">BAMAnalysis</span><span class="sxs-lookup"><span data-stu-id="23381-123">BAMAnalysis</span></span>|<span data-ttu-id="23381-124">オンライン分析用およびオフライン分析用の BAM OLAP キューブを格納します。</span><span class="sxs-lookup"><span data-stu-id="23381-124">Contains BAM OLAP cubes for both online and offline analysis.</span></span>|  
|<span data-ttu-id="23381-125">BAM アーカイブ データベース</span><span class="sxs-lookup"><span data-stu-id="23381-125">BAM Archive database</span></span>|<span data-ttu-id="23381-126">BAMArchive</span><span class="sxs-lookup"><span data-stu-id="23381-126">BAMArchive</span></span>|<span data-ttu-id="23381-127">古いビジネス アクティビティ データをアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="23381-127">Archives old business activity data.</span></span> <span data-ttu-id="23381-128">BAM アーカイブ データベースを作成すると、BAM プライマリ インポート データベースにおけるビジネス アクティビティ データの蓄積を最小限に抑えることができます。</span><span class="sxs-lookup"><span data-stu-id="23381-128">You can create a BAM Archive database to minimize the accumulation of business activity data in the BAM Primary Import database.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="23381-129">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="23381-129">In This Section</span></span>  
  
-   [<span data-ttu-id="23381-130">プライマリ インポート データベースのデータのアーカイブ</span><span class="sxs-lookup"><span data-stu-id="23381-130">Archiving Primary Import Database Data</span></span>](../core/archiving-primary-import-database-data.md)  
  
-   [<span data-ttu-id="23381-131">アーカイブ データベースでパーティション分割されたビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="23381-131">Creating a Partitioned View in the Archiving Database</span></span>](../core/creating-a-partitioned-view-in-the-archiving-database.md)  
  
-   [<span data-ttu-id="23381-132">スケジュール SQL Server Integration Services パッケージ</span><span class="sxs-lookup"><span data-stu-id="23381-132">Scheduling SQL Server Integration Services Packages</span></span>](../core/scheduling-sql-server-integration-services-packages.md)  
  
-   [<span data-ttu-id="23381-133">BAM 管理ユーティリティを使用して BAM データベースを設定する方法</span><span class="sxs-lookup"><span data-stu-id="23381-133">How to Set Up the BAM Databases Using the BAM Management Utility</span></span>](../core/how-to-set-up-the-bam-databases-using-the-bam-management-utility.md)  
  
-   [<span data-ttu-id="23381-134">BAM 管理ユーティリティを使用して BAM 構成ファイルを取得する方法</span><span class="sxs-lookup"><span data-stu-id="23381-134">How to Retrieve the BAM Configuration File Using the BAM Management Utility</span></span>](../core/how-to-retrieve-the-bam-configuration-file-using-the-bam-management-utility.md)  
  
-   [<span data-ttu-id="23381-135">BAM 管理ユーティリティを使用して BAM 構成を更新する方法</span><span class="sxs-lookup"><span data-stu-id="23381-135">How to Update the BAM Configuration Using the BAM Management Utility</span></span>](../core/how-to-update-the-bam-configuration-using-the-bam-management-utility.md)  
  
-   [<span data-ttu-id="23381-136">追加の BAM プライマリ インポート データベースを参照する方法</span><span class="sxs-lookup"><span data-stu-id="23381-136">How to Reference Additional BAM Primary Import Databases</span></span>](../core/how-to-reference-additional-bam-primary-import-databases.md)  
  
-   [<span data-ttu-id="23381-137">BAM プライマリ インポート データベース参照を無効にする方法</span><span class="sxs-lookup"><span data-stu-id="23381-137">How to Disable a BAM Primary Import Database Reference</span></span>](../core/how-to-disable-a-bam-primary-import-database-reference.md)  
  
-   [<span data-ttu-id="23381-138">参照されるデータベースのすべての一覧を表示する方法</span><span class="sxs-lookup"><span data-stu-id="23381-138">How to List All Referenced Databases</span></span>](../core/how-to-list-all-referenced-databases.md)  
  
-   [<span data-ttu-id="23381-139">不完全なアクティビティ インスタンスを削除する方法</span><span class="sxs-lookup"><span data-stu-id="23381-139">How to Remove Incomplete Activity Instances</span></span>](../core/how-to-remove-incomplete-activity-instances.md)  
  
-   [<span data-ttu-id="23381-140">バックアップと復元の後に BAM 管理ユーティリティ構成を更新する方法</span><span class="sxs-lookup"><span data-stu-id="23381-140">How to Update the BAM Management Utility Configuration After a Backup and Restore</span></span>](../core/update-the-bam-management-utility-configuration-after-a-backup-and-restore.md)  
  
-   [<span data-ttu-id="23381-141">BAM を SQL Server Reporting Services と統合する方法</span><span class="sxs-lookup"><span data-stu-id="23381-141">How to Integrate BAM with SQL Server Reporting Services</span></span>](../core/how-to-integrate-bam-with-sql-server-reporting-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="23381-142">参照</span><span class="sxs-lookup"><span data-stu-id="23381-142">See Also</span></span>  
 [<span data-ttu-id="23381-143">BAM の管理</span><span class="sxs-lookup"><span data-stu-id="23381-143">Managing BAM</span></span>](../core/managing-bam.md)