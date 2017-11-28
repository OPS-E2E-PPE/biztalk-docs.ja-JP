---
title: "災害復旧のための構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: acdafe68-c8bf-4064-afca-6dfd22d15052
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8c6a188255097f0a1c1e85086688252f9154b36
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-for-disaster-recovery"></a><span data-ttu-id="d946d-102">災害復旧のための構成</span><span class="sxs-lookup"><span data-stu-id="d946d-102">Configuring for Disaster Recovery</span></span>
<span data-ttu-id="d946d-103">[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]既存のバックアップを拡張する機能のログ配布[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ジョブです。</span><span class="sxs-lookup"><span data-stu-id="d946d-103">The [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] Log Shipping feature extends the existing Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job.</span></span> [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]<span data-ttu-id="d946d-104">ログ配布は、一連のバックアップ ジョブによって生成されたバックアップ セットを手動で復元する必要があるし、システム障害時のダウンタイムを短縮します。</span><span class="sxs-lookup"><span data-stu-id="d946d-104"> Log Shipping eliminates the need to manually restore a series of backup sets produced by the backup job, and reduces downtime in the event of a system failure.</span></span> [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]<span data-ttu-id="d946d-105">ログ配布は、BizTalk の障害復旧手順の重要なコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="d946d-105"> Log Shipping is a critical component for BizTalk disaster recovery procedures.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d946d-106">各アプリケーション チームは、文書化されたバックアップがあるし、復元のこのトピックで説明する概念を補足する災害復旧の計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d946d-106">Each application team must have a documented backup and restore plan for disaster recovery that complements the concepts provided in this topic.</span></span> <span data-ttu-id="d946d-107">全体的な計画は、アプリケーションおよびオペレーティング システムのコンポーネントを含め、システム全体に対処する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d946d-107">The overall plan should address the entire system, including applications and the components of the operating system.</span></span>  
  
 <span data-ttu-id="d946d-108">新しいセットを BizTalk グループの復元を手動で実行するとよく似ていますが、障害復旧操作を実行する[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベース インスタンスです。</span><span class="sxs-lookup"><span data-stu-id="d946d-108">Performing a disaster recovery operation is very similar to manually performing a restore of a BizTalk group to a new set of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] database instances.</span></span> <span data-ttu-id="d946d-109">主な違いは[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]ログ配布は継続的に、障害復旧サイトで、多くの手動処理の保存ログを適用します。</span><span class="sxs-lookup"><span data-stu-id="d946d-109">The primary difference is that [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] log shipping applies logs continuously at the disaster recovery site, saving many manual steps.</span></span> <span data-ttu-id="d946d-110">そのため、ログの最後のセットにのみ必要があります手動で復元するときに[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]ログ配布を実装します。</span><span class="sxs-lookup"><span data-stu-id="d946d-110">Therefore, only the last set of logs must be restored manually when [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] log shipping is implemented.</span></span> <span data-ttu-id="d946d-111">それ以外の場合、前回の完全バックアップ以降のすべてのログ バックアップ後に、最後の完全バックアップは、手動で復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d946d-111">Otherwise, the last full backup followed by all log backups since the last full backup would have to be manually restored.</span></span> [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]<span data-ttu-id="d946d-112">ログ配布では、この手動プロセスで、障害復旧サイトの復元を迅速化労力が減少します。</span><span class="sxs-lookup"><span data-stu-id="d946d-112"> log shipping reduces the effort for this manual process, speeding restoration of the disaster recovery site.</span></span>  
  
 <span data-ttu-id="d946d-113">このセクションでは、障害復旧プロセスを容易にする production 構成に関する推奨事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="d946d-113">This section covers recommendations on production configuration to facilitate the disaster recovery process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d946d-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d946d-114">In This Section</span></span>  
  
-   [<span data-ttu-id="d946d-115">障害復旧サイトを準備します。</span><span class="sxs-lookup"><span data-stu-id="d946d-115">Prepare the Disaster Recovery Site</span></span>](../technical-guides/prepare-the-disaster-recovery-site.md)  
  
-   [<span data-ttu-id="d946d-116">ログ配布のユーザー アカウントとロール</span><span class="sxs-lookup"><span data-stu-id="d946d-116">Log Shipping User Accounts and Roles</span></span>](../technical-guides/log-shipping-user-accounts-and-roles.md)  
  
-   [<span data-ttu-id="d946d-117">ログ配布の BizTalk Server の構成</span><span class="sxs-lookup"><span data-stu-id="d946d-117">Configuring BizTalk Server Log Shipping</span></span>](../technical-guides/configuring-biztalk-server-log-shipping.md)  
  
## <a name="see-also"></a><span data-ttu-id="d946d-118">参照</span><span class="sxs-lookup"><span data-stu-id="d946d-118">See Also</span></span>  
 [<span data-ttu-id="d946d-119">災害復旧</span><span class="sxs-lookup"><span data-stu-id="d946d-119">Disaster Recovery</span></span>](../technical-guides/disaster-recovery.md)