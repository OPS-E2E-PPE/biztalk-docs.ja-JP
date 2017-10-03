---
title: "展開先の環境をクリーンアップ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8585853b-e625-48c3-a241-81ebf1be0e1e
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4023492bf79223b3ba6b1db5cedebadf88feb9c4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="cleaning-the-destination-environment"></a><span data-ttu-id="512fb-102">展開先の環境のクリーンアップ</span><span class="sxs-lookup"><span data-stu-id="512fb-102">Cleaning the Destination Environment</span></span>
<span data-ttu-id="512fb-103">復元ジョブには、解決できないエラーが発生すると、空の環境からそれを開始するために、送信先の環境をクリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="512fb-103">If the restore job encounters error conditions that cannot be resolved, clean the destination environment so that it can start from an empty environment.</span></span> <span data-ttu-id="512fb-104">ストアド プロシージャを実行している**sp_LogShippingClean** 、変換先の master データベースにある[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスは「クリーンアップ」送信先の環境。</span><span class="sxs-lookup"><span data-stu-id="512fb-104">Running the stored procedure **sp_LogShippingClean** located in the master database on the destination [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance will “clean” the destination environment.</span></span> <span data-ttu-id="512fb-105">この手順では、すべてのデータベースを削除し、指定されたソースの最後に復元されたデータ セットを削除します。</span><span class="sxs-lookup"><span data-stu-id="512fb-105">This procedure drops all databases and deletes the last restored data set for the specified source.</span></span>  
  
 <span data-ttu-id="512fb-106">この手順を実行する前に無効にする、 **BTS ログの配布 - データベースの復元**ジョブ (get 履歴のバックアップ ジョブは実行し続けます)。</span><span class="sxs-lookup"><span data-stu-id="512fb-106">Before running this procedure, disable the **BTS Log Shipping - Restore Databases** job (the get backup history job may continue running).</span></span> <span data-ttu-id="512fb-107">無効化の詳細については、 **BTS ログの配布 - データベースの復元**ジョブを参照してください[BizTalk Server のバックアップ ジョブでデータベースを復元する方法](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)です。</span><span class="sxs-lookup"><span data-stu-id="512fb-107">For more information about disabling the **BTS Log Shipping - Restore Databases** job see [How to Restore Databases in the Backup BizTalk Server Job](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md).</span></span> <span data-ttu-id="512fb-108">後に、 **sp_LogShippingClean**プロシージャが実行されて、次回、復元ジョブの実行時に、最新の完全バックアップ セット以降、有効なログのバックアップ セットが検出されます。</span><span class="sxs-lookup"><span data-stu-id="512fb-108">After the **sp_LogShippingClean** procedure is run, the next time the restore job runs it will find the most recent full backup set with a valid subsequent log backup set.</span></span> <span data-ttu-id="512fb-109">このセットが既に復元されている場合、復元ジョブをクリア、**リストア**設定および後続のすべての列を設定し、セットを復元する処理を実行し、します。</span><span class="sxs-lookup"><span data-stu-id="512fb-109">If this set has already been restored, the restore job clears the **Restored** column for the set and all subsequent sets and then proceeds with restoring the set.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="512fb-110">環境が消去された後に設定、最新の完全バックアップ ジョブを検索するため強制的に完全バックアップ元システムでこの手順を実行した後は、復元ジョブを実行する前にします。</span><span class="sxs-lookup"><span data-stu-id="512fb-110">Because the job looks for the most recent full backup set after the environment has been cleaned, force a full backup on the source system after running this procedure but before running the restore job.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="512fb-111">**Sp_LogShippingClean**さまざまなサーバーの設定が適用されているという観点から、相互に同期を保つために、指定したソース システムのデータベースの復元は、すべてのサーバー上の手順を繰り返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="512fb-111">The **sp_LogShippingClean** procedure must be repeated on all servers that are restoring databases for a given source system in order to keep the different servers in synch with each other in terms of which sets have been applied.</span></span>  
  
 <span data-ttu-id="512fb-112">実行する、 **sp_LogShippingClean**プロシージャ、すべての master データベースに接続[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]、障害回復の一部であるインスタンスがサイトし、では、次のコマンドを実行、**新しいクエリ**オプションで使用できる[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ごとの Management Studio[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンス。</span><span class="sxs-lookup"><span data-stu-id="512fb-112">To run the **sp_LogShippingClean** procedure, connect to the master database on all [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instances that are part of the disaster recovery site and execute the following command in the **New Query** option available in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Studio for each [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instance:</span></span>  
  
```  
sp_LogShippingClean 'SourceID'  
```  
  
 <span data-ttu-id="512fb-113">ここで**SourceID**運用環境で構成されている識別子に対応する[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンス。</span><span class="sxs-lookup"><span data-stu-id="512fb-113">where **SourceID** corresponds to the identifier configured on the production [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instances.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="512fb-114">参照</span><span class="sxs-lookup"><span data-stu-id="512fb-114">See Also</span></span>  
 [<span data-ttu-id="512fb-115">ログ配布のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="512fb-115">Troubleshooting Log Shipping</span></span>](../technical-guides/troubleshooting-log-shipping.md)