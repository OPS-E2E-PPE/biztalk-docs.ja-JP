---
title: バックアップと、BizTalk Server データベースを復元 |Microsoft ドキュメント
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
ms.openlocfilehash: 44bbb9316f1d036551acba5441424bcce65c2549
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230370"
---
# <a name="backing-up-and-restoring-the-biztalk-server-databases"></a><span data-ttu-id="89aa6-102">バックアップと、BizTalk Server データベースの復元</span><span class="sxs-lookup"><span data-stu-id="89aa6-102">Backing Up and Restoring the BizTalk Server Databases</span></span>
<span data-ttu-id="89aa6-103">ここでは、BizTalk Server データベースをバックアップおよび復元する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="89aa6-103">This section provides information about how to back up and restore the BizTalk Server databases.</span></span> <span data-ttu-id="89aa6-104">ハードウェア障害が発生したときに整合性のある BizTalk Server 環境を復元するためには、このセクションの手順に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="89aa6-104">You should follow the procedures in this section to ensure your ability to restore a consistent BizTalk Server environment in the event of a hardware failure.</span></span> <span data-ttu-id="89aa6-105">BizTalk Server では、いくつものデータベースに関わる分散トランザクションが実行されるため、すべてのデータベースのバックアップおよび復元が不可欠です。</span><span class="sxs-lookup"><span data-stu-id="89aa6-105">BizTalk Server performs distributed transactions across databases, so it is critical that you back up and then restore all databases.</span></span>  
  
 <span data-ttu-id="89aa6-106">BizTalk Server には、完全バックアップおよびログ バックアップをトランザクション ログ マーキングと共に使用する、カスタマイズされたバックアップ プロセスが必要です。</span><span class="sxs-lookup"><span data-stu-id="89aa6-106">BizTalk Server requires a customized backup process that uses full database backups and log backups in conjunction with transactional log marking.</span></span> <span data-ttu-id="89aa6-107">このプロセスについては、次を参照してください。[マークされたトランザクション、完全バックアップ、およびログ バックアップ](../core/marked-transactions-full-backups-and-log-backups.md)です。</span><span class="sxs-lookup"><span data-stu-id="89aa6-107">For information about this process, see [Marked Transactions, Full Backups, and Log Backups](../core/marked-transactions-full-backups-and-log-backups.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="89aa6-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="89aa6-108">In This Section</span></span>  
  
-   [<span data-ttu-id="89aa6-109">チェックリスト: をバックアップし、BizTalk Server データベースの復元</span><span class="sxs-lookup"><span data-stu-id="89aa6-109">Checklist: Back Up and Restore BizTalk Server Databases</span></span>](../core/checklist-back-up-and-restore-biztalk-server-databases.md)  
  
-   [<span data-ttu-id="89aa6-110">バックアップおよびデータベースを復元するためのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="89aa6-110">Best Practices for Backing Up and Restoring Databases</span></span>](../core/best-practices-for-backing-up-and-restoring-databases.md)  
  
-   [<span data-ttu-id="89aa6-111">BizTalk Server データベースのバックアップと復元</span><span class="sxs-lookup"><span data-stu-id="89aa6-111">Backing Up and Restoring BizTalk Server Databases</span></span>](../core/backing-up-and-restoring-biztalk-server-databases.md)  
  
-   [<span data-ttu-id="89aa6-112">バックアップおよび BAM を復元します。</span><span class="sxs-lookup"><span data-stu-id="89aa6-112">Backing Up and Restoring BAM</span></span>](../core/backing-up-and-restoring-bam.md)  
  
-   [<span data-ttu-id="89aa6-113">データ損失の解決</span><span class="sxs-lookup"><span data-stu-id="89aa6-113">Resolving Data Loss</span></span>](../core/resolving-data-loss.md)  
  
-   [<span data-ttu-id="89aa6-114">バックアップと復元に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="89aa6-114">Advanced Information About Backup and Restore</span></span>](../core/advanced-information-about-backup-and-restore1.md)