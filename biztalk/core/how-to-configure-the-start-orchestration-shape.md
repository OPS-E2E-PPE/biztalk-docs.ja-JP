---
title: オーケストレーションの開始図形を構成する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 6f8181849b700939ba86f55cd372b80ed2ebf70e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249666"
---
# <a name="how-to-configure-the-start-orchestration-shape"></a><span data-ttu-id="7d948-102">オーケストレーションの開始図形を構成する方法</span><span class="sxs-lookup"><span data-stu-id="7d948-102">How to Configure the Start Orchestration Shape</span></span>
<span data-ttu-id="7d948-103">**オーケストレーションの開始**図形がに似ていますが、**オーケストレーションの呼び出し**図形が使用した非同期の別のオーケストレーションを呼び出す、**オーケストレーションの開始**図形: 呼び出されたオーケストレーションがその作業を終了するを待たず、呼び出しを超える、呼び出し側オーケストレーションの制御フローの開始されます。</span><span class="sxs-lookup"><span data-stu-id="7d948-103">The **Start Orchestration** shape is similar to the **Call Orchestration** shape, but you invoke another orchestration asynchronously with the **Start Orchestration** shape—that is, the flow of control in the invoking orchestration proceeds beyond the invocation, without waiting for the invoked orchestration to finish its work.</span></span>  
  
 <span data-ttu-id="7d948-104">呼び出されたオーケストレーションに渡すパラメーターを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="7d948-104">You can specify parameters that will be passed to the invoked orchestration.</span></span> <span data-ttu-id="7d948-105">パラメーターとして指定できるのは、メッセージ、変数、ポート参照、ロール リンク、または関連付けセットです。</span><span class="sxs-lookup"><span data-stu-id="7d948-105">Parameters can be messages, variables, port references, role links, or correlation sets.</span></span> <span data-ttu-id="7d948-106">**オーケストレーションの開始**図形が受け取ることができる*で*パラメーター; ことはできません*アウト*または*ref*パラメーター。</span><span class="sxs-lookup"><span data-stu-id="7d948-106">The **Start Orchestration** shape can only take *in* parameters; it cannot take *out* or *ref* parameters.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="7d948-107">XmlDocument や XmlNode などのシリアル化できないオブジェクトをパラメーターとしてオーケストレーションに渡すことは失敗します。</span><span class="sxs-lookup"><span data-stu-id="7d948-107">If you pass non-serializable objects such as XmlDocument or XmlNode as parameters to an orchestration, it will fail.</span></span>  
  
 <span data-ttu-id="7d948-108">**オーケストレーションの開始**図形をパラメーターとして渡すポートの極性を反転できる唯一の図形では、たとえば、*を使用して*呼び出されたオーケストレーションのポート (送信ポート) に渡すことができます呼び出されたオーケストレーションを使用すると扱うことができますが、*実装*ポート (受信ポート)。</span><span class="sxs-lookup"><span data-stu-id="7d948-108">The **Start Orchestration** shape is the only shape in which you can reverse the polarity on a port being passed as a parameter—for example a *uses* port (send port) can be passed in to an invoked orchestration, but the invoked orchestration can treat it as an *implements* port (receive port).</span></span> <span data-ttu-id="7d948-109">ただし、これを実行できるのは直接バインドを使用するポートだけです。</span><span class="sxs-lookup"><span data-stu-id="7d948-109">Note that this can only be done with ports that use direct binding.</span></span>  
  
 <span data-ttu-id="7d948-110">**オーケストレーションの開始**図形は、別のプロジェクトで参照されているオーケストレーションの呼び出しにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="7d948-110">The **Start Orchestration** shape can also be used to call an orchestration that is referenced in another project.</span></span> <span data-ttu-id="7d948-111">これにより、一般的なオーケストレーション ワークフロー パターンを BizTalk プロジェクト間で再利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="7d948-111">This allows for reuse of common orchestration workflow patterns across BizTalk projects.</span></span> <span data-ttu-id="7d948-112">呼び出し可能である参照先のオーケストレーションでは、いることを確認、**型修飾子**呼び出されたオーケストレーションのプロパティに設定されて**パブリック**です。</span><span class="sxs-lookup"><span data-stu-id="7d948-112">For the referenced orchestration to be callable, ensure that the **Type Modifier** property for the called orchestration is set to **Public**.</span></span> <span data-ttu-id="7d948-113">設定する、**型修飾子**にオーケストレーションのプロパティを**パブリック**、Microsoft では、オーケストレーションを開いて[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、を表示するオーケストレーションの上部にある緑のスタート図形をクリックして**オーケストレーションのプロパティ**ダイアログとセット、**型修飾子**プロパティを**パブリック**です。</span><span class="sxs-lookup"><span data-stu-id="7d948-113">To set the **Type Modifier** property for an orchestration to **Public**, open the orchestration in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], click the green start shape at the top of the orchestration to display the **Orchestration Properties** dialog and set the **Type Modifier** property to **Public**.</span></span> <span data-ttu-id="7d948-114">既定値**型修飾子**は**プライベート**です。</span><span class="sxs-lookup"><span data-stu-id="7d948-114">The default value for **Type Modifier** is **Private**.</span></span>  
  
 <span data-ttu-id="7d948-115">使用する方法の例については**オーケストレーションの開始**図形、SDK サンプルの「実装 Scatter and Gather Pattern」からダウンロード[http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)です。</span><span class="sxs-lookup"><span data-stu-id="7d948-115">For an example of how to use **Start Orchestration** shape, download the SDK sample "Implementing Scatter and Gather Pattern" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
### <a name="to-configure-a-start-orchestration-shape"></a><span data-ttu-id="7d948-116">オーケストレーションの開始図形を構成するには</span><span class="sxs-lookup"><span data-stu-id="7d948-116">To configure a Start Orchestration shape</span></span>  
  
1.  <span data-ttu-id="7d948-117">使用して、 **Orchestration Selection**ドロップダウン リスト ボックス、一覧から、オーケストレーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="7d948-117">Using the **Orchestration Selection** drop-down list box, select an orchestration from the list.</span></span>  
  
2.  <span data-ttu-id="7d948-118">使用して、**オーケストレーション パラメーター**グリッド コントロールをオーケストレーションに渡す引数を指定: で指定した、 **Orchestration Selection**ドロップダウン リスト ボックス-に開始されます。</span><span class="sxs-lookup"><span data-stu-id="7d948-118">Using the **Orchestration Parameters** grid control, specify arguments to pass to the orchestration—as specified in the **Orchestration Selection** drop-down list box—that is started.</span></span> <span data-ttu-id="7d948-119">これらの引数は、[変数] 列の各セルに 1 つずつ変数の名前を入力するか、各セルのドロップダウン リストでいずれかの変数をクリックすることによって指定します。</span><span class="sxs-lookup"><span data-stu-id="7d948-119">You specify these arguments in the cells of the Variable column, one variable per cell, by typing the name of a variable or clicking a variable from a drop-down list in a cell.</span></span>  
  
3.  <span data-ttu-id="7d948-120">構成する、**オーケストレーションの開始**サービスと、ダイアログ ボックスで指定した引数に応じて図形をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="7d948-120">To configure the **Start Orchestration** shape according to the service and arguments that you specified in the dialog box, click **OK**.</span></span> <span data-ttu-id="7d948-121">閉じるには、**オーケストレーション構成の開始**に変更を加えずに ダイアログ ボックス、**オーケストレーションの開始**図形をクリックして**キャンセル**です。</span><span class="sxs-lookup"><span data-stu-id="7d948-121">To close the **Start Orchestration Configuration** dialog box without making any changes to the **Start Orchestration** shape, click **Cancel**.</span></span>  
  
    > [!CAUTION]
    >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="7d948-122"> では、再帰的なオーケストレーションはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7d948-122"> does not support recursive orchestrations.</span></span> <span data-ttu-id="7d948-123">オーケストレーション A でオーケストレーション B を呼び出すか開始すると、オーケストレーション B でオーケストレーション A を直接呼び出したり開始したりすることはできなくなり、直接または間接的にオーケストレーション A を呼び出すオーケストレーションの呼び出しや開始もできなくなります。</span><span class="sxs-lookup"><span data-stu-id="7d948-123">If Orchestration A calls or starts Orchestration B, then Orchestration B cannot call or start Orchestration A directly, nor can it call or start any orchestration that directly or indirectly calls Orchestration A.</span></span>  
  
## <a name="orchestration-selection-drop-down-list-box"></a><span data-ttu-id="7d948-124">[Orchestration Selection] ボックス</span><span class="sxs-lookup"><span data-stu-id="7d948-124">Orchestration Selection drop-down list box</span></span>  
 <span data-ttu-id="7d948-125">ドロップダウン リスト ボックスの下矢印をクリックして使用可能なオーケストレーションを参照し、いずれか 1 つを選択します。</span><span class="sxs-lookup"><span data-stu-id="7d948-125">Click the Down arrow in the drop-down list box to view available orchestrations and select one.</span></span> <span data-ttu-id="7d948-126">この一覧には、参照アセンブリも含め、現在のオーケストレーションから開始できるすべてのオーケストレーションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7d948-126">This list contains all the orchestrations that can be started from the current orchestration, including referenced assemblies.</span></span>  
  
## <a name="orchestration-parameters-grid-control"></a><span data-ttu-id="7d948-127">[オーケストレーション パラメーター] グリッド コントロール</span><span class="sxs-lookup"><span data-stu-id="7d948-127">Orchestration Parameters grid control</span></span>  
 <span data-ttu-id="7d948-128">使用してパラメーター化されたオーケストレーションに渡す引数を指定する、**オーケストレーション パラメーター**グリッド コントロール。</span><span class="sxs-lookup"><span data-stu-id="7d948-128">You specify the arguments to pass to a parameterized orchestration by using the **Orchestration Parameters** grid control.</span></span> <span data-ttu-id="7d948-129">グリッドには、4 つの列:、変数のスコープ パラメーターの名前、パラメーターの型、パラメーターの方向。</span><span class="sxs-lookup"><span data-stu-id="7d948-129">The grid has four columns: Variables in Scope, Parameter Name, Parameter Type, and Parameter Direction.</span></span> <span data-ttu-id="7d948-130">変更を加えられるのは 1 列目のみで、その他の列は読み取り専用になっています。</span><span class="sxs-lookup"><span data-stu-id="7d948-130">You can make changes only in the first column; the other columns are read-only.</span></span>  
  
 <span data-ttu-id="7d948-131">有効なオーケストレーションを選択すると、そのパラメーターの値がグリッド コントロールの [パラメーター名]、[パラメーターの種類]、および [パラメーターの方向] 列に設定されます。</span><span class="sxs-lookup"><span data-stu-id="7d948-131">When you select a valid orchestration, its parameters populate the parameter name, type, and direction columns of the grid control.</span></span> <span data-ttu-id="7d948-132">次に、引数として渡す変数を各行で選択します。</span><span class="sxs-lookup"><span data-stu-id="7d948-132">You then select the variables in each row to pass as arguments.</span></span> <span data-ttu-id="7d948-133">これらの変数は、[スコープ内の変数] 列の各セルにあるドロップダウン リストから選択します。</span><span class="sxs-lookup"><span data-stu-id="7d948-133">You select these variables from a drop-down list present in each cell in the Variables in Scope column.</span></span> <span data-ttu-id="7d948-134">このドロップダウン リストには、隣の [パラメーターの種類] セルで指定された種類の使用可能な変数がすべて表示されます。</span><span class="sxs-lookup"><span data-stu-id="7d948-134">This list displays all the available variables of the type specified in the adjacent Parameter Type cell.</span></span> <span data-ttu-id="7d948-135">その種類の使用可能なオブジェクトが 1 つしかない場合、[スコープ内の変数] セルにはそのオブジェクトが自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="7d948-135">If only one object of that type is available, the Variables in Scope cell is automatically populated with that object.</span></span> <span data-ttu-id="7d948-136">[スコープ内の変数] セルのドロップダウン リストにある変数を直接入力して選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="7d948-136">You can also type in a Variables in Scope cell to select a variable that is available in the drop-down list.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7d948-137">**オーケストレーションの開始**図形がオーケストレーションを開始、このダイアログ ボックスで選択する「オーケストレーション パラメーター」は実際にはオーケストレーション変数を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d948-137">Because a **Start Orchestration** shape starts an orchestration, the "Orchestration Parameters" you select in this dialog box actually refer to orchestration variables.</span></span>  
  
 <span data-ttu-id="7d948-138">実行するオーケストレーションでパラメーターが定義されていない場合、このダイアログ ボックスのグリッド コントロールは使用できません。</span><span class="sxs-lookup"><span data-stu-id="7d948-138">If an orchestration you are executing has no defined parameters, the grid control in this dialog box is unavailable.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7d948-139">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="7d948-139">In This Section</span></span>  
 [<span data-ttu-id="7d948-140">作成する方法で呼び出されたオーケストレーションのサブスクリプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7d948-140">How to Create Receive Subscriptions at Invoked Orchestrations</span></span>](../core/how-to-create-receive-subscriptions-at-invoked-orchestrations.md) 
  
## <a name="see-also"></a><span data-ttu-id="7d948-141">参照</span><span class="sxs-lookup"><span data-stu-id="7d948-141">See Also</span></span>  
 [<span data-ttu-id="7d948-142">オーケストレーションの呼び出し図形を構成する方法</span><span class="sxs-lookup"><span data-stu-id="7d948-142">How to Configure the Call Orchestration Shape</span></span>](../core/how-to-configure-the-call-orchestration-shape.md)