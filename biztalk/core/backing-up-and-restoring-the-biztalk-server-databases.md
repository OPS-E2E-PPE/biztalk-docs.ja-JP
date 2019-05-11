---
title: バックアップおよび BizTalk Server データベースを復元する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- backing up, BizTalk Server
- backing up, transaction logs
- maintaining, restoring
- restoring, BizTalk Server
- maintaining, backing up
- transaction logs
ms.assetid: 7c08ce19-614c-4728-8dde-c40d4052339e
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6fbf2bfec008d48623aa5238d1208d55460f0cc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358673"
---
# <a name="backing-up-and-restoring-the-biztalk-server-databases"></a><span data-ttu-id="22473-102">バックアップおよび BizTalk Server データベースを復元します。</span><span class="sxs-lookup"><span data-stu-id="22473-102">Backing Up and Restoring the BizTalk Server Databases</span></span>
<span data-ttu-id="22473-103">このセクションでは、バックアップして、BizTalk Server データベースを復元する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="22473-103">This section provides information about how to back up and restore the BizTalk Server databases.</span></span> <span data-ttu-id="22473-104">ハードウェア障害が発生した場合、一貫性のある BizTalk Server 環境を復元することを確認するには、このセクションの手順が従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="22473-104">You should follow the procedures in this section to ensure your ability to restore a consistent BizTalk Server environment in the event of a hardware failure.</span></span> <span data-ttu-id="22473-105">BizTalk Server では、重要なは、バックアップを作成し、すべてのデータベースを復元するために、データベース間で分散トランザクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="22473-105">BizTalk Server performs distributed transactions across databases, so it is critical that you back up and then restore all databases.</span></span>  
  
 <span data-ttu-id="22473-106">BizTalk Server では、カスタマイズされたバックアップ プロセスとトランザクション ログ マーキングと共にデータベースの完全バックアップとログ バックアップを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22473-106">BizTalk Server requires a customized backup process that uses full database backups and log backups in conjunction with transactional log marking.</span></span> <span data-ttu-id="22473-107">このプロセスの詳細については、次を参照してください。[マークされたトランザクション、完全バックアップ、およびログ バックアップ](../core/marked-transactions-full-backups-and-log-backups.md)します。</span><span class="sxs-lookup"><span data-stu-id="22473-107">For information about this process, see [Marked Transactions, Full Backups, and Log Backups](../core/marked-transactions-full-backups-and-log-backups.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="22473-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="22473-108">In This Section</span></span>  
  
-   [<span data-ttu-id="22473-109">チェックリスト:バックアップおよび BizTalk Server データベースを復元します。</span><span class="sxs-lookup"><span data-stu-id="22473-109">Checklist: Back Up and Restore BizTalk Server Databases</span></span>](../core/checklist-back-up-and-restore-biztalk-server-databases.md)  
  
-   [<span data-ttu-id="22473-110">データベースのバックアップと復元のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="22473-110">Best Practices for Backing Up and Restoring Databases</span></span>](../core/best-practices-for-backing-up-and-restoring-databases.md)  
  
-   [<span data-ttu-id="22473-111">バックアップおよび BizTalk Server データベースを復元します。</span><span class="sxs-lookup"><span data-stu-id="22473-111">Backing Up and Restoring BizTalk Server Databases</span></span>](../core/backing-up-and-restoring-biztalk-server-databases.md)  
  
-   [<span data-ttu-id="22473-112">BAM のバックアップと復元</span><span class="sxs-lookup"><span data-stu-id="22473-112">Backing Up and Restoring BAM</span></span>](../core/backing-up-and-restoring-bam.md)  
  
-   [<span data-ttu-id="22473-113">データ損失の解決</span><span class="sxs-lookup"><span data-stu-id="22473-113">Resolving Data Loss</span></span>](../core/resolving-data-loss.md)  
  
-   [<span data-ttu-id="22473-114">バックアップおよび復元に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="22473-114">Advanced Information About Backup and Restore</span></span>](../core/advanced-information-about-backup-and-restore1.md)