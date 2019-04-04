---
title: Functoid 入力パラメーターを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- bts10.mapper.functoid.inputs
ms.assetid: 2c8f773a-932c-423d-b3fe-724265304b0a
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69048e7ec60ad723a8393c745ccd17c8cdd4bd16
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999795"
---
# <a name="how-to-configure-functoid-input-parameters"></a><span data-ttu-id="51df2-102">Functoid 入力パラメーターを構成する方法</span><span class="sxs-lookup"><span data-stu-id="51df2-102">How to Configure Functoid Input Parameters</span></span>
<span data-ttu-id="51df2-103">マップ内の Functoid に対する入力パラメーターを適切に構成する操作は、最も重要な操作の 1 つです。ただし、Functoid を使用する際にエラーが発生する可能性があるので注意して行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="51df2-103">Properly configuring the input parameters to the functoids in your map is one of the most important, and potentially error-prone, aspects of using functoids.</span></span> <span data-ttu-id="51df2-104">Functoid の入力パラメーターは次のように構成できます。</span><span class="sxs-lookup"><span data-stu-id="51df2-104">You can configure the functoid input parameters as follows:</span></span>  
  
- <span data-ttu-id="51df2-105">接続のスキーマ ノードと個々 の functoid (ドラッグ アンド ドロップを functoid にスキーマ ノードからマウス) で表示可能な入力リンクを作成します。</span><span class="sxs-lookup"><span data-stu-id="51df2-105">Create visible input links by connecting schema nodes and respective functoids (drag-and-drop the mouse from schema node to the functoid).</span></span>  
  
- <span data-ttu-id="51df2-106">使用して入力パラメーターの一覧を直接編集、**構成\<Functoid\> Functoid**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="51df2-106">Directly edit the list of input parameters using the **Configure \<Functoid\> Functoid** dialog box.</span></span>  
  
  <span data-ttu-id="51df2-107">これらのメソッドを使用して、functoid の入力パラメーターを構成する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="51df2-107">This topic provides step-by-step instructions for configuring the input parameters for a functoid using these methods.</span></span>  
  
  <span data-ttu-id="51df2-108">ドラッグして Functoid の入力パラメーターを設定する方法は、XPath 仕様を含む入力パラメーターを送信元スキーマに指定する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="51df2-108">The dragging method of establishing functoid input parameters provides a convenient way to specify input parameters that involve XPath specifications into the source schema.</span></span> <span data-ttu-id="51df2-109">スキーマ ノードおよび functoid の入力パラメーターを作成する方法の詳細については、[マップに基本 Functoid を追加する方法](../core/how-to-add-basic-functoids-to-a-map.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51df2-109">For information on creating a schema node and functoid input parameters, see [How to Add Basic Functoids to a Map](../core/how-to-add-basic-functoids-to-a-map.md).</span></span> <span data-ttu-id="51df2-110">ただし、**構成\<Functoid\> Functoid**  ダイアログ ボックスは、明確なメカニズムの functoid へのすべての入力パラメーターを表示、作成と、定数のパラメーターを変更、およびの必要に応じて入力パラメーターの順序の再配置します。</span><span class="sxs-lookup"><span data-stu-id="51df2-110">However, the **Configure \<Functoid\> Functoid** dialog box is the definitive mechanism for viewing all the input parameters to a functoid, for creating and modifying any constant parameters, and for re-arranging the order of the input parameters when necessary.</span></span>  
  
  <span data-ttu-id="51df2-111">グリッド ページで Functoid の入力パラメーターを直接構成する (マウスのドラッグ アンド ドロップによって送信元スキーマ ノードから線を描画して Functoid にリンクする) 場合、入力数が最大値に達すると、カーソルが禁止の状態に変わります。</span><span class="sxs-lookup"><span data-stu-id="51df2-111">When you configure the input parameters for a functoid directly on the grid page (by drawing lines, using the mouse drag-and-drop, from the source schema node and linking it to the functoid), if the number of inputs reaches maximum, the cursor changes to a NO state.</span></span> <span data-ttu-id="51df2-112">また、ステータス バーに理由が表示されます。</span><span class="sxs-lookup"><span data-stu-id="51df2-112">Also, the status bar displays the reason.</span></span> <span data-ttu-id="51df2-113">次の図は、入力リンクを 1 つだけ受け付ける Functoid を示しています。</span><span class="sxs-lookup"><span data-stu-id="51df2-113">The figure below shows a functoid which accepts only one input link.</span></span>  
  
  <span data-ttu-id="51df2-114">![Functoid 入力パラメーターを構成するための NO 状態](../core/media/configure-input-parameters-no-state.gif "Configure_input_parameters_NO_state")</span><span class="sxs-lookup"><span data-stu-id="51df2-114">![NO state for configuring functoid input parameter](../core/media/configure-input-parameters-no-state.gif "Configure_input_parameters_NO_state")</span></span>  
  
  <span data-ttu-id="51df2-115">使用してスクリプトの作成とテーブル ループ functoid を構成することができます、**構成\<Functoid\> Functoid**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="51df2-115">You can configure the Scripting and Table Looping functoids using the **Configure \<Functoid\> Functoid** dialog box.</span></span> <span data-ttu-id="51df2-116">Functoid を構成する方法については、[スクリプト Functoid を構成する方法](../core/how-to-configure-the-scripting-functoid.md)と[テーブル ループとテーブル抽出 Functoid を構成する方法](../core/how-to-configure-the-table-looping-and-table-extractor-functoids.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51df2-116">For information about how to configure the functoids, see [How to Configure the Scripting Functoid](../core/how-to-configure-the-scripting-functoid.md) and [How to Configure the Table Looping and Table Extractor Functoids](../core/how-to-configure-the-table-looping-and-table-extractor-functoids.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="51df2-117">前提条件</span><span class="sxs-lookup"><span data-stu-id="51df2-117">Prerequisites</span></span>  
 <span data-ttu-id="51df2-118">これらの手順では、BizTalk マッパーが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="51df2-118">These instructions require that BizTalk Mapper is running.</span></span>  
  
## <a name="what-is-an-input-parameter"></a><span data-ttu-id="51df2-119">入力パラメーターとは</span><span class="sxs-lookup"><span data-stu-id="51df2-119">What is an input parameter?</span></span>  
 <span data-ttu-id="51df2-120">入力パラメーターには、次のいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="51df2-120">An input parameter can be any of the following:</span></span>  
  
-   <span data-ttu-id="51df2-121">送信元スキーマ ノードから Functoid へのリンク</span><span class="sxs-lookup"><span data-stu-id="51df2-121">A link from source schema node to a functoid</span></span>  
  
-   <span data-ttu-id="51df2-122">Functoid から別の有効な Functoid へのリンク</span><span class="sxs-lookup"><span data-stu-id="51df2-122">A link from functoid to another valid functoid</span></span>  
  
-   <span data-ttu-id="51df2-123">定数値</span><span class="sxs-lookup"><span data-stu-id="51df2-123">A constant value</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="51df2-124">など一部の functoid がある**日付**、**時間**、**日付と時刻**、および**Nil**、すべての入力パラメーターを必要としません。</span><span class="sxs-lookup"><span data-stu-id="51df2-124">There are a few functoids, such as **Date**, **Time**, **Date and Time**, and **Nil**, which do not need any input parameters.</span></span>  
  
 <span data-ttu-id="51df2-125">次の図に、2 つの入力パラメーター (Input[0] および Input[1]) と定数パラメーター (Input[2]) を持つ Functoid (赤で強調表示) を示します。</span><span class="sxs-lookup"><span data-stu-id="51df2-125">The figure below displays a functoid (highlighted in red) with two input parameters (Input[0] and Input[1]) and a constant parameter (Input[2]).</span></span>  
  
 <span data-ttu-id="51df2-126">![Functoid に入力パラメーターの表示](../core/media/identifying-input-parameters.gif "Identifying_input_parameters")</span><span class="sxs-lookup"><span data-stu-id="51df2-126">![Displaying the input parameters to a functoid](../core/media/identifying-input-parameters.gif "Identifying_input_parameters")</span></span>  
  
## <a name="to-open-the-configure-functoid-functoid-dialog-box"></a><span data-ttu-id="51df2-127">構成を開く\<Functoid\> Functoid のダイアログ ボックス</span><span class="sxs-lookup"><span data-stu-id="51df2-127">To open the Configure \<Functoid\> Functoid dialog box</span></span>  
 <span data-ttu-id="51df2-128">開くことができます、**構成\<Functoid\> Functoid**  ダイアログ ボックスで、次の方法のいずれか。</span><span class="sxs-lookup"><span data-stu-id="51df2-128">You can open the **Configure \<Functoid\> Functoid** dialog box in one of the following ways:</span></span>  
  
-   <span data-ttu-id="51df2-129">関連するグリッド ページで、functoid を右クリックし、順にクリックします**Functoid 入力の構成**します。</span><span class="sxs-lookup"><span data-stu-id="51df2-129">In the relevant grid page, right-click the functoid, and then click **Configure Functoid Inputs**.</span></span>  
  
-   <span data-ttu-id="51df2-130">入力パラメーターを構成する Functoid をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="51df2-130">Double-click the functoid for which you want to configure the input parameters.</span></span>  
  
-   <span data-ttu-id="51df2-131">Functoid を選択し、省略記号ボタンをクリックし (**.**) Visual studio の**プロパティ**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="51df2-131">Select the functoid and then click the ellipses (**…**) in the Visual Studio’s **Properties** window.</span></span>  
  
-   <span data-ttu-id="51df2-132">Functoid を選択し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="51df2-132">Select the functoid and then press ENTER from the keyboard.</span></span>  
  
-   <span data-ttu-id="51df2-133">Functoid を選択し、Ctrl キーを押しながら M キーを押し、Ctrl キーを押しながら I キーを押します。</span><span class="sxs-lookup"><span data-stu-id="51df2-133">Select the functoid and then press CTRL+M, CTRL+I from the keyboard.</span></span> <span data-ttu-id="51df2-134">マッパーのショートカット キーの一覧は、[BizTalk マッパーのキーボード ショートカット](../core/biztalk-mapper-keyboard-shortcuts.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51df2-134">For a list of Mapper shortcut keys, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
### <a name="to-insert-constant-input-parameters"></a><span data-ttu-id="51df2-135">定数の入力パラメーターを挿入するには</span><span class="sxs-lookup"><span data-stu-id="51df2-135">To insert constant input parameters</span></span>  
  
1.  <span data-ttu-id="51df2-136">**構成\<Functoid\> Functoid**ダイアログ ボックスで、 **Functoid 入力の**タブ。</span><span class="sxs-lookup"><span data-stu-id="51df2-136">In the **Configure \<Functoid\> Functoid** dialog box, select the **Functoid Inputs** tab.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="51df2-137">**Functoid 入力の**タブは既定で選択します。</span><span class="sxs-lookup"><span data-stu-id="51df2-137">The **Functoid Inputs** tab is selected by default.</span></span>  
  
2.  <span data-ttu-id="51df2-138">をクリックして、 ![functoid への定数入力パラメーターの追加](../core/media/add-input-parameters.gif "Add_input_parameters")ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="51df2-138">Click the ![Adding constant input parameters to a functoid](../core/media/add-input-parameters.gif "Add_input_parameters") button.</span></span> <span data-ttu-id="51df2-139">新しい行が追加されます。</span><span class="sxs-lookup"><span data-stu-id="51df2-139">A new row is added.</span></span>  
  
3.  <span data-ttu-id="51df2-140">新しい入力パラメーターの値を入力し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="51df2-140">Type the value for the new input parameter, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="51df2-141">追加ボタンが使用できない場合は、Functoid が入力パラメーターを受け入れないか、入力パラメーターを必要としていません。または、許可される入力パラメーターの最大数に達しています。</span><span class="sxs-lookup"><span data-stu-id="51df2-141">If the add button is not enabled, the functoid does not accept or require input parameters, or may already have the maximum number of allowed inputs.</span></span>  
  
### <a name="to-edit-existing-constant-input-parameters"></a><span data-ttu-id="51df2-142">既存の定数入力パラメーターを編集するには</span><span class="sxs-lookup"><span data-stu-id="51df2-142">To edit existing constant input parameters</span></span>  
  
1.  <span data-ttu-id="51df2-143">**構成\<Functoid\> Functoid**ダイアログ ボックスで、既存の定数入力パラメーターを編集する をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51df2-143">In the **Configure \<Functoid\> Functoid** dialog box, click the existing constant input parameter that you want to edit.</span></span> <span data-ttu-id="51df2-144">現在の値が選択されています。</span><span class="sxs-lookup"><span data-stu-id="51df2-144">The current value is selected.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="51df2-145">編集できるのは定数入力のパラメーターだけです。</span><span class="sxs-lookup"><span data-stu-id="51df2-145">You can edit the parameters of constant inputs only.</span></span> <span data-ttu-id="51df2-146">その他の種類の入力パラメーターは編集できません。</span><span class="sxs-lookup"><span data-stu-id="51df2-146">Input parameters of all other types cannot be edited.</span></span> <span data-ttu-id="51df2-147">順序の並べ替えまたは削除のみ行うことができます。</span><span class="sxs-lookup"><span data-stu-id="51df2-147">They can only be rearranged or deleted.</span></span>  
  
2.  <span data-ttu-id="51df2-148">をクリックして、![定数入力パラメーターの編集](../core/media/edit-input-parameters.gif "Edit_input_parameters")ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="51df2-148">Click the ![Editing constant input parameters](../core/media/edit-input-parameters.gif "Edit_input_parameters") button.</span></span> <span data-ttu-id="51df2-149">定数の値に必要な変更を行い、をクリックし、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="51df2-149">Make the appropriate changes to the constant value, and then click **OK**.</span></span>  
  
     <span data-ttu-id="51df2-150">この代わりに、定数入力パラメーターをダブルクリックして編集するか、または F2 キーを押すこともできます。</span><span class="sxs-lookup"><span data-stu-id="51df2-150">Alternatively, you can double-click the constant input parameter to edit it, or press F2 from the keyboard.</span></span>  
  
## <a name="to-select-multiple-input-parameters"></a><span data-ttu-id="51df2-151">複数の入力パラメーターを選択するには</span><span class="sxs-lookup"><span data-stu-id="51df2-151">To select multiple input parameters</span></span>  
 <span data-ttu-id="51df2-152">Ctrl キーを押しながら目的の行をクリックして複数の入力パラメーターを選択した後、次のいずれかの操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="51df2-152">You can select multiple input parameters by holding down the CTRL key and clicking the desired rows, and then perform any of the following operations.</span></span> <span data-ttu-id="51df2-153">Ctrl キーを押しながら A キーを押すと、すべての行を選択できます。</span><span class="sxs-lookup"><span data-stu-id="51df2-153">You can press CTRL+A from the keyboard to select all the rows.</span></span>  
  
-   <span data-ttu-id="51df2-154">選択項目を上下に移動します。</span><span class="sxs-lookup"><span data-stu-id="51df2-154">Move the selection up/down.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="51df2-155">一括選択に一番上の行または一番下の行が含まれる場合は、選択項目を上下に移動することはできません。</span><span class="sxs-lookup"><span data-stu-id="51df2-155">If the bulk selection includes either the top-most or the bottom-most row among the other rows, you cannot move the selection up/down respectively.</span></span>  
  
-   <span data-ttu-id="51df2-156">選択項目を並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="51df2-156">Rearrange the selection.</span></span>  
  
-   <span data-ttu-id="51df2-157">選択項目を削除します。</span><span class="sxs-lookup"><span data-stu-id="51df2-157">Delete the selection.</span></span>  
  
### <a name="to-change-the-order-of-existing-input-parameters"></a><span data-ttu-id="51df2-158">既存の入力パラメーターの順序を変更するには</span><span class="sxs-lookup"><span data-stu-id="51df2-158">To change the order of existing input parameters</span></span>  
  
1.  <span data-ttu-id="51df2-159">**構成\<Functoid\> Functoid**ダイアログ ボックスで、既存の入力パラメーターの入力パラメーターの順序付きリストで別の位置に移動する をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51df2-159">In the **Configure \<Functoid\> Functoid** dialog box, click the existing input parameter that you want to move to a different position in the ordered list of input parameters.</span></span>  
  
2.  <span data-ttu-id="51df2-160">をクリックして、![の一覧で上へ移動](../core/media/move-up-button.gif "Move_up_button")パラメーター リストで、パラメーターを上に移動するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="51df2-160">Click the ![Move up in the list](../core/media/move-up-button.gif "Move_up_button") button to move the parameter up in the parameter list.</span></span> <span data-ttu-id="51df2-161">選択した入力パラメーターが目的の位置になるまで必要なだけ繰り返します。</span><span class="sxs-lookup"><span data-stu-id="51df2-161">Repeat as necessary until the selected input parameter is in the desired position.</span></span> <span data-ttu-id="51df2-162">または、上方向キーを押してもかまいません。</span><span class="sxs-lookup"><span data-stu-id="51df2-162">Alternatively, you can press the UP ARROW key from the keyboard.</span></span> <span data-ttu-id="51df2-163">マッパーのショートカット キーの一覧は、[BizTalk マッパーのキーボード ショートカット](../core/biztalk-mapper-keyboard-shortcuts.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51df2-163">For a list of Mapper shortcut keys, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
     <span data-ttu-id="51df2-164">-または-</span><span class="sxs-lookup"><span data-stu-id="51df2-164">-OR-</span></span>  
  
     <span data-ttu-id="51df2-165">をクリックして、![一覧で下へ移動](../core/media/move-down-button.gif "Move_down_button")パラメーター リストで、パラメーターを下に移動するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="51df2-165">Click the ![Moving down in a list](../core/media/move-down-button.gif "Move_down_button") button to move the parameter down in the parameter list.</span></span> <span data-ttu-id="51df2-166">選択した入力パラメーターが目的の位置になるまで必要なだけ繰り返します。</span><span class="sxs-lookup"><span data-stu-id="51df2-166">Repeat as necessary until the selected input parameter is in the desired position.</span></span> <span data-ttu-id="51df2-167">または、下方向キーを押してもかまいません。</span><span class="sxs-lookup"><span data-stu-id="51df2-167">Alternatively, you can press the DOWN ARROW key from the keyboard.</span></span> <span data-ttu-id="51df2-168">マッパーのショートカット キーの一覧は、[BizTalk マッパーのキーボード ショートカット](../core/biztalk-mapper-keyboard-shortcuts.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51df2-168">For a list of Mapper shortcut keys, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="51df2-169">のみからの入力のシーケンスを並べ替えることができます、**構成\<Functoid\> Functoid**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="51df2-169">You can rearrange the sequence of inputs only from the **Configure \<Functoid\> Functoid** dialog box.</span></span> <span data-ttu-id="51df2-170">最上位または最下位の行を選択した場合、![の一覧で上へ移動](../core/media/move-up-button.gif "Move_up_button")または![一覧で下へ移動](../core/media/move-down-button.gif "Move_down_button")ボタンが無効になります、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="51df2-170">If you select the top-most or bottom-most row, the ![Move up in the list](../core/media/move-up-button.gif "Move_up_button") or ![Moving down in a list](../core/media/move-down-button.gif "Move_down_button") buttons would be disabled, respectively.</span></span>  
  
### <a name="to-delete-an-input-parameter-by-deleting-the-input-link"></a><span data-ttu-id="51df2-171">入力リンクを削除して入力パラメーターを削除するには</span><span class="sxs-lookup"><span data-stu-id="51df2-171">To delete an input parameter by deleting the input link</span></span>  
  
1.  <span data-ttu-id="51df2-172">関連するグリッド ページで、削除する入力パラメーターに対応する入力リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="51df2-172">In the relevant grid page, click the input link corresponding to the input parameter you want to delete.</span></span>  
  
2.  <span data-ttu-id="51df2-173">**編集** メニューのをクリックして**削除**します。</span><span class="sxs-lookup"><span data-stu-id="51df2-173">On the **Edit** menu, click **Delete**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="51df2-174">またはを DEL キーを押してまたは関連するグリッド ページで、リンクを右クリックし、をクリックして**削除**ショートカット メニューから。</span><span class="sxs-lookup"><span data-stu-id="51df2-174">Alternatively, you can press the DELETE key, or right-click the link in the relevant grid page, and click **Delete** from the shortcut menu.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="51df2-175">入力リンクは、確認メッセージが表示されずに削除されます。</span><span class="sxs-lookup"><span data-stu-id="51df2-175">The input link is deleted silently.</span></span> <span data-ttu-id="51df2-176">よくわからない場合は削除をいつでも元に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="51df2-176">You can always undo delete if you are not sure about it.</span></span> <span data-ttu-id="51df2-177">元に戻す/やり直し操作の詳細については、[を元に戻すまたはユーザーの操作をやり直す方法](../core/how-to-undo-or-redo-user-operations.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51df2-177">For more information about undo/redo operations, see [How to Undo or Redo User Operations](../core/how-to-undo-or-redo-user-operations.md).</span></span>  
  
### <a name="to-delete-existing-input-parameters-within-the-configure-functoid-functoid-dialog-box"></a><span data-ttu-id="51df2-178">既存の入力パラメーターの構成を削除する\<Functoid\> Functoid のダイアログ ボックス</span><span class="sxs-lookup"><span data-stu-id="51df2-178">To delete existing input parameters within the Configure \<Functoid\> Functoid dialog box</span></span>  
  
1.  <span data-ttu-id="51df2-179">**構成\<Functoid\> Functoid**ダイアログ ボックスで、既存の入力パラメーターを削除する をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51df2-179">In the **Configure \<Functoid\> Functoid** dialog box, click the existing input parameter that you want to delete.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="51df2-180">この方法を使用して、入力パラメーター (入力リンクに対応するパラメーターを含む) を削除できます。</span><span class="sxs-lookup"><span data-stu-id="51df2-180">You can delete any input parameter using this technique, even those that correspond to an input link.</span></span>  
  
2.  <span data-ttu-id="51df2-181">をクリックして、![選択項目の削除](../core/media/delete-button.gif "Delete_button")ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="51df2-181">Click the ![Deleting the selection](../core/media/delete-button.gif "Delete_button") button.</span></span> <span data-ttu-id="51df2-182">選択した既存の入力パラメーターが、パラメーター一覧から削除されます。</span><span class="sxs-lookup"><span data-stu-id="51df2-182">The selected existing input parameter is deleted from the parameter list.</span></span> <span data-ttu-id="51df2-183">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="51df2-183">Click **OK**.</span></span>  
  
     <span data-ttu-id="51df2-184">または、削除する行を選択して、キーボードの Del キーを押します。</span><span class="sxs-lookup"><span data-stu-id="51df2-184">Alternatively, you can select the row you want to delete, and press the DELETE key from the keyboard.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="51df2-185">入力パラメーターは、確認メッセージが表示されずに削除されます。</span><span class="sxs-lookup"><span data-stu-id="51df2-185">The input parameter is deleted silently.</span></span> <span data-ttu-id="51df2-186">よくわからない場合は削除をいつでも元に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="51df2-186">You can always undo delete if you are not sure about it.</span></span> <span data-ttu-id="51df2-187">元に戻す/やり直し操作の詳細については、[を元に戻すまたはユーザーの操作をやり直す方法](../core/how-to-undo-or-redo-user-operations.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51df2-187">For more information about undo/redo operations, see [How to Undo or Redo User Operations](../core/how-to-undo-or-redo-user-operations.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="51df2-188">削除ボタンは、パラメーターの一覧に入力パラメーターがないと使用できません。</span><span class="sxs-lookup"><span data-stu-id="51df2-188">The delete button is not enabled when there are no input parameters in the parameter list.</span></span>  
  
## <a name="to-set-labels-and-comments-for-functoids"></a><span data-ttu-id="51df2-189">Functoid のラベルおよびコメントを設定するには</span><span class="sxs-lookup"><span data-stu-id="51df2-189">To set labels and comments for functoids</span></span>  
 <span data-ttu-id="51df2-190">Functoid を使用してのラベルおよびコメントを設定することができます、**構成\<Functoid\> Functoid**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="51df2-190">You can set labels and comments for functoids using the **Configure \<Functoid\> Functoid** dialog box.</span></span>  
  
1.  <span data-ttu-id="51df2-191">**構成\<Functoid\> Functoid**ダイアログ ボックスで、をクリックして、**ラベルとコメント**タブ。</span><span class="sxs-lookup"><span data-stu-id="51df2-191">In the **Configure \<Functoid\> Functoid** dialog box, click the **Label and Comments** tab.</span></span>  
  
2.  <span data-ttu-id="51df2-192">型、**ラベル**と**コメント**、 をクリックし、 **OK**。</span><span class="sxs-lookup"><span data-stu-id="51df2-192">Type the **Label** and **Comments**, and then click **OK**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="51df2-193">ラベルとコメントの functoid やリンクする方法の詳細については、[リンクにラベルを付ける方法](../core/how-to-label-a-link.md)と[方法、Functoid ラベルとコメント](../core/how-to-label-and-comment-a-functoid.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51df2-193">For more information about how to label and comment functoids and/or links, see [How to Label a Link](../core/how-to-label-a-link.md) and [How to Label and Comment a Functoid](../core/how-to-label-and-comment-a-functoid.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51df2-194">参照</span><span class="sxs-lookup"><span data-stu-id="51df2-194">See Also</span></span>  
 [<span data-ttu-id="51df2-195">Functoid のプロパティおよび入力パラメーターの編集</span><span class="sxs-lookup"><span data-stu-id="51df2-195">Editing Functoid Properties and Input Parameters</span></span>](../core/editing-functoid-properties-and-input-parameters.md)