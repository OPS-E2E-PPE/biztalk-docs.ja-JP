---
title: "不完全なアクティビティ インスタンスを解決するには |Microsoft ドキュメント"
description: "BAM アクティビティ インスタンスが BizTalk Server で BAMPrimaryImport データベースをバックアップした後アクティブなまま"
ms.custom: 
ms.date: 01/17/2018
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8adbcb66-58ad-42c5-ba16-7dc07572099e
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 616ba096062da7ede8d78122e5a6faaca2befdc4
ms.sourcegitcommit: 20d33d8b74bf129a8d1a506ac4a1ad960184966d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/18/2018
---
# <a name="resolve-incomplete-bam-activity-instances---biztalk-server"></a><span data-ttu-id="94b69-103">不完全な BAM アクティビティ インスタンスを解決するには、BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="94b69-103">Resolve incomplete BAM activity instances - BizTalk Server</span></span>
<span data-ttu-id="94b69-104">BAM では、不完全なアクティビティ インスタンスのデータを格納特殊な *アクティブなインスタンス* BAMPrimaryImport データベースのテーブルです。</span><span class="sxs-lookup"><span data-stu-id="94b69-104">BAM stores data for incomplete activity instances in a special *active instance* table in the BAMPrimaryImport database.</span></span>  
  
 <span data-ttu-id="94b69-105">インスタンス レコードの一部では、BAMPrimaryImport データベースの最後のバックアップする前に開始は、バックアップ後に完了することが、これらのレコードはアクティブ インスタンス テーブルに残ります。</span><span class="sxs-lookup"><span data-stu-id="94b69-105">If some instance records were started before the last backup of the BAMPrimaryImport database but completed after the backup, those instance records remain in an active instance table.</span></span> <span data-ttu-id="94b69-106">これは、BAMPrimaryImport データベースが復元された後、これらのインスタンスの完了レコードが失われるからです。</span><span class="sxs-lookup"><span data-stu-id="94b69-106">This is because after the BAMPrimaryImport database is restored, the completion records for these instances are lost.</span></span>  
  
 <span data-ttu-id="94b69-107">アクティブ インスタンス テーブルに残ったレコードが、BAM の正常な機能を阻害することはありませんが、これらのレコードは "完了" としてマークし、アクティブ インスタンス テーブルから取り除くことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="94b69-107">Although the records in the active instance table do not prevent BAM from functioning properly, we recommend that you mark these records as "completed," and then move them out of the active instance table.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="94b69-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="94b69-108">Prerequisites</span></span>  
<span data-ttu-id="94b69-109">BizTalk Server 管理者グループのメンバーとしてサインインします。</span><span class="sxs-lookup"><span data-stu-id="94b69-109">Sign in as a member of the BizTalk Server Administrators group.</span></span>  
  
## <a name="create-a-list-of-incomplete-activityids"></a><span data-ttu-id="94b69-110">不完全な activityid 検索リストを作成します。</span><span class="sxs-lookup"><span data-stu-id="94b69-110">Create a list of incomplete ActivityIDs</span></span> 
  
1.  <span data-ttu-id="94b69-111">BAMPrimaryImport データベースに対し、次のクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="94b69-111">Run the following query against the BAMPrimaryImport database:</span></span>  
  
    ```  
    Select ActivityID from bam_<ActivityName>_Active where IsComplete = 0  
    ```  
  
2.  <span data-ttu-id="94b69-112">外部システムからデータには、アクティビティ インスタンスが実際に完了したことが示されている場合は、インスタンスを手動で完了するには、以下のクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="94b69-112">If data from external systems indicates that the activity instance is in fact completed, run the following query to manually complete the instance:</span></span>  
  
    ```  
    begin transaction
    exec bam_<ActivityName>_PrimaryImport @ActivityID=N'<ActivityID>', @IsStartNew=0, @IsComplete=1  
    commit transaction
    ```  
  
> [!NOTE]
>  <span data-ttu-id="94b69-113">置き換えることにより、継続アクティビティを完了する同じ処理を行うことができる`ActivityID`で`ContinuationID`です。</span><span class="sxs-lookup"><span data-stu-id="94b69-113">You can follow the same process to complete a continuation activity by replacing `ActivityID` with `ContinuationID`.</span></span>  
> 
>  <span data-ttu-id="94b69-114">アクティブな継続トレースがメイン トレースに存在した場合、メイン トレースは、その継続トレースが完了するまでアクティブな状態のままとなります。</span><span class="sxs-lookup"><span data-stu-id="94b69-114">If the main trace has any active continuation traces, it remains active until the continuation traces are completed.</span></span>  

## <a name="remove-incomplete-instances"></a><span data-ttu-id="94b69-115">不完全なインスタンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="94b69-115">Remove incomplete instances</span></span>
<span data-ttu-id="94b69-116">不完全なアクティビティ インスタンスは、カスタムの SQL スクリプトを使用して、BAMPrimaryImport データベースから削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="94b69-116">You can also remove incomplete activity instances from the BAMPrimaryImport database using a custom SQL script.</span></span> <span data-ttu-id="94b69-117">参照してください[不完全なアクティビティ インスタンスを削除する](how-to-remove-incomplete-activity-instances.md)サンプルについてはします。</span><span class="sxs-lookup"><span data-stu-id="94b69-117">See [Remove incomplete activity instances](how-to-remove-incomplete-activity-instances.md) for a sample.</span></span>

## <a name="see-also"></a><span data-ttu-id="94b69-118">参照</span><span class="sxs-lookup"><span data-stu-id="94b69-118">See Also</span></span>  
 [<span data-ttu-id="94b69-119">BAM のバックアップと復元</span><span class="sxs-lookup"><span data-stu-id="94b69-119">Backing Up and Restoring BAM</span></span>](../core/backing-up-and-restoring-bam.md)
