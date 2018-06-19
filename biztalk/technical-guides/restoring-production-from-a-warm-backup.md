---
title: ウォーム バックアップから運用環境の復元 |Microsoft ドキュメント
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
ms.openlocfilehash: 8e590b4eccb6ee946a915ff1f3a0265bbfe977e7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302090"
---
# <a name="restoring-production-from-a-warm-backup"></a><span data-ttu-id="8ab77-102">ウォーム バックアップから運用環境の復元</span><span class="sxs-lookup"><span data-stu-id="8ab77-102">Restoring Production from a Warm Backup</span></span>
<span data-ttu-id="8ab77-103">ソース システムの信頼性の低いになると、そのソースに、ターゲット データベースを復元する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8ab77-103">If the source system becomes unreliable, it is possible to restore the databases from the destination to the source.</span></span> <span data-ttu-id="8ab77-104">データベースを復元するターゲットからソースへの次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8ab77-104">Perform the following procedure to restore databases from the destination to the source.</span></span>  
  
### <a name="to-restore-the-databases-from-the-destination-to-the-source-follow-these-steps"></a><span data-ttu-id="8ab77-105">ターゲットからソースへのデータベースを復元するには、以下の手順</span><span class="sxs-lookup"><span data-stu-id="8ab77-105">To restore the databases from the destination to the source follow these steps</span></span>  
  
1.  <span data-ttu-id="8ab77-106">ソース (運用環境) 上のすべてのバックアップ ジョブを無効にする[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンス。</span><span class="sxs-lookup"><span data-stu-id="8ab77-106">Disable all backup jobs on the source (production) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s).</span></span>  
  
2.  <span data-ttu-id="8ab77-107">すべての復元ジョブが移行先の災害復旧 (DR) で完了するまで待機[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンス。</span><span class="sxs-lookup"><span data-stu-id="8ab77-107">Wait for all restore jobs to complete on the destination disaster recovery (DR) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s).</span></span>  
  
3.  <span data-ttu-id="8ab77-108">移行先 (DR) 上のすべての復元ジョブを無効にする[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンス。</span><span class="sxs-lookup"><span data-stu-id="8ab77-108">Disable all restore jobs on the destination (DR) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s).</span></span>  
  
4.  <span data-ttu-id="8ab77-109">STOPATMARK 先 (DR) にあるすべてのデータベースを復元[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンス。</span><span class="sxs-lookup"><span data-stu-id="8ab77-109">Restore all databases with STOPATMARK on the destination (DR) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s).</span></span>  
  
5.  <span data-ttu-id="8ab77-110">すべて停止[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]すべての BizTalk server 上のサービスです。</span><span class="sxs-lookup"><span data-stu-id="8ab77-110">Stop all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services on all BizTalk servers.</span></span>  
  
6.  <span data-ttu-id="8ab77-111">すべてを削除[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-ソース (運用環境) 上のデータベースの関連[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンス。</span><span class="sxs-lookup"><span data-stu-id="8ab77-111">Drop all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-related databases on the source (production) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s).</span></span>  
  
7.  <span data-ttu-id="8ab77-112">(完全) すべてのデータベースをバックアップ先 (DR)[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンス。</span><span class="sxs-lookup"><span data-stu-id="8ab77-112">Back up (full) all databases on the destination (DR) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s).</span></span>  
  
8.  <span data-ttu-id="8ab77-113">すべての復元 (完全)[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース バックアップ手順 7. で、ソース (運用)[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンス。</span><span class="sxs-lookup"><span data-stu-id="8ab77-113">Restore (full) all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases backed up in step 7 to the source (production) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s).</span></span>  
  
9. <span data-ttu-id="8ab77-114">マスター シークレット サーバーを含むすべての BizTalk server を再起動します。</span><span class="sxs-lookup"><span data-stu-id="8ab77-114">Restart all BizTalk servers including the master secret server.</span></span>  
  
10. <span data-ttu-id="8ab77-115">すべてを削除[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-移行先 (DR) 上のデータベースの関連[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンス。</span><span class="sxs-lookup"><span data-stu-id="8ab77-115">Drop all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]-related databases on the destination (DR) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s).</span></span>  
  
11. <span data-ttu-id="8ab77-116">ソースのバックアップ ジョブを有効にする[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンス。</span><span class="sxs-lookup"><span data-stu-id="8ab77-116">Enable backup jobs on the source [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s).</span></span>  
  
12. <span data-ttu-id="8ab77-117">宛先 (DR) の復元ジョブを有効にする[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンス。</span><span class="sxs-lookup"><span data-stu-id="8ab77-117">Enable restore jobs on the destination (DR) [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance(s).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ab77-118">参照</span><span class="sxs-lookup"><span data-stu-id="8ab77-118">See Also</span></span>  
 [<span data-ttu-id="8ab77-119">バックアップおよび Restore2 に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="8ab77-119">Advanced Information About Backup and Restore2</span></span>](../technical-guides/advanced-information-about-backup-and-restore2.md)