---
title: オーケストレーションの呼び出し図形を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Call Orchestration shape [Orchestration Designer], parameters
- Call Orchestration shape [Orchestration Designer], configuring
- Call Orchestration shape [Orchestration Designer], about Call Orchestration shapes
- configuring [Orchestration Designer], Call Orchestration shapes
- Call Orchestration shape [Orchestration Designer]
- nonserializable objects
- orchestrations, nonserializable objects
- Call Orchestration shape [Orchestration Designer], referencing orchestrations
- orchestrations, parameters
ms.assetid: 718ce2a0-ac08-4662-8b4e-1be279dbc749
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f20025f771f28f91e1fe40b10bfc0e999685eb68
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386117"
---
# <a name="how-to-configure-the-call-orchestration-shape"></a><span data-ttu-id="c8ca3-102">オーケストレーションの呼び出し図形を構成する方法</span><span class="sxs-lookup"><span data-stu-id="c8ca3-102">How to Configure the Call Orchestration Shape</span></span>
<span data-ttu-id="c8ca3-103">**オーケストレーションの呼び出し**を別のプロジェクトで参照されているオーケストレーションを同期的に呼び出す図形を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="c8ca3-103">The **Call Orchestration** shape can be used to synchronously call an orchestration that is referenced in another project.</span></span> <span data-ttu-id="c8ca3-104">これにより、一般的なオーケストレーション ワークフロー パターンの再利用するための BizTalk プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="c8ca3-104">This allows for reuse of common orchestration workflow patterns across BizTalk projects.</span></span> <span data-ttu-id="c8ca3-105">同期的に入れ子になった別のオーケストレーションを呼び出すと、**オーケストレーションの呼び出し**図形の外側のオーケストレーションが、入れ子になったオーケストレーションを続行する前に完了を待ちます。</span><span class="sxs-lookup"><span data-stu-id="c8ca3-105">When you invoke another nested orchestration synchronously with the **Call Orchestration** shape the enclosing orchestration waits for the nested orchestration to finish before continuing.</span></span>  
  
 <span data-ttu-id="c8ca3-106">入れ子になったオーケストレーションに渡されるパラメーターを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="c8ca3-106">You can specify parameters that will be passed to the nested orchestration.</span></span> <span data-ttu-id="c8ca3-107">パラメーターは、メッセージ、変数、ポート参照、ロール リンク、または関連付けセットにすることができます。</span><span class="sxs-lookup"><span data-stu-id="c8ca3-107">Parameters can be messages, variables, port references, role links, or correlation sets.</span></span> <span data-ttu-id="c8ca3-108">渡されたポート参照、ロール リンク、および関連付けセットのすべてを封筒のように実行します。 外側のオーケストレーションに情報が送信に使用できる、入れ子になったオーケストレーション情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="c8ca3-108">Passed-in port references, role links, and correlation sets all perform like self-addressed envelopes: they supply the nested orchestration information it can use to send information back to the enclosing orchestration.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="c8ca3-109">XmlDocument や XmlNode などのシリアル化できないオブジェクトをパラメーターとしてオーケストレーションに渡すことがある場合は失敗します。</span><span class="sxs-lookup"><span data-stu-id="c8ca3-109">If you pass nonserializable objects such as XmlDocument or XmlNode as parameters to an orchestration, it will fail.</span></span>  
  
 <span data-ttu-id="c8ca3-110">使用する方法の例については**オーケストレーションの呼び出し**図形は、「 [CallOrchestration (BizTalk Server サンプル)](../core/callorchestration-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="c8ca3-110">For an example of how to use **Call Orchestration** shape, see [CallOrchestration (BizTalk Server Sample)](../core/callorchestration-biztalk-server-sample.md).</span></span>  
  
### <a name="to-configure-a-call-orchestration-shape"></a><span data-ttu-id="c8ca3-111">オーケストレーションの呼び出し図形を構成するには</span><span class="sxs-lookup"><span data-stu-id="c8ca3-111">To configure a Call Orchestration shape</span></span>  
  
1. <span data-ttu-id="c8ca3-112">使用して、 **Orchestration Selection**ドロップダウン リスト ボックスで、一覧からオーケストレーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="c8ca3-112">Using the **Orchestration Selection** drop-down list box, select an orchestration from the list.</span></span>  
  
2. <span data-ttu-id="c8ca3-113">使用して、**オーケストレーション パラメーター**グリッド コントロールをオーケストレーションに渡す引数を指定 — で指定されている、 **Orchestration Selection**ドロップダウン リスト ボックス-呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c8ca3-113">Using the **Orchestration Parameters** grid control, specify arguments to pass to the orchestration—as specified in the **Orchestration Selection** drop-down list box—that is called.</span></span> <span data-ttu-id="c8ca3-114">変数の名前を入力するか、セルのドロップダウン リストから変数をクリックして、各セルの 1 つの変数、変数列のセルでこれらの引数を指定します。</span><span class="sxs-lookup"><span data-stu-id="c8ca3-114">You specify these arguments in the cells of the Variable column, one variable per cell, by typing the name of a variable or clicking a variable from a drop-down list in a cell.</span></span>  
  
3. <span data-ttu-id="c8ca3-115">構成する、**オーケストレーションの呼び出し**サービスと、ダイアログ ボックスで指定した引数に従って図形をクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="c8ca3-115">To configure the **Call Orchestration** shape according to the service and arguments that you specified in the dialog box, click **OK**.</span></span> <span data-ttu-id="c8ca3-116">閉じるには、**オーケストレーション構成の呼び出し**] ダイアログ ボックスに変更を加えずに、**オーケストレーションの呼び出し**図形で、[**キャンセル**します。</span><span class="sxs-lookup"><span data-stu-id="c8ca3-116">To close the **Call Orchestration Configuration** dialog box without making any changes to the **Call Orchestration** shape, click **Cancel**.</span></span>  
  
   > [!CAUTION]
   >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="c8ca3-117">再帰的なオーケストレーションはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="c8ca3-117">does not support recursive orchestrations.</span></span> <span data-ttu-id="c8ca3-118">呼び出すかを直接または間接的に呼び出すオーケストレーション A. すべてのオーケストレーションを開始も、オーケストレーション A は、呼び出しや、オーケストレーション B を開始、し、オーケストレーション B を呼び出しまたはを直接、オーケストレーションを開始できません。</span><span class="sxs-lookup"><span data-stu-id="c8ca3-118">If Orchestration A calls or starts Orchestration B, then Orchestration B cannot call or start Orchestration A directly, nor can it call or start any orchestration that directly or indirectly calls Orchestration A.</span></span>  
  
## <a name="referenced-orchestrations"></a><span data-ttu-id="c8ca3-119">参照されているオーケストレーション</span><span class="sxs-lookup"><span data-stu-id="c8ca3-119">Referenced Orchestrations</span></span>  
 <span data-ttu-id="c8ca3-120">呼び出せるようにする参照先のオーケストレーションでは、呼び出し先オーケストレーションの次のプロパティが構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c8ca3-120">For the referenced orchestration to be callable, ensure that the following properties have been configured for the called orchestration:</span></span>  
  
- <span data-ttu-id="c8ca3-121">設定、**型修飾子**プロパティを**パブリック**呼び出し先オーケストレーションします。</span><span class="sxs-lookup"><span data-stu-id="c8ca3-121">Set the **Type Modifier** property to **Public** for the called orchestration.</span></span> <span data-ttu-id="c8ca3-122">設定する、**型修飾子**にオーケストレーションのプロパティ**パブリック**、Microsoft では、オーケストレーションを開いて[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、を表示するオーケストレーションの上部にある緑色の開始図形をクリックします。**オーケストレーションのプロパティ**ダイアログとセット、**型修飾子**プロパティを**パブリック**します。</span><span class="sxs-lookup"><span data-stu-id="c8ca3-122">To set the **Type Modifier** property for an orchestration to **Public**, open the orchestration in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], click the green start shape at the top of the orchestration to display the **Orchestration Properties** dialog and set the **Type Modifier** property to **Public**.</span></span>  
  
- <span data-ttu-id="c8ca3-123">設定、 **Activate**プロパティをオーケストレーションの当初の受信図形の**False**します。</span><span class="sxs-lookup"><span data-stu-id="c8ca3-123">Set the **Activate** property of the initial receive shape in the orchestration to **False**.</span></span>  
  
## <a name="orchestration-selection-drop-down-list-box"></a><span data-ttu-id="c8ca3-124">オーケストレーションの選択ドロップダウン リスト ボックス</span><span class="sxs-lookup"><span data-stu-id="c8ca3-124">Orchestration Selection drop-down list box</span></span>  
 <span data-ttu-id="c8ca3-125">利用可能なサービスを表示し、1 つを選択するドロップダウン リスト ボックスの下矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8ca3-125">Click the Down arrow in the drop-down list box to view available services and select one.</span></span> <span data-ttu-id="c8ca3-126">この一覧には、参照アセンブリも含め、現在のオーケストレーションから呼び出すことができるすべてのサービスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c8ca3-126">This list contains all the services that can be called from the current orchestration, including referenced assemblies.</span></span>  
  
## <a name="orchestration-parameters-grid-control"></a><span data-ttu-id="c8ca3-127">オーケストレーション パラメーター グリッド コントロール</span><span class="sxs-lookup"><span data-stu-id="c8ca3-127">Orchestration Parameters grid control</span></span>  
 <span data-ttu-id="c8ca3-128">使用して、パラメーターを受け取るオーケストレーションに渡す引数を指定する、**オーケストレーション パラメーター**グリッド コントロール。</span><span class="sxs-lookup"><span data-stu-id="c8ca3-128">You specify the arguments to pass to a parameterized orchestration by using the **Orchestration Parameters** grid control.</span></span> <span data-ttu-id="c8ca3-129">グリッドには、4 つの列があります。スコープ、パラメーター名、パラメーターの型、およびパラメーターの方向での変数。</span><span class="sxs-lookup"><span data-stu-id="c8ca3-129">The grid has four columns: Variables in Scope, Parameter Name, Parameter Type, and Parameter Direction.</span></span> <span data-ttu-id="c8ca3-130">最初の列でのみ変更を行うことができます。その他の列とは、読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="c8ca3-130">You can make changes only in the first column; the other columns are read-only.</span></span>  
  
 <span data-ttu-id="c8ca3-131">有効なオーケストレーションを選択すると、そのパラメーターは、グリッド コントロールのパラメーターの名前、型および方向の列を設定します。</span><span class="sxs-lookup"><span data-stu-id="c8ca3-131">When you select a valid orchestration, its parameters populate the parameter name, type and direction columns of the grid control.</span></span> <span data-ttu-id="c8ca3-132">各行を引数として渡す変数を選択します。</span><span class="sxs-lookup"><span data-stu-id="c8ca3-132">You then select the variables in each row to pass as arguments.</span></span> <span data-ttu-id="c8ca3-133">[スコープ] 列内の変数には、各セルにあるドロップダウン リストから、これらの変数を選択します。</span><span class="sxs-lookup"><span data-stu-id="c8ca3-133">You select these variables from a drop-down list present in each cell in the Variables in Scope column.</span></span> <span data-ttu-id="c8ca3-134">この一覧には、パラメーターの型の隣のセルで指定された型の使用可能なすべての変数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c8ca3-134">This list displays all the available variables of the type specified in the adjacent Parameter Type cell.</span></span> <span data-ttu-id="c8ca3-135">その型の 1 つのオブジェクトにしか使用できない場合はそのオブジェクトはスコープのセル内の変数が自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="c8ca3-135">If only one object of that type is available, the Variables in Scope cell is automatically populated with that object.</span></span> <span data-ttu-id="c8ca3-136">ドロップダウン リストで使用できる変数を選択するには、スコープのセルに変数に入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="c8ca3-136">You can also type in a Variables in Scope cell to select a variable that is available in the drop-down list.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c8ca3-137">**オーケストレーションの呼び出し**図形がオーケストレーションを呼び出し、このダイアログ ボックスで選択する「オーケストレーション パラメーター」は実際にはオーケストレーション変数を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8ca3-137">Because a **Call Orchestration** shape calls an orchestration, the "Orchestration Parameters" you select in this dialog box actually refer to orchestration variables.</span></span>  
  
 <span data-ttu-id="c8ca3-138">呼び出しているオーケストレーションが定義されているパラメーターを持たない場合はこのダイアログ ボックスでグリッド コントロールは使用できません。</span><span class="sxs-lookup"><span data-stu-id="c8ca3-138">If an orchestration you are calling has no defined parameters, the grid control in this dialog box is unavailable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8ca3-139">参照</span><span class="sxs-lookup"><span data-stu-id="c8ca3-139">See Also</span></span>  
 [<span data-ttu-id="c8ca3-140">オーケストレーションの開始図形を構成する方法</span><span class="sxs-lookup"><span data-stu-id="c8ca3-140">How to Configure the Start Orchestration Shape</span></span>](../core/how-to-configure-the-start-orchestration-shape.md)