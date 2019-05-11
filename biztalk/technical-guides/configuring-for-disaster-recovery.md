---
title: ディザスター リカバリーのための構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: acdafe68-c8bf-4064-afca-6dfd22d15052
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0bce395a5873947d006aa84b620b921a4a8e943
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65253555"
---
# <a name="configuring-for-disaster-recovery"></a><span data-ttu-id="89a04-102">ディザスター リカバリーを構成します。</span><span class="sxs-lookup"><span data-stu-id="89a04-102">Configuring for Disaster Recovery</span></span>
<span data-ttu-id="89a04-103">既存のバックアップを拡張する BizTalk Server のログ配布機能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ジョブ。</span><span class="sxs-lookup"><span data-stu-id="89a04-103">The BizTalk Server Log Shipping feature extends the existing Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job.</span></span> <span data-ttu-id="89a04-104">BizTalk Server のログ配布、一連のバックアップのジョブによって生成されたバックアップ セットを手動で復元する必要はありませんし、システム障害が発生した場合のダウンタイムを短縮します。</span><span class="sxs-lookup"><span data-stu-id="89a04-104">BizTalk Server Log Shipping eliminates the need to manually restore a series of backup sets produced by the backup job, and reduces downtime in the event of a system failure.</span></span> <span data-ttu-id="89a04-105">BizTalk Server のログ配布は、BizTalk のディザスター リカバリーの手順の重要なコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="89a04-105">BizTalk Server Log Shipping is a critical component for BizTalk disaster recovery procedures.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="89a04-106">各アプリケーション チームがこのトピックで説明する概念を補完するディザスター リカバリー計画を復元し、文書化されているバックアップがある必要があります。</span><span class="sxs-lookup"><span data-stu-id="89a04-106">Each application team must have a documented backup and restore plan for disaster recovery that complements the concepts provided in this topic.</span></span> <span data-ttu-id="89a04-107">全体的な計画は、アプリケーションやオペレーティング システムのコンポーネントを含めて、システム全体に対処する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89a04-107">The overall plan should address the entire system, including applications and the components of the operating system.</span></span>  
  
 <span data-ttu-id="89a04-108">手動での新しいセットを BizTalk グループの復元を実行するとよく似ていますディザスター リカバリー操作を実行して[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベース インスタンス。</span><span class="sxs-lookup"><span data-stu-id="89a04-108">Performing a disaster recovery operation is very similar to manually performing a restore of a BizTalk group to a new set of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] database instances.</span></span> <span data-ttu-id="89a04-109">主な違いは、その BizTalk Server ログ配布には、多くの手動手順を保存、ディザスター リカバリー サイトに継続的にログが適用されます。</span><span class="sxs-lookup"><span data-stu-id="89a04-109">The primary difference is that BizTalk Server log shipping applies logs continuously at the disaster recovery site, saving many manual steps.</span></span> <span data-ttu-id="89a04-110">そのため、ログの最後のセットにのみ必要があります手動で復元するときに BizTalk Server のログ配布を実装します。</span><span class="sxs-lookup"><span data-stu-id="89a04-110">Therefore, only the last set of logs must be restored manually when BizTalk Server log shipping is implemented.</span></span> <span data-ttu-id="89a04-111">それ以外の場合、前回の完全バックアップ以降のすべてのログ バックアップ後に、前回の完全バックアップは、手動で復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89a04-111">Otherwise, the last full backup followed by all log backups since the last full backup would have to be manually restored.</span></span> <span data-ttu-id="89a04-112">BizTalk Server ログ配布は、この手動プロセスで、ディザスター リカバリー サイトの復元を高速化労力を減らします。</span><span class="sxs-lookup"><span data-stu-id="89a04-112">BizTalk Server log shipping reduces the effort for this manual process, speeding restoration of the disaster recovery site.</span></span>  
  
 <span data-ttu-id="89a04-113">このセクションでは、ディザスター リカバリーのプロセスを容易に運用環境の構成に関する推奨事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="89a04-113">This section covers recommendations on production configuration to facilitate the disaster recovery process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="89a04-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="89a04-114">In This Section</span></span>  
  
-   [<span data-ttu-id="89a04-115">ディザスター リカバリー サイトの準備</span><span class="sxs-lookup"><span data-stu-id="89a04-115">Prepare the Disaster Recovery Site</span></span>](../technical-guides/prepare-the-disaster-recovery-site.md)  
  
-   [<span data-ttu-id="89a04-116">ログ配布のユーザー アカウントとロール</span><span class="sxs-lookup"><span data-stu-id="89a04-116">Log Shipping User Accounts and Roles</span></span>](../technical-guides/log-shipping-user-accounts-and-roles.md)  
  
-   [<span data-ttu-id="89a04-117">BizTalk Server のログ配布の構成</span><span class="sxs-lookup"><span data-stu-id="89a04-117">Configuring BizTalk Server Log Shipping</span></span>](../technical-guides/configuring-biztalk-server-log-shipping.md)  
  
## <a name="see-also"></a><span data-ttu-id="89a04-118">参照</span><span class="sxs-lookup"><span data-stu-id="89a04-118">See Also</span></span>  
 [<span data-ttu-id="89a04-119">ディザスター リカバリー</span><span class="sxs-lookup"><span data-stu-id="89a04-119">Disaster Recovery</span></span>](../technical-guides/disaster-recovery.md)