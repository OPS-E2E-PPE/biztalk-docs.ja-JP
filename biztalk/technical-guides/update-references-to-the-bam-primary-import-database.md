---
title: BAM プライマリ インポート データベースへの参照の更新 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3da3b545-0d81-491b-bc37-0a980a7814b6
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ba37a32c82967e84b61bb46c58c62af9bf23b1b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22301826"
---
# <a name="update-references-to-the-bam-primary-import-database"></a><span data-ttu-id="f7b05-102">BAM プライマリ インポート データベースへの参照を更新します。</span><span class="sxs-lookup"><span data-stu-id="f7b05-102">Update References to the BAM Primary Import Database</span></span>
<span data-ttu-id="f7b05-103">BAM プライマリ インポート データベースがバックアップされていると、システムまたはデータに障害が発生したときには、別のコンピュータにバックアップを復元でき、さらにその名前を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="f7b05-103">If you backed up your BAM Primary Import database in the event of a system or data failure, you can restore that backup to a different computer and rename the backup.</span></span>  
  
 <span data-ttu-id="f7b05-104">BAM イベント バス サービスでは、イベント データをメッセージ ボックス データベースから BAM プライマリ インポート データベースに移動します。</span><span class="sxs-lookup"><span data-stu-id="f7b05-104">The BAM Event Bus service moves event data from the MessageBox database to the BAM Primary Import database.</span></span> <span data-ttu-id="f7b05-105">BAM イベント バス サービスには、予期しない障害が発生した場合にデータを失わずに復旧して再起動するためのフォールト トレランス ロジックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f7b05-105">The BAM Event Bus service includes fault tolerance logic that enables it to recover and restart from an unexpected failure without losing any data.</span></span> <span data-ttu-id="f7b05-106">BAM イベント バス サービスの詳細については、トピックを参照してください。 [BAM イベント バス サービスを管理する](http://go.microsoft.com/fwlink/?LinkID=154194)(http://go.microsoft.com/fwlink/?LinkID=154194)。</span><span class="sxs-lookup"><span data-stu-id="f7b05-106">For more information about the BAM Event Bus service, see the topic [Managing the BAM Event Bus Service](http://go.microsoft.com/fwlink/?LinkID=154194) (http://go.microsoft.com/fwlink/?LinkID=154194).</span></span>  
  
 <span data-ttu-id="f7b05-107">BAM プライマリ インポート データベースを復元する」の手順を実行[BizTalk Server のバックアップ ジョブでデータベースを復元する方法](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)です。</span><span class="sxs-lookup"><span data-stu-id="f7b05-107">To restore the BAM Primary Import database, perform the steps in [How to Restore Databases in the Backup BizTalk Server Job](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md).</span></span> <span data-ttu-id="f7b05-108">さらに、新しいサーバー名とデータベース名と BAM SSIS パッケージを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7b05-108">In addition, you must update the BAM SSIS packages with the new server name and database name.</span></span>  
  
## <a name="how-to-update-references-to-bam-primary-import-database"></a><span data-ttu-id="f7b05-109">BAM プライマリ インポート データベースへの参照を更新する方法</span><span class="sxs-lookup"><span data-stu-id="f7b05-109">How to Update References to BAM Primary Import Database</span></span>  
 <span data-ttu-id="f7b05-110">BAM プライマリ インポート データベースへの参照を更新する方法の詳細について[新しい BAM プライマリ インポート データベースへの参照の更新](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_BAMPIRef)です。</span><span class="sxs-lookup"><span data-stu-id="f7b05-110">For instructions on how to update references to BAM Primary Import database, [Updating References to the New BAM Primary Import Database](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_BAMPIRef).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7b05-111">参照</span><span class="sxs-lookup"><span data-stu-id="f7b05-111">See Also</span></span>  
 [<span data-ttu-id="f7b05-112">BAM 分析をバックアップして、追跡分析サーバー データベース</span><span class="sxs-lookup"><span data-stu-id="f7b05-112">Backing Up the BAM Analysis and Tracking Analysis Server Databases</span></span>](../technical-guides/backing-up-the-bam-analysis-and-tracking-analysis-server-databases.md)