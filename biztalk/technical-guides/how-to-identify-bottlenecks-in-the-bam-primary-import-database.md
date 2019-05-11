---
title: BAM プライマリ インポート データベースのボトルネックを特定する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0372f1f1-d892-4f7d-b6c4-e0f2b5a02f1c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 541e5bcce9420fdbca8af25de9bee24bfb607435
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65253470"
---
# <a name="how-to-identify-bottlenecks-in-the-bam-primary-import-database"></a><span data-ttu-id="a6c39-102">BAM プライマリ インポート データベースのボトルネックを特定する方法</span><span class="sxs-lookup"><span data-stu-id="a6c39-102">How to Identify Bottlenecks in the BAM Primary Import Database</span></span>
<span data-ttu-id="a6c39-103">ビジネス アクティビティ監視 (BAM) データベースのボトルネックを識別するために、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="a6c39-103">To identify bottlenecks in the Business Activity Monitoring (BAM) database, perform the following steps:</span></span>  
  
1. <span data-ttu-id="a6c39-104">アクティブ インスタンス数が増えていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="a6c39-104">Ensure that the Active Instances count is not climbing.</span></span>  
  
2. <span data-ttu-id="a6c39-105">SQL エージェント サービスが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a6c39-105">Ensure that the SQL-Agent Service is running.</span></span>  
  
3. <span data-ttu-id="a6c39-106">OLAP 分析が構成されている場合ことを確認、bam_an _\<activityname\>ジョブが定期的に実行します。</span><span class="sxs-lookup"><span data-stu-id="a6c39-106">If OLAP Analysis is configured, ensure that the BAM_AN_\<activityname\> job is running at periodic intervals.</span></span>  
  
4. <span data-ttu-id="a6c39-107">確認する bam_dm _\<activityname\>定期的な間隔で実行する (データ管理) ジョブがスケジュールされています。</span><span class="sxs-lookup"><span data-stu-id="a6c39-107">Ensure that BAM_DM_\<activityname\> (Data Maintenance) job is scheduled to run at periodic intervals.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="a6c39-108">使用率が高いシナリオの BAM データベースのアクティビティは、BizTalk サーバー全体のパフォーマンスに影響を与える他の BizTalk Server データベースのパフォーマンスが影響します。</span><span class="sxs-lookup"><span data-stu-id="a6c39-108">In high usage scenarios BAM database activity can impact the performance of other BizTalk Server databases, which will affect overall BizTalk Server performance.</span></span> <span data-ttu-id="a6c39-109">ここで、次の操作を検討してください。</span><span class="sxs-lookup"><span data-stu-id="a6c39-109">In this case consider taking the following actions:</span></span>  
   > 
   > - <span data-ttu-id="a6c39-110">1 か月を以下に既定値 (6 か月) からのすべての BAM アクティビティの実行時間の短縮を検討します。</span><span class="sxs-lookup"><span data-stu-id="a6c39-110">Consider decreasing the duration of all BAM activities from the default value (6 months) to 1 month or less.</span></span> <span data-ttu-id="a6c39-111">これにより、対象は、BAMPrimaryImport データベースに BAM データを保持アーカイブされる前に期間が低減されます。</span><span class="sxs-lookup"><span data-stu-id="a6c39-111">This will reduce the time period for which BAM data is maintained in the BAMPrimaryImport database before being archived.</span></span> <span data-ttu-id="a6c39-112">BAM 管理ユーティリティを使用して`set-activitywindow`BAM アクティビティの期間を変更するコマンド。</span><span class="sxs-lookup"><span data-stu-id="a6c39-112">Use the BAM Management Utility `set-activitywindow` command to modify the duration of BAM activities.</span></span> <span data-ttu-id="a6c39-113">コマンドを参照してください、BAM 管理ユーティリティの活動管理の詳細については[アクティビティ管理コマンド](http://go.microsoft.com/fwlink/?LinkId=210417)(http://go.microsoft.com/fwlink/?LinkId=210417)します。</span><span class="sxs-lookup"><span data-stu-id="a6c39-113">For more information about the BAM Management Utility activity management commands see [Activity Management Commands](http://go.microsoft.com/fwlink/?LinkId=210417) (http://go.microsoft.com/fwlink/?LinkId=210417).</span></span>  
   >   -   <span data-ttu-id="a6c39-114">すべての BizTalk メッセージ ボックス データベースをホストしていない SQL Server のインスタンスには、BAM アーカイブ データベースを移動します。</span><span class="sxs-lookup"><span data-stu-id="a6c39-114">Move the BAM Archive database to an instance of SQL Server that does not host any BizTalk MessageBox databases.</span></span> <span data-ttu-id="a6c39-115">これらのデータベースがリソースの競合を防ぐを全体的なパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="a6c39-115">This will prevent these databases from competing for resources and improve overall performance.</span></span>  
  
5. <span data-ttu-id="a6c39-116">追跡専用のホストに使用し、負荷の下にある場合、Host Queue Length パフォーマンス カウンターを測定します。</span><span class="sxs-lookup"><span data-stu-id="a6c39-116">Use a dedicated host for tracking and measure the Host Queue Length performance counter when under load.</span></span>  
  
6. <span data-ttu-id="a6c39-117">時間の経過と共に、スプール テーブルのサイズのパフォーマンス カウンターを増加傾向を確認します。</span><span class="sxs-lookup"><span data-stu-id="a6c39-117">Check the Spool Table size performance counter for an increasing trend over time.</span></span>  
  
7. <span data-ttu-id="a6c39-118">Archive/purge ジョブの実行時間の長い実行時間を確認します。</span><span class="sxs-lookup"><span data-stu-id="a6c39-118">Check the Archive/Purge job execution duration for long execution times.</span></span>  
  
8. <span data-ttu-id="a6c39-119">BizTalk 追跡データベースをホストしているディスク上のディスク (ディスク秒数パフォーマンス カウンタの読み取り/書き込み) の応答性を確認します。</span><span class="sxs-lookup"><span data-stu-id="a6c39-119">Check disk responsiveness (Disk Seconds per Read/Write performance counter) on the disk hosting the BizTalk Tracking database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6c39-120">参照</span><span class="sxs-lookup"><span data-stu-id="a6c39-120">See Also</span></span>  
 [<span data-ttu-id="a6c39-121">データベース層のボトルネック</span><span class="sxs-lookup"><span data-stu-id="a6c39-121">Bottlenecks in the Database Tier</span></span>](../technical-guides/bottlenecks-in-the-database-tier.md)