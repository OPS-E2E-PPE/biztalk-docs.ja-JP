---
title: "管理メンテナンス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 67cdf9d7-5448-40c5-8c5f-eae0e281d22c
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed53236352831d3ae920263d57b89ed4789be0ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="administrative-maintenance"></a><span data-ttu-id="36c61-102">管理用のメンテナンス</span><span class="sxs-lookup"><span data-stu-id="36c61-102">Administrative Maintenance</span></span>
<span data-ttu-id="36c61-103">このセクションでの管理に関する問題を解決する方法に関する情報を提供する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]システムです。</span><span class="sxs-lookup"><span data-stu-id="36c61-103">This section provides information about how you can resolve administration issues with a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system.</span></span> <span data-ttu-id="36c61-104">実行される定期的なメンテナンス チェックでこれらの問題を検出する可能性があります、[ルーチン メンテナンス チェックリスト](../technical-guides/routine-maintenance-checklists.md)セクションです。</span><span class="sxs-lookup"><span data-stu-id="36c61-104">These issues may be discovered by the routine maintenance checks that are performed in the [Routine Maintenance Checklists](../technical-guides/routine-maintenance-checklists.md) section.</span></span>  
  
 <span data-ttu-id="36c61-105">このセクションのトピック、に加えては、このドキュメントでは、その他のトピックは、管理の問題を解決します。</span><span class="sxs-lookup"><span data-stu-id="36c61-105">In addition to the topics in this section, other topics in this document address administration issues.</span></span> <span data-ttu-id="36c61-106">これらのトピックは、関連するセクションの下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="36c61-106">These topics are listed in Related Sections below.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="36c61-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="36c61-107">In This Section</span></span>  
  
-   [<span data-ttu-id="36c61-108">管理用のメンテナンスのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="36c61-108">Best Practices for Administrative Maintenance</span></span>](../technical-guides/best-practices-for-administrative-maintenance.md)  
  
-   [<span data-ttu-id="36c61-109">SQL Server エージェントを開始する方法</span><span class="sxs-lookup"><span data-stu-id="36c61-109">How to Start the SQL Server Agent</span></span>](../technical-guides/how-to-start-the-sql-server-agent.md)  
  
-   [<span data-ttu-id="36c61-110">バックアップの BizTalk Server のジョブをスケジュールする方法</span><span class="sxs-lookup"><span data-stu-id="36c61-110">How to Schedule a Backup BizTalk Server Job</span></span>](../technical-guides/how-to-schedule-a-backup-biztalk-server-job.md)  
  
-   [<span data-ttu-id="36c61-111">バックアップの BizTalk Server ジョブを構成する方法</span><span class="sxs-lookup"><span data-stu-id="36c61-111">How to Configure a Backup BizTalk Server Job</span></span>](../technical-guides/how-to-configure-a-backup-biztalk-server-job.md)  
  
## <a name="related-sections"></a><span data-ttu-id="36c61-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="36c61-112">Related Sections</span></span>  
  
-   <span data-ttu-id="36c61-113">確認する方法について、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]でエージェント サービスが実行されている、 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]、SQL Server ジョブが正常に動作しているすべての BizTalk に関連することを確認を参照してください、 [SQL Server エージェント ジョブの監視](../technical-guides/monitoring-sql-server-agent-jobs.md)です。</span><span class="sxs-lookup"><span data-stu-id="36c61-113">For information about ensuring that the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Agent service is running on the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], and ensuring that all BizTalk related SQL Server jobs are working properly, see [Monitoring SQL Server Agent Jobs](../technical-guides/monitoring-sql-server-agent-jobs.md).</span></span>  
  
-   <span data-ttu-id="36c61-114">BizTalk アプリケーションまたは BTSTask コマンド ライン ツールを使用して成果物の削除についてを参照してください「RemoveApp コマンド」[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ[http://go.microsoft.com/fwlink/?LinkID=154687](http://go.microsoft.com/fwlink/?LinkID=154687)です。</span><span class="sxs-lookup"><span data-stu-id="36c61-114">For information about removing a BizTalk application or artifact using the BTSTask command-line tool, see "RemoveApp Command" in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help at [http://go.microsoft.com/fwlink/?LinkID=154687](http://go.microsoft.com/fwlink/?LinkID=154687).</span></span>  
  
-   <span data-ttu-id="36c61-115">BizTalk Server 管理コンソールまたは BTSTask コマンド ライン ツールを使用してアプリケーションからアイテムを削除する方法の詳細についてを参照してください「どのように削除成果物からのアプリケーションへ」[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ[http://go.microsoft.com/fwlink/ しますか。LinkID = 154688](http://go.microsoft.com/fwlink/?LinkID=154688)です。</span><span class="sxs-lookup"><span data-stu-id="36c61-115">For information about removing an artifact from an application using either the BizTalk Server Administration console or the BTSTask command-line tool, see "How to Remove an Artifact from an Application" in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help at [http://go.microsoft.com/fwlink/?LinkID=154688](http://go.microsoft.com/fwlink/?LinkID=154688).</span></span>  
  
-   <span data-ttu-id="36c61-116">BizTalk 管理コンソールで構成を検証する方法の詳細についてを参照してください「を使用して、BizTalk Server 管理コンソール」[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ[http://go.microsoft.com/fwlink/?LinkID=154689](http://go.microsoft.com/fwlink/?LinkID=154689)です。</span><span class="sxs-lookup"><span data-stu-id="36c61-116">For information about verifying the configuration in the BizTalk Administration Console, see "Using the BizTalk Server Administration Console" in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help at [http://go.microsoft.com/fwlink/?LinkID=154689](http://go.microsoft.com/fwlink/?LinkID=154689).</span></span>  
  
-   <span data-ttu-id="36c61-117">BTSNTSvc.exe.config ファイルの検証についてを参照してください「BTSNTSvc.exe.config ファイル」[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ[http://go.microsoft.com/fwlink/?LinkID=154690](http://go.microsoft.com/fwlink/?LinkID=154690)です。</span><span class="sxs-lookup"><span data-stu-id="36c61-117">For information about verifying the BTSNTSvc.exe.config file, see "BTSNTSvc.exe.config File" in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help at [http://go.microsoft.com/fwlink/?LinkID=154690](http://go.microsoft.com/fwlink/?LinkID=154690).</span></span>  
  
-   <span data-ttu-id="36c61-118">BizTalk の検証については、の関連するレジストリ キーを参照してくださいで Microsoft ヘルプとサポート Web サイトで「上級ユーザーのレジストリ情報を Windows」 [http://go.microsoft.com/fwlink/?LinkId=155583](http://go.microsoft.com/fwlink/?LinkId=155583)です。</span><span class="sxs-lookup"><span data-stu-id="36c61-118">For information about verifying the BizTalk related registry keys, see "Windows registry information for advanced users" in the Microsoft Help and Support Web site at [http://go.microsoft.com/fwlink/?LinkId=155583](http://go.microsoft.com/fwlink/?LinkId=155583).</span></span>  
  
-   <span data-ttu-id="36c61-119">BizTalk のベスト プラクティス アナライザーの実行方法の詳細については、「BizTalk Server ベスト プラクティス アナライザー」で、Microsoft ダウンロード センターを参照してください。 [http://go.microsoft.com/fwlink/?LinkId=83317](http://go.microsoft.com/fwlink/?LinkId=83317)です。</span><span class="sxs-lookup"><span data-stu-id="36c61-119">For information about running the BizTalk Best Practices Analyzer, see "BizTalk Server Best Practices Analyzer" in the Microsoft Download Center at [http://go.microsoft.com/fwlink/?LinkId=83317](http://go.microsoft.com/fwlink/?LinkId=83317).</span></span>  
  
-   <span data-ttu-id="36c61-120">BAM データベースを維持する方法の詳細については、「BAM データベースを管理する」を参照してください[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ[http://go.microsoft.com/fwlink/?LinkId=155584](http://go.microsoft.com/fwlink/?LinkId=155584)です。</span><span class="sxs-lookup"><span data-stu-id="36c61-120">For information about maintaining BAM databases, see "Managing BAM Databases" in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help at [http://go.microsoft.com/fwlink/?LinkId=155584](http://go.microsoft.com/fwlink/?LinkId=155584).</span></span>  
  
-   <span data-ttu-id="36c61-121">最新の service pack と修正プログラムがインストールされていることを確認する方法については、Microsoft Update の Web サイトでを参照してください。 [http://go.microsoft.com/fwlink/?LinkID=47813](http://go.microsoft.com/fwlink/?LinkID=47813)です。</span><span class="sxs-lookup"><span data-stu-id="36c61-121">For information about ensuring that the latest service packs and hotfixes are installed, see the Microsoft Update Web site at [http://go.microsoft.com/fwlink/?LinkID=47813](http://go.microsoft.com/fwlink/?LinkID=47813).</span></span>