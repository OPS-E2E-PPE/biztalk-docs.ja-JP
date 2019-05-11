---
title: 進行中トランザクションを BAM で完了としてマークする |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, data recovery
- data recovery, BAM
- BAM, data loss
- data loss, BAM
ms.assetid: 8f734953-483a-481a-9ded-b48923859199
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e975893867906d9f9570741e780abfcf10625f30
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65531106"
---
# <a name="marking-in-progress-transactions-as-complete-in-bam"></a><span data-ttu-id="4eb4c-102">BAM の進行中トランザクションを "完了" としてマークする</span><span class="sxs-lookup"><span data-stu-id="4eb4c-102">Marking In-Progress Transactions as Complete in BAM</span></span>
<span data-ttu-id="4eb4c-103">ビジネス アクティビティ監視 (BAM) は、特殊なアクティブ インスタンス テーブル内の不完全なトレース インスタンスのデータを保持します。</span><span class="sxs-lookup"><span data-stu-id="4eb4c-103">Business Activity Monitoring (BAM) keeps data for incomplete trace instances in a special active instance table.</span></span> <span data-ttu-id="4eb4c-104">インスタンス レコードの一部では、最後のバックアップの前に開始しましたが、バックアップ後に完了した、いるこれらのレコードはアクティブ インスタンス テーブルに残ります。</span><span class="sxs-lookup"><span data-stu-id="4eb4c-104">If some instance records were started before the last backup but completed after the backup, those records will remain in the active instance table.</span></span> <span data-ttu-id="4eb4c-105">これができない、システムが機能してから、アクティブなインスタンス テーブルから移動できるようにを完了すると、これらのレコード手動でマークできます。</span><span class="sxs-lookup"><span data-stu-id="4eb4c-105">Although this does not prevent the system from functioning, you can manually mark these records as completed so that they can be moved out of the active instance table.</span></span>  
  
 <span data-ttu-id="4eb4c-106">BAM プライマリ インポート データベースに対して次のクエリを発行して、特定のアクティビティに対する不完全な Activityid の一覧を決定できます。</span><span class="sxs-lookup"><span data-stu-id="4eb4c-106">A list of incomplete ActivityIDs for a given activity can be determined by issuing the following query against the BAM Primary Import database:</span></span>  
  
```  
Select ActivityID from bam_<ActivityName> where IsComplete = 0  
```  
  
 <span data-ttu-id="4eb4c-107">外部システムからのデータは、アクティビティ インスタンスが完了したことを示す場合、は、手動でインスタンスを完了する次のクエリを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4eb4c-107">If data from external systems indicates that the activity instance is complete, you can use the following query to manually complete the instance:</span></span>  
  
```  
exec bam_<ActivityName>_PrimaryImport @ActivityID=N'<ActivityID>', @IsStartNew=0, @IsComplete=1  
```  
  
## <a name="see-also"></a><span data-ttu-id="4eb4c-108">参照</span><span class="sxs-lookup"><span data-stu-id="4eb4c-108">See Also</span></span>  
 [<span data-ttu-id="4eb4c-109">データ損失の解決</span><span class="sxs-lookup"><span data-stu-id="4eb4c-109">Resolving Data Loss</span></span>](../core/resolving-data-loss.md)