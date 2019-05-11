---
title: オーケストレーションの開始図形を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [Orchestration Designer], Start Orchestration shapes
- Start Orchestration shape [Orchestration Designer], parameters
- Start Orchestration shape [Orchestration Designer], configuring
- orchestrations, starting
- Start Orchestration shape [Orchestration Designer]
- Start Orchestration shape [Orchestration Designer], starting orchestrations
- Start Orchestration shape [Orchestration Designer], about Star Orchestration shape
ms.assetid: 9d01c41e-9bc5-4c1c-a869-b2f0df13036a
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f3e9524198b414fc43e5c4e957ba2f6b6f3f689
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386037"
---
# <a name="how-to-configure-the-start-orchestration-shape"></a><span data-ttu-id="33804-102">オーケストレーションの開始図形を構成する方法</span><span class="sxs-lookup"><span data-stu-id="33804-102">How to Configure the Start Orchestration Shape</span></span>
<span data-ttu-id="33804-103">**オーケストレーションの開始**図形と似ています、**オーケストレーションの呼び出し**図形が非同期的に別のオーケストレーションを呼び出す、**オーケストレーションの開始**図形など、呼び出されたオーケストレーションの処理を完了するを待たず、次に、呼び出し側オーケストレーションの制御フローの開始されます。</span><span class="sxs-lookup"><span data-stu-id="33804-103">The **Start Orchestration** shape is similar to the **Call Orchestration** shape, but you invoke another orchestration asynchronously with the **Start Orchestration** shape—that is, the flow of control in the invoking orchestration proceeds beyond the invocation, without waiting for the invoked orchestration to finish its work.</span></span>  
  
 <span data-ttu-id="33804-104">呼び出されたオーケストレーションに渡されるパラメーターを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="33804-104">You can specify parameters that will be passed to the invoked orchestration.</span></span> <span data-ttu-id="33804-105">パラメーターは、メッセージ、変数、ポート参照、ロール リンク、または関連付けセットにすることができます。</span><span class="sxs-lookup"><span data-stu-id="33804-105">Parameters can be messages, variables, port references, role links, or correlation sets.</span></span> <span data-ttu-id="33804-106">**オーケストレーションの開始**図形が受け取ることができる*で*はパラメーターは使用できません*アウト*または*ref*パラメーター。</span><span class="sxs-lookup"><span data-stu-id="33804-106">The **Start Orchestration** shape can only take *in* parameters; it cannot take *out* or *ref* parameters.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="33804-107">XmlDocument や XmlNode などの非シリアル化可能なオブジェクトをパラメーターとしてオーケストレーションに渡すことがある場合は失敗します。</span><span class="sxs-lookup"><span data-stu-id="33804-107">If you pass non-serializable objects such as XmlDocument or XmlNode as parameters to an orchestration, it will fail.</span></span>  
  
 <span data-ttu-id="33804-108">**オーケストレーションの開始**図形をパラメーターとして渡すポートの極性を反転できる唯一の図形では、たとえば、*を使用して*呼び出されたオーケストレーションにポート (送信ポート) に渡すことができます呼び出されたオーケストレーションを使用すると扱うことができますが、*実装*ポート (受信ポート)。</span><span class="sxs-lookup"><span data-stu-id="33804-108">The **Start Orchestration** shape is the only shape in which you can reverse the polarity on a port being passed as a parameter—for example a *uses* port (send port) can be passed in to an invoked orchestration, but the invoked orchestration can treat it as an *implements* port (receive port).</span></span> <span data-ttu-id="33804-109">これのみ行う直接バインドを使用するポートとに注意してください。</span><span class="sxs-lookup"><span data-stu-id="33804-109">Note that this can only be done with ports that use direct binding.</span></span>  
  
 <span data-ttu-id="33804-110">**オーケストレーションの開始**図形を使用して別のプロジェクトで参照されているオーケストレーションを呼び出すこともできます。</span><span class="sxs-lookup"><span data-stu-id="33804-110">The **Start Orchestration** shape can also be used to call an orchestration that is referenced in another project.</span></span> <span data-ttu-id="33804-111">これにより、一般的なオーケストレーション ワークフロー パターンの再利用するための BizTalk プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="33804-111">This allows for reuse of common orchestration workflow patterns across BizTalk projects.</span></span> <span data-ttu-id="33804-112">参照先のオーケストレーションを呼び出せるようにすることを確認、**型修飾子**呼び出し先オーケストレーションのプロパティに設定されて**パブリック**します。</span><span class="sxs-lookup"><span data-stu-id="33804-112">For the referenced orchestration to be callable, ensure that the **Type Modifier** property for the called orchestration is set to **Public**.</span></span> <span data-ttu-id="33804-113">設定する、**型修飾子**にオーケストレーションのプロパティ**パブリック**、Microsoft では、オーケストレーションを開いて[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、を表示するオーケストレーションの上部にある緑色の開始図形をクリックします。**オーケストレーションのプロパティ**ダイアログとセット、**型修飾子**プロパティを**パブリック**します。</span><span class="sxs-lookup"><span data-stu-id="33804-113">To set the **Type Modifier** property for an orchestration to **Public**, open the orchestration in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], click the green start shape at the top of the orchestration to display the **Orchestration Properties** dialog and set the **Type Modifier** property to **Public**.</span></span> <span data-ttu-id="33804-114">既定値**型修飾子**は**プライベート**します。</span><span class="sxs-lookup"><span data-stu-id="33804-114">The default value for **Type Modifier** is **Private**.</span></span>  
  
 <span data-ttu-id="33804-115">使用する方法の例については**オーケストレーションの開始**図形、SDK サンプル「を実装する Scatter and Gather Pattern」からダウンロード[ http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)します。</span><span class="sxs-lookup"><span data-stu-id="33804-115">For an example of how to use **Start Orchestration** shape, download the SDK sample "Implementing Scatter and Gather Pattern" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
### <a name="to-configure-a-start-orchestration-shape"></a><span data-ttu-id="33804-116">オーケストレーションの開始図形を構成するには</span><span class="sxs-lookup"><span data-stu-id="33804-116">To configure a Start Orchestration shape</span></span>  
  
1. <span data-ttu-id="33804-117">使用して、 **Orchestration Selection**ドロップダウン リスト ボックスで、一覧からオーケストレーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="33804-117">Using the **Orchestration Selection** drop-down list box, select an orchestration from the list.</span></span>  
  
2. <span data-ttu-id="33804-118">使用して、**オーケストレーション パラメーター**グリッド コントロールをオーケストレーションに渡す引数を指定 — で指定されている、 **Orchestration Selection**ドロップダウン リスト ボックス-開始します。</span><span class="sxs-lookup"><span data-stu-id="33804-118">Using the **Orchestration Parameters** grid control, specify arguments to pass to the orchestration—as specified in the **Orchestration Selection** drop-down list box—that is started.</span></span> <span data-ttu-id="33804-119">変数の名前を入力するか、セルのドロップダウン リストから変数をクリックして、各セルの 1 つの変数、変数列のセルでこれらの引数を指定します。</span><span class="sxs-lookup"><span data-stu-id="33804-119">You specify these arguments in the cells of the Variable column, one variable per cell, by typing the name of a variable or clicking a variable from a drop-down list in a cell.</span></span>  
  
3. <span data-ttu-id="33804-120">構成する、**オーケストレーションの開始**サービスと、ダイアログ ボックスで指定した引数に従って図形をクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="33804-120">To configure the **Start Orchestration** shape according to the service and arguments that you specified in the dialog box, click **OK**.</span></span> <span data-ttu-id="33804-121">閉じるには、**オーケストレーション構成の開始**] ダイアログ ボックスに変更を加えずに、**オーケストレーションの開始**図形で、[**キャンセル**します。</span><span class="sxs-lookup"><span data-stu-id="33804-121">To close the **Start Orchestration Configuration** dialog box without making any changes to the **Start Orchestration** shape, click **Cancel**.</span></span>  
  
   > [!CAUTION]
   >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="33804-122">再帰的なオーケストレーションはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="33804-122">does not support recursive orchestrations.</span></span> <span data-ttu-id="33804-123">呼び出すかを直接または間接的に呼び出すオーケストレーション A. すべてのオーケストレーションを開始も、オーケストレーション A は、呼び出しや、オーケストレーション B を開始、し、オーケストレーション B を呼び出しまたはを直接、オーケストレーションを開始できません。</span><span class="sxs-lookup"><span data-stu-id="33804-123">If Orchestration A calls or starts Orchestration B, then Orchestration B cannot call or start Orchestration A directly, nor can it call or start any orchestration that directly or indirectly calls Orchestration A.</span></span>  
  
## <a name="orchestration-selection-drop-down-list-box"></a><span data-ttu-id="33804-124">オーケストレーションの選択ドロップダウン リスト ボックス</span><span class="sxs-lookup"><span data-stu-id="33804-124">Orchestration Selection drop-down list box</span></span>  
 <span data-ttu-id="33804-125">使用可能なオーケストレーションを表示し、1 つを選択するドロップダウン リスト ボックスの下矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33804-125">Click the Down arrow in the drop-down list box to view available orchestrations and select one.</span></span> <span data-ttu-id="33804-126">この一覧には、参照アセンブリも含め、現在のオーケストレーションから開始できるすべてのオーケストレーションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="33804-126">This list contains all the orchestrations that can be started from the current orchestration, including referenced assemblies.</span></span>  
  
## <a name="orchestration-parameters-grid-control"></a><span data-ttu-id="33804-127">オーケストレーション パラメーター グリッド コントロール</span><span class="sxs-lookup"><span data-stu-id="33804-127">Orchestration Parameters grid control</span></span>  
 <span data-ttu-id="33804-128">使用して、パラメーターを受け取るオーケストレーションに渡す引数を指定する、**オーケストレーション パラメーター**グリッド コントロール。</span><span class="sxs-lookup"><span data-stu-id="33804-128">You specify the arguments to pass to a parameterized orchestration by using the **Orchestration Parameters** grid control.</span></span> <span data-ttu-id="33804-129">グリッドには、4 つの列があります。スコープ、パラメーター名、パラメーターの型、およびパラメーターの方向での変数。</span><span class="sxs-lookup"><span data-stu-id="33804-129">The grid has four columns: Variables in Scope, Parameter Name, Parameter Type, and Parameter Direction.</span></span> <span data-ttu-id="33804-130">最初の列でのみ変更を行うことができます。その他の列とは、読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="33804-130">You can make changes only in the first column; the other columns are read-only.</span></span>  
  
 <span data-ttu-id="33804-131">有効なオーケストレーションを選択すると、そのパラメーターは、パラメーター名、型、およびグリッド コントロールの方向 列を設定します。</span><span class="sxs-lookup"><span data-stu-id="33804-131">When you select a valid orchestration, its parameters populate the parameter name, type, and direction columns of the grid control.</span></span> <span data-ttu-id="33804-132">各行を引数として渡す変数を選択します。</span><span class="sxs-lookup"><span data-stu-id="33804-132">You then select the variables in each row to pass as arguments.</span></span> <span data-ttu-id="33804-133">[スコープ] 列内の変数には、各セルにあるドロップダウン リストから、これらの変数を選択します。</span><span class="sxs-lookup"><span data-stu-id="33804-133">You select these variables from a drop-down list present in each cell in the Variables in Scope column.</span></span> <span data-ttu-id="33804-134">この一覧には、パラメーターの型の隣のセルで指定された型の使用可能なすべての変数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="33804-134">This list displays all the available variables of the type specified in the adjacent Parameter Type cell.</span></span> <span data-ttu-id="33804-135">その型の 1 つのオブジェクトにしか使用できない場合はそのオブジェクトはスコープのセル内の変数が自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="33804-135">If only one object of that type is available, the Variables in Scope cell is automatically populated with that object.</span></span> <span data-ttu-id="33804-136">ドロップダウン リストで使用できる変数を選択するには、スコープのセルに変数に入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="33804-136">You can also type in a Variables in Scope cell to select a variable that is available in the drop-down list.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="33804-137">**オーケストレーションの開始**図形をオーケストレーションを開始する、このダイアログ ボックスで選択する「オーケストレーション パラメーター」は実際にはオーケストレーション変数を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33804-137">Because a **Start Orchestration** shape starts an orchestration, the "Orchestration Parameters" you select in this dialog box actually refer to orchestration variables.</span></span>  
  
 <span data-ttu-id="33804-138">実行しているオーケストレーションが定義されているパラメーターを持たない場合はこのダイアログ ボックスでグリッド コントロールは使用できません。</span><span class="sxs-lookup"><span data-stu-id="33804-138">If an orchestration you are executing has no defined parameters, the grid control in this dialog box is unavailable.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="33804-139">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="33804-139">In This Section</span></span>  
 [<span data-ttu-id="33804-140">作成する方法について呼び出されたオーケストレーションに受信サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="33804-140">How to Create Receive Subscriptions at Invoked Orchestrations</span></span>](../core/how-to-create-receive-subscriptions-at-invoked-orchestrations.md) 
  
## <a name="see-also"></a><span data-ttu-id="33804-141">参照</span><span class="sxs-lookup"><span data-stu-id="33804-141">See Also</span></span>  
 [<span data-ttu-id="33804-142">オーケストレーションの呼び出し図形を構成する方法</span><span class="sxs-lookup"><span data-stu-id="33804-142">How to Configure the Call Orchestration Shape</span></span>](../core/how-to-configure-the-call-orchestration-shape.md)