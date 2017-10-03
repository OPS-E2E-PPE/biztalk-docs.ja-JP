---
title: "不完全なアクティビティ インスタンスを解決する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- instances, incomplete [BAM]
- restoring, BAM
- Primary Import database [BAM], incomplete instances
- restoring [BAM], Primary Import database
- Primary Import database [BAM], restoring
- BAM, restoring
ms.assetid: 8adbcb66-58ad-42c5-ba16-7dc07572099e
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81df9ee8b004a2dbd4a672eecb4f34894421a432
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-resolve-incomplete-activity-instances"></a><span data-ttu-id="ffa6c-102">不完全なアクティビティ インスタンスを解決する方法</span><span class="sxs-lookup"><span data-stu-id="ffa6c-102">How to Resolve Incomplete Activity Instances</span></span>
<span data-ttu-id="ffa6c-103">BAM では、不完全なアクティビティ インスタンスのデータを格納特殊な*アクティブ インスタンス*BAMPrimaryImport データベースのテーブルにします。</span><span class="sxs-lookup"><span data-stu-id="ffa6c-103">BAM stores data for incomplete activity instances in a special *active instance* table in the BAMPrimaryImport database.</span></span>  
  
 <span data-ttu-id="ffa6c-104">インスタンス レコードの一部が開始し、BAMPrimaryImport データベースの最後のバックアップの前に、バックアップ後に、これらのレコードはアクティブ インスタンス テーブルに残ります。</span><span class="sxs-lookup"><span data-stu-id="ffa6c-104">If some instance records were started before the last backup of the BAMPrimaryImport database but completed after the backup, those instance records remain in an active instance table.</span></span> <span data-ttu-id="ffa6c-105">これは、BAMPrimaryImport データベースが復元された後、これらのインスタンスの完了レコードが失われるからです。</span><span class="sxs-lookup"><span data-stu-id="ffa6c-105">This is because after the BAMPrimaryImport database is restored, the completion records for these instances are lost.</span></span>  
  
 <span data-ttu-id="ffa6c-106">アクティブ インスタンス テーブルに残ったレコードが、BAM の正常な機能を阻害することはありませんが、これらのレコードは "完了" としてマークし、アクティブ インスタンス テーブルから取り除くことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ffa6c-106">Although the records in the active instance table do not prevent BAM from functioning properly, we recommend that you mark these records as "completed," and then move them out of the active instance table.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ffa6c-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="ffa6c-107">Prerequisites</span></span>  
 <span data-ttu-id="ffa6c-108">ここで示す手順を実行するには、BizTalk Server Administrators グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ffa6c-108">You must be logged on as a member of the BizTalk Server Administrators group to perform this procedure.</span></span>  
  
### <a name="to-generate-a-list-of-incomplete-activityids-for-an-activity"></a><span data-ttu-id="ffa6c-109">特定のアクティビティに対する不完全な ActivityID を検索するには</span><span class="sxs-lookup"><span data-stu-id="ffa6c-109">To generate a list of incomplete ActivityIDs for an activity</span></span>  
  
1.  <span data-ttu-id="ffa6c-110">BAMPrimaryImport データベースに対し、次のクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="ffa6c-110">Run the following query against the BAMPrimaryImport database:</span></span>  
  
    ```  
    Select ActivityID from bam_<ActivityName>_Active where IsComplete = 0  
    ```  
  
2.  <span data-ttu-id="ffa6c-111">外部システムからデータがアクティビティのインスタンスが実際に完了したことを示している場合は、インスタンスを手動で完了する次のクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="ffa6c-111">If data from external systems indicates that the activity instance is in fact completed, run the following query to manually complete the instance:</span></span>  
  
    ```  
    exec bam_<ActivityName>_PrimaryImport @ActivityID=N'<ActivityID>', @IsStartNew=0, @IsComplete=1  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="ffa6c-112">ActivityID を ContinuationID に置き換えることにより、同様の手順で、継続アクティビティを完了させることができます。</span><span class="sxs-lookup"><span data-stu-id="ffa6c-112">You can follow the same process to complete a continuation activity by replacing ActivityID with ContinuationID.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ffa6c-113">アクティブな継続トレースがメイン トレースに存在した場合、メイン トレースは、その継続トレースが完了するまでアクティブな状態のままとなります。</span><span class="sxs-lookup"><span data-stu-id="ffa6c-113">If the main trace has any active continuation traces, it remains active until the continuation traces are completed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffa6c-114">参照</span><span class="sxs-lookup"><span data-stu-id="ffa6c-114">See Also</span></span>  
 [<span data-ttu-id="ffa6c-115">バックアップおよび BAM を復元します。</span><span class="sxs-lookup"><span data-stu-id="ffa6c-115">Backing Up and Restoring BAM</span></span>](../core/backing-up-and-restoring-bam.md)