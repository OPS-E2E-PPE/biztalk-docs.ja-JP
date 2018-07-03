---
title: 関連付けセットを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- correlation sets, send activities
- correlation sets, assigning correlation types
- correlation types, correlation sets
- correlation sets, receive activities
- configuring, correlation sets
- correlation sets, configuring
- correlation types, assigning
ms.assetid: 060bf2ba-c173-4dca-a8c4-4c5341e5ceaa
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51c56d7f319023bb0379050452253c65634929c0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968859"
---
# <a name="how-to-configure-correlation-sets"></a><span data-ttu-id="1237d-102">関連付けセットを構成する方法</span><span class="sxs-lookup"><span data-stu-id="1237d-102">How to Configure Correlation Sets</span></span>
<span data-ttu-id="1237d-103">関連付けセットを構成するには、既存の関連付けの種類を選択し、新しい関連付けの種類を作成するか、既存の関連付けの種類を変更します。</span><span class="sxs-lookup"><span data-stu-id="1237d-103">To configure your correlation set, you can select an existing correlation type, create a new correlation type, or modify an existing correlation type.</span></span>  
  
### <a name="to-assign-a-correlation-type-to-a-correlation-set"></a><span data-ttu-id="1237d-104">関連付けの種類を関連付けセットに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="1237d-104">To assign a correlation type to a correlation set</span></span>  
  
- <span data-ttu-id="1237d-105">既存の関連付けの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="1237d-105">Select an existing correlation type.</span></span>  
  
   <span data-ttu-id="1237d-106">\- または -</span><span class="sxs-lookup"><span data-stu-id="1237d-106">\- Or -</span></span>  
  
   <span data-ttu-id="1237d-107">新しい関連付けの種類を右クリックして**関連付けプロパティの構成**します。</span><span class="sxs-lookup"><span data-stu-id="1237d-107">Right-click the new correlation type and select **Configure Correlation Properties**.</span></span>  
  
   <span data-ttu-id="1237d-108">\- または -</span><span class="sxs-lookup"><span data-stu-id="1237d-108">\- Or -</span></span>  
  
   <span data-ttu-id="1237d-109">省略記号をクリックします (**.**) ボタンを**相関**プロパティで、**プロパティ**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="1237d-109">Click the Ellipsis (**...**) button on **Correlation** Properties in the **Properties** window.</span></span>  
  
   <span data-ttu-id="1237d-110">**関連付けのプロパティ** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1237d-110">The **Correlation Properties** dialog box comes up.</span></span> <span data-ttu-id="1237d-111">関連付けセットに含めるプロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="1237d-111">Add properties that you want to include in your correlation set.</span></span> <span data-ttu-id="1237d-112">関連付けの種類を関連付けセットにまだ割り当てていない場合、新しい関連付けの種類が作成されます。</span><span class="sxs-lookup"><span data-stu-id="1237d-112">If a correlation type was not already assigned to your correlation set, a new correlation type will be created.</span></span>  
  
  <span data-ttu-id="1237d-113">関連付けセットに対して関連付けの種類が既に存在して、追加またはプロパティを削除する場合、**関連付けのプロパティ**ダイアログ ボックスで、既存の相関関係の種類が変更されます。</span><span class="sxs-lookup"><span data-stu-id="1237d-113">If a correlation type already exists for your correlation set, and you add or remove properties with the **Correlation Properties** dialog box, the existing correlation type will be modified.</span></span>  
  
#### <a name="to-associate-send-and-receive-activities-with-a-correlation-set"></a><span data-ttu-id="1237d-114">関連付けセットに送受信の動作を関連付けるには</span><span class="sxs-lookup"><span data-stu-id="1237d-114">To associate send and receive activities with a correlation set</span></span>  
  
1.  <span data-ttu-id="1237d-115">展開、**関連付けセット**ノード。</span><span class="sxs-lookup"><span data-stu-id="1237d-115">Expand the **Correlation Set** node.</span></span>  
  
2.  <span data-ttu-id="1237d-116">ドロップダウン リストから送信または受信の動作を選択します。</span><span class="sxs-lookup"><span data-stu-id="1237d-116">Select a send or receive activity from the drop-down.</span></span>  
  
     <span data-ttu-id="1237d-117">\- または -</span><span class="sxs-lookup"><span data-stu-id="1237d-117">\- Or -</span></span>  
  
     <span data-ttu-id="1237d-118">いずれかで関連付けセットを選択して、**イニシャライズ関連付けセット**プロパティまたは**フォロー関連付けセット**プロパティ、**プロパティ**各ウィンドウ**送信**または**受信**図形を関連付けセットに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="1237d-118">Select the correlation set in either the **Initializing Correlation Sets** property or the **Following Correlation Sets** property in the **Properties** window for each **Send** or **Receive** shape you want to associate with the correlation set.</span></span>  
  
#### <a name="to-disassociate-send-and-receive-activities-from-a-correlation-set"></a><span data-ttu-id="1237d-119">関連付けセットと送受信の動作との関連付けを解除するには</span><span class="sxs-lookup"><span data-stu-id="1237d-119">To disassociate send and receive activities from a correlation set</span></span>  
  
-   <span data-ttu-id="1237d-120">**オーケストレーション**ウィンドウで、必要な場合は、関連付けセットのノードを展開し、削除、およびクリックするアクティビティを右クリックして**削除**します。</span><span class="sxs-lookup"><span data-stu-id="1237d-120">In the **Orchestration View** window, expand the correlation set node if necessary, right-click the activity you want to remove, and then click **Delete**.</span></span>  
  
     <span data-ttu-id="1237d-121">\- または -</span><span class="sxs-lookup"><span data-stu-id="1237d-121">\- Or -</span></span>  
  
     <span data-ttu-id="1237d-122">いずれかで関連付けセットを消去、**イニシャライズ関連付けセット**プロパティまたは**フォロー関連付けセット**プロパティ、**プロパティ**各のウィンドウ**送信**または**受信**図形の関連付けセットから関連付けを解除します。</span><span class="sxs-lookup"><span data-stu-id="1237d-122">Clear the correlation set in either the **Initializing Correlation Sets** property or the **Following Correlation Sets** property in the **Properties** window for each **Send** or **Receive** shape you want to disassociate from the correlation set.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1237d-123">参照</span><span class="sxs-lookup"><span data-stu-id="1237d-123">See Also</span></span>  
 <span data-ttu-id="1237d-124">[受信メッセージ図形にフィルターを使用します。](../core/using-filters-with-the-receive-message-shape.md) </span><span class="sxs-lookup"><span data-stu-id="1237d-124">[Using Filters With the Receive Message Shape](../core/using-filters-with-the-receive-message-shape.md) </span></span>  
 [<span data-ttu-id="1237d-125">オーケストレーションでの関連付けの使用</span><span class="sxs-lookup"><span data-stu-id="1237d-125">Using Correlations in Orchestrations</span></span>](../core/using-correlations-in-orchestrations.md)