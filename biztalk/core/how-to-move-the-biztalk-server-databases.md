---
title: BizTalk Server データベースを移動 |Microsoft ドキュメント
description: BizTalk Server データベースを含むサービスを停止して、SQL Server エージェント ジョブを使用して、新しいサーバーに移動する手順
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec302e6d-c89d-4fe7-849f-97b5566e8ba4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12bd1d6bc8a46d4e63dc69166d87f3678a0e3272
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254178"
---
# <a name="how-to-move-the-biztalk-server-databases"></a><span data-ttu-id="0bef2-103">BizTalk Server データベースを移動する方法</span><span class="sxs-lookup"><span data-stu-id="0bef2-103">How to Move the BizTalk Server Databases</span></span>

## <a name="overview"></a><span data-ttu-id="0bef2-104">概要</span><span class="sxs-lookup"><span data-stu-id="0bef2-104">Overview</span></span>
<span data-ttu-id="0bef2-105">ここでは、プライマリ [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースを他のサーバーに移動する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="0bef2-105">You can use this procedure to move the primary [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases to another server.</span></span> <span data-ttu-id="0bef2-106">これと同じ基本的な手順を使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースを、ローカルの [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] からリモートの [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] または [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] クラスターに移動することもできます。</span><span class="sxs-lookup"><span data-stu-id="0bef2-106">This same basic procedure can also be used to move the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases from a local [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] to a remote [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] or to a [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] cluster.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="0bef2-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="0bef2-107">Prerequisites</span></span>  
<span data-ttu-id="0bef2-108">メンバーであるアカウントでサインイン、 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin 固定サーバー ロールにこの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0bef2-108">Sign in with an account that is a member of the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin fixed server role to perform this procedure.</span></span>  
  
## <a name="move-steps"></a><span data-ttu-id="0bef2-109">手順を移動します。</span><span class="sxs-lookup"><span data-stu-id="0bef2-109">Move steps</span></span>
  
1.  <span data-ttu-id="0bef2-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] サービスをすべて停止します。</span><span class="sxs-lookup"><span data-stu-id="0bef2-110">Stop all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services.</span></span> <span data-ttu-id="0bef2-111">詳細については、次を参照してください。 [BizTalk Server サービスの再起動とシャット ダウンの BizTalk Server](how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md)です。</span><span class="sxs-lookup"><span data-stu-id="0bef2-111">For more information, see [Restart BizTalk Server Services, and shut down BizTalk Server](how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md).</span></span>
  
    > [!IMPORTANT]
    >  <span data-ttu-id="0bef2-112">データベースを移動する前に、すべての [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] サービスおよびジョブが停止していることを必ず確認してください。</span><span class="sxs-lookup"><span data-stu-id="0bef2-112">It is critical to make sure that all the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services and jobs are stopped before you move the databases.</span></span>  
  
2.  <span data-ttu-id="0bef2-113">IIS サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="0bef2-113">Stop the IIS service.</span></span>  
  
3.  <span data-ttu-id="0bef2-114">SQL Server エージェント サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="0bef2-114">Stop the SQL Server Agent service.</span></span>  
  
4.  <span data-ttu-id="0bef2-115">」の説明に従って、データベース バックアップの手順に従って、BizTalk データベースをバックアップ[をバックアップおよび BizTalk Server データベースの復元](../core/backing-up-and-restoring-the-biztalk-server-databases.md)です。</span><span class="sxs-lookup"><span data-stu-id="0bef2-115">Back up the BizTalk databases by following the database backup procedures as described at [Backing Up and Restoring the BizTalk Server Databases](../core/backing-up-and-restoring-the-biztalk-server-databases.md).</span></span>  
  
5.  <span data-ttu-id="0bef2-116">新しいサーバーで、次のデータベース、BizTalk データベースの復元時にプロシージャ復元[、データベースを復元する方法](../core/how-to-restore-your-databases.md)です。</span><span class="sxs-lookup"><span data-stu-id="0bef2-116">Restore the BizTalk databases on the new server following the database restore procedures at [How to Restore Your Databases](../core/how-to-restore-your-databases.md).</span></span>  
  
6.  <span data-ttu-id="0bef2-117">SQL Server エージェント ジョブは、以下に示す、新しいサーバーに転送するための説明に従ってスクリプト[Back Up and SQL エージェント ジョブを復元する方法](../core/how-to-back-up-and-restore-sql-agent-jobs.md)です。</span><span class="sxs-lookup"><span data-stu-id="0bef2-117">Script the SQL Server Agent jobs listed below for transfer to the new server, as described at [How to Back Up and Restore SQL Agent Jobs](../core/how-to-back-up-and-restore-sql-agent-jobs.md).</span></span>  <span data-ttu-id="0bef2-118">それぞれのスクリプトを新しいサーバーで実行してジョブを再作成します。</span><span class="sxs-lookup"><span data-stu-id="0bef2-118">Run each of the scripts on the new server to recreate the jobs.</span></span>  
  
     <span data-ttu-id="0bef2-119">それぞれのスクリプトを新しいサーバーで実行してジョブを再作成します。</span><span class="sxs-lookup"><span data-stu-id="0bef2-119">Run each of the scripts on the new server to recreate the jobs.</span></span> <span data-ttu-id="0bef2-120">などの特定のジョブ、 **BizTalk Server のバックアップ (BizTalkMsgBoxDb)** ジョブに、新しいサーバーのファイル パスとサーバー名は、古いサーバーと同じ場合を除き、再構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0bef2-120">Certain jobs, such as the **Backup BizTalk Server (BizTalkMsgBoxDb)** job, will have to be reconfigured unless the new server file paths and server name are identical to the old server.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0bef2-121">SSIS または DTS を使用することもできます。**ジョブ転送**タスクは、新しいサーバーにジョブを移動するが、ほとんどのユーザーはおそらくほうが簡単な SQL Management Studio を使用してジョブのスクリプトを作成します。</span><span class="sxs-lookup"><span data-stu-id="0bef2-121">You can also use the SSIS/DTS **Transfer Jobs** task to move the jobs to the new server, but most users will probably find it easier to script the jobs using SQL Management Studio.</span></span>  
  
7.  <span data-ttu-id="0bef2-122">SQL Server エージェント ジョブのスクリプトを作成して、前の手順」の説明に従って、に加えてする必要がありますログインもスクリプト」の説明に従って[Back Up and SQL Server ログインを復元する方法](../core/how-to-back-up-and-restore-sql-server-logins.md)です。</span><span class="sxs-lookup"><span data-stu-id="0bef2-122">In addition to scripting SQL Server Agent jobs as described in the previous step, you must also script logins as described in [How to Back Up and Restore SQL Server Logins](../core/how-to-back-up-and-restore-sql-server-logins.md).</span></span> <span data-ttu-id="0bef2-123">これらのログインは、移動先のサーバーに復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0bef2-123">These logins need to be restored on the destination server.</span></span>  
  
8.  <span data-ttu-id="0bef2-124">復元、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースを次の手順 9. ~ 22. [、データベースを復元する方法](../core/how-to-restore-your-databases.md)です。</span><span class="sxs-lookup"><span data-stu-id="0bef2-124">Restore the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases by following steps 9 through 22 in [How to Restore Your Databases](../core/how-to-restore-your-databases.md).</span></span> <span data-ttu-id="0bef2-125">この手順によって BizTalk 管理 (BizTalkMgmtDb) データベースおよびレジストリが更新され、BizTalk データベースの新しい場所が反映されます。</span><span class="sxs-lookup"><span data-stu-id="0bef2-125">This procedure updates the BizTalk Management (BizTalkMgmtDb) database and registry with the new location of the BizTalk databases.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0bef2-126">**SampleUpdateInfo.xml**ファイルをすべてコメント アウトを除き、データベースの新しいサーバーに移動されました。</span><span class="sxs-lookup"><span data-stu-id="0bef2-126">In the **SampleUpdateInfo.xml** file, comment out all of the databases except for those you have moved to the new server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bef2-127">参照</span><span class="sxs-lookup"><span data-stu-id="0bef2-127">See Also</span></span>  
 [<span data-ttu-id="0bef2-128">BizTalk Server データベースの移動</span><span class="sxs-lookup"><span data-stu-id="0bef2-128">Moving BizTalk Server Databases</span></span>](../core/moving-biztalk-server-databases.md)