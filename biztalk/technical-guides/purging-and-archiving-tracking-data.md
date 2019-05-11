---
title: 削除とアーカイブ データの追跡 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14094fda-3fd9-4d45-9bbb-cd9377c2cbad
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f18b65d8e33a7a651d743f0ff6cd3292396189a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399559"
---
# <a name="purging-and-archiving-tracking-data"></a><span data-ttu-id="9bace-102">削除とアーカイブ データの追跡</span><span class="sxs-lookup"><span data-stu-id="9bace-102">Purging and Archiving Tracking Data</span></span>
<span data-ttu-id="9bace-103">構成して、DTA Purge and Archive SQL エージェント ジョブを有効にするのには重要です。</span><span class="sxs-lookup"><span data-stu-id="9bace-103">It is important to configure and enable the DTA Purge and Archive SQL Agent job.</span></span> <span data-ttu-id="9bace-104">このジョブをアーカイブして、BizTalk 追跡 (DTA) データベースから古いデータを削除します。</span><span class="sxs-lookup"><span data-stu-id="9bace-104">This job archives and purges old data from the BizTalk Tracking (DTA) database.</span></span> <span data-ttu-id="9bace-105">これは、正常性のために不可欠な[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]システム。</span><span class="sxs-lookup"><span data-stu-id="9bace-105">This is essential for a healthy [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system.</span></span> <span data-ttu-id="9bace-106">追跡データベースのクエリを実行すると、追跡ホストの他のプロセスのパフォーマンスに影響を与える大きな追跡データベースが開始されます。</span><span class="sxs-lookup"><span data-stu-id="9bace-106">A large Tracking database will begin to affect the performance of the tracking host and any other processes that query the Tracking database.</span></span> <span data-ttu-id="9bace-107">追跡データは追跡データベースから削除されませんが場合、データベースは拡張し続けます。</span><span class="sxs-lookup"><span data-stu-id="9bace-107">If the tracking data is not purged from the Tracking database, the database will continue to grow.</span></span>  
  
## <a name="guidelines-for-using-the-dta-purge-and-archive-job"></a><span data-ttu-id="9bace-108">DTA の使用に関するガイドラインは、Purge and Archive ジョブ</span><span class="sxs-lookup"><span data-stu-id="9bace-108">Guidelines for Using the DTA Purge and Archive Job</span></span>  
  
-   <span data-ttu-id="9bace-109">**DTA Purge and Archive SQL エージェント ジョブが適切に構成された、有効化、および正常に完了することを確認します。**</span><span class="sxs-lookup"><span data-stu-id="9bace-109">**Ensure that the DTA Purge and Archive SQL Agent job is properly configured, enabled, and successfully completing.**</span></span>  
  
     <span data-ttu-id="9bace-110">アーカイブ ファイルの書き込み先のディレクトリを含めるように構成する必要がありますまずために、このジョブは既定で有効にできません。</span><span class="sxs-lookup"><span data-stu-id="9bace-110">This job is not enabled by default because you must first configure it to include a directory where the archive files can be written.</span></span>  
  
-   <span data-ttu-id="9bace-111">**古いデータを消去しないだけの場合必要があります最初に、アーカイブし、変更、SQL エージェント ジョブ"dtasp_PurgeTrackingDatabase"ストアド プロシージャを呼び出します。**</span><span class="sxs-lookup"><span data-stu-id="9bace-111">**If you only need to purge the old data and do not need to archive it first, then change the SQL Agent job to call the stored procedure “dtasp_PurgeTrackingDatabase”.**</span></span>  
  
     <span data-ttu-id="9bace-112">これにより、アーカイブの手順をスキップし、のみ、消去を行います。</span><span class="sxs-lookup"><span data-stu-id="9bace-112">This skips the archive step, and just does the purge.</span></span> <span data-ttu-id="9bace-113">ストアド プロシージャおよびそれを使用する SQL エージェント ジョブの変更の詳細については、これはの参照[「方法にデータから、BizTalk 追跡データベースの削除」](http://go.microsoft.com/fwlink/?LinkId=153817) (http://go.microsoft.com/fwlink/?LinkId=153817)します。</span><span class="sxs-lookup"><span data-stu-id="9bace-113">For more information about this stored procedure and changing the SQL Agent job to use it, see ["How to Purge Data from the BizTalk Tracking Database"](http://go.microsoft.com/fwlink/?LinkId=153817) (http://go.microsoft.com/fwlink/?LinkId=153817).</span></span>  
  
-   <span data-ttu-id="9bace-114">**ジョブが追跡データを受信した追跡データが生成された高速消去できることを確認します。**</span><span class="sxs-lookup"><span data-stu-id="9bace-114">**Ensure that the job is able to purge the tracking data as fast as the incoming tracking data is generated.**</span></span>  
  
     <span data-ttu-id="9bace-115">ジョブの背後にあるをピーク負荷時に取得するのにもかまいませんが、遅延を解消することを必ず。</span><span class="sxs-lookup"><span data-stu-id="9bace-115">It is acceptable for the job to get behind during peak load times, but it should always be able to catch up.</span></span> <span data-ttu-id="9bace-116">Purge ジョブでは、背後にある取得し、遅延を解消することはありませんが場合、追跡データベースは引き続き拡大、およびパフォーマンスが悪影響を受ける最終的には。</span><span class="sxs-lookup"><span data-stu-id="9bace-116">If the purge job gets behind and is never able to catch up, the Tracking database will continue to grow, and performance will eventually be adversely affected.</span></span>  
  
-   <span data-ttu-id="9bace-117">**論理削除を確認し、物理最適な時間の長さのデータを保持するようにパラメーターを削除します。**</span><span class="sxs-lookup"><span data-stu-id="9bace-117">**Review the soft purge and hard purge parameters to ensure that you are keeping data for the optimal length of time.**</span></span>  
  
     <span data-ttu-id="9bace-118">これらのパラメーターの詳細については、次を参照してください。 ["アーカイブと削除、BizTalk 追跡データベース"](http://go.microsoft.com/fwlink/?LinkId=153816) (http://go.microsoft.com/fwlink/?LinkId=153816)します。</span><span class="sxs-lookup"><span data-stu-id="9bace-118">For more information about these parameters see ["Archiving and Purging the BizTalk Tracking Database"](http://go.microsoft.com/fwlink/?LinkId=153816) (http://go.microsoft.com/fwlink/?LinkId=153816).</span></span>  
  
-   <span data-ttu-id="9bace-119">**追跡を維持する必要がある場合、ファイルをアーカイブして、正常に復元し、それらを使用するためのプロセスがあることを確認します。**</span><span class="sxs-lookup"><span data-stu-id="9bace-119">**If you need to keep the tracking archive files, ensure that you have a process in place to successfully restore and use them.**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bace-120">参照</span><span class="sxs-lookup"><span data-stu-id="9bace-120">See Also</span></span>  
 [<span data-ttu-id="9bace-121">チェックリスト:SQL Server の構成</span><span class="sxs-lookup"><span data-stu-id="9bace-121">Checklist: Configuring SQL Server</span></span>](~/technical-guides/checklist-configuring-sql-server.md)