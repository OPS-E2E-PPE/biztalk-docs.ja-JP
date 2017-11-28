---
title: "タスク一覧内のビルド エラー |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- building, errors
- errors, building
ms.assetid: 05b36511-3031-4e13-ac2f-bfdbec0f48cb
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1bfd5b9f7b974b00d63831484ecbaa44e2568fa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="build-errors-in-the-task-list"></a><span data-ttu-id="8584a-102">タスク一覧内のビルド エラー</span><span class="sxs-lookup"><span data-stu-id="8584a-102">Build Errors in the Task List</span></span>
<span data-ttu-id="8584a-103">プロジェクト (ソリューション) をビルドすると、個別のエラーおよび警告がタスク一覧に表示され、結果は出力ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8584a-103">When you build your project, or solution, the results will appear in the Output window, while individual errors and warnings will appear in the task list.</span></span>  
  
 <span data-ttu-id="8584a-104">エラーおよび警告は、タスク一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="8584a-104">Errors and warnings appear in the task list.</span></span> <span data-ttu-id="8584a-105">エラーをダブルクリックすると、正しく構成されていないオブジェクトにフォーカスが移動します。</span><span class="sxs-lookup"><span data-stu-id="8584a-105">You can double-click the error, and the focus will be applied to the object that is not correctly configured.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8584a-106">ビルドを行うとき、コンパイラは XPath を検証しないため、</span><span class="sxs-lookup"><span data-stu-id="8584a-106">When you build, the compiler does not validate XPaths.</span></span> <span data-ttu-id="8584a-107">有効な XPath 構文を使用してください。</span><span class="sxs-lookup"><span data-stu-id="8584a-107">Take care to use valid XPath syntax.</span></span>  
  
## <a name="insufficient-configuration-action"></a><span data-ttu-id="8584a-108">不十分な構成の操作</span><span class="sxs-lookup"><span data-stu-id="8584a-108">Insufficient configuration Action</span></span>  
 ![](../core/media/ebiz-orch-insufficconfig.gif "ebiz_orch_insufficconfig")  
  
> [!CAUTION]
>  <span data-ttu-id="8584a-109">オーケストレーション デザイナーでは状況に応じて不十分な構成の警告が発生しますが、この警告が発生しないからといってオーケストレーションが正しくコンパイルされるという保証はありません。</span><span class="sxs-lookup"><span data-stu-id="8584a-109">While Orchestration Designer will provide insufficient configuration warnings where it can, there is no guarantee that your orchestration will compile correctly in the absence of such warnings.</span></span>  
  
## <a name="compiler-asks-if-you-are-missing-an-assembly-reference"></a><span data-ttu-id="8584a-110">コンパイラによるアセンブリ参照の確認</span><span class="sxs-lookup"><span data-stu-id="8584a-110">Compiler asks if you are missing an assembly reference</span></span>  
  
### <a name="problem"></a><span data-ttu-id="8584a-111">問題</span><span class="sxs-lookup"><span data-stu-id="8584a-111">Problem</span></span>  
 <span data-ttu-id="8584a-112">オーケストレーションをコンパイルすると、"アセンブリ参照があるか確認してください" で終わるエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8584a-112">When you compile your orchestration you get an error message that ends with the question "are you missing an assembly reference?"</span></span> <span data-ttu-id="8584a-113">以下の 2 つが一般的なメッセージです。</span><span class="sxs-lookup"><span data-stu-id="8584a-113">Two of the more common messages are:</span></span>  
  
-   <span data-ttu-id="8584a-114">型または名前空間名 'X' は名前空間 'Y' に存在しません。アセンブリ参照が不足しています。</span><span class="sxs-lookup"><span data-stu-id="8584a-114">The type or namespace name 'X' does not exist in the namespace 'Y' (are you missing an assembly reference?)</span></span>  
  
-   <span data-ttu-id="8584a-115">識別子 'X' は 'Y' に存在しません。アセンブリ参照があるか確認してください。</span><span class="sxs-lookup"><span data-stu-id="8584a-115">Identifier 'X' does not exist in 'Y'; are you missing an assembly reference?</span></span>  
  
### <a name="cause"></a><span data-ttu-id="8584a-116">原因</span><span class="sxs-lookup"><span data-stu-id="8584a-116">Cause</span></span>  
 <span data-ttu-id="8584a-117">次のいずれかが原因で、このエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="8584a-117">Any of the following could be the cause of this error.</span></span>  
  
-   <span data-ttu-id="8584a-118">プロジェクトは 1 つ以上の必要なアセンブリを参照していません。</span><span class="sxs-lookup"><span data-stu-id="8584a-118">Your project does not reference one or more required assemblies.</span></span>  
  
-   <span data-ttu-id="8584a-119">プロジェクトに、プロジェクトと同じ名前のマップまたはその他のオブジェクトの種類が存在します。</span><span class="sxs-lookup"><span data-stu-id="8584a-119">Your project has a map or other object type that has the same name as the project.</span></span>  
  
-   <span data-ttu-id="8584a-120">プロジェクトは XSD (XML スキーマ定義) 言語ベースの PIP (Partner Interface Process) スキーマを使用し、System という名前のサブフォルダーに XSD スキーマが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8584a-120">Your project uses XML Schema definition language (XSD)-based Partner Interface Process (PIP) schemas and contains XSD schemas in a subfolder that is named System.</span></span>  
  
-   <span data-ttu-id="8584a-121">プロジェクトは、名前空間が現在のプロジェクトの名前空間のサブセットになっているグローバル プロパティを使用しています。</span><span class="sxs-lookup"><span data-stu-id="8584a-121">Your project is using a Global Property whose namespace is a subset of the current project's namespace.</span></span> <span data-ttu-id="8584a-122">たとえば、プロジェクト "Accounts.FILE" に含まれているオーケストレーションでグローバル プロパティ名前空間 "File.ReceivedFileName" を使用しています。</span><span class="sxs-lookup"><span data-stu-id="8584a-122">For example, using the Global Property namespace "File.ReceivedFileName" in an orchestration contained in the project "Accounts.FILE".</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="8584a-123">解決策</span><span class="sxs-lookup"><span data-stu-id="8584a-123">Resolution</span></span>  
 <span data-ttu-id="8584a-124">問題の原因に応じて、次の解決策があります。</span><span class="sxs-lookup"><span data-stu-id="8584a-124">Depending upon the cause of the problem, the resolution could be any of the following:</span></span>  
  
-   <span data-ttu-id="8584a-125">欠落しているアセンブリへの参照をプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="8584a-125">Add a reference to the missing assemblies your project requires.</span></span>  
  
-   <span data-ttu-id="8584a-126">マップまたは他のオブジェクトの名前を、プロジェクト名とは異なる名前に変更します。</span><span class="sxs-lookup"><span data-stu-id="8584a-126">Change the name of the map or other object to something other than the project name.</span></span> <span data-ttu-id="8584a-127">これは通常、オブジェクトのプロパティ ページで実行できます (たとえば、マップのプロパティ ページには、"名前" プロパティが含まれています)。</span><span class="sxs-lookup"><span data-stu-id="8584a-127">This can typically be done through the object's property page (for example, the Map property page contains a Name property).</span></span>  
  
-   <span data-ttu-id="8584a-128">Visual Studio でスキーマの名前空間を変更します。</span><span class="sxs-lookup"><span data-stu-id="8584a-128">Change the namespace for the schemas in Visual Studio.</span></span> <span data-ttu-id="8584a-129">Visual Studio を使用してこれには、をクリックして**すべてのファイル**上、**プロジェクト** メニューの 順に展開し、**システム**ソリューション エクスプ ローラー内のノードです。</span><span class="sxs-lookup"><span data-stu-id="8584a-129">To do this using Visual Studio, click **Show All Files** on the **Project** menu, and then expand the **System** node in Solution Explorer.</span></span> <span data-ttu-id="8584a-130">各ファイル システム フォルダーとサブフォルダーをクリックし、[プロパティ] ウィンドウで名前空間のエントリをする変更の発生**システム**_ になります**システム**です。</span><span class="sxs-lookup"><span data-stu-id="8584a-130">Click each file in the System folder and in any subfolders, and then change the namespace entry in the Properties window so that any occurrence of **System** becomes _**System**.</span></span> <span data-ttu-id="8584a-131">たとえば、変更、 **MyProject.System.SubFolder**名前空間を**MyProject._System.Subfolder**名前空間。</span><span class="sxs-lookup"><span data-stu-id="8584a-131">For example, change the **MyProject.System.SubFolder** namespace to **the MyProject._System.Subfolder** namespace.</span></span> <span data-ttu-id="8584a-132">サポート技術情報の記事を参照して、この問題の詳細については[916649](http://support.microsoft.com/?kbid=916649)です。</span><span class="sxs-lookup"><span data-stu-id="8584a-132">For more information about this issue, see KB article [916649](http://support.microsoft.com/?kbid=916649).</span></span>  
  
-   <span data-ttu-id="8584a-133">プロジェクトから、競合するグローバル プロパティ名前空間を削除します。</span><span class="sxs-lookup"><span data-stu-id="8584a-133">Remove the conflicting Global Property namespace from the project.</span></span>  
  
## <a name="you-receive-a-message-has-not-been-initialized-in-construct-statement-error-when-building-your-project"></a><span data-ttu-id="8584a-134">プロジェクトのビルド時に発生する "メッセージは construct ステートメントで初期化されていません" エラー</span><span class="sxs-lookup"><span data-stu-id="8584a-134">You receive a "Message has not been initialized in construct statement" error when building your project</span></span>  
  
### <a name="problem"></a><span data-ttu-id="8584a-135">問題</span><span class="sxs-lookup"><span data-stu-id="8584a-135">Problem</span></span>  
 <span data-ttu-id="8584a-136">エラーが発生する、BizTalk アプリケーションをコンパイルするときに「メッセージが初期化されていません construct ステートメントで」です。</span><span class="sxs-lookup"><span data-stu-id="8584a-136">When you compile your BizTalk application, you get the error "Message has not been initialized in construct statement".</span></span>  
  
### <a name="cause"></a><span data-ttu-id="8584a-137">原因</span><span class="sxs-lookup"><span data-stu-id="8584a-137">Cause</span></span>  
 <span data-ttu-id="8584a-138">メッセージを作成するときに、すべてのメッセージ変数を指定します。</span><span class="sxs-lookup"><span data-stu-id="8584a-138">When you construct a message, you specify all the message variables.</span></span> <span data-ttu-id="8584a-139">メッセージまたはメッセージの部分に割り当てを行います。</span><span class="sxs-lookup"><span data-stu-id="8584a-139">Then you make assignments to the message or its parts.</span></span> <span data-ttu-id="8584a-140">別の特定のメッセージの割り当ての一部が含まれているかどうかは**メッセージの構築**図形、初期化エラー メッセージが表示される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8584a-140">If part of a specific message assignment is included in a separate **Construct Message** shape, you may receive the initialization error message.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="8584a-141">解決策</span><span class="sxs-lookup"><span data-stu-id="8584a-141">Resolution</span></span>  
 <span data-ttu-id="8584a-142">この問題を解決するには、同じで、特定のメッセージの割り当てのすべての部分を含めることを確認します**メッセージの構築**図形です。</span><span class="sxs-lookup"><span data-stu-id="8584a-142">To resolve this behavior, make sure that you include all parts of a specific message assignment in the same **Construct Message** shape.</span></span> <span data-ttu-id="8584a-143">サポート技術情報の記事を参照して関連するサポートの問題点[870606](http://support.microsoft.com/?kbid=870606)です。</span><span class="sxs-lookup"><span data-stu-id="8584a-143">For a related support issue, see KB article [870606](http://support.microsoft.com/?kbid=870606).</span></span>  
  
 <span data-ttu-id="8584a-144">メッセージを作成することで、この問題を解決することができますも、**構築**図形で、そのインスタンスを使用する前に、**式**図形です。</span><span class="sxs-lookup"><span data-stu-id="8584a-144">You can also resolve this behavior by creating your message in a **Construct** shape before using an instance of it in an **Expression** shape.</span></span> <span data-ttu-id="8584a-145">たとえば、次のコード エラーが発生に配置されている場合、**式**図形。</span><span class="sxs-lookup"><span data-stu-id="8584a-145">For example, the following code will cause an error if placed in an **Expression** shape:</span></span>  
  
```  
XMLDOM = new System.Xml.XmlDocument();  
POAckMsg = XMLDOM;  
```  
  
 <span data-ttu-id="8584a-146">を解決するには、内に XMLDOM のインスタンスを作成、**構築**図形、および、ダウン ストリームの割り当てを行う**式**図形です。</span><span class="sxs-lookup"><span data-stu-id="8584a-146">To fix, create the instance of XMLDOM in a **Construct** shape, and then do the assignment in a downstream **Expression** shape.</span></span>  
  
## <a name="you-receive-a-use-of-unconstructed-message-error-when-building-your-project"></a><span data-ttu-id="8584a-147">プロジェクトのビルド時に発生する "未構築のメッセージが使用されました" エラー</span><span class="sxs-lookup"><span data-stu-id="8584a-147">You receive a "use of unconstructed message" error when building your project</span></span>  
  
### <a name="problem"></a><span data-ttu-id="8584a-148">問題</span><span class="sxs-lookup"><span data-stu-id="8584a-148">Problem</span></span>  
 <span data-ttu-id="8584a-149">BizTalk プロジェクトをコンパイルするときに、エラー"未構築のメッセージの使用 '\<メッセージ >'"です。</span><span class="sxs-lookup"><span data-stu-id="8584a-149">When you compile your BizTalk project, you receive the error "use of unconstructed message '\<message>'".</span></span>  
  
### <a name="cause"></a><span data-ttu-id="8584a-150">原因</span><span class="sxs-lookup"><span data-stu-id="8584a-150">Cause</span></span>  
 <span data-ttu-id="8584a-151">未構築のメッセージを使用する場合、このエラーが発生した、**送信**図形です。</span><span class="sxs-lookup"><span data-stu-id="8584a-151">This error occurs when an unconstructed message is used in a **Send** shape.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="8584a-152">解決策</span><span class="sxs-lookup"><span data-stu-id="8584a-152">Resolution</span></span>  
 <span data-ttu-id="8584a-153">この問題を解決するには、追加、**メッセージの構築**オーケストレーションへの図形です。</span><span class="sxs-lookup"><span data-stu-id="8584a-153">To resolve this issue, add a **Construct Message** shape to the orchestration.</span></span> <span data-ttu-id="8584a-154">含める、**メッセージの構築**図形の前に、**送信**Web サービスにバインドされている図形です。</span><span class="sxs-lookup"><span data-stu-id="8584a-154">Include the **Construct Message** shape before the **Send** shape that is bound to the Web service.</span></span>  
  
 <span data-ttu-id="8584a-155">詳細については、このエラーと Web サービス、サポート技術情報の記事を参照してください[921043](http://support.microsoft.com/?kbid=921043)です。</span><span class="sxs-lookup"><span data-stu-id="8584a-155">For more information about this error and Web services, see KB article [921043](http://support.microsoft.com/?kbid=921043).</span></span>  
  
## <a name="setting-a-transaction-level-for-a-scope-results-in-an-error"></a><span data-ttu-id="8584a-156">エラーで、その結果、スコープのトランザクション レベルの設定</span><span class="sxs-lookup"><span data-stu-id="8584a-156">Setting a transaction level for a scope results in an error</span></span>  
  
### <a name="problem"></a><span data-ttu-id="8584a-157">問題</span><span class="sxs-lookup"><span data-stu-id="8584a-157">Problem</span></span>  
 <span data-ttu-id="8584a-158">オーケストレーション内のスコープまたはトランザクションをサポートするその他のエンティティのトランザクションの種類を構成した後に、"トランザクションでないオーケストレーションに他のトランザクションを含めることはできません" というエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8584a-158">After configuring the transaction type for a scope or other entity supporting transactions in an orchestration, you receive the error "A Non-transactional Orchestration cannot contain any other Transactions".</span></span>  
  
### <a name="cause"></a><span data-ttu-id="8584a-159">原因</span><span class="sxs-lookup"><span data-stu-id="8584a-159">Cause</span></span>  
 <span data-ttu-id="8584a-160">このエラーは、オーケストレーション自体のトランザクションの種類が "なし" である場合に、オーケストレーション内のスコープ (またはその他のエンティティ) のトランザクションの種類を "アトミック" または "長時間トランザクション" に構成しようとすると発生します。</span><span class="sxs-lookup"><span data-stu-id="8584a-160">This error occurs when you try to configure the transaction type of a scope (or other entity) in an orchestration to "Atomic" or "Long-Running" when the orchestration itself has a transaction type of "None".</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="8584a-161">解決策</span><span class="sxs-lookup"><span data-stu-id="8584a-161">Resolution</span></span>  
 <span data-ttu-id="8584a-162">オーケストレーションと構成要素であるオブジェクトのトランザクションの種類の設定が互換することを確認します。</span><span class="sxs-lookup"><span data-stu-id="8584a-162">Ensure that the transaction type settings of your orchestration and constituent objects are compatible.</span></span>  
  
## <a name="project-build-results-in-the-error-you-must-specify-at-least-one-already-initialized-correlation-set-for-a-non-activation-receive-that-is-on-a-non-selfcorrelating-port"></a><span data-ttu-id="8584a-163">プロジェクトのビルドによって発生する "自己関連付けを行わないポート上での非アクティベーション受信に対して、既に初期化されている関連付けセットを少なくとも 1 つ指定する必要があります" エラー</span><span class="sxs-lookup"><span data-stu-id="8584a-163">Project build results in the error "you must specify at least one already-initialized correlation set for a non-activation receive that is on a non-selfcorrelating port"</span></span>  
  
### <a name="problem"></a><span data-ttu-id="8584a-164">問題</span><span class="sxs-lookup"><span data-stu-id="8584a-164">Problem</span></span>  
 <span data-ttu-id="8584a-165">BizTalk プロジェクトをコンパイルすると、"自己関連付けを行わないポート上での非アクティベーション受信に対して、既に初期化されている関連付けセットを少なくとも 1 つ指定する必要があります" というエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8584a-165">When you compile your BizTalk project, you receive the error "you must specify at least one already-initialized correlation set for a non-activation receive that is on a non-selfcorrelating port".</span></span>  
  
### <a name="cause"></a><span data-ttu-id="8584a-166">原因</span><span class="sxs-lookup"><span data-stu-id="8584a-166">Cause</span></span>  
 <span data-ttu-id="8584a-167">アクティブ化、オーケストレーションが存在しない場合、このエラーが発生する可能性が**受信**図形 (Activate = true) のアクティブ化がないか**受信**図形し、は別のオーケストレーションによって直接呼び出されません。</span><span class="sxs-lookup"><span data-stu-id="8584a-167">This error can occur if your orchestration has no activating **Receive** shapes (Activate = true) or has no activating **Receive** shapes and is not called directly by another orchestration.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="8584a-168">解決策</span><span class="sxs-lookup"><span data-stu-id="8584a-168">Resolution</span></span>  
 <span data-ttu-id="8584a-169">オーケストレーションが別のオーケストレーションによって呼び出されない場合のいずれかを構成する必要があります、**受信**アクティブ化受信である図形です。</span><span class="sxs-lookup"><span data-stu-id="8584a-169">If your orchestration is not called by another orchestration, you must configure one of the **Receive** shapes to be an activated receive.</span></span> <span data-ttu-id="8584a-170">構成の詳細については、**受信**関連付けへのリンクを含む図形を参照してください[受信図形を構成する方法](../core/how-to-configure-the-receive-shape.md)です。</span><span class="sxs-lookup"><span data-stu-id="8584a-170">For more information about configuring the **Receive** shape, including links to correlation, see [How to Configure the Receive Shape](../core/how-to-configure-the-receive-shape.md).</span></span>  
  
## <a name="you-receive-the-error-assembly-generation-failed----referenced-assembly-assembly-does-not-have-a-strong-name-when-building-your-solution"></a><span data-ttu-id="8584a-171">エラーが発生する"アセンブリの生成に失敗しました--参照されたアセンブリ '\<アセンブリ >' は厳密な名前がありません"ソリューションをビルドする場合</span><span class="sxs-lookup"><span data-stu-id="8584a-171">You receive the error "Assembly generation failed -- Referenced assembly '\<assembly>' does not have a strong name" when building your solution</span></span>  
  
### <a name="problem"></a><span data-ttu-id="8584a-172">問題</span><span class="sxs-lookup"><span data-stu-id="8584a-172">Problem</span></span>  
 <span data-ttu-id="8584a-173">エラーが発生する"アセンブリの生成に失敗しました--参照されたアセンブリ '\<アセンブリ >' は厳密な名前がありません"ときにオーケストレーションを持つソリューションを構築します。</span><span class="sxs-lookup"><span data-stu-id="8584a-173">You receive the error "Assembly generation failed -- Referenced assembly '\<assembly>' does not have a strong name" when building your solution that has an orchestration.</span></span>  
  
### <a name="cause"></a><span data-ttu-id="8584a-174">原因</span><span class="sxs-lookup"><span data-stu-id="8584a-174">Cause</span></span>  
 <span data-ttu-id="8584a-175">この問題は、署名されていない参照アセンブリの型がオーケストレーション内で使用されている場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="8584a-175">This problem occurs when a type from an unsigned referenced assembly is used within an orchestration.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="8584a-176">解決策</span><span class="sxs-lookup"><span data-stu-id="8584a-176">Resolution</span></span>  
 <span data-ttu-id="8584a-177">参照アセンブリに厳密な名前を適用します。</span><span class="sxs-lookup"><span data-stu-id="8584a-177">Apply a strong name to the referenced assembly.</span></span> <span data-ttu-id="8584a-178">このアセンブリが再コンパイル可能なカスタム アセンブリである場合は、厳密名ツールを使用して .snk (キー) ファイルを作成してから、プロジェクトのアセンブリ プロパティ内でそのキー ファイルを参照します。</span><span class="sxs-lookup"><span data-stu-id="8584a-178">If it is a custom assembly that you can recompile, use the strong name tool to create an .snk (key) file and then reference that key file in the assembly properties for the project.</span></span> <span data-ttu-id="8584a-179">アセンブリを厳密な名前付けの詳細については、次を参照してください。[厳密な名前のアセンブリ キー ファイルを構成する方法](../core/how-to-configure-a-strong-name-assembly-key-file.md)です。</span><span class="sxs-lookup"><span data-stu-id="8584a-179">For more information about strong naming an assembly, see [How to Configure a Strong Name Assembly Key File](../core/how-to-configure-a-strong-name-assembly-key-file.md).</span></span>  
  
## <a name="the-error-failed-to-add-resources-change-requests-failed-for-some-resources-occurs-when-deploying-an-orchestration"></a><span data-ttu-id="8584a-180">オーケストレーションの展開時に発生する "リソースの追加に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="8584a-180">The error "Failed to add resource(s).</span></span> <span data-ttu-id="8584a-181">一部のリソースに対する変更要求に失敗しました。" エラー</span><span class="sxs-lookup"><span data-stu-id="8584a-181">Change requests failed for some resources" occurs when deploying an orchestration</span></span>  
  
### <a name="problem"></a><span data-ttu-id="8584a-182">問題</span><span class="sxs-lookup"><span data-stu-id="8584a-182">Problem</span></span>  
 <span data-ttu-id="8584a-183">オーケストレーションを展開するときに、次のようなエラーが表示され、オーケストレーションの展開は失敗します。</span><span class="sxs-lookup"><span data-stu-id="8584a-183">When deploying an orchestration, an error similar to the following is displayed and deployment of the orchestration fails:</span></span>  
  
```  
Failed to add resource(s). Change requests failed for some resources. BizTalkAssemblyResourceManager failed to complete end type change request. Object reference not set to an instance of an object.  
```  
  
### <a name="cause"></a><span data-ttu-id="8584a-184">原因</span><span class="sxs-lookup"><span data-stu-id="8584a-184">Cause</span></span>  
 <span data-ttu-id="8584a-185">このエラーは、オーケストレーションに、C# キーワードを使用するオブジェクトが含まれている場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8584a-185">This error can occur if the orchestration contains any objects that use C# keywords.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="8584a-186">解決策</span><span class="sxs-lookup"><span data-stu-id="8584a-186">Resolution</span></span>  
 <span data-ttu-id="8584a-187">オーケストレーションから C# キーワードをすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="8584a-187">Remove any C# keywords from the orchestration.</span></span> <span data-ttu-id="8584a-188">C# のキーワードの一覧は、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=74346](http://go.microsoft.com/fwlink/?LinkId=74346)です。</span><span class="sxs-lookup"><span data-stu-id="8584a-188">For a list of C# keywords, see [http://go.microsoft.com/fwlink/?LinkId=74346](http://go.microsoft.com/fwlink/?LinkId=74346).</span></span>  
  
## <a name="you-receive-an-invalid-property-value-error-when-compiling-your-orchestration"></a><span data-ttu-id="8584a-189">オーケストレーションのコンパイル時に発生する "無効なプロパティ値" エラー</span><span class="sxs-lookup"><span data-stu-id="8584a-189">You receive an "invalid property value" error when compiling your orchestration</span></span>  
  
### <a name="problem"></a><span data-ttu-id="8584a-190">問題</span><span class="sxs-lookup"><span data-stu-id="8584a-190">Problem</span></span>  
 <span data-ttu-id="8584a-191">オーケストレーションをビルドしているときに、"無効なプロパティ値" エラー ダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8584a-191">You receive the error dialog "Invalid property value" when building your orchestration.</span></span>  
  
### <a name="cause"></a><span data-ttu-id="8584a-192">原因</span><span class="sxs-lookup"><span data-stu-id="8584a-192">Cause</span></span>  
 <span data-ttu-id="8584a-193">ソリューション内の 1 つ以上のオブジェクトが別のプロジェクトと同じ名前になっています。</span><span class="sxs-lookup"><span data-stu-id="8584a-193">One or more of the objects in your solution has the same name as another object.</span></span> <span data-ttu-id="8584a-194">たとえば、メッセージ名がポート名と同じになっています。</span><span class="sxs-lookup"><span data-stu-id="8584a-194">For example, a message name is the same as a port name.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="8584a-195">解決策</span><span class="sxs-lookup"><span data-stu-id="8584a-195">Resolution</span></span>  
 <span data-ttu-id="8584a-196">ソリューション内のすべてのオブジェクトの名前が一意であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8584a-196">Ensure that every object in your solution has a unique name.</span></span> <span data-ttu-id="8584a-197">名前付け規則に従うことで、このエラーの発生を最小限に抑えることができます。</span><span class="sxs-lookup"><span data-stu-id="8584a-197">You can minimize the risk of this error by adhering to a naming convention.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8584a-198">参照</span><span class="sxs-lookup"><span data-stu-id="8584a-198">See Also</span></span>  
 [<span data-ttu-id="8584a-199">オーケストレーションを構築する方法</span><span class="sxs-lookup"><span data-stu-id="8584a-199">How to Build Orchestrations</span></span>](../core/how-to-build-orchestrations.md)