---
title: "オーケストレーションの呼び出し図形を構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dabb73b3bed616f17c69923799169a7c6ca2b6d0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-call-orchestration-shape"></a><span data-ttu-id="6fe89-102">オーケストレーションの呼び出し図形を構成する方法</span><span class="sxs-lookup"><span data-stu-id="6fe89-102">How to Configure the Call Orchestration Shape</span></span>
<span data-ttu-id="6fe89-103">**オーケストレーションの呼び出し**図形を同期的に呼び出す別のプロジェクトで参照されているオーケストレーションを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="6fe89-103">The **Call Orchestration** shape can be used to synchronously call an orchestration that is referenced in another project.</span></span> <span data-ttu-id="6fe89-104">これにより、一般的なオーケストレーション ワークフロー パターンを BizTalk プロジェクト間で再利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="6fe89-104">This allows for reuse of common orchestration workflow patterns across BizTalk projects.</span></span> <span data-ttu-id="6fe89-105">同期的に入れ子になった別のオーケストレーションを呼び出した場合、**オーケストレーションの呼び出し**図形、外側のオーケストレーションが、入れ子になったオーケストレーションで続行する前に完了を待機します。</span><span class="sxs-lookup"><span data-stu-id="6fe89-105">When you invoke another nested orchestration synchronously with the **Call Orchestration** shape the enclosing orchestration waits for the nested orchestration to finish before continuing.</span></span>  
  
 <span data-ttu-id="6fe89-106">ネストされているオーケストレーションに渡すパラメーターを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="6fe89-106">You can specify parameters that will be passed to the nested orchestration.</span></span> <span data-ttu-id="6fe89-107">パラメーターとして指定できるのは、メッセージ、変数、ポート参照、ロール リンク、または関連付けセットです。</span><span class="sxs-lookup"><span data-stu-id="6fe89-107">Parameters can be messages, variables, port references, role links, or correlation sets.</span></span> <span data-ttu-id="6fe89-108">渡されたポート参照、ロール リンク、および関連付けセットが自動的に指定される封筒のように機能します。、外側のオーケストレーションに情報が送信を使用すると、入れ子になったオーケストレーション情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="6fe89-108">Passed-in port references, role links, and correlation sets all perform like self-addressed envelopes: they supply the nested orchestration information it can use to send information back to the enclosing orchestration.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="6fe89-109">XmlDocument や XmlNode などのシリアル化できないオブジェクトをパラメーターとしてオーケストレーションに渡すと失敗します。</span><span class="sxs-lookup"><span data-stu-id="6fe89-109">If you pass nonserializable objects such as XmlDocument or XmlNode as parameters to an orchestration, it will fail.</span></span>  
  
 <span data-ttu-id="6fe89-110">使用する方法の例については**オーケストレーションの呼び出し**図形は、「 [CallOrchestration (BizTalk Server サンプル)](../core/callorchestration-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="6fe89-110">For an example of how to use **Call Orchestration** shape, see [CallOrchestration (BizTalk Server Sample)](../core/callorchestration-biztalk-server-sample.md).</span></span>  
  
### <a name="to-configure-a-call-orchestration-shape"></a><span data-ttu-id="6fe89-111">オーケストレーションの呼び出し図形を構成するには</span><span class="sxs-lookup"><span data-stu-id="6fe89-111">To configure a Call Orchestration shape</span></span>  
  
1.  <span data-ttu-id="6fe89-112">使用して、 **Orchestration Selection**ドロップダウン リスト ボックス、一覧から、オーケストレーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="6fe89-112">Using the **Orchestration Selection** drop-down list box, select an orchestration from the list.</span></span>  
  
2.  <span data-ttu-id="6fe89-113">使用して、**オーケストレーション パラメーター**グリッド コントロールをオーケストレーションに渡す引数を指定 — で指定した、 **Orchestration Selection**ドロップダウン リスト ボックス-呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="6fe89-113">Using the **Orchestration Parameters** grid control, specify arguments to pass to the orchestration—as specified in the **Orchestration Selection** drop-down list box—that is called.</span></span> <span data-ttu-id="6fe89-114">これらの引数は、[変数] 列の各セルに 1 つずつ変数の名前を入力するか、各セルのドロップダウン リストでいずれかの変数をクリックすることによって指定します。</span><span class="sxs-lookup"><span data-stu-id="6fe89-114">You specify these arguments in the cells of the Variable column, one variable per cell, by typing the name of a variable or clicking a variable from a drop-down list in a cell.</span></span>  
  
3.  <span data-ttu-id="6fe89-115">構成する、**オーケストレーションの呼び出し**サービスと、ダイアログ ボックスで指定した引数に応じて図形をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="6fe89-115">To configure the **Call Orchestration** shape according to the service and arguments that you specified in the dialog box, click **OK**.</span></span> <span data-ttu-id="6fe89-116">閉じるには、**オーケストレーション構成の呼び出し**に変更を加えずに ダイアログ ボックス、**オーケストレーションの呼び出し**図形をクリックして**キャンセル**です。</span><span class="sxs-lookup"><span data-stu-id="6fe89-116">To close the **Call Orchestration Configuration** dialog box without making any changes to the **Call Orchestration** shape, click **Cancel**.</span></span>  
  
    > [!CAUTION]
    >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="6fe89-117"> では、再帰的なオーケストレーションはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6fe89-117"> does not support recursive orchestrations.</span></span> <span data-ttu-id="6fe89-118">オーケストレーション A でオーケストレーション B を呼び出すか開始すると、オーケストレーション B でオーケストレーション A を直接呼び出したり開始したりすることはできなくなり、直接または間接的にオーケストレーション A を呼び出すオーケストレーションの呼び出しや開始もできなくなります。</span><span class="sxs-lookup"><span data-stu-id="6fe89-118">If Orchestration A calls or starts Orchestration B, then Orchestration B cannot call or start Orchestration A directly, nor can it call or start any orchestration that directly or indirectly calls Orchestration A.</span></span>  
  
## <a name="referenced-orchestrations"></a><span data-ttu-id="6fe89-119">参照されているオーケストレーション</span><span class="sxs-lookup"><span data-stu-id="6fe89-119">Referenced Orchestrations</span></span>  
 <span data-ttu-id="6fe89-120">参照されているオーケストレーションを呼び出せるようにするには、呼び出し先オーケストレーションに対して次のプロパティが構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6fe89-120">For the referenced orchestration to be callable, ensure that the following properties have been configured for the called orchestration:</span></span>  
  
-   <span data-ttu-id="6fe89-121">設定、**型修飾子**プロパティを**パブリック**呼び出されたオーケストレーションにします。</span><span class="sxs-lookup"><span data-stu-id="6fe89-121">Set the **Type Modifier** property to **Public** for the called orchestration.</span></span> <span data-ttu-id="6fe89-122">設定する、**型修飾子**にオーケストレーションのプロパティを**パブリック**、Microsoft では、オーケストレーションを開いて[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、を表示するオーケストレーションの上部にある緑のスタート図形をクリックして**オーケストレーションのプロパティ**ダイアログとセット、**型修飾子**プロパティを**パブリック**です。</span><span class="sxs-lookup"><span data-stu-id="6fe89-122">To set the **Type Modifier** property for an orchestration to **Public**, open the orchestration in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], click the green start shape at the top of the orchestration to display the **Orchestration Properties** dialog and set the **Type Modifier** property to **Public**.</span></span>  
  
-   <span data-ttu-id="6fe89-123">設定、 **Activate**をオーケストレーションの最初の受信図形のプロパティ**False**です。</span><span class="sxs-lookup"><span data-stu-id="6fe89-123">Set the **Activate** property of the initial receive shape in the orchestration to **False**.</span></span>  
  
## <a name="orchestration-selection-drop-down-list-box"></a><span data-ttu-id="6fe89-124">[Orchestration Selection] ボックス</span><span class="sxs-lookup"><span data-stu-id="6fe89-124">Orchestration Selection drop-down list box</span></span>  
 <span data-ttu-id="6fe89-125">ドロップダウン リスト ボックスの下矢印をクリックして使用可能なサービスを参照し、いずれか 1 つを選択します。</span><span class="sxs-lookup"><span data-stu-id="6fe89-125">Click the Down arrow in the drop-down list box to view available services and select one.</span></span> <span data-ttu-id="6fe89-126">この一覧には、参照アセンブリも含め、現在のオーケストレーションから呼び出せるすべてのサービスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6fe89-126">This list contains all the services that can be called from the current orchestration, including referenced assemblies.</span></span>  
  
## <a name="orchestration-parameters-grid-control"></a><span data-ttu-id="6fe89-127">[オーケストレーション パラメーター] グリッド コントロール</span><span class="sxs-lookup"><span data-stu-id="6fe89-127">Orchestration Parameters grid control</span></span>  
 <span data-ttu-id="6fe89-128">使用してパラメーター化されたオーケストレーションに渡す引数を指定する、**オーケストレーション パラメーター**グリッド コントロール。</span><span class="sxs-lookup"><span data-stu-id="6fe89-128">You specify the arguments to pass to a parameterized orchestration by using the **Orchestration Parameters** grid control.</span></span> <span data-ttu-id="6fe89-129">グリッドには、4 つの列:、変数のスコープ パラメーターの名前、パラメーターの型、パラメーターの方向。</span><span class="sxs-lookup"><span data-stu-id="6fe89-129">The grid has four columns: Variables in Scope, Parameter Name, Parameter Type, and Parameter Direction.</span></span> <span data-ttu-id="6fe89-130">変更を加えられるのは 1 列目のみで、その他の列は読み取り専用になっています。</span><span class="sxs-lookup"><span data-stu-id="6fe89-130">You can make changes only in the first column; the other columns are read-only.</span></span>  
  
 <span data-ttu-id="6fe89-131">有効なオーケストレーションを選択すると、そのパラメーターは、パラメーター名、種類、方向、グリッド コントロールの列を設定します。</span><span class="sxs-lookup"><span data-stu-id="6fe89-131">When you select a valid orchestration, its parameters populate the parameter name, type and direction columns of the grid control.</span></span> <span data-ttu-id="6fe89-132">次に、引数として渡す変数を各行で選択します。</span><span class="sxs-lookup"><span data-stu-id="6fe89-132">You then select the variables in each row to pass as arguments.</span></span> <span data-ttu-id="6fe89-133">これらの変数は、[スコープ内の変数] 列の各セルにあるドロップダウン リストから選択します。</span><span class="sxs-lookup"><span data-stu-id="6fe89-133">You select these variables from a drop-down list present in each cell in the Variables in Scope column.</span></span> <span data-ttu-id="6fe89-134">このドロップダウン リストには、隣の [パラメーターの種類] セルで指定された種類の使用可能な変数がすべて表示されます。</span><span class="sxs-lookup"><span data-stu-id="6fe89-134">This list displays all the available variables of the type specified in the adjacent Parameter Type cell.</span></span> <span data-ttu-id="6fe89-135">その種類の使用可能なオブジェクトが 1 つしかない場合、[スコープ内の変数] セルにはそのオブジェクトが自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="6fe89-135">If only one object of that type is available, the Variables in Scope cell is automatically populated with that object.</span></span> <span data-ttu-id="6fe89-136">[スコープ内の変数] セルのドロップダウン リストにある変数を直接入力して選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="6fe89-136">You can also type in a Variables in Scope cell to select a variable that is available in the drop-down list.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6fe89-137">**オーケストレーションの呼び出し**図形がオーケストレーションを呼び出して、このダイアログ ボックスで選択する「オーケストレーション パラメーター」は実際にはオーケストレーション変数を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fe89-137">Because a **Call Orchestration** shape calls an orchestration, the "Orchestration Parameters" you select in this dialog box actually refer to orchestration variables.</span></span>  
  
 <span data-ttu-id="6fe89-138">呼び出し先オーケストレーションでパラメーターが定義されていない場合、このダイアログ ボックスのグリッド コントロールは使用できません。</span><span class="sxs-lookup"><span data-stu-id="6fe89-138">If an orchestration you are calling has no defined parameters, the grid control in this dialog box is unavailable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fe89-139">参照</span><span class="sxs-lookup"><span data-stu-id="6fe89-139">See Also</span></span>  
 [<span data-ttu-id="6fe89-140">オーケストレーションの開始図形を構成する方法</span><span class="sxs-lookup"><span data-stu-id="6fe89-140">How to Configure the Start Orchestration Shape</span></span>](../core/how-to-configure-the-start-orchestration-shape.md)