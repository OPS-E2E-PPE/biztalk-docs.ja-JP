---
title: カスタム パイプラインのデバッグ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 27e5445a-6415-4c52-a450-b74a71fc4aa2
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be0c8714f0349ad415beca010795d2cb0b57aabb
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970352"
---
# <a name="debugging-custom-pipelines"></a><span data-ttu-id="625eb-102">カスタム パイプラインのデバッグ</span><span class="sxs-lookup"><span data-stu-id="625eb-102">Debugging Custom Pipelines</span></span>
<span data-ttu-id="625eb-103">カスタム パイプラインでメッセージ処理が失敗するときは、ソース レベルのデバッグを使用して、問題の特定と修正を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="625eb-103">When message processing fails in your custom pipeline, you can use source level debugging to identify and correct problems.</span></span> <span data-ttu-id="625eb-104">ソース レベルのデバッグは、BTSNTSVC.exe (カスタム パイプラインを配置している場合) または Pipeline.exe (スタンドアロン パイプライン ツールを使用している場合) にアタッチすることにより、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] デバッガーを使用して行います。</span><span class="sxs-lookup"><span data-stu-id="625eb-104">Source level debugging is done using the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] debugger by attaching to BTSNTSVC.exe (if the custom pipeline is deployed) or Pipeline.exe (if using the stand-alone pipeline tool).</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="625eb-105">手順</span><span class="sxs-lookup"><span data-stu-id="625eb-105">Procedures</span></span>  
 <span data-ttu-id="625eb-106">次の手順に従って、カスタム パイプラインをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="625eb-106">Use the following procedures to debug custom pipelines.</span></span>  
  
### <a name="how-to-debug-a-deployed-pipeline"></a><span data-ttu-id="625eb-107">配置済みのパイプラインをデバッグする方法</span><span class="sxs-lookup"><span data-stu-id="625eb-107">How to Debug a Deployed Pipeline</span></span>  
 <span data-ttu-id="625eb-108">[グループ ハブ] ページからのクエリの追跡およびイベント ビューアーでは、配置済みのコンポーネントでのメッセージ処理の失敗に関する役立つ情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="625eb-108">Tracking queries from the Group Hub page, and the event viewers, provide useful information about message processing failures in deployed components.</span></span> <span data-ttu-id="625eb-109">この情報を使用すると、問題の原因を絞り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="625eb-109">This information can often be used to narrow down the origin of a problem.</span></span> <span data-ttu-id="625eb-110">カスタム パイプラインが関係している場合には、ソース レベルのデバッグを使用して、問題のあるコードを特定できます。</span><span class="sxs-lookup"><span data-stu-id="625eb-110">Once a custom pipeline has been implicated, source level debugging can be used to identify any problematic code.</span></span>  
  
##### <a name="to-debug-a-deployed-custom-pipeline-using-visual-studio"></a><span data-ttu-id="625eb-111">Visual Studio を使用して配置済みのカスタム パイプラインをデバッグするには</span><span class="sxs-lookup"><span data-stu-id="625eb-111">To Debug a Deployed Custom Pipeline using Visual Studio</span></span>  
  
1.  <span data-ttu-id="625eb-112">カスタム パイプライン プロジェクトのソリューションを [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] に読み込みます。</span><span class="sxs-lookup"><span data-stu-id="625eb-112">Load the custom pipeline project solution into [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="625eb-113">ソリューションの出力パスを変更する*\<インストール フォルダー\>* \Pipeline Components です。</span><span class="sxs-lookup"><span data-stu-id="625eb-113">Change the output path for your solution to *\<Installation Folder\>* \Pipeline Components.</span></span> <span data-ttu-id="625eb-114">ソリューション エクスプ ローラーでプロジェクトを右クリックし、ビルド タブをクリックしをクリックして出力パスを変更、**参照** ボタンを選択して、 *\<インストール フォルダー\>* \Pipeline components ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="625eb-114">In Solution Explorer, right-click your project, click the Build tab, and then change the Output Path by clicking the **Browse** button and selecting the *\<Installation Folder\>* \Pipeline Components directory.</span></span>  
  
3.  <span data-ttu-id="625eb-115">内から[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]をクリックして、ソリューションをデプロイ**ビルド**&#124;です。**展開**です。</span><span class="sxs-lookup"><span data-stu-id="625eb-115">From within [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], deploy the solution by clicking **Build** &#124; **Deploy**.</span></span>  
  
4.  <span data-ttu-id="625eb-116">パイプラインを実行するホスト インスタンスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="625eb-116">Restart the host instance that runs the pipeline.</span></span> <span data-ttu-id="625eb-117">BizTalk Server 管理コンソールを使用してパイプラインを実行するホスト インスタンスに移動し、ホスト インスタンスを右クリックし、をクリックして**再起動**です。</span><span class="sxs-lookup"><span data-stu-id="625eb-117">Using the BizTalk Server Management console, navigate to the host instance that runs the pipeline, right-click the host instance then click **Restart**.</span></span>  
  
5.  <span data-ttu-id="625eb-118">アタッチ、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]デバッガーを BTSNTSVC.exe にします。</span><span class="sxs-lookup"><span data-stu-id="625eb-118">Attach the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] debugger to BTSNTSVC.exe.</span></span> <span data-ttu-id="625eb-119">クリックしてこれ行う**デバッグ**&#124;です。**プロセスにアタッチする**を すべてのセッションのプロセス表示をクリックし、BTSNTSVC.exe をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="625eb-119">This can be done by clicking **Debug** &#124; **Attach to Process**, click Show processes in all sessions, and then double-click BTSNTSVC.exe.</span></span>  
  
6.  <span data-ttu-id="625eb-120">ブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="625eb-120">Set breakpoints.</span></span>  
  
7.  <span data-ttu-id="625eb-121">適切な位置にメッセージをドロップして、カスタム パイプライン コンポーネントを開始します。</span><span class="sxs-lookup"><span data-stu-id="625eb-121">Drop a message in the appropriate location to initiate the custom pipeline component.</span></span> <span data-ttu-id="625eb-122">設定したブレークポイントで処理が停止します。</span><span class="sxs-lookup"><span data-stu-id="625eb-122">Processing should halt on the breakpoints you set.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="625eb-123">コードが例外をスローすると、BizTalk Server がそれをキャッチし、最終的にメッセージを保留します。</span><span class="sxs-lookup"><span data-stu-id="625eb-123">If your code throws an exception, BizTalk Server will catch it and ultimately suspend the message.</span></span> <span data-ttu-id="625eb-124">この動作を回避するには、初回例外でブレークする必要があります。</span><span class="sxs-lookup"><span data-stu-id="625eb-124">To avoid this behavior, you should break on first chance exceptions.</span></span>  
  
### <a name="how-to-debug-using-pipelineexe"></a><span data-ttu-id="625eb-125">Pipeline.exe を使用してデバッグする方法</span><span class="sxs-lookup"><span data-stu-id="625eb-125">How to Debug Using Pipeline.exe</span></span>  
 <span data-ttu-id="625eb-126">Pipeline.exe を使用してカスタム パイプラインをテストすることもできます。</span><span class="sxs-lookup"><span data-stu-id="625eb-126">You can also test custom pipelines using Pipeline.exe.</span></span> <span data-ttu-id="625eb-127">これにより、実稼働に近い条件下で実行されていないを犠牲にして、パイプラインをデプロイする必要がないという利点があります。</span><span class="sxs-lookup"><span data-stu-id="625eb-127">This has the advantage of not requiring you to deploy the pipeline at the expense of not running under conditions similar to production.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="625eb-128">カスタム パイプラインがフラット ファイル アセンブラー/逆アセンブラーを使用している場合は、Pipeline.exe は正常に機能しません。</span><span class="sxs-lookup"><span data-stu-id="625eb-128">If your custom pipeline uses the flat file assembler / disassembler, Pipeline.exe will not execute properly.</span></span> <span data-ttu-id="625eb-129">これは、Pipeline.exe が BizTalk データベースにアクセスしないためです。</span><span class="sxs-lookup"><span data-stu-id="625eb-129">This is because Pipeline.exe does not access the BizTalk database.</span></span> <span data-ttu-id="625eb-130">1 つのソリューションは、アセンブラーを削除する/逆アセンブラー コンポーネント FFDasm.exe および FFAsm.exe でそれらを個別にテストします。</span><span class="sxs-lookup"><span data-stu-id="625eb-130">One solution is to remove the assembler / disassembler components and test them separately with FFDasm.exe and FFAsm.exe.</span></span> <span data-ttu-id="625eb-131">参照してください[パイプライン ツール](../core/pipeline-tools.md)詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="625eb-131">See [Pipeline Tools](../core/pipeline-tools.md) for more information.</span></span>  
  
##### <a name="to-debug-a-custom-pipeline-using-pipelineexe-and-visual-studio"></a><span data-ttu-id="625eb-132">Pipeline.exe と Visual Studio を使用してカスタム パイプラインをデバッグするには</span><span class="sxs-lookup"><span data-stu-id="625eb-132">To Debug a Custom Pipeline using Pipeline.exe and Visual Studio</span></span>  
  
1.  <span data-ttu-id="625eb-133">カスタム パイプライン プロジェクトのソリューションを [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] に読み込みます。</span><span class="sxs-lookup"><span data-stu-id="625eb-133">Load the custom pipeline project solution into [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="625eb-134">ソリューションの出力パスを変更する*\<インストール フォルダー\>* \Pipeline Components です。</span><span class="sxs-lookup"><span data-stu-id="625eb-134">Change the output path for your solution to *\<Installation Folder\>* \Pipeline Components.</span></span> <span data-ttu-id="625eb-135">ソリューション エクスプ ローラーでプロジェクトを右クリックし、ビルド タブをクリックしをクリックして出力パスを変更、**参照** ボタンを選択して、 *\<インストール フォルダー\>* \Pipeline components ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="625eb-135">In Solution Explorer, right-click your project, click the Build tab, and then change the Output Path by clicking the **Browse** button and selecting the *\<Installation Folder\>* \Pipeline Components directory.</span></span>  
  
3.  <span data-ttu-id="625eb-136">ソリューションの開始アクションを変更します。</span><span class="sxs-lookup"><span data-stu-id="625eb-136">Change the start action for your solution.</span></span> <span data-ttu-id="625eb-137">ソリューション エクスプ ローラーでプロジェクトを右クリックし、デバッグ タブをクリックして、外部プログラムの開始 をクリックし をクリック**しています.**</span><span class="sxs-lookup"><span data-stu-id="625eb-137">In Solution Explorer, right-click your project, click the Debug tab, click Start external program, then click **…**</span></span> <span data-ttu-id="625eb-138">移動して*\<インストール フォルダー\>* \SDK\Utilities\PipelineTools Pipeline.exe を選択します。</span><span class="sxs-lookup"><span data-stu-id="625eb-138">and navigate to *\<Installation Folder\>* \SDK\Utilities\PipelineTools and choose Pipeline.exe.</span></span> <span data-ttu-id="625eb-139">[開始オプション]、コンポーネントの適切なコマンドライン引数を入力します。</span><span class="sxs-lookup"><span data-stu-id="625eb-139">Under Start Options, enter the command line arguments appropriate for your component.</span></span> <span data-ttu-id="625eb-140">Pipeline.exe の詳細については、次を参照してください。[パイプライン ツール](../core/pipeline-tools.md)です。</span><span class="sxs-lookup"><span data-stu-id="625eb-140">For more information on Pipeline.exe, see [Pipeline Tools](../core/pipeline-tools.md).</span></span> <span data-ttu-id="625eb-141">一般的な構成では、パイプラインとサンプル ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="625eb-141">A typical configuration specifies the pipeline and a sample file:</span></span>  
  
    ```  
    <Path>\YourPipeline.btp -d <Path>\YourTestFile.txt -c  
    ```  
  
4.  <span data-ttu-id="625eb-142">ブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="625eb-142">Set your breakpoints.</span></span>  
  
5.  <span data-ttu-id="625eb-143">F5 キーを押してデバッグを開始します。</span><span class="sxs-lookup"><span data-stu-id="625eb-143">Press F5 to begin debugging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="625eb-144">参照</span><span class="sxs-lookup"><span data-stu-id="625eb-144">See Also</span></span>  
 [<span data-ttu-id="625eb-145">パイプライン ツール</span><span class="sxs-lookup"><span data-stu-id="625eb-145">Pipeline Tools</span></span>](../core/pipeline-tools.md)