---
title: タスク一覧のビルド エラー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- building, errors
- errors, building
ms.assetid: 05b36511-3031-4e13-ac2f-bfdbec0f48cb
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5cc22550629d8ae66652e0afe1da61b1443dc580
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357778"
---
# <a name="build-errors-in-the-task-list"></a><span data-ttu-id="6650f-102">タスク一覧のビルド エラー</span><span class="sxs-lookup"><span data-stu-id="6650f-102">Build Errors in the Task List</span></span>
<span data-ttu-id="6650f-103">プロジェクト、またはソリューションをビルドするときに、個々 のエラーと警告がタスク一覧に表示されます、[出力] ウィンドウで、結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6650f-103">When you build your project, or solution, the results will appear in the Output window, while individual errors and warnings will appear in the task list.</span></span>  
  
 <span data-ttu-id="6650f-104">タスク一覧には、エラーと警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6650f-104">Errors and warnings appear in the task list.</span></span> <span data-ttu-id="6650f-105">エラーをダブルクリックして、フォーカスを正しく構成されていないオブジェクトに適用されます。</span><span class="sxs-lookup"><span data-stu-id="6650f-105">You can double-click the error, and the focus will be applied to the object that is not correctly configured.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6650f-106">ビルドすると、コンパイラは Xpath を検証しません。</span><span class="sxs-lookup"><span data-stu-id="6650f-106">When you build, the compiler does not validate XPaths.</span></span> <span data-ttu-id="6650f-107">有効な XPath 構文を使用して、注意してください。</span><span class="sxs-lookup"><span data-stu-id="6650f-107">Take care to use valid XPath syntax.</span></span>  
  
## <a name="insufficient-configuration-action"></a><span data-ttu-id="6650f-108">不十分な構成アクション</span><span class="sxs-lookup"><span data-stu-id="6650f-108">Insufficient configuration Action</span></span>  
 <span data-ttu-id="6650f-109">![](../core/media/ebiz-orch-insufficconfig.gif "ebiz_orch_insufficconfig")</span><span class="sxs-lookup"><span data-stu-id="6650f-109">![](../core/media/ebiz-orch-insufficconfig.gif "ebiz_orch_insufficconfig")</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="6650f-110">オーケストレーション デザイナーを提供すると、不十分な構成の警告をこのような警告がない場合、オーケストレーションが正しくコンパイルされるという保証はありません。</span><span class="sxs-lookup"><span data-stu-id="6650f-110">While Orchestration Designer will provide insufficient configuration warnings where it can, there is no guarantee that your orchestration will compile correctly in the absence of such warnings.</span></span>  
  
## <a name="compiler-asks-if-you-are-missing-an-assembly-reference"></a><span data-ttu-id="6650f-111">コンパイラがアセンブリ参照が欠落しているかどうかを求める</span><span class="sxs-lookup"><span data-stu-id="6650f-111">Compiler asks if you are missing an assembly reference</span></span>  
  
### <a name="problem"></a><span data-ttu-id="6650f-112">問題</span><span class="sxs-lookup"><span data-stu-id="6650f-112">Problem</span></span>  
 <span data-ttu-id="6650f-113">"をアセンブリ参照が存在しますか?"という質問で終了するエラー メッセージを表示するオーケストレーションをコンパイルするときに</span><span class="sxs-lookup"><span data-stu-id="6650f-113">When you compile your orchestration you get an error message that ends with the question "are you missing an assembly reference?"</span></span> <span data-ttu-id="6650f-114">2 つの一般的なメッセージは。</span><span class="sxs-lookup"><span data-stu-id="6650f-114">Two of the more common messages are:</span></span>  
  
-   <span data-ttu-id="6650f-115">型または名前空間の名前 'X' は名前空間 'Y' に存在しません (する、アセンブリ参照が存在しますか?)</span><span class="sxs-lookup"><span data-stu-id="6650f-115">The type or namespace name 'X' does not exist in the namespace 'Y' (are you missing an assembly reference?)</span></span>  
  
-   <span data-ttu-id="6650f-116">識別子 'X' が 'Y'; に存在しません。アセンブリ参照が見当たりませんか。</span><span class="sxs-lookup"><span data-stu-id="6650f-116">Identifier 'X' does not exist in 'Y'; are you missing an assembly reference?</span></span>  
  
### <a name="cause"></a><span data-ttu-id="6650f-117">原因</span><span class="sxs-lookup"><span data-stu-id="6650f-117">Cause</span></span>  
 <span data-ttu-id="6650f-118">このエラーの原因は次のいずれかの可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6650f-118">Any of the following could be the cause of this error.</span></span>  
  
-   <span data-ttu-id="6650f-119">プロジェクトは、1 つまたは複数の必要なアセンブリを参照していません。</span><span class="sxs-lookup"><span data-stu-id="6650f-119">Your project does not reference one or more required assemblies.</span></span>  
  
-   <span data-ttu-id="6650f-120">プロジェクトには、マップまたはその他のプロジェクトと同じ名前を持つオブジェクトの種類が存在します。</span><span class="sxs-lookup"><span data-stu-id="6650f-120">Your project has a map or other object type that has the same name as the project.</span></span>  
  
-   <span data-ttu-id="6650f-121">プロジェクトで XML スキーマ定義言語 (XSD) を使用-プロセス PIP (Partner Interface) のスキーマに基づいており、System という名前のサブフォルダーに XSD スキーマを含みます。</span><span class="sxs-lookup"><span data-stu-id="6650f-121">Your project uses XML Schema definition language (XSD)-based Partner Interface Process (PIP) schemas and contains XSD schemas in a subfolder that is named System.</span></span>  
  
-   <span data-ttu-id="6650f-122">プロジェクトには、名前空間を持つ現在のプロジェクトの名前空間のサブセットであるグローバル プロパティが使用しています。</span><span class="sxs-lookup"><span data-stu-id="6650f-122">Your project is using a Global Property whose namespace is a subset of the current project's namespace.</span></span> <span data-ttu-id="6650f-123">たとえば、プロジェクト"Accounts.FILE"に含まれるオーケストレーション内のグローバル プロパティ名前空間"File.ReceivedFileName"を使用します。</span><span class="sxs-lookup"><span data-stu-id="6650f-123">For example, using the Global Property namespace "File.ReceivedFileName" in an orchestration contained in the project "Accounts.FILE".</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="6650f-124">解決策</span><span class="sxs-lookup"><span data-stu-id="6650f-124">Resolution</span></span>  
 <span data-ttu-id="6650f-125">問題の原因によっては、解決策があります、次のいずれか。</span><span class="sxs-lookup"><span data-stu-id="6650f-125">Depending upon the cause of the problem, the resolution could be any of the following:</span></span>  
  
-   <span data-ttu-id="6650f-126">不足しているへの参照を追加するアセンブリのプロジェクトが必要です。</span><span class="sxs-lookup"><span data-stu-id="6650f-126">Add a reference to the missing assemblies your project requires.</span></span>  
  
-   <span data-ttu-id="6650f-127">プロジェクト名以外に、マップまたはその他のオブジェクトの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="6650f-127">Change the name of the map or other object to something other than the project name.</span></span> <span data-ttu-id="6650f-128">これは、オブジェクトのプロパティ ページで通常行うことができます (たとえば、Name プロパティを含むプロパティ [マップ] ページ)。</span><span class="sxs-lookup"><span data-stu-id="6650f-128">This can typically be done through the object's property page (for example, the Map property page contains a Name property).</span></span>  
  
-   <span data-ttu-id="6650f-129">Visual Studio 内のスキーマの名前空間を変更します。</span><span class="sxs-lookup"><span data-stu-id="6650f-129">Change the namespace for the schemas in Visual Studio.</span></span> <span data-ttu-id="6650f-130">Visual Studio を使用してこれを行うに**すべてのファイル**で、**プロジェクト** メニューの 順に展開し、**システム**ソリューション エクスプ ローラーでノード。</span><span class="sxs-lookup"><span data-stu-id="6650f-130">To do this using Visual Studio, click **Show All Files** on the **Project** menu, and then expand the **System** node in Solution Explorer.</span></span> <span data-ttu-id="6650f-131">システム フォルダーおよびすべてのサブフォルダーでは、各ファイルをクリックし、[プロパティ] ウィンドウで名前空間エントリを変更に出現する**システム**なります _**システム**します。</span><span class="sxs-lookup"><span data-stu-id="6650f-131">Click each file in the System folder and in any subfolders, and then change the namespace entry in the Properties window so that any occurrence of **System** becomes _**System**.</span></span> <span data-ttu-id="6650f-132">たとえば、変更、 **MyProject.System.SubFolder**名前空間を**MyProject._System.Subfolder**名前空間。</span><span class="sxs-lookup"><span data-stu-id="6650f-132">For example, change the **MyProject.System.SubFolder** namespace to **the MyProject._System.Subfolder** namespace.</span></span> <span data-ttu-id="6650f-133">サポート技術情報の記事を参照してください、この問題の詳細については[916649](http://support.microsoft.com/?kbid=916649)します。</span><span class="sxs-lookup"><span data-stu-id="6650f-133">For more information about this issue, see KB article [916649](http://support.microsoft.com/?kbid=916649).</span></span>  
  
-   <span data-ttu-id="6650f-134">競合するグローバル プロパティ名前空間をプロジェクトから削除します。</span><span class="sxs-lookup"><span data-stu-id="6650f-134">Remove the conflicting Global Property namespace from the project.</span></span>  
  
## <a name="you-receive-a-message-has-not-been-initialized-in-construct-statement-error-when-building-your-project"></a><span data-ttu-id="6650f-135">プロジェクトのビルド時に「メッセージが初期化されていません construct ステートメントで」エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="6650f-135">You receive a "Message has not been initialized in construct statement" error when building your project</span></span>  
  
### <a name="problem"></a><span data-ttu-id="6650f-136">問題</span><span class="sxs-lookup"><span data-stu-id="6650f-136">Problem</span></span>  
 <span data-ttu-id="6650f-137">エラーが発生する、BizTalk アプリケーションをコンパイルするときに「メッセージが初期化されていません construct ステートメントで」。</span><span class="sxs-lookup"><span data-stu-id="6650f-137">When you compile your BizTalk application, you get the error "Message has not been initialized in construct statement".</span></span>  
  
### <a name="cause"></a><span data-ttu-id="6650f-138">原因</span><span class="sxs-lookup"><span data-stu-id="6650f-138">Cause</span></span>  
 <span data-ttu-id="6650f-139">メッセージを構築する場合は、すべてのメッセージ変数を指定します。</span><span class="sxs-lookup"><span data-stu-id="6650f-139">When you construct a message, you specify all the message variables.</span></span> <span data-ttu-id="6650f-140">メッセージまたはメッセージの部分に割り当てを行います。</span><span class="sxs-lookup"><span data-stu-id="6650f-140">Then you make assignments to the message or its parts.</span></span> <span data-ttu-id="6650f-141">別の特定のメッセージの割り当ての一部が含まれているかどうかは**メッセージの構築**図形、初期化のエラー メッセージが表示される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6650f-141">If part of a specific message assignment is included in a separate **Construct Message** shape, you may receive the initialization error message.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="6650f-142">解決策</span><span class="sxs-lookup"><span data-stu-id="6650f-142">Resolution</span></span>  
 <span data-ttu-id="6650f-143">この問題を解決するには、同じ特定のメッセージの割り当てのすべての部分を含めることを確認します**メッセージの構築**図形。</span><span class="sxs-lookup"><span data-stu-id="6650f-143">To resolve this behavior, make sure that you include all parts of a specific message assignment in the same **Construct Message** shape.</span></span> <span data-ttu-id="6650f-144">関連するサポートの問題点、サポート技術情報の記事を参照してくださいについて[870606](http://support.microsoft.com/?kbid=870606)します。</span><span class="sxs-lookup"><span data-stu-id="6650f-144">For a related support issue, see KB article [870606](http://support.microsoft.com/?kbid=870606).</span></span>  
  
 <span data-ttu-id="6650f-145">内のメッセージを作成して、この問題を解決することができますも、**構築**図形内のイメージのインスタンスを使用する前に、**式**図形。</span><span class="sxs-lookup"><span data-stu-id="6650f-145">You can also resolve this behavior by creating your message in a **Construct** shape before using an instance of it in an **Expression** shape.</span></span> <span data-ttu-id="6650f-146">たとえば、次のコード エラーが発生に配置されている場合、**式**図形。</span><span class="sxs-lookup"><span data-stu-id="6650f-146">For example, the following code will cause an error if placed in an **Expression** shape:</span></span>  
  
```  
XMLDOM = new System.Xml.XmlDocument();  
POAckMsg = XMLDOM;  
```  
  
 <span data-ttu-id="6650f-147">を解決するには、内に XMLDOM のインスタンスを作成、**構築**図形し、ダウン ストリームの割り当てを行って**式**図形。</span><span class="sxs-lookup"><span data-stu-id="6650f-147">To fix, create the instance of XMLDOM in a **Construct** shape, and then do the assignment in a downstream **Expression** shape.</span></span>  
  
## <a name="you-receive-a-use-of-unconstructed-message-error-when-building-your-project"></a><span data-ttu-id="6650f-148">プロジェクトのビルド時に「未構築のメッセージの使用」エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="6650f-148">You receive a "use of unconstructed message" error when building your project</span></span>  
  
### <a name="problem"></a><span data-ttu-id="6650f-149">問題</span><span class="sxs-lookup"><span data-stu-id="6650f-149">Problem</span></span>  
 <span data-ttu-id="6650f-150">BizTalk プロジェクトをコンパイルするときにエラーが発生した"未構築のメッセージの使用 '\<メッセージ\>'"です。</span><span class="sxs-lookup"><span data-stu-id="6650f-150">When you compile your BizTalk project, you receive the error "use of unconstructed message '\<message\>'".</span></span>  
  
### <a name="cause"></a><span data-ttu-id="6650f-151">原因</span><span class="sxs-lookup"><span data-stu-id="6650f-151">Cause</span></span>  
 <span data-ttu-id="6650f-152">未構築のメッセージを使用すると、このエラーが発生した、**送信**図形。</span><span class="sxs-lookup"><span data-stu-id="6650f-152">This error occurs when an unconstructed message is used in a **Send** shape.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="6650f-153">解決策</span><span class="sxs-lookup"><span data-stu-id="6650f-153">Resolution</span></span>  
 <span data-ttu-id="6650f-154">この問題を解決するには、追加、**メッセージの構築**オーケストレーションへの図形。</span><span class="sxs-lookup"><span data-stu-id="6650f-154">To resolve this issue, add a **Construct Message** shape to the orchestration.</span></span> <span data-ttu-id="6650f-155">含める、**メッセージの構築**図形の前に、**送信**Web サービスにバインドされている図形。</span><span class="sxs-lookup"><span data-stu-id="6650f-155">Include the **Construct Message** shape before the **Send** shape that is bound to the Web service.</span></span>  
  
 <span data-ttu-id="6650f-156">このエラーとサポート技術情報の記事を参照してください、Web サービスの詳細については[921043](http://support.microsoft.com/?kbid=921043)します。</span><span class="sxs-lookup"><span data-stu-id="6650f-156">For more information about this error and Web services, see KB article [921043](http://support.microsoft.com/?kbid=921043).</span></span>  
  
## <a name="setting-a-transaction-level-for-a-scope-results-in-an-error"></a><span data-ttu-id="6650f-157">エラーの結果を絞り込む、トランザクション レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="6650f-157">Setting a transaction level for a scope results in an error</span></span>  
  
### <a name="problem"></a><span data-ttu-id="6650f-158">問題</span><span class="sxs-lookup"><span data-stu-id="6650f-158">Problem</span></span>  
 <span data-ttu-id="6650f-159">スコープの入力、トランザクションを構成または他のエンティティでは、オーケストレーションでのトランザクションのサポート、エラーが発生した後に「非トランザクション オーケストレーションを含めることはできません他のトランザクション」。</span><span class="sxs-lookup"><span data-stu-id="6650f-159">After configuring the transaction type for a scope or other entity supporting transactions in an orchestration, you receive the error "A Non-transactional Orchestration cannot contain any other Transactions".</span></span>  
  
### <a name="cause"></a><span data-ttu-id="6650f-160">原因</span><span class="sxs-lookup"><span data-stu-id="6650f-160">Cause</span></span>  
 <span data-ttu-id="6650f-161">このエラーと発生しますスコープ (またはその他のエンティティ) のトランザクションの種類を構成しようとすると「アトミック」または「実行時間の長い」するためのオーケストレーションで、オーケストレーション自体がある"None"のトランザクションの種類。</span><span class="sxs-lookup"><span data-stu-id="6650f-161">This error occurs when you try to configure the transaction type of a scope (or other entity) in an orchestration to "Atomic" or "Long-Running" when the orchestration itself has a transaction type of "None".</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="6650f-162">解決策</span><span class="sxs-lookup"><span data-stu-id="6650f-162">Resolution</span></span>  
 <span data-ttu-id="6650f-163">オーケストレーションと構成のオブジェクトのトランザクションの種類の設定に互換性があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6650f-163">Ensure that the transaction type settings of your orchestration and constituent objects are compatible.</span></span>  
  
## <a name="project-build-results-in-the-error-you-must-specify-at-least-one-already-initialized-correlation-set-for-a-non-activation-receive-that-is-on-a-non-selfcorrelating-port"></a><span data-ttu-id="6650f-164">プロジェクト ビルド エラーが発生"する必要があります 1 つ以上指定初期化済みの関連付けが非アクティブ化の設定が表示される非自己関連付けを行わないポート上にある"</span><span class="sxs-lookup"><span data-stu-id="6650f-164">Project build results in the error "you must specify at least one already-initialized correlation set for a non-activation receive that is on a non-selfcorrelating port"</span></span>  
  
### <a name="problem"></a><span data-ttu-id="6650f-165">問題</span><span class="sxs-lookup"><span data-stu-id="6650f-165">Problem</span></span>  
 <span data-ttu-id="6650f-166">BizTalk プロジェクトをコンパイルするときに、"する必要があります 1 つ以上指定初期化済みの関連付けが非アクティブ化の設定が表示される非自己関連付けを行わないポート上にある"エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6650f-166">When you compile your BizTalk project, you receive the error "you must specify at least one already-initialized correlation set for a non-activation receive that is on a non-selfcorrelating port".</span></span>  
  
### <a name="cause"></a><span data-ttu-id="6650f-167">原因</span><span class="sxs-lookup"><span data-stu-id="6650f-167">Cause</span></span>  
 <span data-ttu-id="6650f-168">アクティブ化するオーケストレーションが存在しない場合、このエラーが発生する可能性が**受信**図形 (Activate = true)、またはアクティブ化がありません**受信**図形し、は別のオーケストレーションによって直接呼び出されません。</span><span class="sxs-lookup"><span data-stu-id="6650f-168">This error can occur if your orchestration has no activating **Receive** shapes (Activate = true) or has no activating **Receive** shapes and is not called directly by another orchestration.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="6650f-169">解決策</span><span class="sxs-lookup"><span data-stu-id="6650f-169">Resolution</span></span>  
 <span data-ttu-id="6650f-170">オーケストレーションが別のオーケストレーションによって呼び出されない場合のいずれかを構成する必要があります、**受信**をアクティブ化された受信図形。</span><span class="sxs-lookup"><span data-stu-id="6650f-170">If your orchestration is not called by another orchestration, you must configure one of the **Receive** shapes to be an activated receive.</span></span> <span data-ttu-id="6650f-171">構成の詳細については、**受信**図形、相関関係へのリンクなどを参照してください[受信図形を構成する方法](../core/how-to-configure-the-receive-shape.md)します。</span><span class="sxs-lookup"><span data-stu-id="6650f-171">For more information about configuring the **Receive** shape, including links to correlation, see [How to Configure the Receive Shape](../core/how-to-configure-the-receive-shape.md).</span></span>  
  
## <a name="you-receive-the-error-assembly-generation-failed----referenced-assembly-assembly-does-not-have-a-strong-name-when-building-your-solution"></a><span data-ttu-id="6650f-172">エラーが発生した"アセンブリの生成に失敗しました--参照されたアセンブリ '\<アセンブリ\>' 厳密な名前が"ソリューションを構築するときに</span><span class="sxs-lookup"><span data-stu-id="6650f-172">You receive the error "Assembly generation failed -- Referenced assembly '\<assembly\>' does not have a strong name" when building your solution</span></span>  
  
### <a name="problem"></a><span data-ttu-id="6650f-173">問題</span><span class="sxs-lookup"><span data-stu-id="6650f-173">Problem</span></span>  
 <span data-ttu-id="6650f-174">エラーが発生した"アセンブリの生成に失敗しました--参照されたアセンブリ '\<アセンブリ\>' 厳密な名前ではありません"がオーケストレーション ソリューションを構築した場合にします。</span><span class="sxs-lookup"><span data-stu-id="6650f-174">You receive the error "Assembly generation failed -- Referenced assembly '\<assembly\>' does not have a strong name" when building your solution that has an orchestration.</span></span>  
  
### <a name="cause"></a><span data-ttu-id="6650f-175">原因</span><span class="sxs-lookup"><span data-stu-id="6650f-175">Cause</span></span>  
 <span data-ttu-id="6650f-176">この問題は、符号なしの参照先アセンブリの型は、オーケストレーション内で使用する場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="6650f-176">This problem occurs when a type from an unsigned referenced assembly is used within an orchestration.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="6650f-177">解決策</span><span class="sxs-lookup"><span data-stu-id="6650f-177">Resolution</span></span>  
 <span data-ttu-id="6650f-178">参照アセンブリに厳密な名前を適用します。</span><span class="sxs-lookup"><span data-stu-id="6650f-178">Apply a strong name to the referenced assembly.</span></span> <span data-ttu-id="6650f-179">カスタム アセンブリが再コンパイルすることができますがの場合は、厳密な名前ツールを使用して、.snk (キー) ファイルを作成し、プロジェクトのアセンブリのプロパティのキー ファイルを参照します。</span><span class="sxs-lookup"><span data-stu-id="6650f-179">If it is a custom assembly that you can recompile, use the strong name tool to create an .snk (key) file and then reference that key file in the assembly properties for the project.</span></span> <span data-ttu-id="6650f-180">アセンブリを厳密な名前付けの詳細については、次を参照してください。[厳密な名前のアセンブリ キー ファイルを構成する方法](../core/how-to-configure-a-strong-name-assembly-key-file.md)します。</span><span class="sxs-lookup"><span data-stu-id="6650f-180">For more information about strong naming an assembly, see [How to Configure a Strong Name Assembly Key File](../core/how-to-configure-a-strong-name-assembly-key-file.md).</span></span>  
  
## <a name="the-error-failed-to-add-resources-change-requests-failed-for-some-resources-occurs-when-deploying-an-orchestration"></a><span data-ttu-id="6650f-181">"リソースの追加に失敗しましたエラー。</span><span class="sxs-lookup"><span data-stu-id="6650f-181">The error "Failed to add resource(s).</span></span> <span data-ttu-id="6650f-182">オーケストレーションを展開するときに発生する変更要求の一部のリソースに失敗しました"</span><span class="sxs-lookup"><span data-stu-id="6650f-182">Change requests failed for some resources" occurs when deploying an orchestration</span></span>  
  
### <a name="problem"></a><span data-ttu-id="6650f-183">問題</span><span class="sxs-lookup"><span data-stu-id="6650f-183">Problem</span></span>  
 <span data-ttu-id="6650f-184">オーケストレーションを展開するには、次のようなエラーが表示され、オーケストレーションの展開は失敗します。</span><span class="sxs-lookup"><span data-stu-id="6650f-184">When deploying an orchestration, an error similar to the following is displayed and deployment of the orchestration fails:</span></span>  
  
```  
Failed to add resource(s). Change requests failed for some resources. BizTalkAssemblyResourceManager failed to complete end type change request. Object reference not set to an instance of an object.  
```  
  
### <a name="cause"></a><span data-ttu-id="6650f-185">原因</span><span class="sxs-lookup"><span data-stu-id="6650f-185">Cause</span></span>  
 <span data-ttu-id="6650f-186">このエラーは、オーケストレーションに使用する任意のオブジェクトが含まれている場合に発生する可能性がC#キーワード。</span><span class="sxs-lookup"><span data-stu-id="6650f-186">This error can occur if the orchestration contains any objects that use C# keywords.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="6650f-187">解決策</span><span class="sxs-lookup"><span data-stu-id="6650f-187">Resolution</span></span>  
 <span data-ttu-id="6650f-188">削除C#オーケストレーションからのキーワード。</span><span class="sxs-lookup"><span data-stu-id="6650f-188">Remove any C# keywords from the orchestration.</span></span> <span data-ttu-id="6650f-189">一覧についてはC#キーワードを参照してください[ http://go.microsoft.com/fwlink/?LinkId=74346](http://go.microsoft.com/fwlink/?LinkId=74346)します。</span><span class="sxs-lookup"><span data-stu-id="6650f-189">For a list of C# keywords, see [http://go.microsoft.com/fwlink/?LinkId=74346](http://go.microsoft.com/fwlink/?LinkId=74346).</span></span>  
  
## <a name="you-receive-an-invalid-property-value-error-when-compiling-your-orchestration"></a><span data-ttu-id="6650f-190">オーケストレーションをコンパイルするときに、「無効なプロパティの値」エラーを受信します。</span><span class="sxs-lookup"><span data-stu-id="6650f-190">You receive an "invalid property value" error when compiling your orchestration</span></span>  
  
### <a name="problem"></a><span data-ttu-id="6650f-191">問題</span><span class="sxs-lookup"><span data-stu-id="6650f-191">Problem</span></span>  
 <span data-ttu-id="6650f-192">「無効なプロパティの値」エラー ダイアログが表示されたら、オーケストレーションを構築するときにします。</span><span class="sxs-lookup"><span data-stu-id="6650f-192">You receive the error dialog "Invalid property value" when building your orchestration.</span></span>  
  
### <a name="cause"></a><span data-ttu-id="6650f-193">原因</span><span class="sxs-lookup"><span data-stu-id="6650f-193">Cause</span></span>  
 <span data-ttu-id="6650f-194">1 つ以上のソリューション内のオブジェクトは、別のオブジェクトと同じ名前を持ちます。</span><span class="sxs-lookup"><span data-stu-id="6650f-194">One or more of the objects in your solution has the same name as another object.</span></span> <span data-ttu-id="6650f-195">たとえば、メッセージ名は、ポート名と同じ。</span><span class="sxs-lookup"><span data-stu-id="6650f-195">For example, a message name is the same as a port name.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="6650f-196">解決策</span><span class="sxs-lookup"><span data-stu-id="6650f-196">Resolution</span></span>  
 <span data-ttu-id="6650f-197">ソリューション内のすべてのオブジェクトに一意の名前があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6650f-197">Ensure that every object in your solution has a unique name.</span></span> <span data-ttu-id="6650f-198">名前付け規則に従うことで、このエラーのリスクを最小限に抑えることができます。</span><span class="sxs-lookup"><span data-stu-id="6650f-198">You can minimize the risk of this error by adhering to a naming convention.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6650f-199">参照</span><span class="sxs-lookup"><span data-stu-id="6650f-199">See Also</span></span>  
 [<span data-ttu-id="6650f-200">オーケストレーションを構築する方法</span><span class="sxs-lookup"><span data-stu-id="6650f-200">How to Build Orchestrations</span></span>](../core/how-to-build-orchestrations.md)