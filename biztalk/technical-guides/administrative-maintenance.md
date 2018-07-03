---
title: 管理メンテナンス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67cdf9d7-5448-40c5-8c5f-eae0e281d22c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd107a9b596919c92e4cb8ac5a0538e8f4ded3ab
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007971"
---
# <a name="administrative-maintenance"></a><span data-ttu-id="083eb-102">管理メンテナンス</span><span class="sxs-lookup"><span data-stu-id="083eb-102">Administrative Maintenance</span></span>
<span data-ttu-id="083eb-103">このセクションで管理上の問題を解決する方法について説明します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]システム。</span><span class="sxs-lookup"><span data-stu-id="083eb-103">This section provides information about how you can resolve administration issues with a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system.</span></span> <span data-ttu-id="083eb-104">実行される定期的なメンテナンスのチェックでこれらの問題を検出する可能性がある、[ルーチン メンテナンスのチェックリスト](../technical-guides/routine-maintenance-checklists.md)セクション。</span><span class="sxs-lookup"><span data-stu-id="083eb-104">These issues may be discovered by the routine maintenance checks that are performed in the [Routine Maintenance Checklists](../technical-guides/routine-maintenance-checklists.md) section.</span></span>  

 <span data-ttu-id="083eb-105">このセクションのトピックだけでなくは、このドキュメントの他のトピックは、管理の問題を解決します。</span><span class="sxs-lookup"><span data-stu-id="083eb-105">In addition to the topics in this section, other topics in this document address administration issues.</span></span> <span data-ttu-id="083eb-106">これらのトピックは、関連するセクションの下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="083eb-106">These topics are listed in Related Sections below.</span></span>  

## <a name="in-this-section"></a><span data-ttu-id="083eb-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="083eb-107">In This Section</span></span>  

-   [<span data-ttu-id="083eb-108">管理メンテナンスのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="083eb-108">Best Practices for Administrative Maintenance</span></span>](../technical-guides/best-practices-for-administrative-maintenance.md)  

-   [<span data-ttu-id="083eb-109">SQL Server エージェントを開始する方法</span><span class="sxs-lookup"><span data-stu-id="083eb-109">How to Start the SQL Server Agent</span></span>](../technical-guides/how-to-start-the-sql-server-agent.md)  

-   [<span data-ttu-id="083eb-110">BizTalk Server のバックアップ ジョブのスケジュールを設定する方法</span><span class="sxs-lookup"><span data-stu-id="083eb-110">How to Schedule a Backup BizTalk Server Job</span></span>](../technical-guides/how-to-schedule-a-backup-biztalk-server-job.md)  

-   [<span data-ttu-id="083eb-111">バックアップ BizTalk Server ジョブを構成する方法</span><span class="sxs-lookup"><span data-stu-id="083eb-111">How to Configure a Backup BizTalk Server Job</span></span>](../technical-guides/how-to-configure-a-backup-biztalk-server-job.md)  

## <a name="related-sections"></a><span data-ttu-id="083eb-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="083eb-112">Related Sections</span></span>  

- <span data-ttu-id="083eb-113">確認する方法については、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]でエージェント サービスが実行されている、 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]、すべての BizTalk 関連 SQL Server ジョブが正常に動作していることを確認を参照してくださいと[SQL Server エージェント ジョブの監視](../technical-guides/monitoring-sql-server-agent-jobs.md)します。</span><span class="sxs-lookup"><span data-stu-id="083eb-113">For information about ensuring that the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Agent service is running on the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], and ensuring that all BizTalk related SQL Server jobs are working properly, see [Monitoring SQL Server Agent Jobs](../technical-guides/monitoring-sql-server-agent-jobs.md).</span></span>  

- <span data-ttu-id="083eb-114">BizTalk アプリケーションまたは BTSTask コマンド ライン ツールを使用して成果物を削除する方法については、「RemoveApp コマンド」を参照してください[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ[ http://go.microsoft.com/fwlink/?LinkID=154687](http://go.microsoft.com/fwlink/?LinkID=154687)します。</span><span class="sxs-lookup"><span data-stu-id="083eb-114">For information about removing a BizTalk application or artifact using the BTSTask command-line tool, see "RemoveApp Command" in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help at [http://go.microsoft.com/fwlink/?LinkID=154687](http://go.microsoft.com/fwlink/?LinkID=154687).</span></span>  

- <span data-ttu-id="083eb-115">BizTalk Server 管理コンソールまたは BTSTask コマンド ライン ツールを使用して、アプリケーションからアイテムを削除する方法の詳細については、「どのように削除の成果物からアプリケーションへ」を参照してください[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ[ http://go.microsoft.com/fwlink/?LinkID=154688](http://go.microsoft.com/fwlink/?LinkID=154688).</span><span class="sxs-lookup"><span data-stu-id="083eb-115">For information about removing an artifact from an application using either the BizTalk Server Administration console or the BTSTask command-line tool, see "How to Remove an Artifact from an Application" in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help at [http://go.microsoft.com/fwlink/?LinkID=154688](http://go.microsoft.com/fwlink/?LinkID=154688).</span></span>  

- <span data-ttu-id="083eb-116">BizTalk 管理コンソールで構成を確認する方法の詳細については、「を使用して、BizTalk Server 管理コンソール」を参照してください[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ[ http://go.microsoft.com/fwlink/?LinkID=154689](http://go.microsoft.com/fwlink/?LinkID=154689)します。</span><span class="sxs-lookup"><span data-stu-id="083eb-116">For information about verifying the configuration in the BizTalk Administration Console, see "Using the BizTalk Server Administration Console" in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help at [http://go.microsoft.com/fwlink/?LinkID=154689](http://go.microsoft.com/fwlink/?LinkID=154689).</span></span>  

- <span data-ttu-id="083eb-117">BTSNTSvc.exe.config ファイルを確認する方法の詳細については、「BTSNTSvc.exe.config ファイル」を参照してください[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ[ http://go.microsoft.com/fwlink/?LinkID=154690](http://go.microsoft.com/fwlink/?LinkID=154690)します。</span><span class="sxs-lookup"><span data-stu-id="083eb-117">For information about verifying the BTSNTSvc.exe.config file, see "BTSNTSvc.exe.config File" in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help at [http://go.microsoft.com/fwlink/?LinkID=154690](http://go.microsoft.com/fwlink/?LinkID=154690).</span></span>  

- <span data-ttu-id="083eb-118">については、BizTalk の検証方法については、関連するレジストリ キーで Microsoft ヘルプとサポート Web サイトで「高度なユーザーのレジストリ情報を Windows」を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=155583](http://go.microsoft.com/fwlink/?LinkId=155583)します。</span><span class="sxs-lookup"><span data-stu-id="083eb-118">For information about verifying the BizTalk related registry keys, see "Windows registry information for advanced users" in the Microsoft Help and Support Web site at [http://go.microsoft.com/fwlink/?LinkId=155583](http://go.microsoft.com/fwlink/?LinkId=155583).</span></span>  

- <span data-ttu-id="083eb-119">BizTalk のベスト プラクティス アナライザーの実行方法の詳細については、"BizTalk Server Best Practices Analyzer"で、Microsoft ダウンロード センターを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=83317](http://go.microsoft.com/fwlink/?LinkId=83317)します。</span><span class="sxs-lookup"><span data-stu-id="083eb-119">For information about running the BizTalk Best Practices Analyzer, see "BizTalk Server Best Practices Analyzer" in the Microsoft Download Center at [http://go.microsoft.com/fwlink/?LinkId=83317](http://go.microsoft.com/fwlink/?LinkId=83317).</span></span>  

- <span data-ttu-id="083eb-120">BAM データベースを保守する方法の詳細については、「BAM データベースを管理する」を参照してください[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ[ http://go.microsoft.com/fwlink/?LinkId=155584](http://go.microsoft.com/fwlink/?LinkId=155584)します。</span><span class="sxs-lookup"><span data-stu-id="083eb-120">For information about maintaining BAM databases, see "Managing BAM Databases" in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help at [http://go.microsoft.com/fwlink/?LinkId=155584](http://go.microsoft.com/fwlink/?LinkId=155584).</span></span>  

- <span data-ttu-id="083eb-121">最新のサービス パックと修正プログラムがインストールされていることを確認する方法については、Microsoft Update Web サイトを参照してください。 [ http://go.microsoft.com/fwlink/?LinkID=47813](http://go.microsoft.com/fwlink/?LinkID=47813)します。</span><span class="sxs-lookup"><span data-stu-id="083eb-121">For information about ensuring that the latest service packs and hotfixes are installed, see the Microsoft Update Web site at [http://go.microsoft.com/fwlink/?LinkID=47813](http://go.microsoft.com/fwlink/?LinkID=47813).</span></span>
