---
title: ウォーム バックアップから運用環境の復元 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2bda14b8-b3cc-4a5e-a353-fca5885fd594
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66177cd1f6f10e252a71d2875b4079e660125719
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971363"
---
# <a name="restoring-production-from-a-warm-backup"></a><span data-ttu-id="3cd3d-102">ウォーム バックアップから運用環境の復元</span><span class="sxs-lookup"><span data-stu-id="3cd3d-102">Restoring Production from a Warm Backup</span></span>
<span data-ttu-id="3cd3d-103">ソース システムには、信頼性の低いになると、ソース、ターゲット データベースを復元すること勧めします。</span><span class="sxs-lookup"><span data-stu-id="3cd3d-103">If the source system becomes unreliable, it is possible to restore the databases from the destination to the source.</span></span> <span data-ttu-id="3cd3d-104">ソース コピー先からデータベースを復元する次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3cd3d-104">Perform the following procedure to restore databases from the destination to the source.</span></span>  
  
### <a name="to-restore-the-databases-from-the-destination-to-the-source-follow-these-steps"></a><span data-ttu-id="3cd3d-105">ソースに、ターゲット データベースを復元するには、以下の手順</span><span class="sxs-lookup"><span data-stu-id="3cd3d-105">To restore the databases from the destination to the source follow these steps</span></span>  
  
1. <span data-ttu-id="3cd3d-106">ソース (運用) 上のすべてのバックアップ ジョブを無効にする[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスします。</span><span class="sxs-lookup"><span data-stu-id="3cd3d-106">Disable all backup jobs on the source (production) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s).</span></span>  
  
2. <span data-ttu-id="3cd3d-107">すべての復元ジョブが移行先のディザスター リカバリー (DR) を完了するまで待機[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスします。</span><span class="sxs-lookup"><span data-stu-id="3cd3d-107">Wait for all restore jobs to complete on the destination disaster recovery (DR) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s).</span></span>  
  
3. <span data-ttu-id="3cd3d-108">宛先 (DR) のすべての復元ジョブを無効にする[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスします。</span><span class="sxs-lookup"><span data-stu-id="3cd3d-108">Disable all restore jobs on the destination (DR) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s).</span></span>  
  
4. <span data-ttu-id="3cd3d-109">STOPATMARK (DR) の接続先であるすべてのデータベースを復元[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスします。</span><span class="sxs-lookup"><span data-stu-id="3cd3d-109">Restore all databases with STOPATMARK on the destination (DR) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s).</span></span>  
  
5. <span data-ttu-id="3cd3d-110">すべて停止[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]すべての BizTalk server 上のサービスです。</span><span class="sxs-lookup"><span data-stu-id="3cd3d-110">Stop all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services on all BizTalk servers.</span></span>  
  
6. <span data-ttu-id="3cd3d-111">すべて削除[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-ソース (運用) 上のデータベースに関連[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスします。</span><span class="sxs-lookup"><span data-stu-id="3cd3d-111">Drop all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-related databases on the source (production) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s).</span></span>  
  
7. <span data-ttu-id="3cd3d-112">変換先 (DR) 上のすべてのデータベースの (完全) をバックアップ[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスします。</span><span class="sxs-lookup"><span data-stu-id="3cd3d-112">Back up (full) all databases on the destination (DR) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s).</span></span>  
  
8. <span data-ttu-id="3cd3d-113">すべての復元 (完全)[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース バックアップ手順 7. で、ソース (運用)[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスします。</span><span class="sxs-lookup"><span data-stu-id="3cd3d-113">Restore (full) all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases backed up in step 7 to the source (production) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s).</span></span>  
  
9. <span data-ttu-id="3cd3d-114">マスター シークレット サーバーを含むすべての BizTalk server を再起動します。</span><span class="sxs-lookup"><span data-stu-id="3cd3d-114">Restart all BizTalk servers including the master secret server.</span></span>  
  
10. <span data-ttu-id="3cd3d-115">すべて削除[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-変換先 (DR) 上のデータベースに関連[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスします。</span><span class="sxs-lookup"><span data-stu-id="3cd3d-115">Drop all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-related databases on the destination (DR) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s).</span></span>  
  
11. <span data-ttu-id="3cd3d-116">ソースのバックアップ ジョブを有効にする[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスします。</span><span class="sxs-lookup"><span data-stu-id="3cd3d-116">Enable backup jobs on the source [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s).</span></span>  
  
12. <span data-ttu-id="3cd3d-117">宛先 (DR) の復元ジョブを有効にする[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスします。</span><span class="sxs-lookup"><span data-stu-id="3cd3d-117">Enable restore jobs on the destination (DR) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cd3d-118">参照</span><span class="sxs-lookup"><span data-stu-id="3cd3d-118">See Also</span></span>  
 [<span data-ttu-id="3cd3d-119">バックアップおよび Restore2 に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="3cd3d-119">Advanced Information About Backup and Restore2</span></span>](../technical-guides/advanced-information-about-backup-and-restore2.md)