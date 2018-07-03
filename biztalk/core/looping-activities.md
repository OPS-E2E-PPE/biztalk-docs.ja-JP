---
title: ループ アクティビティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- activities [BAM], looping activities
- activities [BAM], orchestrations
- orchestrations, looping
- orchestrations, activities
ms.assetid: fb40fdd0-ac8f-486a-b3d0-9d2200a87cda
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18cf2b768deca72b281bc189431b01f5e63a4887
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005073"
---
# <a name="looping-activities"></a><span data-ttu-id="d54b7-102">ループ アクティビティ</span><span class="sxs-lookup"><span data-stu-id="d54b7-102">Looping Activities</span></span>
<span data-ttu-id="d54b7-103">ループ アクティビティとは、オーケストレーション内でループ処理されるアクションのことです。</span><span class="sxs-lookup"><span data-stu-id="d54b7-103">Looping activities refers to actions that loop within an orchestration.</span></span> <span data-ttu-id="d54b7-104">オーケストレーション内でループ処理されるアクションからイベントをキャプチャできます。</span><span class="sxs-lookup"><span data-stu-id="d54b7-104">It is possible to capture the events from actions that loop within an orchestration.</span></span> <span data-ttu-id="d54b7-105">この操作を行うには、アクティビティをもう 1 つ作成し、ループ内の新しいアクティビティ マイルストーンとデータのすべてをマップします。</span><span class="sxs-lookup"><span data-stu-id="d54b7-105">To do this, you create another activity and map all of the new activity milestones and data inside the loop.</span></span> <span data-ttu-id="d54b7-106">ループ内でのデータ処理は、スケジュールされた実行ごとに 1 回以上行われるので、この操作が必要です。</span><span class="sxs-lookup"><span data-stu-id="d54b7-106">This is necessary because the data processing in the loop will occur more than once per scheduled execution.</span></span> <span data-ttu-id="d54b7-107">次の図は、この状況の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="d54b7-107">The following figure shows an example of this situation.</span></span>  
  
 <span data-ttu-id="d54b7-108">![](../core/media/handlingloops2.gif "handlingloops2")</span><span class="sxs-lookup"><span data-stu-id="d54b7-108">![](../core/media/handlingloops2.gif "handlingloops2")</span></span>  
  
 <span data-ttu-id="d54b7-109">ループ内で処理される複数の行項目を含む購買発注書がある場合に、図に示すようにのような質問「どの注文書は、100 ドルの価格がある」でしょうか。</span><span class="sxs-lookup"><span data-stu-id="d54b7-109">As shown in the figure, if you have a Purchase Order with multiple Line Items that process in a loop, questions like "Which purchase orders have item prices of $100?"</span></span> <span data-ttu-id="d54b7-110">あいまいになります。</span><span class="sxs-lookup"><span data-stu-id="d54b7-110">are ambiguous.</span></span> <span data-ttu-id="d54b7-111">質問を明確にすると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="d54b7-111">Unambiguous questions are:</span></span>  
  
- <span data-ttu-id="d54b7-112">価格が 100 ドルの品目があるのはどの注文書か</span><span class="sxs-lookup"><span data-stu-id="d54b7-112">Which purchase orders have line items with a price of $100?</span></span>  
  
- <span data-ttu-id="d54b7-113">合計/最低/最高 100 ドルの価格があるのはどの注文書か</span><span class="sxs-lookup"><span data-stu-id="d54b7-113">Which purchase orders have Total/Min/Max item prices of $100?</span></span>  
  
  <span data-ttu-id="d54b7-114">明確な質問を作成するには、注文書とは別のものとして品目を考える必要があります。</span><span class="sxs-lookup"><span data-stu-id="d54b7-114">Creating unambiguous questions requires thinking of the line items as something separate from the purchase order.</span></span> <span data-ttu-id="d54b7-115">追跡プロファイル エディターでは、ルート アクティビティ (注文書など) はループの外側のすべてのアクションにマップされます。</span><span class="sxs-lookup"><span data-stu-id="d54b7-115">In the Tracking Profile Editor, the root activity (for example, a purchase order) maps to all actions outside the loop.</span></span> <span data-ttu-id="d54b7-116">子アクティビティ (品目など) は、ループ内のアクションにマップされます。</span><span class="sxs-lookup"><span data-stu-id="d54b7-116">The child activity (for example, line item) maps to the actions inside the loop.</span></span>  
  
  <span data-ttu-id="d54b7-117">ルート アクティビティの ActivityID としてペイロード項目を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d54b7-117">You need to use a payload item as ActivityID for the root activity.</span></span> <span data-ttu-id="d54b7-118">ループ内のメッセージの一部でこのペイロード項目を使用可能にします。</span><span class="sxs-lookup"><span data-stu-id="d54b7-118">Have this payload item available in some of the messages inside the loop.</span></span> <span data-ttu-id="d54b7-119">アクティビティを子アクティビティの下に表示されるリレーションシップ ノードにマップして、ルート アクティビティとして名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="d54b7-119">Map the activity to the Relationship node that displays under the child activity and name it as the root activity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d54b7-120">参照</span><span class="sxs-lookup"><span data-stu-id="d54b7-120">See Also</span></span>  
 [<span data-ttu-id="d54b7-121">イベント ストリームを使用した BAM アクティビティを実装します。</span><span class="sxs-lookup"><span data-stu-id="d54b7-121">Implementing BAM Activities with Event Streams</span></span>](../core/implementing-bam-activities-with-event-streams.md)