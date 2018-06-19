---
title: バックアップ ファイルが破損 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc48197c-944a-4f0a-ba01-8e1d91c88ad3
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fda5acae756fd2c4d0afc0263bc723af3ba77e15
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299634"
---
# <a name="corrupt-backup-files"></a><span data-ttu-id="9d37e-102">バックアップ ファイルが壊れています</span><span class="sxs-lookup"><span data-stu-id="9d37e-102">Corrupt Backup Files</span></span>
<span data-ttu-id="9d37e-103">バックアップ ファイルには、破損している、壊れているか、または不足している可能性がありますになります。</span><span class="sxs-lookup"><span data-stu-id="9d37e-103">A backup file may become corrupt, damaged, or missing.</span></span> <span data-ttu-id="9d37e-104">このような場合に、少なくとも 1 つのファイルは復元できません。</span><span class="sxs-lookup"><span data-stu-id="9d37e-104">If this occurs, at least one file cannot be restored.</span></span> <span data-ttu-id="9d37e-105">エラーがあって、システム上の復元ジョブは、[次へ] の有効な完全バックアップ セットを検索します。</span><span class="sxs-lookup"><span data-stu-id="9d37e-105">The restore job on the system that suffered the failure searches for the next valid full backup set.</span></span> <span data-ttu-id="9d37e-106">ほとんどの場合、ソース システム上の完全バックアップを強制する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d37e-106">In most cases it will be necessary to force a full backup on the source system.</span></span> <span data-ttu-id="9d37e-107">このようなセットが存在しない場合、復元ジョブが失敗して、以降の実行ごとは、有効な完全バックアップ セットが到着するまでにも失敗します。</span><span class="sxs-lookup"><span data-stu-id="9d37e-107">If no such set exists, the restore job fails and each subsequent run also fails until a valid full backup set arrives.</span></span> <span data-ttu-id="9d37e-108">セットが存在する場合、環境を修復に使用されます。</span><span class="sxs-lookup"><span data-stu-id="9d37e-108">If a set does exist, it is used to repair the environment.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9d37e-109">方式により[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]可能であれば、ファイルにバックアップ データを書き込みますを[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データの実際の書き込み中にバックアップが失敗した場合でも正常に完了が報告されます。</span><span class="sxs-lookup"><span data-stu-id="9d37e-109">Due to the manner in which [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] writes backup data to a file, it is possible that [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] will report successful completion even if the backup failed during the actual writing of the data.</span></span> <span data-ttu-id="9d37e-110">このシナリオでは、ディスクに書き込まれているが、コンピューターおよびネットワークの障害にローカルでないまたは中断が発生したときに、主に発生します。</span><span class="sxs-lookup"><span data-stu-id="9d37e-110">This scenario primarily occurs when the disk being written to is not local to the computer and a network failure or interruption occurs.</span></span> <span data-ttu-id="9d37e-111">一般的な予防策として、バックアップ ジョブの実行中に、ネットワーク障害が発生する場合強制的に完全バックアップ ネットワーク接続の問題が解決された後です。</span><span class="sxs-lookup"><span data-stu-id="9d37e-111">As a general precaution, if a network failure occurs while the backup job is running, force a full backup after the network connectivity problem is resolved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d37e-112">参照</span><span class="sxs-lookup"><span data-stu-id="9d37e-112">See Also</span></span>  
 [<span data-ttu-id="9d37e-113">ログ配布のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="9d37e-113">Troubleshooting Log Shipping</span></span>](../technical-guides/troubleshooting-log-shipping.md)