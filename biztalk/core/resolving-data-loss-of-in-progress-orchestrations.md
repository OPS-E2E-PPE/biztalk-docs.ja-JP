---
title: 実行中のオーケストレーションのデータ損失の解決 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- data loss, MessageBox database
- data recovery
- data loss, recovery
- data loss, orchestrations
- data recovery, MessageBox database
- data recovery, orchestrations
- data loss, data recovery
- orchestrations, data recovery
- orchestrations, data loss
ms.assetid: dc6f1fd2-1976-40f2-ab57-41c7db40705e
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5eca757b80e31ee5db829d2d2079bf657d01079b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269002"
---
# <a name="resolving-data-loss-of-in-progress-orchestrations"></a><span data-ttu-id="a2bfe-102">進行中のオーケストレーションのデータ損失の解決</span><span class="sxs-lookup"><span data-stu-id="a2bfe-102">Resolving Data Loss of In-Progress Orchestrations</span></span>
<span data-ttu-id="a2bfe-103">メッセージ ボックス データベースには、現在進行中のオーケストレーションの状態情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="a2bfe-103">MessageBox databases contain the state of orchestrations that are currently in progress.</span></span> <span data-ttu-id="a2bfe-104">メッセージ ボックス データベースで正確にどのデータの損失があったかを検出する方法はありませんが、損失データの情報を収集するための手段はあります。</span><span class="sxs-lookup"><span data-stu-id="a2bfe-104">Although there is no way to tell exactly what data has been lost from the MessageBox databases, there are some steps you can take to gather information about the lost data:</span></span>  
  
-   <span data-ttu-id="a2bfe-105">復旧ポイント以降、現在のオーケストレーションで、どのメッセージが送信および受信されたか、また、どの外部システムが使用されたかを特定します。</span><span class="sxs-lookup"><span data-stu-id="a2bfe-105">Determine what messages have been sent and received in the current orchestrations, and what external systems have been used after the point of recovery.</span></span> <span data-ttu-id="a2bfe-106">たとえば、システムにメッセージおよびイベントの外部ログが保持されている場合は、そのログを調べます。</span><span class="sxs-lookup"><span data-stu-id="a2bfe-106">For example, if your system maintains an external log of messages and events, you can examine that log.</span></span> <span data-ttu-id="a2bfe-107">また、外部システムを手動でチェックして、どのようなアクティビティが発生したかを確認することも必要です。</span><span class="sxs-lookup"><span data-stu-id="a2bfe-107">You may also need to manually review the external systems to see what activities have occurred.</span></span>  
  
-   <span data-ttu-id="a2bfe-108">データ損失の原因を特定した後で、復元されたシステムの修正を開始できます。続行中のプロセス、終了して再開 (失われたアクティベーション メッセージを再送信) する必要のあるプロセス、および正常に完了していて終了できるプロセスを識別します。</span><span class="sxs-lookup"><span data-stu-id="a2bfe-108">After you determine the cause of the data loss, you can begin to correct the restored system, deciding which processes can continue, which processes must be terminated and restarted (by resubmitting the lost activation messages), and which processes have completed successfully and can be terminated.</span></span> <span data-ttu-id="a2bfe-109">このプロセスは、システムのアーキテクチャによって大きく異なります。これは、復旧計画の一部として考える必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2bfe-109">This process depends largely on the architecture of your system and must be considered as part of your system recovery planning.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2bfe-110">参照</span><span class="sxs-lookup"><span data-stu-id="a2bfe-110">See Also</span></span>  
 [<span data-ttu-id="a2bfe-111">データ損失の解決</span><span class="sxs-lookup"><span data-stu-id="a2bfe-111">Resolving Data Loss</span></span>](../core/resolving-data-loss.md)