---
title: バックアップを復元の履歴の表示 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- restoring, history
- backing up, history
ms.assetid: 8852befa-b8e7-469d-b014-75c881907442
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f4685512b0dc841bd0cbbd7673ed1bf4d8b130a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65320856"
---
# <a name="viewing-the-history-of-restored-backups"></a><span data-ttu-id="7174f-102">バックアップ復元履歴の表示</span><span class="sxs-lookup"><span data-stu-id="7174f-102">Viewing the History of Restored Backups</span></span>
<span data-ttu-id="7174f-103">最後に復元に成功したバックアップ セットを確認するには、Master.dbo.bts_LogShippingHistory テーブルの内容を調べます。</span><span class="sxs-lookup"><span data-stu-id="7174f-103">To determine the last successful backup set restored, review the contents of the Master.dbo.bts_LogShippingHistory table.</span></span> <span data-ttu-id="7174f-104">このテーブルの内容は、バックアップ履歴の取得ジョブによって取得され、データベースの復元ジョブによって更新されます。</span><span class="sxs-lookup"><span data-stu-id="7174f-104">This table is populated by the Get Backup History job and updated by the Restore Databases job.</span></span> <span data-ttu-id="7174f-105">バックアップの復元に成功した場合、Restored 列に 1 が、RestoredDateTime に現在の日時が格納されます。</span><span class="sxs-lookup"><span data-stu-id="7174f-105">When a backup is successfully restored, the Restored column is set to 1 and the RestoredDateTime is set to the current date and time.</span></span>  
  
 <span data-ttu-id="7174f-106">特定のバックアップ セットから、復元対象のすべてのデータベースが正しくサーバーに復元された場合、そのバックアップ セットの ID が Master.dbo.bts_LogShippingLastRestoreSet テーブルに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="7174f-106">When all of the databases being restored to the server from a particular backup set have been successfully restored, that backup set ID is written to the Master.dbo.bts_LogShippingLastRestoreSet table.</span></span>  
  
## <a name="gaps-in-the-restore-process"></a><span data-ttu-id="7174f-107">復元プロセスのギャップ</span><span class="sxs-lookup"><span data-stu-id="7174f-107">Gaps in the restore process</span></span>  
 <span data-ttu-id="7174f-108">Master.dbo.bts_LogShippingHistory テーブルのレコードを確認すると、復元済みのバックアップ セット間にギャップが存在する場合があります。</span><span class="sxs-lookup"><span data-stu-id="7174f-108">When reviewing records in the Master.dbo.bts_LogShippingHistory table, you may find gaps in the sets restored.</span></span> <span data-ttu-id="7174f-109">これにはいくつかの理由が考えられます。</span><span class="sxs-lookup"><span data-stu-id="7174f-109">This can occur for several reasons.</span></span> <span data-ttu-id="7174f-110">ただし、ギャップが発生しても、復元先システム (つまり、バックアップ コンピュータ) の安定性を回復できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7174f-110">However, you can still recover the stability of your destination system (which are your backup computers), even when gaps have occurred.</span></span> <span data-ttu-id="7174f-111">復元先のシステムを修復するには、ギャップの後に完全バックアップ セットの復元が必要です。</span><span class="sxs-lookup"><span data-stu-id="7174f-111">A gap must be followed by a restore of a full backup set to repair the destination system.</span></span> <span data-ttu-id="7174f-112">ギャップの後に完全バックアップ セットの復元を行わないと、復元先の環境が不安定になります。</span><span class="sxs-lookup"><span data-stu-id="7174f-112">If a gap is not followed by a full backup set restore, the destination environment is not stable.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7174f-113">本来、完全バックアップを復元する目的は、データベースの初期状態を作成したり、ログ履歴バックアップ チェーンの問題を修復したりすることです。</span><span class="sxs-lookup"><span data-stu-id="7174f-113">Full backups are only restored to initially create the database and to repair problems in the log history backup chain.</span></span> <span data-ttu-id="7174f-114">完全バックアップ セットは、ログ バックアップ チェーンには含まれないため、通常、完全バックアップ セットから復元することはありません。</span><span class="sxs-lookup"><span data-stu-id="7174f-114">In most cases full backup sets are not restored, as they are not part of the log backup chain.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7174f-115">参照</span><span class="sxs-lookup"><span data-stu-id="7174f-115">See Also</span></span>  
 [<span data-ttu-id="7174f-116">バックアップおよび復元に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="7174f-116">Advanced Information About Backup and Restore</span></span>](../core/advanced-information-about-backup-and-restore1.md)