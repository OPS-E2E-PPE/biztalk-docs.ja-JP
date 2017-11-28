---
title: "受信図形を構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- filter expressions, Receive shape [Orchestration Designer]
- Receive shape [Orchestration Designer], about Receive shape
- configuring [Orchestration Designer], Receive shapes
- Receive shape [Orchestration Designer]
- Receive shape [Orchestration Designer], filter expressions
ms.assetid: 15aadee4-fa05-4edd-a191-e4d191c1ea22
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3868384641e4c5fa03c82c7ec4ba18e3ee9fb1b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-receive-shape"></a><span data-ttu-id="7c7da-102">受信図形を構成する方法</span><span class="sxs-lookup"><span data-stu-id="7c7da-102">How to Configure the Receive Shape</span></span>
![](../core/media/ebiz-orch-receive.gif "ebiz_orch_receive")  
<span data-ttu-id="7c7da-103">受信図形</span><span class="sxs-lookup"><span data-stu-id="7c7da-103">Receive shape</span></span>  
  
 <span data-ttu-id="7c7da-104">A**受信**図形は、オーケストレーションを開始するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="7c7da-104">A **Receive** shape can be used to start an orchestration.</span></span> <span data-ttu-id="7c7da-105">設定した場合、 **Activate**プロパティを**True**、ランタイム エンジンは、受信メッセージと表示する適切な種類であるかどうか、フィルターが適用されている場合、フィルター式があるかどうかをテスト満たされます。</span><span class="sxs-lookup"><span data-stu-id="7c7da-105">If you set the **Activate** property to **True**, the runtime engine will test an incoming message to see whether it is of the right type and, if a filter has been applied, whether the filter expression is satisfied.</span></span> <span data-ttu-id="7c7da-106">メッセージの受信の条件が満たされた場合、ランタイム エンジンを作成およびで新しいオーケストレーション インスタンスを実行し、**受信**図形がメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="7c7da-106">If the criteria for receipt of the message are met, the runtime engine creates and runs a new orchestration instance, and the **Receive** shape receives the message.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7c7da-107">場合、 **Activate**受信図形のプロパティが True に設定されて、**受信**オーケストレーションの最初のアクションをする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c7da-107">If the **Activate** property of a Receive shape is set to True, the **Receive** must be the first action in the orchestration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7c7da-108">場合、 **Activate**すべてのプロパティが False に設定されて**受信**図形、オーケストレーションを呼び出さなければなりません別のオーケストレーションによって実行するためにします。</span><span class="sxs-lookup"><span data-stu-id="7c7da-108">If the **Activate** property is set to False on all **Receive** shapes, your orchestration must be called by another orchestration in order to run.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7c7da-109">配置した場合は、**受信**のスコープ内の図形、 **Activate**プロパティに設定**True**、.NET クラス変数を変更することがなく、オーケストレーションに追加し、変数の**既定のコンス トラクターを使用**プロパティを**False**では、アクティブ化受信ステートメントは、生成された XLANG/S コードでは、スコープの外部でされますが、デザイン画面は引き続きとしてスコープ内には、これを表示します。</span><span class="sxs-lookup"><span data-stu-id="7c7da-109">If you put a **Receive** shape inside a scope with the **Activate** property set to **True**, and then add a .NET Class variable to your orchestration without changing the variable's **Use Default Constructor** property to **False**, the activate receive statement will be outside of the scope in the generated XLANG/S code, but the design surface will continue to show it as being inside the scope.</span></span>  
  
 <span data-ttu-id="7c7da-110">各オーケストレーションは少なくとも 1 つである必要があります**受信**図形を含み、**アクティブ化**プロパティに設定**True**です。</span><span class="sxs-lookup"><span data-stu-id="7c7da-110">Each orchestration must have at least one **Receive** shape with the **Activate** property set to **True**.</span></span>  
  
 <span data-ttu-id="7c7da-111">以前送信したメッセージへの応答を間接的または非同期に (要求 - 応答ポートではなく) 受信する場合は、応答者が適切なインスタンスに応答できるように、送信したメッセージを現在実行中のオーケストレーションのインスタンスに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c7da-111">If you expect to receive an indirect or asynchronous response (not on a request-response port) to a message that you have previously sent, you need to correlate the message with the currently running instance of the orchestration, so that the respondent can get the response to the correct instance.</span></span> <span data-ttu-id="7c7da-112">受信メッセージ内の値に対して関連付けを行う場合は受信図形にイニシャライズ関連付けセットを適用することができます。または、既にイニシャライズ関連付けセットを使用した関連付けに次の関連付けセットを適用することができます。</span><span class="sxs-lookup"><span data-stu-id="7c7da-112">You can apply an initializing correlation set to the Receive shape if you plan to do subsequent correlation on values in the incoming message, or a following correlation set for correlating using a previously initialized correlation set.</span></span> <span data-ttu-id="7c7da-113">詳細については、次を参照してください。[オーケストレーションでの相関関係を使用して](../core/using-correlations-in-orchestrations.md)です。</span><span class="sxs-lookup"><span data-stu-id="7c7da-113">For more information, see [Using Correlations in Orchestrations](../core/using-correlations-in-orchestrations.md).</span></span>  
  
### <a name="to-configure-a-receive-shape"></a><span data-ttu-id="7c7da-114">受信図形を構成するには</span><span class="sxs-lookup"><span data-stu-id="7c7da-114">To configure a Receive shape</span></span>  
  
1.  <span data-ttu-id="7c7da-115">メッセージとポート操作を設定します。</span><span class="sxs-lookup"><span data-stu-id="7c7da-115">Set a message and a port operation.</span></span>  
  
    1.  <span data-ttu-id="7c7da-116">[オーケストレーションの種類] ウィンドウで、受信されているメッセージの種類に対して定義されているメッセージとポート操作の両方がオーケストレーションにあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7c7da-116">In the Orchestration View window, verify that your orchestration has both a message and a port operation defined for the message type being received.</span></span>  
  
         <span data-ttu-id="7c7da-117">[プロパティ] ウィンドウでから受信するメッセージを選択、**メッセージ**プロパティ ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="7c7da-117">In the Properties window, select the message to receive from the **Message** property drop-down list.</span></span>  
  
    2.  <span data-ttu-id="7c7da-118">[プロパティ] ウィンドウでからメッセージを受信するポート操作を選択、**操作**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="7c7da-118">In the Properties window, select the port operation to receive the message from the **Operation** drop-down list.</span></span>  
  
         <span data-ttu-id="7c7da-119">- または -</span><span class="sxs-lookup"><span data-stu-id="7c7da-119">—Or—</span></span>  
  
         <span data-ttu-id="7c7da-120">受信コネクタをドラッグして、**受信**図形、メッセージを受信するポート ソケットにします。</span><span class="sxs-lookup"><span data-stu-id="7c7da-120">Drag the receive connector from the **Receive** shape to the port socket that will receive the message.</span></span>  
  
2.  <span data-ttu-id="7c7da-121">指定する、**受信**図形がオーケストレーションをアクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="7c7da-121">Specify that the **Receive** shape will activate the orchestration.</span></span>  
  
3.  <span data-ttu-id="7c7da-122">[プロパティ] ウィンドウで "アクティブ化" プロパティを True に設定します。</span><span class="sxs-lookup"><span data-stu-id="7c7da-122">In the Properties window, set the Activate property to True.</span></span>  
  
    1.  <span data-ttu-id="7c7da-123">[プロパティ] ウィンドウ、**省略記号**(**.**) ボタンをメッセージを制限するフィルターを作成するフィルター式のプロパティをこの**受信**図形が受け入れます。</span><span class="sxs-lookup"><span data-stu-id="7c7da-123">In the Properties window, click the **Ellipsis** (**...**) button for the Filter Expression property to create a filter to restrict the messages that this **Receive** shape accepts.</span></span>  
  
         <span data-ttu-id="7c7da-124">- または -</span><span class="sxs-lookup"><span data-stu-id="7c7da-124">—Or—</span></span>  
  
         <span data-ttu-id="7c7da-125">右クリックし、**受信**図形をクリックして**フィルタ式の編集**です。</span><span class="sxs-lookup"><span data-stu-id="7c7da-125">Right-click the **Receive** shape and then click **Edit Filter Expression**.</span></span>  
  
    2.  <span data-ttu-id="7c7da-126">**フィルター式** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7c7da-126">The **Filter Expression** dialog box appears.</span></span> <span data-ttu-id="7c7da-127">このダイアログ ボックスを使用して、1 つ以上のフィルター式を作成します。</span><span class="sxs-lookup"><span data-stu-id="7c7da-127">Use this dialog box to create one or more filter expressions.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="7c7da-128">メッセージの種類を定義してに割り当てられている必要があります、**受信**図形のフィルターを適用する前にします。</span><span class="sxs-lookup"><span data-stu-id="7c7da-128">A message type must be defined and assigned to the **Receive** shape before you can apply a filter to it.</span></span>  
  
4.  <span data-ttu-id="7c7da-129">メッセージの制限に相関関係のセットを指定する、**受信**図形が受け入れます。</span><span class="sxs-lookup"><span data-stu-id="7c7da-129">Specify correlation sets to restrict the messages the **Receive** shape accepts.</span></span>  
  
    -   <span data-ttu-id="7c7da-130">ドロップダウン リストから設定の相関関係を確認して、実行する各関連付けセット、**フォロー関連付けセット**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="7c7da-130">For each correlation set you want to follow, check a correlation set from the drop-down on the **Following Correlation Sets** property.</span></span>  
  
    -   <span data-ttu-id="7c7da-131">各関連付けセットを初期化する場合、ドロップダウン リストから設定の相関関係を確認して、**イニシャライズ関連付けセット**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="7c7da-131">For each correlation set that you want to initialize, check a correlation set from the drop-down on the **Initializing Correlation Sets** property.</span></span>  
  
## <a name="filter-expression-grid-control"></a><span data-ttu-id="7c7da-132">[フィルター式] グリッド コントロール</span><span class="sxs-lookup"><span data-stu-id="7c7da-132">Filter Expression grid control</span></span>  
 <span data-ttu-id="7c7da-133">このグリッド コントロールを使用してフィルター式を構築し、式を構成する述語を定義します。</span><span class="sxs-lookup"><span data-stu-id="7c7da-133">You build a filter expression by using this grid control to define the predicates that make up the expression.</span></span> <span data-ttu-id="7c7da-134">グリッドのセルから述語を追加、編集、および削除できます。</span><span class="sxs-lookup"><span data-stu-id="7c7da-134">You can add, edit, and delete predicates from the cells of the grid.</span></span> <span data-ttu-id="7c7da-135">このグリッド コントロールが 4 つの列: プロパティ、演算子、値、およびグループ化します。</span><span class="sxs-lookup"><span data-stu-id="7c7da-135">This grid control has four columns: Property, Operator, Value, and Grouping.</span></span>  
  
-   <span data-ttu-id="7c7da-136">**プロパティ。**</span><span class="sxs-lookup"><span data-stu-id="7c7da-136">**Property.**</span></span> <span data-ttu-id="7c7da-137">: プロパティの参照を入力するか、セルのドロップダウン リストからいずれかのプロパティを選択します。</span><span class="sxs-lookup"><span data-stu-id="7c7da-137">You can type a property reference, or select one from the cell's drop-down list.</span></span> <span data-ttu-id="7c7da-138">一覧には、受信メッセージのプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7c7da-138">The list contains properties on the incoming message.</span></span>  
  
-   <span data-ttu-id="7c7da-139">**演算子。**</span><span class="sxs-lookup"><span data-stu-id="7c7da-139">**Operator.**</span></span> <span data-ttu-id="7c7da-140">: このセルに演算子を直接入力するか、ドロップダウン リストから演算子を選択します。</span><span class="sxs-lookup"><span data-stu-id="7c7da-140">You can type in this cell, or select an operator from the drop-down list.</span></span> <span data-ttu-id="7c7da-141">有効な選択肢は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7c7da-141">Possible selections are:</span></span>  
  
    |<span data-ttu-id="7c7da-142">オペランド</span><span class="sxs-lookup"><span data-stu-id="7c7da-142">Operand</span></span>|<span data-ttu-id="7c7da-143">意味</span><span class="sxs-lookup"><span data-stu-id="7c7da-143">Meaning</span></span>|  
    |-------------|-------------|  
    |==|<span data-ttu-id="7c7da-144">次の値に等しい</span><span class="sxs-lookup"><span data-stu-id="7c7da-144">Is equal to</span></span>|  
    |<span data-ttu-id="7c7da-145">!=</span><span class="sxs-lookup"><span data-stu-id="7c7da-145">!=</span></span>|<span data-ttu-id="7c7da-146">次の値に等しくない</span><span class="sxs-lookup"><span data-stu-id="7c7da-146">Is not equal to</span></span>|  
    |<|<span data-ttu-id="7c7da-147">次の値より小さい</span><span class="sxs-lookup"><span data-stu-id="7c7da-147">Is less than</span></span>|  
    |\<=|<span data-ttu-id="7c7da-148">次の値以下</span><span class="sxs-lookup"><span data-stu-id="7c7da-148">Is less than or equal to</span></span>|  
    |>|<span data-ttu-id="7c7da-149">次の値より大きい</span><span class="sxs-lookup"><span data-stu-id="7c7da-149">Is greater than</span></span>|  
    |>=|<span data-ttu-id="7c7da-150">次の値以上</span><span class="sxs-lookup"><span data-stu-id="7c7da-150">Is greater than or equal to</span></span>|  
    |<span data-ttu-id="7c7da-151">Exists</span><span class="sxs-lookup"><span data-stu-id="7c7da-151">Exists</span></span>|<span data-ttu-id="7c7da-152">Exists</span><span class="sxs-lookup"><span data-stu-id="7c7da-152">Exists</span></span>|  
  
-   <span data-ttu-id="7c7da-153">**値。**</span><span class="sxs-lookup"><span data-stu-id="7c7da-153">**Value.**</span></span> <span data-ttu-id="7c7da-154">セル、**値**列に入力した任意の定数を保持できます: 文字列リテラル、整数リテラル、または null。</span><span class="sxs-lookup"><span data-stu-id="7c7da-154">Cells in the **Value** column can hold any constant that you type in: a string-literal, an integer-literal, or null.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7c7da-155">選択したプロパティの型が文字列の場合、値を二重引用符で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c7da-155">If the property selected is of type string, the value needs to be in quotes.</span></span> <span data-ttu-id="7c7da-156">たとえば、「SMTP.From = "MyServer"」となります。</span><span class="sxs-lookup"><span data-stu-id="7c7da-156">For example, SMTP.From = "MyServer".</span></span>  
  
-   <span data-ttu-id="7c7da-157">**グループ化します。**</span><span class="sxs-lookup"><span data-stu-id="7c7da-157">**Grouping.**</span></span> <span data-ttu-id="7c7da-158">述語のグループ化を制御する場合にこの列を使用します。</span><span class="sxs-lookup"><span data-stu-id="7c7da-158">Use this column to control predicate grouping.</span></span> <span data-ttu-id="7c7da-159">フィルター式では、グループ化を自動的に決定できるようにで選言標準形 (dnf) で表しますは常に表現されます。</span><span class="sxs-lookup"><span data-stu-id="7c7da-159">Filter expressions are always expressed in Disjunctive Normal Form (DNF) so grouping can be determined automatically.</span></span> <span data-ttu-id="7c7da-160">[および] は、述語が次の述語とグループ化されることを意味します。一方、[または] は、述語が次の行の述語から分離されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="7c7da-160">AND means the predicate is to be grouped with the predicate following it, while OR means the predicate is separate from the predicate in the next row.</span></span> <span data-ttu-id="7c7da-161">グリッド コントロールの左側の灰色の角かっこは、述語がグループ化されているときに表示されます。</span><span class="sxs-lookup"><span data-stu-id="7c7da-161">Gray brackets to the left of the grid control appear when predicates are grouped together.</span></span> <span data-ttu-id="7c7da-162">述語グループを入れ子にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="7c7da-162">Predicate groups cannot be nested.</span></span> <span data-ttu-id="7c7da-163">このセルに値を指定しなかった場合は、既定値として [および] が設定されます。</span><span class="sxs-lookup"><span data-stu-id="7c7da-163">If you do not specify a value in this cell, the value of the cell defaults to AND.</span></span>  
  
 <span data-ttu-id="7c7da-164">たとえば、次のような式を作成できます。</span><span class="sxs-lookup"><span data-stu-id="7c7da-164">For example, you might create an expression like the following:</span></span>  
  
 `MSMQ.MsgID = 1`  
  
 <span data-ttu-id="7c7da-165">このフィルターを適用した場合、送信ポート グループは、MSMQ のメッセージ ID が 1 であるメッセージだけをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="7c7da-165">With this filter, the send port group would only subscribe to messages having an MSMQ message ID of 1.</span></span>  
  
 <span data-ttu-id="7c7da-166">さらに式を追加したり、AND や OR で他の式と組み合わせることもできます。その例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="7c7da-166">You can create additional expressions and specify that they have an AND or OR relationship with other expressions, for example:</span></span>  
  
 `MSMQ.MsgID = 1 OR`  
  
 `SMTP.From = "MyServer"`  
  
 <span data-ttu-id="7c7da-167">この場合、送信ポート グループは、MSMQ メッセージ ID が 1 であるか、または、送信元が MyServer という名前の SMTP サーバーであるすべてのメッセージをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="7c7da-167">In this case, the send port group would subscribe to all messages that have either an MSMQ message ID of 1 or that have been sent from the SMTP server named MyServer.</span></span>  
  
## <a name="hint-label"></a><span data-ttu-id="7c7da-168">ヒント ラベル</span><span class="sxs-lookup"><span data-stu-id="7c7da-168">Hint label</span></span>  
 <span data-ttu-id="7c7da-169">このフィールドは、ユーザー ガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="7c7da-169">This field provides user guidance.</span></span> <span data-ttu-id="7c7da-170">ラベル テキストは、列に含まれているアクティブなセルに応じて異なります。</span><span class="sxs-lookup"><span data-stu-id="7c7da-170">The label text changes depending on which column contains the active cell.</span></span> <span data-ttu-id="7c7da-171">テキストには、列名が表示され、その後に次のようにガイダンス テキストが続きます。</span><span class="sxs-lookup"><span data-stu-id="7c7da-171">The text displays the column name followed by guidance text as follows:</span></span>  
  
-   <span data-ttu-id="7c7da-172">**プロパティ。**</span><span class="sxs-lookup"><span data-stu-id="7c7da-172">**Property.**</span></span> <span data-ttu-id="7c7da-173">リストから受信メッセージのプロパティを選択してください。</span><span class="sxs-lookup"><span data-stu-id="7c7da-173">Please select a property on the incoming message from the list.</span></span>  
  
-   <span data-ttu-id="7c7da-174">**演算子。**</span><span class="sxs-lookup"><span data-stu-id="7c7da-174">**Operator.**</span></span> <span data-ttu-id="7c7da-175">プロパティを値と比較するための演算子を選択します。</span><span class="sxs-lookup"><span data-stu-id="7c7da-175">Select an operator to compare the Property with the Value.</span></span>  
  
-   <span data-ttu-id="7c7da-176">**値。**</span><span class="sxs-lookup"><span data-stu-id="7c7da-176">**Value.**</span></span> <span data-ttu-id="7c7da-177">リストからメッセージ プロパティを選択するか、リテラル値で入力します。</span><span class="sxs-lookup"><span data-stu-id="7c7da-177">Select a message property from the list, or type in a literal value.</span></span>  
  
-   <span data-ttu-id="7c7da-178">**グループ化します。**</span><span class="sxs-lookup"><span data-stu-id="7c7da-178">**Grouping.**</span></span> <span data-ttu-id="7c7da-179">この行が次の行とどのようにグループ化されるかを指定します。</span><span class="sxs-lookup"><span data-stu-id="7c7da-179">Specify how this row is to be grouped with the next row.</span></span> <span data-ttu-id="7c7da-180">"AND" は行を組み合わせ、"OR" は行を分離します。</span><span class="sxs-lookup"><span data-stu-id="7c7da-180">'AND' will join the rows, and 'OR' will separate them.</span></span>  
  
## <a name="move-up-button"></a><span data-ttu-id="7c7da-181">[上へ移動] ボタン</span><span class="sxs-lookup"><span data-stu-id="7c7da-181">Move Up button</span></span>  
 <span data-ttu-id="7c7da-182">選択した行を上へ移動するには、このボタンをクリックします </span><span class="sxs-lookup"><span data-stu-id="7c7da-182">Click this to move a selected row up.</span></span> <span data-ttu-id="7c7da-183">(最初の行をクリックして選択、*右矢印*(**>)**グリッド コントロールの左側にあるボタンをクリックします)。</span><span class="sxs-lookup"><span data-stu-id="7c7da-183">(First select a row by clicking the *right arrow* (**>)** button at the left side of the grid control.)</span></span>  
  
## <a name="move-down-button"></a><span data-ttu-id="7c7da-184">[下へ移動] ボタン</span><span class="sxs-lookup"><span data-stu-id="7c7da-184">Move Down button</span></span>  
 <span data-ttu-id="7c7da-185">選択した行を下へ移動するには、このボタンをクリックします </span><span class="sxs-lookup"><span data-stu-id="7c7da-185">Click this to move a selected row down.</span></span> <span data-ttu-id="7c7da-186">(最初の行をクリックして選択、*右矢印*(**>)**グリッド コントロールの左側にあるボタンをクリックします)。</span><span class="sxs-lookup"><span data-stu-id="7c7da-186">(First select a row by clicking the *right arrow* (**>)** button at the left side of the grid control.)</span></span>  
  
## <a name="filter-expression-created-field"></a><span data-ttu-id="7c7da-187">"作成されたフィルター式" フィールド</span><span class="sxs-lookup"><span data-stu-id="7c7da-187">Filter Expression Created field</span></span>  
 <span data-ttu-id="7c7da-188">この読み取り専用のテキスト ボックスには、式を構築するにつれてその式が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7c7da-188">This read-only text box shows the expression as you are building it.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7c7da-189">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="7c7da-189">In This Section</span></span>  
 [<span data-ttu-id="7c7da-190">受信メッセージ図形にフィルターを使用します。</span><span class="sxs-lookup"><span data-stu-id="7c7da-190">Using Filters With the Receive Message Shape</span></span>](../core/using-filters-with-the-receive-message-shape.md)