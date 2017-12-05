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
ms.openlocfilehash: 3899b27324fa00e0b5c630c7be4433f65a917a1b
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="configuring-for-disaster-recovery"></a><span data-ttu-id="a5c0a-102">災害復旧のための構成</span><span class="sxs-lookup"><span data-stu-id="a5c0a-102">Configuring for Disaster Recovery</span></span>
<span data-ttu-id="a5c0a-103">既存のバックアップを拡張する BizTalk Server のログ配布機能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ジョブです。</span><span class="sxs-lookup"><span data-stu-id="a5c0a-103">The BizTalk Server Log Shipping feature extends the existing Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job.</span></span> <span data-ttu-id="a5c0a-104">BizTalk Server のログ配布バックアップ ジョブによって生成されるバックアップ セットの系列を手動で復元する必要があるし、システム障害時のダウンタイムを短縮します。</span><span class="sxs-lookup"><span data-stu-id="a5c0a-104">BizTalk Server Log Shipping eliminates the need to manually restore a series of backup sets produced by the backup job, and reduces downtime in the event of a system failure.</span></span> <span data-ttu-id="a5c0a-105">BizTalk Server のログ配布は、BizTalk の障害復旧手順の重要なコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="a5c0a-105">BizTalk Server Log Shipping is a critical component for BizTalk disaster recovery procedures.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a5c0a-106">各アプリケーション チームは、文書化されたバックアップがあるし、復元のこのトピックで説明する概念を補足する災害復旧の計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5c0a-106">Each application team must have a documented backup and restore plan for disaster recovery that complements the concepts provided in this topic.</span></span> <span data-ttu-id="a5c0a-107">全体的な計画は、アプリケーションおよびオペレーティング システムのコンポーネントを含め、システム全体に対処する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5c0a-107">The overall plan should address the entire system, including applications and the components of the operating system.</span></span>  
  
 <span data-ttu-id="a5c0a-108">新しいセットを BizTalk グループの復元を手動で実行するとよく似ていますが、障害復旧操作を実行する[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベース インスタンスです。</span><span class="sxs-lookup"><span data-stu-id="a5c0a-108">Performing a disaster recovery operation is very similar to manually performing a restore of a BizTalk group to a new set of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] database instances.</span></span> <span data-ttu-id="a5c0a-109">主な違いは、その BizTalk Server ログ配布は継続的に、障害復旧サイトで、多くの手動処理の保存ログを適用します。</span><span class="sxs-lookup"><span data-stu-id="a5c0a-109">The primary difference is that BizTalk Server log shipping applies logs continuously at the disaster recovery site, saving many manual steps.</span></span> <span data-ttu-id="a5c0a-110">そのため、ログの最後のセットにのみ必要があります手動で復元するときに BizTalk Server のログ配布を実装します。</span><span class="sxs-lookup"><span data-stu-id="a5c0a-110">Therefore, only the last set of logs must be restored manually when BizTalk Server log shipping is implemented.</span></span> <span data-ttu-id="a5c0a-111">それ以外の場合、前回の完全バックアップ以降のすべてのログ バックアップ後に、最後の完全バックアップは、手動で復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5c0a-111">Otherwise, the last full backup followed by all log backups since the last full backup would have to be manually restored.</span></span> <span data-ttu-id="a5c0a-112">BizTalk Server ログ配布がこの手動プロセスで、障害復旧サイトの復元を迅速化労力を削減します。</span><span class="sxs-lookup"><span data-stu-id="a5c0a-112">BizTalk Server log shipping reduces the effort for this manual process, speeding restoration of the disaster recovery site.</span></span>  
  
 <span data-ttu-id="a5c0a-113">このセクションでは、障害復旧プロセスを容易にする production 構成に関する推奨事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="a5c0a-113">This section covers recommendations on production configuration to facilitate the disaster recovery process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a5c0a-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a5c0a-114">In This Section</span></span>  
  
-   [<span data-ttu-id="a5c0a-115">ディザスター リカバリー サイトの準備</span><span class="sxs-lookup"><span data-stu-id="a5c0a-115">Prepare the Disaster Recovery Site</span></span>](../technical-guides/prepare-the-disaster-recovery-site.md)  
  
-   [<span data-ttu-id="a5c0a-116">ログ配布のユーザー アカウントとロール</span><span class="sxs-lookup"><span data-stu-id="a5c0a-116">Log Shipping User Accounts and Roles</span></span>](../technical-guides/log-shipping-user-accounts-and-roles.md)  
  
-   [<span data-ttu-id="a5c0a-117">BizTalk Server のログ配布の構成</span><span class="sxs-lookup"><span data-stu-id="a5c0a-117">Configuring BizTalk Server Log Shipping</span></span>](../technical-guides/configuring-biztalk-server-log-shipping.md)  
  
## <a name="see-also"></a><span data-ttu-id="a5c0a-118">参照</span><span class="sxs-lookup"><span data-stu-id="a5c0a-118">See Also</span></span>  
 [<span data-ttu-id="a5c0a-119">ディザスター リカバリー</span><span class="sxs-lookup"><span data-stu-id="a5c0a-119">Disaster Recovery</span></span>](../technical-guides/disaster-recovery.md)