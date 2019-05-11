---
title: 不完全なアクティビティ インスタンスの解決 |Microsoft Docs
description: BizTalk Server で BAMPrimaryImport データベースのバックアップ後に BAM アクティビティ インスタンスがアクティブなまま
ms.custom: ''
ms.date: 01/17/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8adbcb66-58ad-42c5-ba16-7dc07572099e
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 83510267108754985e9121bf473c25215b9a08a1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334918"
---
# <a name="resolve-incomplete-bam-activity-instances---biztalk-server"></a><span data-ttu-id="9a4fa-103">不完全な BAM アクティビティ インスタンスの BizTalk Server を解決します。</span><span class="sxs-lookup"><span data-stu-id="9a4fa-103">Resolve incomplete BAM activity instances - BizTalk Server</span></span>
<span data-ttu-id="9a4fa-104">BAM では、不完全なアクティビティ インスタンスのデータを格納特別な*アクティブなインスタンス*BAMPrimaryImport データベースのテーブル。</span><span class="sxs-lookup"><span data-stu-id="9a4fa-104">BAM stores data for incomplete activity instances in a special *active instance* table in the BAMPrimaryImport database.</span></span>  
  
 <span data-ttu-id="9a4fa-105">インスタンス レコードの一部が前に開始、BAMPrimaryImport データベースの最後のバックアップ、バックアップ後に完了した、これらのレコードは、アクティブ インスタンス テーブルに残ります。</span><span class="sxs-lookup"><span data-stu-id="9a4fa-105">If some instance records were started before the last backup of the BAMPrimaryImport database but completed after the backup, those instance records remain in an active instance table.</span></span> <span data-ttu-id="9a4fa-106">BAMPrimaryImport データベースを復元すると、これらのインスタンスの完了レコードは失われますためにです。</span><span class="sxs-lookup"><span data-stu-id="9a4fa-106">This is because after the BAMPrimaryImport database is restored, the completion records for these instances are lost.</span></span>  
  
 <span data-ttu-id="9a4fa-107">アクティブ インスタンス テーブル内のレコードが妨げられない BAM 正常に機能して、これらのレコードは「完了」としてマークしてから、アクティブなインスタンス テーブルから移動してお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9a4fa-107">Although the records in the active instance table do not prevent BAM from functioning properly, we recommend that you mark these records as "completed," and then move them out of the active instance table.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9a4fa-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="9a4fa-108">Prerequisites</span></span>  
<span data-ttu-id="9a4fa-109">BizTalk Server 管理者グループのメンバーとしてサインインします。</span><span class="sxs-lookup"><span data-stu-id="9a4fa-109">Sign in as a member of the BizTalk Server Administrators group.</span></span>  
  
## <a name="create-a-list-of-incomplete-activityids"></a><span data-ttu-id="9a4fa-110">不完全な Activityid のリストを作成します。</span><span class="sxs-lookup"><span data-stu-id="9a4fa-110">Create a list of incomplete ActivityIDs</span></span> 
  
1.  <span data-ttu-id="9a4fa-111">BAMPrimaryImport データベースに対して次のクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="9a4fa-111">Run the following query against the BAMPrimaryImport database:</span></span>  
  
    ```  
    Select ActivityID from bam_<ActivityName>_Active where IsComplete = 0  
    ```  
  
2.  <span data-ttu-id="9a4fa-112">外部システムからのデータは、アクティビティ インスタンスが実際に完了したことを示している場合は、インスタンスを手動で完了するのには、次のクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="9a4fa-112">If data from external systems indicates that the activity instance is in fact completed, run the following query to manually complete the instance:</span></span>  
  
    ```  
    begin transaction
    exec bam_<ActivityName>_PrimaryImport @ActivityID=N'<ActivityID>', @IsStartNew=0, @IsComplete=1  
    commit transaction
    ```  
  
> [!NOTE]
>  <span data-ttu-id="9a4fa-113">置き換えることで、継続アクティビティを完了すると同じ手順を実行できる`ActivityID`で`ContinuationID`します。</span><span class="sxs-lookup"><span data-stu-id="9a4fa-113">You can follow the same process to complete a continuation activity by replacing `ActivityID` with `ContinuationID`.</span></span>  
> 
>  <span data-ttu-id="9a4fa-114">メイン トレースは、アクティブな継続トレースがある、継続トレースが完了するまでにはアクティブです。</span><span class="sxs-lookup"><span data-stu-id="9a4fa-114">If the main trace has any active continuation traces, it remains active until the continuation traces are completed.</span></span>  

## <a name="remove-incomplete-instances"></a><span data-ttu-id="9a4fa-115">不完全なインスタンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="9a4fa-115">Remove incomplete instances</span></span>
<span data-ttu-id="9a4fa-116">不完全なアクティビティ インスタンスは、カスタム SQL スクリプトを使用して、BAMPrimaryImport データベースから削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="9a4fa-116">You can also remove incomplete activity instances from the BAMPrimaryImport database using a custom SQL script.</span></span> <span data-ttu-id="9a4fa-117">参照してください[不完全なアクティビティ インスタンスを削除](how-to-remove-incomplete-activity-instances.md)サンプルについては、します。</span><span class="sxs-lookup"><span data-stu-id="9a4fa-117">See [Remove incomplete activity instances](how-to-remove-incomplete-activity-instances.md) for a sample.</span></span>

## <a name="see-also"></a><span data-ttu-id="9a4fa-118">参照</span><span class="sxs-lookup"><span data-stu-id="9a4fa-118">See Also</span></span>  
 [<span data-ttu-id="9a4fa-119">BAM のバックアップと復元</span><span class="sxs-lookup"><span data-stu-id="9a4fa-119">Backing Up and Restoring BAM</span></span>](../core/backing-up-and-restoring-bam.md)
