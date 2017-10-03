---
title: "関連付けセットを構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52bcb0216fc24e14107c7632df97671b64f2ac1d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-correlation-sets"></a><span data-ttu-id="e1a58-102">関連付けセットを構成する方法</span><span class="sxs-lookup"><span data-stu-id="e1a58-102">How to Configure Correlation Sets</span></span>
<span data-ttu-id="e1a58-103">関連付けセットを構成するには、既存の関連付けの種類を選択し、新しい関連付けの種類を作成するか、既存の関連付けの種類を変更します。</span><span class="sxs-lookup"><span data-stu-id="e1a58-103">To configure your correlation set, you can select an existing correlation type, create a new correlation type, or modify an existing correlation type.</span></span>  
  
### <a name="to-assign-a-correlation-type-to-a-correlation-set"></a><span data-ttu-id="e1a58-104">関連付けの種類を関連付けセットに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="e1a58-104">To assign a correlation type to a correlation set</span></span>  
  
-   <span data-ttu-id="e1a58-105">既存の関連付けの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1a58-105">Select an existing correlation type.</span></span>  
  
     <span data-ttu-id="e1a58-106">\-または、</span><span class="sxs-lookup"><span data-stu-id="e1a58-106">\- Or -</span></span>  
  
     <span data-ttu-id="e1a58-107">新しい関連付けの種類を右クリックし **関連付けのプロパティを構成する**です。</span><span class="sxs-lookup"><span data-stu-id="e1a58-107">Right-click the new correlation type and select **Configure Correlation Properties**.</span></span>  
  
     <span data-ttu-id="e1a58-108">\-または、</span><span class="sxs-lookup"><span data-stu-id="e1a58-108">\- Or -</span></span>  
  
     <span data-ttu-id="e1a58-109">省略記号ボタン (**.**) ボタンを**相関**プロパティで、**プロパティ**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="e1a58-109">Click the Ellipsis (**...**) button on **Correlation** Properties in the **Properties** window.</span></span>  
  
     <span data-ttu-id="e1a58-110">**関連付けのプロパティ** ダイアログ ボックスが表示されたらです。</span><span class="sxs-lookup"><span data-stu-id="e1a58-110">The **Correlation Properties** dialog box comes up.</span></span> <span data-ttu-id="e1a58-111">関連付けセットに含めるプロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="e1a58-111">Add properties that you want to include in your correlation set.</span></span> <span data-ttu-id="e1a58-112">関連付けの種類を関連付けセットにまだ割り当てていない場合、新しい関連付けの種類が作成されます。</span><span class="sxs-lookup"><span data-stu-id="e1a58-112">If a correlation type was not already assigned to your correlation set, a new correlation type will be created.</span></span>  
  
 <span data-ttu-id="e1a58-113">関連付けの種類が、関連付けセットに既に存在し、追加またはプロパティを削除する場合、**関連付けのプロパティ**ダイアログ ボックスで、既存の相関関係の種類が変更されます。</span><span class="sxs-lookup"><span data-stu-id="e1a58-113">If a correlation type already exists for your correlation set, and you add or remove properties with the **Correlation Properties** dialog box, the existing correlation type will be modified.</span></span>  
  
#### <a name="to-associate-send-and-receive-activities-with-a-correlation-set"></a><span data-ttu-id="e1a58-114">関連付けセットに送受信の動作を関連付けるには</span><span class="sxs-lookup"><span data-stu-id="e1a58-114">To associate send and receive activities with a correlation set</span></span>  
  
1.  <span data-ttu-id="e1a58-115">展開して、**関連付けセット**ノード。</span><span class="sxs-lookup"><span data-stu-id="e1a58-115">Expand the **Correlation Set** node.</span></span>  
  
2.  <span data-ttu-id="e1a58-116">ドロップダウン リストから送信または受信の動作を選択します。</span><span class="sxs-lookup"><span data-stu-id="e1a58-116">Select a send or receive activity from the drop-down.</span></span>  
  
     <span data-ttu-id="e1a58-117">\-または、</span><span class="sxs-lookup"><span data-stu-id="e1a58-117">\- Or -</span></span>  
  
     <span data-ttu-id="e1a58-118">相関関係のいずれかで設定を選択して、**イニシャライズ関連付けセット**プロパティまたは**フォロー関連付けセット**プロパティに、**プロパティ**ごと ウィンドウ**送信**または**受信**図形を関連付けセットに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="e1a58-118">Select the correlation set in either the **Initializing Correlation Sets** property or the **Following Correlation Sets** property in the **Properties** window for each **Send** or **Receive** shape you want to associate with the correlation set.</span></span>  
  
#### <a name="to-disassociate-send-and-receive-activities-from-a-correlation-set"></a><span data-ttu-id="e1a58-119">関連付けセットと送受信の動作との関連付けを解除するには</span><span class="sxs-lookup"><span data-stu-id="e1a58-119">To disassociate send and receive activities from a correlation set</span></span>  
  
-   <span data-ttu-id="e1a58-120">**オーケストレーション**ウィンドウで、必要な場合は、関連付けセットのノードを展開し、削除、およびをクリックする活動を右クリックして**削除**です。</span><span class="sxs-lookup"><span data-stu-id="e1a58-120">In the **Orchestration View** window, expand the correlation set node if necessary, right-click the activity you want to remove, and then click **Delete**.</span></span>  
  
     <span data-ttu-id="e1a58-121">\-または、</span><span class="sxs-lookup"><span data-stu-id="e1a58-121">\- Or -</span></span>  
  
     <span data-ttu-id="e1a58-122">相関関係のいずれかで設定をオフに、**イニシャライズ関連付けセット**プロパティまたは**フォロー関連付けセット**プロパティに、**プロパティ**各のウィンドウ**送信**または**受信**図形を関連付けセットからの関連付けを解除します。</span><span class="sxs-lookup"><span data-stu-id="e1a58-122">Clear the correlation set in either the **Initializing Correlation Sets** property or the **Following Correlation Sets** property in the **Properties** window for each **Send** or **Receive** shape you want to disassociate from the correlation set.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1a58-123">参照</span><span class="sxs-lookup"><span data-stu-id="e1a58-123">See Also</span></span>  
 <span data-ttu-id="e1a58-124">[受信メッセージ図形にフィルターを使用します。](../core/using-filters-with-the-receive-message-shape.md) </span><span class="sxs-lookup"><span data-stu-id="e1a58-124">[Using Filters With the Receive Message Shape](../core/using-filters-with-the-receive-message-shape.md) </span></span>  
 [<span data-ttu-id="e1a58-125">オーケストレーションでの相関関係の使用</span><span class="sxs-lookup"><span data-stu-id="e1a58-125">Using Correlations in Orchestrations</span></span>](../core/using-correlations-in-orchestrations.md)