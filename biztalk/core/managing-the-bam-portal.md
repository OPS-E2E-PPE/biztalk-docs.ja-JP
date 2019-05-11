---
title: BizTalk Server で BAM ポータルの管理 |Microsoft Docs
Description: インストールして、BizTalk Server で BAM ポータルの構成の概要
ms.custom: ''
ms.date: 08/15/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3a08aa85-3a45-4a8c-bdb5-5615ca097ce1
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0448e435e7adcc84d30f31ded54534c248e8e69
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380155"
---
# <a name="manage-the-bam-portal"></a><span data-ttu-id="deb76-103">BAM ポータルを管理します。</span><span class="sxs-lookup"><span data-stu-id="deb76-103">Manage the BAM portal</span></span>

## <a name="set-up-bam-portal"></a><span data-ttu-id="deb76-104">BAM ポータルをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="deb76-104">Set up BAM portal</span></span>
<span data-ttu-id="deb76-105">管理者を実行して BAM ポータルの設定、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストールします。</span><span class="sxs-lookup"><span data-stu-id="deb76-105">Administrators set up the BAM portal by running the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation.</span></span> <span data-ttu-id="deb76-106">BizTalk Server 構成ツールを使用して、BAM が有効になっているかどうかを指定して、ポータルを表示できる Windows グループと、ポータルをホストする Web サイトでは、Web サービスのアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="deb76-106">Use the BizTalk Server configuration tool to specify whether BAM is enabled, and to specify the Web service accounts, the Windows groups that can view portal, and the Web site that will host the portal.</span></span> <span data-ttu-id="deb76-107">BAM ポータルを設定すると、BAM ポータルの構成を更新するために必要になると、構成ツールを使用してポータル ユーザー グループ、アプリケーション プール アカウント、および管理 Web サービスのユーザーなどの構成設定を更新します。</span><span class="sxs-lookup"><span data-stu-id="deb76-107">If it becomes necessary to update the BAM portal configuration once you have set up the BAM portal, you use the configuration tool to update the configuration settings such as the portal users group, the Application Pool account, and the management Web services user.</span></span>  
  
 <span data-ttu-id="deb76-108">BAM ポータルのインストールの詳細については、次を参照してください。[複数コンピュータ環境での BAM の構成のインストールおよび](http://social.technet.microsoft.com/wiki/contents/articles/1888.install-and-configure-bam-business-activity-monitoring-in-a-multi-computer-environment.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="deb76-108">For more information about installing the BAM portal, see [Install and Configure BAM in Multiple Computer Environments](http://social.technet.microsoft.com/wiki/contents/articles/1888.install-and-configure-bam-business-activity-monitoring-in-a-multi-computer-environment.aspx).</span></span>  
  
 <span data-ttu-id="deb76-109">BAM ポータルを構成する方法の詳細については、次を参照してください。 [BizTalk Server の構成](../install-and-config-guides/configure-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="deb76-109">For more information about configuring the BAM portal, see [Configure BizTalk Server](../install-and-config-guides/configure-biztalk-server.md).</span></span>
  
 <span data-ttu-id="deb76-110">BAM ポータルでは、webconfig.xml ファイルを変更することによってアクセスされる多くのカスタマイズ可能な設定があります。</span><span class="sxs-lookup"><span data-stu-id="deb76-110">The BAM portal has many customizable settings that are accessed by modifying the webconfig.xml file.</span></span> <span data-ttu-id="deb76-111">これらの設定は、パフォーマンスと、BAM ポータルの操作を制御します。</span><span class="sxs-lookup"><span data-stu-id="deb76-111">These settings control the performance and operation of the BAM portal.</span></span> <span data-ttu-id="deb76-112">このセクションの残りのこの部分では、BAM ポータル構成をカスタマイズする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="deb76-112">This rest of this section describes how to customize your BAM portal configuration.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="deb76-113">次のステップ</span><span class="sxs-lookup"><span data-stu-id="deb76-113">Next steps</span></span> 
  
-   [<span data-ttu-id="deb76-114">BAM ポータルの構成のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="deb76-114">Customizing the BAM Portal Configuration</span></span>](../core/customizing-the-bam-portal-configuration.md)  
  
-   [<span data-ttu-id="deb76-115">NLB クラスターで機能する BAM ポータルを構成する方法</span><span class="sxs-lookup"><span data-stu-id="deb76-115">How to Configure the BAM Portal to Work on an NLB Cluster</span></span>](../core/how-to-configure-the-bam-portal-to-work-on-an-nlb-cluster.md)  
  
## <a name="see-also"></a><span data-ttu-id="deb76-116">参照</span><span class="sxs-lookup"><span data-stu-id="deb76-116">See Also</span></span>  
 [<span data-ttu-id="deb76-117">BAM 動的インフラストラクチャの管理</span><span class="sxs-lookup"><span data-stu-id="deb76-117">Managing the BAM Dynamic Infrastructure</span></span>](../core/managing-the-bam-dynamic-infrastructure.md)