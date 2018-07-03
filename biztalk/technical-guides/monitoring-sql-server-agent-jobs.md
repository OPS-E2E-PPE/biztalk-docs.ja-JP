---
title: SQL Server エージェント ジョブの監視 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 60d0a377-c86d-429b-9e48-c37bd5b0f912
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6fb4026b95a5f368c265b49425ab1d3e1ec776cd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015393"
---
# <a name="monitoring-sql-server-agent-jobs"></a><span data-ttu-id="e3260-102">SQL Server エージェント ジョブの監視</span><span class="sxs-lookup"><span data-stu-id="e3260-102">Monitoring SQL Server Agent Jobs</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="e3260-103"> には、サーバーの動作状況と状態を維持するための重要な機能を実行する複数の SQL Server エージェント ジョブが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e3260-103"> includes multiple SQL Server Agent jobs that perform important functions to keep your servers operational and healthy.</span></span> <span data-ttu-id="e3260-104">これらのジョブの状態を監視し、エラーが発生せずに動作していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3260-104">You should monitor the health of these jobs and ensure that they are running without errors.</span></span>  

## <a name="guidelines-for-monitoring-the-sql-server-agent-jobs"></a><span data-ttu-id="e3260-105">SQL Server エージェントのジョブを監視するためのガイドライン</span><span class="sxs-lookup"><span data-stu-id="e3260-105">Guidelines for Monitoring the SQL Server Agent Jobs</span></span>  
 <span data-ttu-id="e3260-106">ジョブを監視するためのガイドラインを次に示します。</span><span class="sxs-lookup"><span data-stu-id="e3260-106">Following are guidelines for monitoring the jobs:</span></span>  

- <span data-ttu-id="e3260-107">**SQL Server エージェント サービスが実行されていることを確認します。**</span><span class="sxs-lookup"><span data-stu-id="e3260-107">**Verify that the SQL Server Agent service is running**</span></span>  

- <span data-ttu-id="e3260-108">**BizTalk Server によってインストールされる SQL Server エージェント ジョブが実行されていて正常に確認します**</span><span class="sxs-lookup"><span data-stu-id="e3260-108">**Verify that the SQL Server Agent jobs installed by BizTalk Server are enabled and running successfully**</span></span>  

   <span data-ttu-id="e3260-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SQL Server エージェント ジョブが非常に重要です。 時間の経過と共に実行されていない場合、システムのパフォーマンスが低下します。</span><span class="sxs-lookup"><span data-stu-id="e3260-109">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SQL Server Agent jobs are crucial: if they are not running, system performance will degrade over time.</span></span>  

- <span data-ttu-id="e3260-110">**適切なタイミングで、BizTalk Server SQL Server エージェント ジョブが完了することを確認します。**</span><span class="sxs-lookup"><span data-stu-id="e3260-110">**Verify that the BizTalk Server SQL Server Agent jobs are completing in a timely manner**</span></span>  

   <span data-ttu-id="e3260-111">Microsoft System Center Operations Manager を設定すると、ジョブを監視します。</span><span class="sxs-lookup"><span data-stu-id="e3260-111">Set up Microsoft System Center Operations Manager to monitor the jobs.</span></span>  

   <span data-ttu-id="e3260-112">特定のジョブを特定のスケジュールの注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3260-112">You should be aware of schedules that are particular to certain jobs:</span></span>  

  -   <span data-ttu-id="e3260-113">既定では、MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb ジョブが継続的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="e3260-113">The MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb job runs continuously by default.</span></span> <span data-ttu-id="e3260-114">ソフトウェアを監視、このスケジュールを考慮に入れてし、警告を生成しない必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3260-114">Monitoring software should take this schedule into account and not produce warnings.</span></span>  

  -   <span data-ttu-id="e3260-115">MessageBox_Message_Cleanup_BizTalkMsgBoxDb ジョブは有効、またはスケジュール設定をされませんが、10 秒ごと、MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb ジョブによって起動されました。</span><span class="sxs-lookup"><span data-stu-id="e3260-115">The MessageBox_Message_Cleanup_BizTalkMsgBoxDb job is not enabled or scheduled, but it is started by the MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb job every 10 seconds.</span></span> <span data-ttu-id="e3260-116">そのため、このジョブする必要がありますいない有効、スケジュールまたは手動で開始されました。</span><span class="sxs-lookup"><span data-stu-id="e3260-116">Therefore, this job should not be enabled, scheduled, or manually started.</span></span>  

- <span data-ttu-id="e3260-117">**SQL Server エージェント サービスのスタートアップの種類が正しく構成されていることを確認します。**</span><span class="sxs-lookup"><span data-stu-id="e3260-117">**Verify that the Startup type of the SQL Server Agent service is configured correctly**</span></span>  

   <span data-ttu-id="e3260-118">SQL Server エージェント サービスが構成されていることを確認、**のスタートアップの種類**の**自動**SQL Server エージェント サービスが Windows Server クラスターでクラスター リソースとして構成されていない場合。</span><span class="sxs-lookup"><span data-stu-id="e3260-118">Verify that the SQL Server Agent service is configured with a **Startuptype** of **Automatic** unless the SQL Server Agent service is configured as a cluster resource on a Windows Server cluster.</span></span> <span data-ttu-id="e3260-119">SQL Server エージェント サービスがクラスター リソースとして構成されているかどうかは、構成する必要があります、 **Startuptype**として**手動**サービスは、クラスター サービスによって管理されるためです。</span><span class="sxs-lookup"><span data-stu-id="e3260-119">If the SQL Server Agent service is configured as a cluster resource, then you should configure the **Startuptype** as **Manual** since the service will be managed by the Cluster service.</span></span>  

## <a name="additional-resources"></a><span data-ttu-id="e3260-120">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="e3260-120">Additional Resources</span></span>  

- <span data-ttu-id="e3260-121">監視の詳細については、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SQL エージェント ジョブ, を参照してください[SQL Server エージェント ジョブの監視とデータベース](../technical-guides/monitoring-sql-server-agent-jobs-and-databases.md)します。</span><span class="sxs-lookup"><span data-stu-id="e3260-121">For more information about monitoring the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SQL Agent jobs, see [Monitoring SQL Server Agent Jobs and Databases](../technical-guides/monitoring-sql-server-agent-jobs-and-databases.md).</span></span>  

- <span data-ttu-id="e3260-122">含まれている SQL Server エージェント ジョブの詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[「データベースの構造とジョブ」](http://go.microsoft.com/fwlink/?LinkID=153451) (<http://go.microsoft.com/fwlink/?LinkID=153451>)。</span><span class="sxs-lookup"><span data-stu-id="e3260-122">For more information about the SQL Server Agent jobs that are included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] see ["Database Structure and Jobs"](http://go.microsoft.com/fwlink/?LinkID=153451) (<http://go.microsoft.com/fwlink/?LinkID=153451>).</span></span>
