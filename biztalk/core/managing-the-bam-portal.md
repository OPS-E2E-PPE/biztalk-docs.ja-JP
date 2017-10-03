---
title: "BizTalk Server で、BAM ポータルの管理 |Microsoft ドキュメント"
Description: "インストールして、BizTalk Server で BAM ポータルの構成の概要"
ms.custom: 
ms.date: 08/15/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3a08aa85-3a45-4a8c-bdb5-5615ca097ce1
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d7908c9c7ce8e4b731e0b88569e3dc3fb228a1d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="manage-the-bam-portal"></a><span data-ttu-id="ae1aa-103">BAM ポータルを管理します。</span><span class="sxs-lookup"><span data-stu-id="ae1aa-103">Manage the BAM portal</span></span>

## <a name="set-up-bam-portal"></a><span data-ttu-id="ae1aa-104">BAM ポータルをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="ae1aa-104">Set up BAM portal</span></span>
<span data-ttu-id="ae1aa-105">管理者は、インストールされている [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を実行して BAM ポータルを設定します。</span><span class="sxs-lookup"><span data-stu-id="ae1aa-105">Administrators set up the BAM portal by running the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation.</span></span> <span data-ttu-id="ae1aa-106">BizTalk Server 構成ツールを使用して、BAM を有効にするかどうかを指定したり、Web サービス アカウント、ポータルを表示できる Windows グループ、およびポータルをホストする Web サイトを指定します。</span><span class="sxs-lookup"><span data-stu-id="ae1aa-106">Use the BizTalk Server configuration tool to specify whether BAM is enabled, and to specify the Web service accounts, the Windows groups that can view portal, and the Web site that will host the portal.</span></span> <span data-ttu-id="ae1aa-107">BAM ポータルを設定した後に BAM ポータルの構成を更新することが必要になった場合、構成ツールを使用して、ポータル ユーザー グループ、アプリケーション プール アカウント、管理 Web サービス ユーザーなどの構成設定を更新します。</span><span class="sxs-lookup"><span data-stu-id="ae1aa-107">If it becomes necessary to update the BAM portal configuration once you have set up the BAM portal, you use the configuration tool to update the configuration settings such as the portal users group, the Application Pool account, and the management Web services user.</span></span>  
  
 <span data-ttu-id="ae1aa-108">BAM ポータルのインストールに関する詳細については、次を参照してください。 [BAM インストールおよび構成複数コンピュータ環境で](http://social.technet.microsoft.com/wiki/contents/articles/1888.install-and-configure-bam-business-activity-monitoring-in-a-multi-computer-environment.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="ae1aa-108">For more information about installing the BAM portal, see [Install and Configure BAM in Multiple Computer Environments](http://social.technet.microsoft.com/wiki/contents/articles/1888.install-and-configure-bam-business-activity-monitoring-in-a-multi-computer-environment.aspx).</span></span>  
  
 <span data-ttu-id="ae1aa-109">BAM ポータルの構成の詳細については、次を参照してください。 [BizTalk Server の構成](../install-and-config-guides/configure-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="ae1aa-109">For more information about configuring the BAM portal, see [Configure BizTalk Server](../install-and-config-guides/configure-biztalk-server.md).</span></span>
  
 <span data-ttu-id="ae1aa-110">BAM ポータルにはカスタマイズ可能な設定が数多くあり、これらの設定には webconfig.xml ファイルを変更することによってアクセスします。</span><span class="sxs-lookup"><span data-stu-id="ae1aa-110">The BAM portal has many customizable settings that are accessed by modifying the webconfig.xml file.</span></span> <span data-ttu-id="ae1aa-111">これらの設定により、BAM ポータルのパフォーマンスおよび操作を制御できます。</span><span class="sxs-lookup"><span data-stu-id="ae1aa-111">These settings control the performance and operation of the BAM portal.</span></span> <span data-ttu-id="ae1aa-112">このセクションの他の部分では、BAM ポータルの構成をカスタマイズする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ae1aa-112">This rest of this section describes how to customize your BAM portal configuration.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="ae1aa-113">次の手順</span><span class="sxs-lookup"><span data-stu-id="ae1aa-113">Next steps</span></span> 
  
-   [<span data-ttu-id="ae1aa-114">BAM ポータルの構成をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="ae1aa-114">Customizing the BAM Portal Configuration</span></span>](../core/customizing-the-bam-portal-configuration.md)  
  
-   [<span data-ttu-id="ae1aa-115">NLB クラスターで機能する BAM ポータルを構成する方法</span><span class="sxs-lookup"><span data-stu-id="ae1aa-115">How to Configure the BAM Portal to Work on an NLB Cluster</span></span>](../core/how-to-configure-the-bam-portal-to-work-on-an-nlb-cluster.md)  
  
## <a name="see-also"></a><span data-ttu-id="ae1aa-116">参照</span><span class="sxs-lookup"><span data-stu-id="ae1aa-116">See Also</span></span>  
 [<span data-ttu-id="ae1aa-117">BAM 動的インフラストラクチャの管理</span><span class="sxs-lookup"><span data-stu-id="ae1aa-117">Managing the BAM Dynamic Infrastructure</span></span>](../core/managing-the-bam-dynamic-infrastructure.md)