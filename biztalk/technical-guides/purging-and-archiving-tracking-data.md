---
title: 消去および追跡データをアーカイブ |Microsoft ドキュメント
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
ms.openlocfilehash: 94a2560bc8a57a8f60bf2d1ebcddf68b62fd178a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302938"
---
# <a name="purging-and-archiving-tracking-data"></a><span data-ttu-id="14df3-102">消去および追跡データをアーカイブ</span><span class="sxs-lookup"><span data-stu-id="14df3-102">Purging and Archiving Tracking Data</span></span>
<span data-ttu-id="14df3-103">構成し、DTA Purge and Archive SQL エージェント ジョブを有効にするには重要です。</span><span class="sxs-lookup"><span data-stu-id="14df3-103">It is important to configure and enable the DTA Purge and Archive SQL Agent job.</span></span> <span data-ttu-id="14df3-104">このジョブをアーカイブして、BizTalk 追跡 (DTA) データベースから古いデータを削除します。</span><span class="sxs-lookup"><span data-stu-id="14df3-104">This job archives and purges old data from the BizTalk Tracking (DTA) database.</span></span> <span data-ttu-id="14df3-105">これは、正常なために不可欠な[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]システムです。</span><span class="sxs-lookup"><span data-stu-id="14df3-105">This is essential for a healthy [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system.</span></span> <span data-ttu-id="14df3-106">追跡データベースを照会する追跡ホストおよびその他のすべてのプロセスのパフォーマンスに影響を与える大きな追跡データベースが開始されます。</span><span class="sxs-lookup"><span data-stu-id="14df3-106">A large Tracking database will begin to affect the performance of the tracking host and any other processes that query the Tracking database.</span></span> <span data-ttu-id="14df3-107">追跡データは追跡データベースから削除されませんが場合、データベースが拡大し続けます。</span><span class="sxs-lookup"><span data-stu-id="14df3-107">If the tracking data is not purged from the Tracking database, the database will continue to grow.</span></span>  
  
## <a name="guidelines-for-using-the-dta-purge-and-archive-job"></a><span data-ttu-id="14df3-108">DTA の使用に関するガイドライン Purge and Archive ジョブ</span><span class="sxs-lookup"><span data-stu-id="14df3-108">Guidelines for Using the DTA Purge and Archive Job</span></span>  
  
-   <span data-ttu-id="14df3-109">**DTA Purge and Archive SQL エージェント ジョブが適切に構成された、有効であり、正常に完了することを確認します。**</span><span class="sxs-lookup"><span data-stu-id="14df3-109">**Ensure that the DTA Purge and Archive SQL Agent job is properly configured, enabled, and successfully completing.**</span></span>  
  
     <span data-ttu-id="14df3-110">アーカイブ ファイルの書き込み先ディレクトリを含めるようにを構成する必要がありますまずために、このジョブは既定で有効にできません。</span><span class="sxs-lookup"><span data-stu-id="14df3-110">This job is not enabled by default because you must first configure it to include a directory where the archive files can be written.</span></span>  
  
-   <span data-ttu-id="14df3-111">**だけ古いデータを削除しないようにする必要がある場合必要があります、最初に、アーカイブし、SQL を変更するエージェント ジョブの"dtasp_PurgeTrackingDatabase"ストアド プロシージャを呼び出します。**</span><span class="sxs-lookup"><span data-stu-id="14df3-111">**If you only need to purge the old data and do not need to archive it first, then change the SQL Agent job to call the stored procedure “dtasp_PurgeTrackingDatabase”.**</span></span>  
  
     <span data-ttu-id="14df3-112">これは、アーカイブ手順をスキップし、実行するだけで、パージします。</span><span class="sxs-lookup"><span data-stu-id="14df3-112">This skips the archive step, and just does the purge.</span></span> <span data-ttu-id="14df3-113">詳細については、このストアド プロシージャと、使用する SQL エージェント ジョブを変更するを参照してください[「どのようにパージ データから BizTalk 追跡データベースへ」](http://go.microsoft.com/fwlink/?LinkId=153817) (http://go.microsoft.com/fwlink/?LinkId=153817)。</span><span class="sxs-lookup"><span data-stu-id="14df3-113">For more information about this stored procedure and changing the SQL Agent job to use it, see ["How to Purge Data from the BizTalk Tracking Database"](http://go.microsoft.com/fwlink/?LinkId=153817) (http://go.microsoft.com/fwlink/?LinkId=153817).</span></span>  
  
-   <span data-ttu-id="14df3-114">**ジョブが、受信追跡データが生成された高速の追跡データが削除できることを確認します。**</span><span class="sxs-lookup"><span data-stu-id="14df3-114">**Ensure that the job is able to purge the tracking data as fast as the incoming tracking data is generated.**</span></span>  
  
     <span data-ttu-id="14df3-115">ピーク負荷時の背後に取得するジョブもかまわないが遅れを取り戻すことが常になります。</span><span class="sxs-lookup"><span data-stu-id="14df3-115">It is acceptable for the job to get behind during peak load times, but it should always be able to catch up.</span></span> <span data-ttu-id="14df3-116">Purge ジョブでは、背後にあるを取得し、遅延を解消することはありません場合に増加し、追跡データベースは引き続き、パフォーマンスが悪影響を受ける最終的には</span><span class="sxs-lookup"><span data-stu-id="14df3-116">If the purge job gets behind and is never able to catch up, the Tracking database will continue to grow, and performance will eventually be adversely affected.</span></span>  
  
-   <span data-ttu-id="14df3-117">**論理削除を確認し、物理最適な時間の長さのデータを保持している場合のようにパラメーターを削除します。**</span><span class="sxs-lookup"><span data-stu-id="14df3-117">**Review the soft purge and hard purge parameters to ensure that you are keeping data for the optimal length of time.**</span></span>  
  
     <span data-ttu-id="14df3-118">これらのパラメーターの詳細については、次を参照してください。 ["アーカイブと削除、BizTalk 追跡データベース"](http://go.microsoft.com/fwlink/?LinkId=153816) (http://go.microsoft.com/fwlink/?LinkId=153816)。</span><span class="sxs-lookup"><span data-stu-id="14df3-118">For more information about these parameters see ["Archiving and Purging the BizTalk Tracking Database"](http://go.microsoft.com/fwlink/?LinkId=153816) (http://go.microsoft.com/fwlink/?LinkId=153816).</span></span>  
  
-   <span data-ttu-id="14df3-119">**追跡を保持する必要がある場合、ファイルをアーカイブして、正常に復元し、それらを使用するためのプロセスがあることを確認します。**</span><span class="sxs-lookup"><span data-stu-id="14df3-119">**If you need to keep the tracking archive files, ensure that you have a process in place to successfully restore and use them.**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14df3-120">参照</span><span class="sxs-lookup"><span data-stu-id="14df3-120">See Also</span></span>  
 [<span data-ttu-id="14df3-121">チェックリスト: SQL Server を構成します。</span><span class="sxs-lookup"><span data-stu-id="14df3-121">Checklist: Configuring SQL Server</span></span>](~/technical-guides/checklist-configuring-sql-server.md)