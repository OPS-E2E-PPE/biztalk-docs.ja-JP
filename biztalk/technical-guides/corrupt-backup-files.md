---
title: 破損したバックアップ ファイル |Microsoft Docs
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
ms.openlocfilehash: 5947b527dea1206255daf52f128569fd7a4f659c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987915"
---
# <a name="corrupt-backup-files"></a><span data-ttu-id="a5547-102">バックアップ ファイルが壊れています</span><span class="sxs-lookup"><span data-stu-id="a5547-102">Corrupt Backup Files</span></span>
<span data-ttu-id="a5547-103">バックアップ ファイルは、破損している、壊れているか、または不明になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a5547-103">A backup file may become corrupt, damaged, or missing.</span></span> <span data-ttu-id="a5547-104">このような場合は、少なくとも 1 つのファイルを復元できません。</span><span class="sxs-lookup"><span data-stu-id="a5547-104">If this occurs, at least one file cannot be restored.</span></span> <span data-ttu-id="a5547-105">エラーを検出しました。 システム上の復元ジョブは、[次へ] の有効な完全バックアップ セットを検索します。</span><span class="sxs-lookup"><span data-stu-id="a5547-105">The restore job on the system that suffered the failure searches for the next valid full backup set.</span></span> <span data-ttu-id="a5547-106">ほとんどの場合、ソース システムの完全バックアップを強制する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5547-106">In most cases it will be necessary to force a full backup on the source system.</span></span> <span data-ttu-id="a5547-107">そのようなセットが存在しない場合は、復元ジョブは失敗し、有効な完全バックアップ セットが到着するまでにもそれぞれ後続の実行が失敗しました。</span><span class="sxs-lookup"><span data-stu-id="a5547-107">If no such set exists, the restore job fails and each subsequent run also fails until a valid full backup set arrives.</span></span> <span data-ttu-id="a5547-108">セットが存在する場合、環境を修復に使用されます。</span><span class="sxs-lookup"><span data-stu-id="a5547-108">If a set does exist, it is used to repair the environment.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a5547-109">方法により[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ことは、ファイルにバックアップ データを書き込みますを[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データの実際の書き込み中にバックアップが失敗した場合でも正常に完了が報告されます。</span><span class="sxs-lookup"><span data-stu-id="a5547-109">Due to the manner in which [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] writes backup data to a file, it is possible that [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] will report successful completion even if the backup failed during the actual writing of the data.</span></span> <span data-ttu-id="a5547-110">このシナリオは、主に、ディスクに書き込まれる、ローカル コンピューターとネットワークの障害にまたは中断が発生した場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="a5547-110">This scenario primarily occurs when the disk being written to is not local to the computer and a network failure or interruption occurs.</span></span> <span data-ttu-id="a5547-111">一般的な念のため、バックアップ ジョブの実行中に、ネットワーク障害が発生した場合完全バックアップを強制、ネットワーク接続の問題が解決された後です。</span><span class="sxs-lookup"><span data-stu-id="a5547-111">As a general precaution, if a network failure occurs while the backup job is running, force a full backup after the network connectivity problem is resolved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5547-112">参照</span><span class="sxs-lookup"><span data-stu-id="a5547-112">See Also</span></span>  
 [<span data-ttu-id="a5547-113">ログ配布のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="a5547-113">Troubleshooting Log Shipping</span></span>](../technical-guides/troubleshooting-log-shipping.md)