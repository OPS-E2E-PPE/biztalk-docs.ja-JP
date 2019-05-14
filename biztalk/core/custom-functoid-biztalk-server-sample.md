---
title: カスタム Functoid (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- functoids, customizing
- examples, functoids
- functoids, examples
- XML tools
- examples, XML tools
ms.assetid: 9f1eb260-ff62-46f5-a517-57f4e9172b35
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d115e0a0594bc236487cca62c9b61355a8535116
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353404"
---
# <a name="custom-functoid-biztalk-server-sample"></a><span data-ttu-id="4010c-102">カスタム Functoid (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="4010c-102">Custom Functoid (BizTalk Server Sample)</span></span>
<span data-ttu-id="4010c-103">カスタム Functoid サンプルでは、BizTalk マッパー用のカスタム functoid を記述する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4010c-103">The Custom Functoid sample demonstrates how to write a custom functoid for BizTalk Mapper.</span></span> <span data-ttu-id="4010c-104">Functoid を追加することができます、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックスです。</span><span class="sxs-lookup"><span data-stu-id="4010c-104">You can add the functoid to the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox.</span></span> <span data-ttu-id="4010c-105">BizTalk マッパーにフォーカスがときに、ツールボックスに functoid が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4010c-105">The functoid will be displayed in the Toolbox when BizTalk Mapper is in focus.</span></span>  
  
 <span data-ttu-id="4010c-106">カスタム functoid は、認識する BizTalk マッパー アセンブリ内に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4010c-106">A custom functoid should reside in a BizTalk Mapper assembly to recognize it.</span></span> <span data-ttu-id="4010c-107">これは、いずれかで記述できます。C# または Visual Basic などの NET 準拠言語。</span><span class="sxs-lookup"><span data-stu-id="4010c-107">It can be written in any .NET-compliant language, such as C# or Visual Basic.</span></span>  
  
 <span data-ttu-id="4010c-108">また、カスタム functoid がから派生する必要があります、`Microsoft.BizTalk.BaseFunctoids`クラス、およびは、それらをオーバーライドすることで一部のメソッドの実装を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4010c-108">Also, a custom functoid must derive from the `Microsoft.BizTalk.BaseFunctoids` class, and it must provide implementation for some methods by overriding them.</span></span> <span data-ttu-id="4010c-109">(、`BaseFunctoid`クラスに含まれている Microsoft.BizTalk.BaseFunctoids.dll アセンブリで定義されます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="4010c-109">(The `BaseFunctoid` class is defined in the Microsoft.BizTalk.BaseFunctoids.dll assembly included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].)</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="4010c-110">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="4010c-110">What This Sample Does</span></span>  
 <span data-ttu-id="4010c-111">カスタム Functoid サンプルから派生する各いくつかの functoid を実装する、`BaseFunctoid`クラスといくつかのメソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="4010c-111">The Custom Functoid sample implements several functoids, each deriving from the `BaseFunctoid` class and overriding several methods.</span></span>  
  
 <span data-ttu-id="4010c-112">カスタム functoid を実装する場合は、そのインライン コードを公開できます。</span><span class="sxs-lookup"><span data-stu-id="4010c-112">When implementing a custom functoid, you can expose its code inline.</span></span> <span data-ttu-id="4010c-113">インライン コードは、functoid の計算を実行します。</span><span class="sxs-lookup"><span data-stu-id="4010c-113">The inline code is what performs the computation for the functoid.</span></span> <span data-ttu-id="4010c-114">BizTalk マッパーのコンパイラでは、functoid からインライン コードを抽出し、プロジェクトをビルドするときにコンパイルされた XSLT に埋め込みます。</span><span class="sxs-lookup"><span data-stu-id="4010c-114">The BizTalk Mapper compiler extracts inline code from a functoid and embeds it in the compiled XSLT when you build the project.</span></span>  
  
 <span data-ttu-id="4010c-115">カスタム functoid でインライン コードが公開されない場合、BizTalk マッパーには、カスタム functoid が存在するアセンブリを呼び出す XSLT が生成されます。</span><span class="sxs-lookup"><span data-stu-id="4010c-115">If your custom functoid does not expose any inline code, BizTalk Mapper generates XSLT that calls into the assembly where the custom functoid resides.</span></span> <span data-ttu-id="4010c-116">この場合は、カスタム functoid アセンブリがあることをグローバル アセンブリ キャッシュ (GAC) に、XSLT エンジンが検索できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4010c-116">In this case, you must be sure your custom functoid assembly is available in the global assembly cache (GAC) so the XSLT engine can find it.</span></span> <span data-ttu-id="4010c-117">カスタム functoid は、一意の GUID 属性も必要です。</span><span class="sxs-lookup"><span data-stu-id="4010c-117">A custom functoid must also have a unique GUID attribute.</span></span> <span data-ttu-id="4010c-118">BizTalk マッパーでは、どのアセンブリを読み込むを識別するのに GUID を使用します。</span><span class="sxs-lookup"><span data-stu-id="4010c-118">BizTalk Mapper uses the GUID to identify which assembly to load.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4010c-119">独自の functoid を実装するためにカスタム Functoid サンプル コードを再利用する場合は、一意である 1 つに GUID 属性を変更することを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4010c-119">If you reuse the Custom Functoid sample code to implement your own functoid(s), you must be sure to change the GUID attribute to one that is unique.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="4010c-120">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="4010c-120">Where to Find This Sample</span></span>  
 <span data-ttu-id="4010c-121">*\<パスのサンプル\>* \XmlTools\CustomFunctoid</span><span class="sxs-lookup"><span data-stu-id="4010c-121">*\<Samples Path\>* \XmlTools\CustomFunctoid</span></span>  
  
 <span data-ttu-id="4010c-122">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="4010c-122">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="4010c-123">ファイル</span><span class="sxs-lookup"><span data-stu-id="4010c-123">File(s)</span></span>|<span data-ttu-id="4010c-124">説明</span><span class="sxs-lookup"><span data-stu-id="4010c-124">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4010c-125">AssemblyInfo.cs</span><span class="sxs-lookup"><span data-stu-id="4010c-125">AssemblyInfo.cs</span></span>|<span data-ttu-id="4010c-126">アセンブリ情報 c# ソース コード。</span><span class="sxs-lookup"><span data-stu-id="4010c-126">Assembly information C# source code.</span></span>|  
|<span data-ttu-id="4010c-127">CBuildArray.bmp</span><span class="sxs-lookup"><span data-stu-id="4010c-127">CBuildArray.bmp</span></span>|<span data-ttu-id="4010c-128">ツールボックス ビットマップ。</span><span class="sxs-lookup"><span data-stu-id="4010c-128">Toolbox bitmap.</span></span>|  
|<span data-ttu-id="4010c-129">CConcat.bmp</span><span class="sxs-lookup"><span data-stu-id="4010c-129">CConcat.bmp</span></span>|<span data-ttu-id="4010c-130">ツールボックス ビットマップ。</span><span class="sxs-lookup"><span data-stu-id="4010c-130">Toolbox bitmap.</span></span>|  
|<span data-ttu-id="4010c-131">CExtractArray.bmp</span><span class="sxs-lookup"><span data-stu-id="4010c-131">CExtractArray.bmp</span></span>|<span data-ttu-id="4010c-132">ツールボックス ビットマップ。</span><span class="sxs-lookup"><span data-stu-id="4010c-132">Toolbox bitmap.</span></span>|  
|<span data-ttu-id="4010c-133">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="4010c-133">Cleanup.bat</span></span>|<span data-ttu-id="4010c-134">アセンブリを展開解除し、グローバル アセンブリ キャッシュ (GAC) から削除し、CustomFunctoid.dll を削除するために使用します。</span><span class="sxs-lookup"><span data-stu-id="4010c-134">Used to undeploy assemblies and remove them from the global assembly cache (GAC) and to delete CustomFunctoid.dll.</span></span>|  
|<span data-ttu-id="4010c-135">CLongestString.bmp</span><span class="sxs-lookup"><span data-stu-id="4010c-135">CLongestString.bmp</span></span>|<span data-ttu-id="4010c-136">ツールボックス ビットマップ。</span><span class="sxs-lookup"><span data-stu-id="4010c-136">Toolbox bitmap.</span></span>|  
|<span data-ttu-id="4010c-137">CMultiply.bmp</span><span class="sxs-lookup"><span data-stu-id="4010c-137">CMultiply.bmp</span></span>|<span data-ttu-id="4010c-138">ツールボックス ビットマップ。</span><span class="sxs-lookup"><span data-stu-id="4010c-138">Toolbox bitmap.</span></span>|  
|<span data-ttu-id="4010c-139">CustomFunctoid.cs</span><span class="sxs-lookup"><span data-stu-id="4010c-139">CustomFunctoid.cs</span></span>|<span data-ttu-id="4010c-140">カスタム functoid c# ソース コードです。</span><span class="sxs-lookup"><span data-stu-id="4010c-140">Custom functoid C# source code.</span></span>|  
|<span data-ttu-id="4010c-141">CustomFunctoid.csproj</span><span class="sxs-lookup"><span data-stu-id="4010c-141">CustomFunctoid.csproj</span></span>|<span data-ttu-id="4010c-142">カスタム functoid c# プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="4010c-142">Custom functoid C# project.</span></span>|  
|<span data-ttu-id="4010c-143">CustomFunctoid.sln</span><span class="sxs-lookup"><span data-stu-id="4010c-143">CustomFunctoid.sln</span></span>|<span data-ttu-id="4010c-144">カスタム functoid ソリューション。</span><span class="sxs-lookup"><span data-stu-id="4010c-144">Custom functoid solution.</span></span>|  
|<span data-ttu-id="4010c-145">CustomFunctoidResources.resx</span><span class="sxs-lookup"><span data-stu-id="4010c-145">CustomFunctoidResources.resx</span></span>|<span data-ttu-id="4010c-146">カスタム functoid リソース。</span><span class="sxs-lookup"><span data-stu-id="4010c-146">Custom functoid resources.</span></span>|  
|<span data-ttu-id="4010c-147">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="4010c-147">Setup.bat</span></span>|<span data-ttu-id="4010c-148">ビルド、配置、およびサンプルを開始するために使用します。</span><span class="sxs-lookup"><span data-stu-id="4010c-148">Used to build, deploy, and start the sample.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="4010c-149">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="4010c-149">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="4010c-150">次の手順を使用して、ビルドして、カスタム Functoid サンプルを初期化します。</span><span class="sxs-lookup"><span data-stu-id="4010c-150">Use the following procedure to build and initialize the Custom Functoid sample.</span></span>  
  
#### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="4010c-151">このサンプルを作成および初期化するには</span><span class="sxs-lookup"><span data-stu-id="4010c-151">To build and initialize this sample</span></span>  
  
1.  <span data-ttu-id="4010c-152">コマンド ウィンドウでディレクトリ変更 (**cd**) 次のフォルダーに。</span><span class="sxs-lookup"><span data-stu-id="4010c-152">In a command window, change directory (**cd**) to the following folder:</span></span>  
  
     <span data-ttu-id="4010c-153">\<*パスのサンプル*\>\XmlTools\CustomFunctoid</span><span class="sxs-lookup"><span data-stu-id="4010c-153">\<*Samples Path*\>\XmlTools\CustomFunctoid</span></span>  
  
2.  <span data-ttu-id="4010c-154">ファイルは、次の操作を実行します。 Setup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="4010c-154">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="4010c-155">サンプル プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="4010c-155">Builds the sample project.</span></span>  
  
    -   <span data-ttu-id="4010c-156">生成されたアセンブリを Developer tools \mapper Extensions ディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="4010c-156">Copies the generated assembly to the Developer Tools\Mapper Extensions directory.</span></span>  
  
    -   <span data-ttu-id="4010c-157">生成されたアセンブリを GAC に追加します。</span><span class="sxs-lookup"><span data-stu-id="4010c-157">Adds the generated assembly to the GAC.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="4010c-158">エラーが報告されていないこと、ビルドおよび初期化プロセス中にこのサンプルを実行する前に確認してください。</span><span class="sxs-lookup"><span data-stu-id="4010c-158">You should confirm that no errors were reported during the build and initialization process before attempting to run this sample.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="4010c-159">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="4010c-159">Running This Sample</span></span>  
 <span data-ttu-id="4010c-160">カスタム Functoid サンプルを実行するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="4010c-160">Use the following procedure to run the Custom Functoid sample.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="4010c-161">このサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="4010c-161">To run this sample</span></span>  
  
1. <span data-ttu-id="4010c-162">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクトでは、をクリックして、**ツール**メニューを選択し、 **ツールボックス アイテムの**します。</span><span class="sxs-lookup"><span data-stu-id="4010c-162">From a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, click the **Tools** menu, and select **Choose Toolbox Items**.</span></span>  
  
2. <span data-ttu-id="4010c-163">**ツールボックス アイテムの選択**ダイアログ ボックスで、 **BizTalk マッパー Functoid**タブ。</span><span class="sxs-lookup"><span data-stu-id="4010c-163">In the **Choose Toolbox items** dialog box, select the **BizTalk Mapper Functoids** tab.</span></span>  
  
3. <span data-ttu-id="4010c-164">クリックして**リセット**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="4010c-164">Click **Reset**, and then click **OK**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="4010c-165">カスタム functoid でインライン コードが公開されない場合は、そのアセンブリを GAC に利用可能になってを確認します。</span><span class="sxs-lookup"><span data-stu-id="4010c-165">If your custom functoid does not expose any inline code, make sure its assembly is made available in the GAC.</span></span>  
  
4. <span data-ttu-id="4010c-166">**ファイル**メニューの **終了**を閉じる[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="4010c-166">From the **File** menu, select **Exit** to close [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
5. <span data-ttu-id="4010c-167">開始**Visual Studio コマンド プロンプト**します。</span><span class="sxs-lookup"><span data-stu-id="4010c-167">Start **Visual Studio Command Prompt**.</span></span>  
  
6. <span data-ttu-id="4010c-168">コマンド プロンプトで「 **devenv/setup**します。</span><span class="sxs-lookup"><span data-stu-id="4010c-168">At the command prompt, type **devenv /setup**.</span></span>  
  
7. <span data-ttu-id="4010c-169">開始**Microsoft Visual Studio**します。</span><span class="sxs-lookup"><span data-stu-id="4010c-169">Start **Microsoft Visual Studio**.</span></span>  
  
    <span data-ttu-id="4010c-170">カスタム functoid (カスタム累積連結 functoid、最長文字列、配列作成 functoid、および配列抽出 functoid) が表示、**文字列 Functoid**ツールボックス、および累積乗算 functoid のタブを表示、 **累積 Functoid**タブ。</span><span class="sxs-lookup"><span data-stu-id="4010c-170">The custom functoids (Custom concatenate functoid, Longest String, Build array functoid, and Extract array functoid) appear on the **String Functoids** tab of the Toolbox, and the Cumulative Multiply functoid appears on the **Cumulative Functoids** tab.</span></span>  
  
## <a name="removing-this-sample"></a><span data-ttu-id="4010c-171">このサンプルの削除</span><span class="sxs-lookup"><span data-stu-id="4010c-171">Removing This Sample</span></span>  
 <span data-ttu-id="4010c-172">カスタム Functoid サンプルを削除するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="4010c-172">Use the following procedure to remove the Custom Functoid sample.</span></span>  
  
#### <a name="to-remove-this-sample"></a><span data-ttu-id="4010c-173">このサンプルを削除するには</span><span class="sxs-lookup"><span data-stu-id="4010c-173">To remove this sample</span></span>  
  
1. <span data-ttu-id="4010c-174">Functoid を削除、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックスです。</span><span class="sxs-lookup"><span data-stu-id="4010c-174">Remove the functoids from the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox.</span></span>  
  
   > [!WARNING]
   >  <span data-ttu-id="4010c-175">Cleanup.bat を実行した後は、まだ古いカスタム functoid を (おそらく内部キャッシュのため Visual Studio によって)、ツールボックスを表示、以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="4010c-175">If after running Cleanup.bat, you still see the stale custom functoids in the toolbox (probably due to internal caching by Visual Studio), then follow the procedures below:</span></span>  
  
   1. <span data-ttu-id="4010c-176">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクトでは、をクリックして、**ツール**メニューを選択し、 **ツールボックス アイテムの**します。</span><span class="sxs-lookup"><span data-stu-id="4010c-176">From a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, click the **Tools** menu, and select **Choose Toolbox Items**.</span></span>  
  
   2. <span data-ttu-id="4010c-177">**ツールボックス アイテムの選択**ダイアログ ボックスで、 **BizTalk マッパー Functoid**タブ。</span><span class="sxs-lookup"><span data-stu-id="4010c-177">In the **Choose Toolbox items** dialog box, select the **BizTalk Mapper Functoids** tab.</span></span>  
  
   3. <span data-ttu-id="4010c-178">リスト内のカスタム functoid (カスタム累積連結 functoid、最長文字列、配列作成 functoid、配列抽出 functoid、および累積乗算) を検索します。</span><span class="sxs-lookup"><span data-stu-id="4010c-178">Find the custom functoids (Custom concatenate functoid, Longest String, Build array functoid, Extract array functoid, and Cumulative Multiply) in the list.</span></span> <span data-ttu-id="4010c-179">それぞれクリックして**チェック ボックスをオン**をクリックして、functoid を削除 **[ok]** します。</span><span class="sxs-lookup"><span data-stu-id="4010c-179">Click the respective **check box** to remove the functoids, and then click **OK**.</span></span>  
  
      <span data-ttu-id="4010c-180">上記の手順が機能しない場合は、次の手順の下。</span><span class="sxs-lookup"><span data-stu-id="4010c-180">If the above procedure does not work, follow the below procedure.</span></span>  
  
   4. <span data-ttu-id="4010c-181">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクトでは、をクリックして、**ツールボックス**ツールボックス パレットを表示するマップの編集中のタブ。</span><span class="sxs-lookup"><span data-stu-id="4010c-181">From the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, click the **Toolbox** tab while editing a map to bring up the Toolbox Palette.</span></span>  
  
   5. <span data-ttu-id="4010c-182">ツール ボックスを右クリックして**アイテムの選択**します。</span><span class="sxs-lookup"><span data-stu-id="4010c-182">Right-click the tool box and select **Choose Items**.</span></span>  
  
   6. <span data-ttu-id="4010c-183">[アイテムの選択] ダイアログ ボックスで、**リセット**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="4010c-183">In the Choose Items dialog box, click **Reset**, and then click **OK**.</span></span>  
  
   7. <span data-ttu-id="4010c-184">インスタンスをすべて閉じます[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="4010c-184">Close all instances of [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
      <span data-ttu-id="4010c-185">上記の手順が機能しない場合は、次の手順の下。</span><span class="sxs-lookup"><span data-stu-id="4010c-185">If the above procedure does not work, follow the below procedure.</span></span>  
  
   8. <span data-ttu-id="4010c-186">開始**Visual Studio コマンド プロンプト**に管理者として。</span><span class="sxs-lookup"><span data-stu-id="4010c-186">Start **Visual Studio Command Prompt** as an administrator.</span></span>  
  
   9. <span data-ttu-id="4010c-187">Visual Studio の実行中のすべてのインスタンスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="4010c-187">Close all the running instances of Visual Studio.</span></span>  
  
   10. <span data-ttu-id="4010c-188">次のコマンドを提供します。</span><span class="sxs-lookup"><span data-stu-id="4010c-188">Give the following commands:</span></span>  
  
        `devenv /resetsettings`  
  
        `devenv /setup`  
  
   11. <span data-ttu-id="4010c-189">ツールボックスから不要な functoid を手動で選択することができます。</span><span class="sxs-lookup"><span data-stu-id="4010c-189">You can manually select the unwanted functoids from the toolbox.</span></span> <span data-ttu-id="4010c-190">次に、functoid を右クリックし、クリックして**削除**します。</span><span class="sxs-lookup"><span data-stu-id="4010c-190">Then, right click the functoid, and click **Delete**.</span></span>  
  
       <span data-ttu-id="4010c-191">上記の手順が機能しない場合は、次の手順の下。</span><span class="sxs-lookup"><span data-stu-id="4010c-191">If the above procedure does not work, follow the below procedure.</span></span>  
  
   12. <span data-ttu-id="4010c-192">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクトで、ツールボックス パレットを表示するマップの編集中に、[ツールボックス] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4010c-192">From a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, click the Toolbox tab while editing a map to bring up the Toolbox Palette.</span></span>  
  
   13. <span data-ttu-id="4010c-193">をクリックして、**累積 Functoid**グループ。</span><span class="sxs-lookup"><span data-stu-id="4010c-193">Click the **Cumulative Functoids** group.</span></span>  
  
   14. <span data-ttu-id="4010c-194">クリックして削除する functoid を右クリックして**削除**または del キーを押します。</span><span class="sxs-lookup"><span data-stu-id="4010c-194">Right click the functoid you want to remove and then choose **Delete** or press the delete key.</span></span>  
  
   15. <span data-ttu-id="4010c-195">をクリックして、**文字列 Functoid**グループ。</span><span class="sxs-lookup"><span data-stu-id="4010c-195">Click the **String Functoids** group.</span></span>  
  
   16. <span data-ttu-id="4010c-196">クリックして削除する functoid を右クリックして**削除**または del キーを押します。</span><span class="sxs-lookup"><span data-stu-id="4010c-196">Right click the functoid you want to remove and then choose **Delete** or press the delete key.</span></span>  
  
2. <span data-ttu-id="4010c-197">コマンド ウィンドウでディレクトリ変更 (**cd**) 次のフォルダーに。</span><span class="sxs-lookup"><span data-stu-id="4010c-197">In a command window, change directory (**cd**) to the following folder:</span></span>  
  
    <span data-ttu-id="4010c-198">\<*パスのサンプル*\>\XmlTools\CustomFunctoid</span><span class="sxs-lookup"><span data-stu-id="4010c-198">\<*Samples Path*\>\XmlTools\CustomFunctoid</span></span>  
  
3. <span data-ttu-id="4010c-199">Cleanup.bat は、次の操作を実行するファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="4010c-199">Run the file Cleanup.bat, which performs the following actions:</span></span>  
  
   -   <span data-ttu-id="4010c-200">Developer tools \mapper Extensions ディレクトリからアセンブリを削除します。</span><span class="sxs-lookup"><span data-stu-id="4010c-200">Deletes the assembly from the Developer Tools\Mapper Extensions directory.</span></span>  
  
   -   <span data-ttu-id="4010c-201">GAC からアセンブリを削除します。</span><span class="sxs-lookup"><span data-stu-id="4010c-201">Removes the assembly from the GAC.</span></span>  
  
## <a name="classes-or-methods-used-in-this-sample"></a><span data-ttu-id="4010c-202">クラスまたはメソッドのこのサンプルで使用</span><span class="sxs-lookup"><span data-stu-id="4010c-202">Classes or Methods Used in This Sample</span></span>  
 [<span data-ttu-id="4010c-203">Microsoft.BizTalk.BaseFunctoids.BaseFunctoid</span><span class="sxs-lookup"><span data-stu-id="4010c-203">Microsoft.BizTalk.BaseFunctoids.BaseFunctoid</span></span>](http://msdn.microsoft.com/library/microsoft.biztalk.basefunctoids.basefunctoid.aspx)  
  
## <a name="see-also"></a><span data-ttu-id="4010c-204">参照</span><span class="sxs-lookup"><span data-stu-id="4010c-204">See Also</span></span>  
 <span data-ttu-id="4010c-205">[BaseFunctoid の使用](../core/using-basefunctoid.md) </span><span class="sxs-lookup"><span data-stu-id="4010c-205">[Using BaseFunctoid](../core/using-basefunctoid.md) </span></span>  
 [<span data-ttu-id="4010c-206">XML ツール (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="4010c-206">XML Tools (BizTalk Server Samples Folder)</span></span>](../core/xml-tools-biztalk-server-samples-folder.md)