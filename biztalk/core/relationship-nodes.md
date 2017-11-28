---
title: "リレーションシップ ノード |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- definition files [BAM], relationships
- definition files [BAM], Tracking Profile Editor
- Relationship nodes [Tracking Profile Editor]
- activities [BAM], relationships
- activities [BAM], Tracking Profile Editor
- Tracking Profile Editor, node descriptions
- Tracking Profile Editor, definition files [BAM]
ms.assetid: 74090133-24d1-4aba-a4fc-f12d19c881fb
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f670c62b4e883b124d849ab61396f6f5216e7182
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="relationship-nodes"></a><span data-ttu-id="ebb2e-102">リレーションシップ ノード</span><span class="sxs-lookup"><span data-stu-id="ebb2e-102">Relationship Nodes</span></span>
<span data-ttu-id="ebb2e-103">アクティビティ定義ファイルに複数のアクティビティが含まれている場合は常に、リレーションシップ フォルダーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="ebb2e-103">Relationship folders are used whenever an activity definition file contains more than one activity.</span></span> <span data-ttu-id="ebb2e-104">フォルダー名は、関連するアクティビティと同じ名前になります。</span><span class="sxs-lookup"><span data-stu-id="ebb2e-104">The names of the folders match the name of the associated activity.</span></span> <span data-ttu-id="ebb2e-105">リレーションシップ フォルダーの名前と関連するアクティビティのアクティビティ ID を照合し、データ項目の値を照合して、リンクを形成します。</span><span class="sxs-lookup"><span data-stu-id="ebb2e-105">You form the link by matching the name of the relationship folder to the activity ID of the related activity and by matching the values for the data items.</span></span> <span data-ttu-id="ebb2e-106">リレーションシップは、それぞれ個別のノードを使用して定義します。</span><span class="sxs-lookup"><span data-stu-id="ebb2e-106">You define each relationship using a separate node.</span></span>  
  
## <a name="working-with-relationship-nodes"></a><span data-ttu-id="ebb2e-107">リレーションシップ ノードの操作</span><span class="sxs-lookup"><span data-stu-id="ebb2e-107">Working with Relationship nodes</span></span>  
 <span data-ttu-id="ebb2e-108">アクティビティ間のデータ項目をリンクする一意のインスタンス識別子を指定するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ebb2e-108">To indicate the unique instance identifier that links the data item between activities:</span></span>  
  
-   <span data-ttu-id="ebb2e-109">メインのオーケストレーションの ActivityId ノードには、データ項目をマップします。</span><span class="sxs-lookup"><span data-stu-id="ebb2e-109">Map a data item to the ActivityId node of the main orchestration.</span></span>  
  
-   <span data-ttu-id="ebb2e-110">上記手順と同じ名前のデータ項目を、関連するアクティビティのリレーションシップ ノードにドラッグ アンド ドロップします。</span><span class="sxs-lookup"><span data-stu-id="ebb2e-110">Drag and drop a data item with the same name as above to the Relationship node in the related activity.</span></span> <span data-ttu-id="ebb2e-111">リレーションシップ ノードの名前は、メイン アクティビティのアクティビティ ノードと同じです。</span><span class="sxs-lookup"><span data-stu-id="ebb2e-111">The Relationship node has the same name as the Activity node of the main activity.</span></span>  
  
 <span data-ttu-id="ebb2e-112">たとえば、サンプル シナリオに、RefinanceOrchestration というオーケストレーションで表現される、関連はあるが独立したビジネス プロセスが存在するとします。</span><span class="sxs-lookup"><span data-stu-id="ebb2e-112">For example, in the sample scenario, there could be a related but separate business process represented in an orchestration called RefinanceOrchestration.</span></span> <span data-ttu-id="ebb2e-113">このオーケストレーションには、LoanRefinance アクティビティ ノード、Refinance ActivityID のほか、評価要求受信などのオーケストレーション図形が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ebb2e-113">That orchestration could contain a LoanRefinance Activity node, a Refinance ActivityID, and orchestration shapes such as Receive Appraisal Request.</span></span> <span data-ttu-id="ebb2e-114">ただし、リレーションシップ ノードとリレーションシップ ID は、元の LoanProcess アクティビティへのリンクを示す LoanID になります。</span><span class="sxs-lookup"><span data-stu-id="ebb2e-114">The Relationship node and relationship ID, however, could be LoanID, indicating the link to the original LoanProcess activity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebb2e-115">参照</span><span class="sxs-lookup"><span data-stu-id="ebb2e-115">See Also</span></span>  
 [<span data-ttu-id="ebb2e-116">TPE アクティビティ ビューのノード</span><span class="sxs-lookup"><span data-stu-id="ebb2e-116">TPE Activity View Nodes</span></span>](../core/tpe-activity-view-nodes.md)