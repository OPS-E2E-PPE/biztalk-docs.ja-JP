---
title: リレーションシップ ノード |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce7acbed8914fa7af8c80e739c9d29279df1054d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397983"
---
# <a name="relationship-nodes"></a><span data-ttu-id="92a61-102">リレーションシップ ノード</span><span class="sxs-lookup"><span data-stu-id="92a61-102">Relationship Nodes</span></span>
<span data-ttu-id="92a61-103">アクティビティ定義ファイルには、1 つ以上のアクティビティが含まれている場合、リレーションシップ フォルダーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="92a61-103">Relationship folders are used whenever an activity definition file contains more than one activity.</span></span> <span data-ttu-id="92a61-104">フォルダーの名前では、関連付けられているアクティビティの名前と一致します。</span><span class="sxs-lookup"><span data-stu-id="92a61-104">The names of the folders match the name of the associated activity.</span></span> <span data-ttu-id="92a61-105">関連のアクティビティのアクティビティ ID、リレーションシップ フォルダーの名前を照合することによって、データ アイテムの値を照合することによって、リンクを形成します。</span><span class="sxs-lookup"><span data-stu-id="92a61-105">You form the link by matching the name of the relationship folder to the activity ID of the related activity and by matching the values for the data items.</span></span> <span data-ttu-id="92a61-106">個別のノードを使用して、各リレーションシップを定義します。</span><span class="sxs-lookup"><span data-stu-id="92a61-106">You define each relationship using a separate node.</span></span>  
  
## <a name="working-with-relationship-nodes"></a><span data-ttu-id="92a61-107">リレーションシップ ノードの操作</span><span class="sxs-lookup"><span data-stu-id="92a61-107">Working with Relationship nodes</span></span>  
 <span data-ttu-id="92a61-108">アクティビティ間のデータ項目をリンクする一意のインスタンス識別子を指定します。</span><span class="sxs-lookup"><span data-stu-id="92a61-108">To indicate the unique instance identifier that links the data item between activities:</span></span>  
  
- <span data-ttu-id="92a61-109">データ項目をメインのオーケストレーションの ActivityId ノードにマップします。</span><span class="sxs-lookup"><span data-stu-id="92a61-109">Map a data item to the ActivityId node of the main orchestration.</span></span>  
  
- <span data-ttu-id="92a61-110">ドラッグし、関連するアクティビティのと同じ名前の上にリレーションシップ ノードでのデータ項目を削除します。</span><span class="sxs-lookup"><span data-stu-id="92a61-110">Drag and drop a data item with the same name as above to the Relationship node in the related activity.</span></span> <span data-ttu-id="92a61-111">リレーションシップ ノードには、メイン アクティビティのアクティビティ ノードと同じ名前があります。</span><span class="sxs-lookup"><span data-stu-id="92a61-111">The Relationship node has the same name as the Activity node of the main activity.</span></span>  
  
  <span data-ttu-id="92a61-112">たとえば、サンプル シナリオで、関連が存在する可能性がありますが RefinanceOrchestration というオーケストレーションで独立したビジネス プロセスが表されます。</span><span class="sxs-lookup"><span data-stu-id="92a61-112">For example, in the sample scenario, there could be a related but separate business process represented in an orchestration called RefinanceOrchestration.</span></span> <span data-ttu-id="92a61-113">そのオーケストレーションには、LoanRefinance アクティビティ ノード、Refinance ActivityID の場合、および評価要求受信などのオーケストレーション図形が含まれます。</span><span class="sxs-lookup"><span data-stu-id="92a61-113">That orchestration could contain a LoanRefinance Activity node, a Refinance ActivityID, and orchestration shapes such as Receive Appraisal Request.</span></span> <span data-ttu-id="92a61-114">リレーションシップ ノードとリレーションシップの ID は、元の LoanProcess アクティビティへのリンクを示す LoanID がただし、可能性があります。</span><span class="sxs-lookup"><span data-stu-id="92a61-114">The Relationship node and relationship ID, however, could be LoanID, indicating the link to the original LoanProcess activity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92a61-115">参照</span><span class="sxs-lookup"><span data-stu-id="92a61-115">See Also</span></span>  
 [<span data-ttu-id="92a61-116">TPE アクティビティ ビューのノード</span><span class="sxs-lookup"><span data-stu-id="92a61-116">TPE Activity View Nodes</span></span>](../core/tpe-activity-view-nodes.md)