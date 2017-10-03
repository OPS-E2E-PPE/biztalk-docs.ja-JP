---
title: "カスタム Functoid (BizTalk Server サンプル) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- functoids, customizing
- examples, functoids
- functoids, examples
- XML tools
- examples, XML tools
ms.assetid: 9f1eb260-ff62-46f5-a517-57f4e9172b35
caps.latest.revision: "30"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5117bed6ea1116047052359eadcd11754e9f85d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="custom-functoid-biztalk-server-sample"></a><span data-ttu-id="d7965-102">カスタム Functoid (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="d7965-102">Custom Functoid (BizTalk Server Sample)</span></span>
<span data-ttu-id="d7965-103">カスタム Functoid サンプルは、BizTalk マッパー用のカスタム Functoid を記述する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d7965-103">The Custom Functoid sample demonstrates how to write a custom functoid for BizTalk Mapper.</span></span> <span data-ttu-id="d7965-104">Functoid は [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ツールボックスに追加できます。</span><span class="sxs-lookup"><span data-stu-id="d7965-104">You can add the functoid to the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox.</span></span> <span data-ttu-id="d7965-105">Functoid は、BizTalk マッパーにフォーカスがある場合にツールボックスに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d7965-105">The functoid will be displayed in the Toolbox when BizTalk Mapper is in focus.</span></span>  
  
 <span data-ttu-id="d7965-106">カスタム Functoid が認識されるには、BizTalk マッパー アセンブリ内に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7965-106">A custom functoid should reside in a BizTalk Mapper assembly to recognize it.</span></span> <span data-ttu-id="d7965-107">カスタム Functoid は、C# や Visual Basic などの .NET 準拠の任意の言語で記述できます。</span><span class="sxs-lookup"><span data-stu-id="d7965-107">It can be written in any .NET-compliant language, such as C# or Visual Basic.</span></span>  
  
 <span data-ttu-id="d7965-108">また、カスタム Functoid は、`Microsoft.BizTalk.BaseFunctoids` クラスから派生し、いくつかのメソッドをオーバーライドすることによって、それらのメソッドの実装を提供する必要があります </span><span class="sxs-lookup"><span data-stu-id="d7965-108">Also, a custom functoid must derive from the `Microsoft.BizTalk.BaseFunctoids` class, and it must provide implementation for some methods by overriding them.</span></span> <span data-ttu-id="d7965-109">(`BaseFunctoid` クラスは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に含まれている Microsoft.BizTalk.BaseFunctoids.dll アセンブリで定義されます)。</span><span class="sxs-lookup"><span data-stu-id="d7965-109">(The `BaseFunctoid` class is defined in the Microsoft.BizTalk.BaseFunctoids.dll assembly included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].)</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="d7965-110">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="d7965-110">What This Sample Does</span></span>  
 <span data-ttu-id="d7965-111">カスタム Functoid サンプルは、いくつかの Functoid を実装します。それぞれの Functoid は、`BaseFunctoid` クラスから派生し、いくつかのメソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="d7965-111">The Custom Functoid sample implements several functoids, each deriving from the `BaseFunctoid` class and overriding several methods.</span></span>  
  
 <span data-ttu-id="d7965-112">カスタム Functoid を実装する場合、そのインライン コードを公開できます。</span><span class="sxs-lookup"><span data-stu-id="d7965-112">When implementing a custom functoid, you can expose its code inline.</span></span> <span data-ttu-id="d7965-113">インライン コードは、Functoid の計算を実行します。</span><span class="sxs-lookup"><span data-stu-id="d7965-113">The inline code is what performs the computation for the functoid.</span></span> <span data-ttu-id="d7965-114">プロジェクトのビルド時に、BizTalk マッパー コンパイラは Functoid からインライン コードを抽出し、コンパイル済みの XSLT に埋め込みます。</span><span class="sxs-lookup"><span data-stu-id="d7965-114">The BizTalk Mapper compiler extracts inline code from a functoid and embeds it in the compiled XSLT when you build the project.</span></span>  
  
 <span data-ttu-id="d7965-115">カスタム Functoid がインライン コードを公開しない場合、カスタム Functoid を格納するアセンブリを呼び出す XSLT が BizTalk マッパーによって生成されます。</span><span class="sxs-lookup"><span data-stu-id="d7965-115">If your custom functoid does not expose any inline code, BizTalk Mapper generates XSLT that calls into the assembly where the custom functoid resides.</span></span> <span data-ttu-id="d7965-116">この場合、カスタム Functoid アセンブリは、XSLT エンジンで検出できるようにグローバル アセンブリ キャッシュ (GAC) で使用可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7965-116">In this case, you must be sure your custom functoid assembly is available in the global assembly cache (GAC) so the XSLT engine can find it.</span></span> <span data-ttu-id="d7965-117">また、カスタム Functoid の GUID 属性が一意であることも必要です。</span><span class="sxs-lookup"><span data-stu-id="d7965-117">A custom functoid must also have a unique GUID attribute.</span></span> <span data-ttu-id="d7965-118">BizTalk マッパーは GUID を使用して、読み込むアセンブリを識別します。</span><span class="sxs-lookup"><span data-stu-id="d7965-118">BizTalk Mapper uses the GUID to identify which assembly to load.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d7965-119">カスタム Functoid サンプル コードを再利用して独自の Functoid を実装する場合は、GUID 属性を一意のものに変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7965-119">If you reuse the Custom Functoid sample code to implement your own functoid(s), you must be sure to change the GUID attribute to one that is unique.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="d7965-120">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="d7965-120">Where to Find This Sample</span></span>  
 <span data-ttu-id="d7965-121">*\<サンプル パス >*\XmlTools\CustomFunctoid</span><span class="sxs-lookup"><span data-stu-id="d7965-121">*\<Samples Path>*\XmlTools\CustomFunctoid</span></span>  
  
 <span data-ttu-id="d7965-122">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="d7965-122">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="d7965-123">ファイル</span><span class="sxs-lookup"><span data-stu-id="d7965-123">File(s)</span></span>|<span data-ttu-id="d7965-124">Description</span><span class="sxs-lookup"><span data-stu-id="d7965-124">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d7965-125">AssemblyInfo.cs</span><span class="sxs-lookup"><span data-stu-id="d7965-125">AssemblyInfo.cs</span></span>|<span data-ttu-id="d7965-126">アセンブリ情報 C# ソース コード。</span><span class="sxs-lookup"><span data-stu-id="d7965-126">Assembly information C# source code.</span></span>|  
|<span data-ttu-id="d7965-127">CBuildArray.bmp</span><span class="sxs-lookup"><span data-stu-id="d7965-127">CBuildArray.bmp</span></span>|<span data-ttu-id="d7965-128">ツールボックス ビットマップ。</span><span class="sxs-lookup"><span data-stu-id="d7965-128">Toolbox bitmap.</span></span>|  
|<span data-ttu-id="d7965-129">CConcat.bmp</span><span class="sxs-lookup"><span data-stu-id="d7965-129">CConcat.bmp</span></span>|<span data-ttu-id="d7965-130">ツールボックス ビットマップ。</span><span class="sxs-lookup"><span data-stu-id="d7965-130">Toolbox bitmap.</span></span>|  
|<span data-ttu-id="d7965-131">CExtractArray.bmp</span><span class="sxs-lookup"><span data-stu-id="d7965-131">CExtractArray.bmp</span></span>|<span data-ttu-id="d7965-132">ツールボックス ビットマップ。</span><span class="sxs-lookup"><span data-stu-id="d7965-132">Toolbox bitmap.</span></span>|  
|<span data-ttu-id="d7965-133">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="d7965-133">Cleanup.bat</span></span>|<span data-ttu-id="d7965-134">アセンブリの展開を解除し、アセンブリをグローバル アセンブリ キャッシュ (GAC) から削除して、CustomFunctoid.dll を削除するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d7965-134">Used to undeploy assemblies and remove them from the global assembly cache (GAC) and to delete CustomFunctoid.dll.</span></span>|  
|<span data-ttu-id="d7965-135">CLongestString.bmp</span><span class="sxs-lookup"><span data-stu-id="d7965-135">CLongestString.bmp</span></span>|<span data-ttu-id="d7965-136">ツールボックス ビットマップ。</span><span class="sxs-lookup"><span data-stu-id="d7965-136">Toolbox bitmap.</span></span>|  
|<span data-ttu-id="d7965-137">CMultiply.bmp</span><span class="sxs-lookup"><span data-stu-id="d7965-137">CMultiply.bmp</span></span>|<span data-ttu-id="d7965-138">ツールボックス ビットマップ。</span><span class="sxs-lookup"><span data-stu-id="d7965-138">Toolbox bitmap.</span></span>|  
|<span data-ttu-id="d7965-139">CustomFunctoid.cs</span><span class="sxs-lookup"><span data-stu-id="d7965-139">CustomFunctoid.cs</span></span>|<span data-ttu-id="d7965-140">カスタム Functoid C# ソース コード。</span><span class="sxs-lookup"><span data-stu-id="d7965-140">Custom functoid C# source code.</span></span>|  
|<span data-ttu-id="d7965-141">CustomFunctoid.csproj</span><span class="sxs-lookup"><span data-stu-id="d7965-141">CustomFunctoid.csproj</span></span>|<span data-ttu-id="d7965-142">カスタム Functoid C# プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="d7965-142">Custom functoid C# project.</span></span>|  
|<span data-ttu-id="d7965-143">CustomFunctoid.sln</span><span class="sxs-lookup"><span data-stu-id="d7965-143">CustomFunctoid.sln</span></span>|<span data-ttu-id="d7965-144">カスタム Functoid ソリューション。</span><span class="sxs-lookup"><span data-stu-id="d7965-144">Custom functoid solution.</span></span>|  
|<span data-ttu-id="d7965-145">CustomFunctoidResources.resx</span><span class="sxs-lookup"><span data-stu-id="d7965-145">CustomFunctoidResources.resx</span></span>|<span data-ttu-id="d7965-146">カスタム Functoid リソース。</span><span class="sxs-lookup"><span data-stu-id="d7965-146">Custom functoid resources.</span></span>|  
|<span data-ttu-id="d7965-147">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="d7965-147">Setup.bat</span></span>|<span data-ttu-id="d7965-148">サンプルのビルド、展開、および起動を行うために使用します。</span><span class="sxs-lookup"><span data-stu-id="d7965-148">Used to build, deploy, and start the sample.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="d7965-149">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="d7965-149">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="d7965-150">次の手順に従って、カスタム Functoid サンプルをビルドおよび初期化します。</span><span class="sxs-lookup"><span data-stu-id="d7965-150">Use the following procedure to build and initialize the Custom Functoid sample.</span></span>  
  
#### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="d7965-151">このサンプルを作成および初期化するには</span><span class="sxs-lookup"><span data-stu-id="d7965-151">To build and initialize this sample</span></span>  
  
1.  <span data-ttu-id="d7965-152">コマンド ウィンドウでディレクトリ変更 (**cd**) 次のフォルダーに。</span><span class="sxs-lookup"><span data-stu-id="d7965-152">In a command window, change directory (**cd**) to the following folder:</span></span>  
  
     <span data-ttu-id="d7965-153">\<*パスのサンプル*> \XmlTools\CustomFunctoid</span><span class="sxs-lookup"><span data-stu-id="d7965-153">\<*Samples Path*>\XmlTools\CustomFunctoid</span></span>  
  
2.  <span data-ttu-id="d7965-154">次の操作を実行する Setup.bat ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="d7965-154">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="d7965-155">サンプル プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="d7965-155">Builds the sample project.</span></span>  
  
    -   <span data-ttu-id="d7965-156">生成されたアセンブリを Developer Tools\Mapper Extensions ディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="d7965-156">Copies the generated assembly to the Developer Tools\Mapper Extensions directory.</span></span>  
  
    -   <span data-ttu-id="d7965-157">生成されたアセンブリを GAC に追加します。</span><span class="sxs-lookup"><span data-stu-id="d7965-157">Adds the generated assembly to the GAC.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="d7965-158">このサンプルを実行する前に、ビルド処理および初期化処理でエラーが報告されていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d7965-158">You should confirm that no errors were reported during the build and initialization process before attempting to run this sample.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="d7965-159">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="d7965-159">Running This Sample</span></span>  
 <span data-ttu-id="d7965-160">次の手順に従って、カスタム Functoid サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="d7965-160">Use the following procedure to run the Custom Functoid sample.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="d7965-161">このサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="d7965-161">To run this sample</span></span>  
  
1.  <span data-ttu-id="d7965-162">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクトをクリックして、**ツール**メニューのおよび選択**ツールボックス アイテムの選択**です。</span><span class="sxs-lookup"><span data-stu-id="d7965-162">From a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, click the **Tools** menu, and select **Choose Toolbox Items**.</span></span>  
  
2.  <span data-ttu-id="d7965-163">**ツールボックス アイテムの選択**ダイアログ ボックスで、 **BizTalk マッパー Functoid**タブです。</span><span class="sxs-lookup"><span data-stu-id="d7965-163">In the **Choose Toolbox items** dialog box, select the **BizTalk Mapper Functoids** tab.</span></span>  
  
3.  <span data-ttu-id="d7965-164">をクリックして**リセット**、クリックして**[ok]**です。</span><span class="sxs-lookup"><span data-stu-id="d7965-164">Click **Reset**, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d7965-165">カスタム Functoid でインライン コードが公開されない場合は、アセンブリが GAC で使用可能になっているかどうかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d7965-165">If your custom functoid does not expose any inline code, make sure its assembly is made available in the GAC.</span></span>  
  
4.  <span data-ttu-id="d7965-166">**ファイル**メニューの **終了**を閉じる[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="d7965-166">From the **File** menu, select **Exit** to close [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
5.  <span data-ttu-id="d7965-167">開始**Visual Studio コマンド プロンプト**です。</span><span class="sxs-lookup"><span data-stu-id="d7965-167">Start **Visual Studio Command Prompt**.</span></span>  
  
6.  <span data-ttu-id="d7965-168">コマンド プロンプトで次のように入力します。 **devenv/setup**です。</span><span class="sxs-lookup"><span data-stu-id="d7965-168">At the command prompt, type **devenv /setup**.</span></span>  
  
7.  <span data-ttu-id="d7965-169">開始**Microsoft Visual Studio**です。</span><span class="sxs-lookup"><span data-stu-id="d7965-169">Start **Microsoft Visual Studio**.</span></span>  
  
     <span data-ttu-id="d7965-170">カスタム functoid (カスタム累積連結 functoid、最長文字列、配列作成 functoid、および配列抽出 functoid) が表示、**文字列 Functoid** に累積乗算functoidツールボックスのタブが表示されます**累積 Functoid**タブです。</span><span class="sxs-lookup"><span data-stu-id="d7965-170">The custom functoids (Custom concatenate functoid, Longest String, Build array functoid, and Extract array functoid) appear on the **String Functoids** tab of the Toolbox, and the Cumulative Multiply functoid appears on the **Cumulative Functoids** tab.</span></span>  
  
## <a name="removing-this-sample"></a><span data-ttu-id="d7965-171">このサンプルの削除</span><span class="sxs-lookup"><span data-stu-id="d7965-171">Removing This Sample</span></span>  
 <span data-ttu-id="d7965-172">次の手順に従って、カスタム Functoid サンプルを削除します。</span><span class="sxs-lookup"><span data-stu-id="d7965-172">Use the following procedure to remove the Custom Functoid sample.</span></span>  
  
#### <a name="to-remove-this-sample"></a><span data-ttu-id="d7965-173">このサンプルを削除するには</span><span class="sxs-lookup"><span data-stu-id="d7965-173">To remove this sample</span></span>  
  
1.  <span data-ttu-id="d7965-174">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ツールボックスから Functoid を削除します。</span><span class="sxs-lookup"><span data-stu-id="d7965-174">Remove the functoids from the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="d7965-175">Cleanup.bat の実行後に、ツールボックスにまだ古いカスタム Functoid がある場合 (通常は Visual Studio の内部キャッシュのため)、下記の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="d7965-175">If after running Cleanup.bat, you still see the stale custom functoids in the toolbox (probably due to internal caching by Visual Studio), then follow the procedures below:</span></span>  
  
    1.  <span data-ttu-id="d7965-176">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクトをクリックして、**ツール**メニューのおよび選択**ツールボックス アイテムの選択**です。</span><span class="sxs-lookup"><span data-stu-id="d7965-176">From a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, click the **Tools** menu, and select **Choose Toolbox Items**.</span></span>  
  
    2.  <span data-ttu-id="d7965-177">**ツールボックス アイテムの選択**ダイアログ ボックスで、 **BizTalk マッパー Functoid**タブです。</span><span class="sxs-lookup"><span data-stu-id="d7965-177">In the **Choose Toolbox items** dialog box, select the **BizTalk Mapper Functoids** tab.</span></span>  
  
    3.  <span data-ttu-id="d7965-178">一覧からカスタム Functoid (カスタム累積連結 Functoid、最長文字列、配列作成 Functoid、配列抽出 Functoid、累積乗算) を探します。</span><span class="sxs-lookup"><span data-stu-id="d7965-178">Find the custom functoids (Custom concatenate functoid, Longest String, Build array functoid, Extract array functoid, and Cumulative Multiply) in the list.</span></span> <span data-ttu-id="d7965-179">それぞれをクリックして **チェック ボックスを**、functoid を削除し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="d7965-179">Click the respective **check box** to remove the functoids, and then click **OK**.</span></span>  
  
     <span data-ttu-id="d7965-180">上記の手順でも問題が解決されない場合は、下記の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="d7965-180">If the above procedure does not work, follow the below procedure.</span></span>  
  
    1.  <span data-ttu-id="d7965-181">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクトをクリックして、**ツールボックス** タブ、ツールボックス パレットを表示するマップを編集するときにします。</span><span class="sxs-lookup"><span data-stu-id="d7965-181">From the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, click the **Toolbox** tab while editing a map to bring up the Toolbox Palette.</span></span>  
  
    2.  <span data-ttu-id="d7965-182">ツール ボックスを右クリックし **アイテムの選択**です。</span><span class="sxs-lookup"><span data-stu-id="d7965-182">Right-click the tool box and select **Choose Items**.</span></span>  
  
    3.  <span data-ttu-id="d7965-183">アイテムの選択 ダイアログ ボックスで、をクリックして**リセット**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="d7965-183">In the Choose Items dialog box, click **Reset**, and then click **OK**.</span></span>  
  
    4.  <span data-ttu-id="d7965-184">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のインスタンスをすべて閉じます。</span><span class="sxs-lookup"><span data-stu-id="d7965-184">Close all instances of [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
     <span data-ttu-id="d7965-185">上記の手順でも問題が解決されない場合は、下記の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="d7965-185">If the above procedure does not work, follow the below procedure.</span></span>  
  
    1.  <span data-ttu-id="d7965-186">開始**Visual Studio コマンド プロンプト**を管理者として。</span><span class="sxs-lookup"><span data-stu-id="d7965-186">Start **Visual Studio Command Prompt** as an administrator.</span></span>  
  
    2.  <span data-ttu-id="d7965-187">実行中の Visual Studio のインスタンスをすべて閉じます。</span><span class="sxs-lookup"><span data-stu-id="d7965-187">Close all the running instances of Visual Studio.</span></span>  
  
    3.  <span data-ttu-id="d7965-188">次のコマンドを提供します。</span><span class="sxs-lookup"><span data-stu-id="d7965-188">Give the following commands:</span></span>  
  
         `devenv /resetsettings`  
  
         `devenv /setup`  
  
    4.  <span data-ttu-id="d7965-189">ツールボックスから不要な Functoid を手動で選択できます。</span><span class="sxs-lookup"><span data-stu-id="d7965-189">You can manually select the unwanted functoids from the toolbox.</span></span> <span data-ttu-id="d7965-190">次に、functoid を右クリックしをクリックして**削除**です。</span><span class="sxs-lookup"><span data-stu-id="d7965-190">Then, right click the functoid, and click **Delete**.</span></span>  
  
     <span data-ttu-id="d7965-191">上記の手順でも問題が解決されない場合は、下記の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="d7965-191">If the above procedure does not work, follow the below procedure.</span></span>  
  
    1.  <span data-ttu-id="d7965-192">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] の BizTalk プロジェクトで、マップを編集しているときに [ツールボックス] タブをクリックして、ツールボックス パレットを開きます。</span><span class="sxs-lookup"><span data-stu-id="d7965-192">From a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, click the Toolbox tab while editing a map to bring up the Toolbox Palette.</span></span>  
  
    2.  <span data-ttu-id="d7965-193">クリックして、**累積 Functoid**グループ。</span><span class="sxs-lookup"><span data-stu-id="d7965-193">Click the **Cumulative Functoids** group.</span></span>  
  
    3.  <span data-ttu-id="d7965-194">クリックして削除する functoid を右クリックして**削除**または del キーを押します。</span><span class="sxs-lookup"><span data-stu-id="d7965-194">Right click the functoid you want to remove and then choose **Delete** or press the delete key.</span></span>  
  
    4.  <span data-ttu-id="d7965-195">クリックして、**文字列 Functoid**グループ。</span><span class="sxs-lookup"><span data-stu-id="d7965-195">Click the **String Functoids** group.</span></span>  
  
    5.  <span data-ttu-id="d7965-196">クリックして削除する functoid を右クリックして**削除**または del キーを押します。</span><span class="sxs-lookup"><span data-stu-id="d7965-196">Right click the functoid you want to remove and then choose **Delete** or press the delete key.</span></span>  
  
2.  <span data-ttu-id="d7965-197">コマンド ウィンドウでディレクトリ変更 (**cd**) 次のフォルダーに。</span><span class="sxs-lookup"><span data-stu-id="d7965-197">In a command window, change directory (**cd**) to the following folder:</span></span>  
  
     <span data-ttu-id="d7965-198">\<*パスのサンプル*> \XmlTools\CustomFunctoid</span><span class="sxs-lookup"><span data-stu-id="d7965-198">\<*Samples Path*>\XmlTools\CustomFunctoid</span></span>  
  
3.  <span data-ttu-id="d7965-199">Cleanup.bat ファイルを実行します。処理内容は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d7965-199">Run the file Cleanup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="d7965-200">アセンブリが Developer Tools\Mapper Extensions ディレクトリから削除されます。</span><span class="sxs-lookup"><span data-stu-id="d7965-200">Deletes the assembly from the Developer Tools\Mapper Extensions directory.</span></span>  
  
    -   <span data-ttu-id="d7965-201">アセンブリが GAC から削除されます。</span><span class="sxs-lookup"><span data-stu-id="d7965-201">Removes the assembly from the GAC.</span></span>  
  
## <a name="classes-or-methods-used-in-this-sample"></a><span data-ttu-id="d7965-202">このサンプルで使用されるクラスまたはメソッド</span><span class="sxs-lookup"><span data-stu-id="d7965-202">Classes or Methods Used in This Sample</span></span>  
 [<span data-ttu-id="d7965-203">Microsoft.BizTalk.BaseFunctoids.BaseFunctoid</span><span class="sxs-lookup"><span data-stu-id="d7965-203">Microsoft.BizTalk.BaseFunctoids.BaseFunctoid</span></span>](http://msdn.microsoft.com/library/microsoft.biztalk.basefunctoids.basefunctoid.aspx)  
  
## <a name="see-also"></a><span data-ttu-id="d7965-204">参照</span><span class="sxs-lookup"><span data-stu-id="d7965-204">See Also</span></span>  
 <span data-ttu-id="d7965-205">[BaseFunctoid の使用](../core/using-basefunctoid.md) </span><span class="sxs-lookup"><span data-stu-id="d7965-205">[Using BaseFunctoid](../core/using-basefunctoid.md) </span></span>  
 [<span data-ttu-id="d7965-206">XML ツール (BizTalk Server Samples フォルダ)</span><span class="sxs-lookup"><span data-stu-id="d7965-206">XML Tools (BizTalk Server Samples Folder)</span></span>](../core/xml-tools-biztalk-server-samples-folder.md)