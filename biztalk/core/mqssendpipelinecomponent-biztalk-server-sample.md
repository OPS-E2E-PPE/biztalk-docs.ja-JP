---
title: MQSSendPipelineComponent (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, MQSeries adapters
- pipelines, examples
- MQSeries adapters, examples
- examples, pipelines
ms.assetid: ac709e45-524b-45ab-9673-060790ecbed2
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3416b4a1ba58a1262e9ff27e3558a2532c839cd4
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752344"
---
# <a name="mqssendpipelinecomponent-biztalk-server-sample"></a><span data-ttu-id="973f2-102">MQSSendPipelineComponent (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="973f2-102">MQSSendPipelineComponent (BizTalk Server Sample)</span></span>
<span data-ttu-id="973f2-103">このサンプルでは、一連の MQSeries プロパティ値を XML ファイルから読み取って、メッセージに適用する、パイプライン コンポーネントの作成方法を示します。</span><span class="sxs-lookup"><span data-stu-id="973f2-103">This sample demonstrates how to write a pipeline component that reads a set of MQSeries property values from an XML file and applies them to a message.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="973f2-104">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="973f2-104">What This Sample Does</span></span>  
 <span data-ttu-id="973f2-105">このサンプルは、パイプライン コンポーネント プロジェクトおよびパイプライン コンポーネントを利用するパイプライン プロジェクトの 2 つの [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] プロジェクトで構成されています。</span><span class="sxs-lookup"><span data-stu-id="973f2-105">This sample is composed of two [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] projects, a pipeline component project and a pipeline project that makes use of the pipeline component.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="973f2-106">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="973f2-106">Where to Find This Sample</span></span>  
  
- <span data-ttu-id="973f2-107">*\<SamplesPath\>* \AdaptersUsage\MQSeriesAdapter\MQSSendPipelineComponent\SetMQSeriesHeaderPropertyComponent</span><span class="sxs-lookup"><span data-stu-id="973f2-107">*\<SamplesPath\>* \AdaptersUsage\MQSeriesAdapter\MQSSendPipelineComponent\SetMQSeriesHeaderPropertyComponent</span></span>  
  
- <span data-ttu-id="973f2-108">*\<SamplesPath\>* \AdaptersUsage\MQSeriesAdapter\MQSSendPipelineComponent\SetMQSeriesHeaderPropertyPipeline</span><span class="sxs-lookup"><span data-stu-id="973f2-108">*\<SamplesPath\>* \AdaptersUsage\MQSeriesAdapter\MQSSendPipelineComponent\SetMQSeriesHeaderPropertyPipeline</span></span>  
  
  <span data-ttu-id="973f2-109">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="973f2-109">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|                                                                              <span data-ttu-id="973f2-110">**[最近使ったファイル]**</span><span class="sxs-lookup"><span data-stu-id="973f2-110">**File**</span></span>                                                                               |                                         <span data-ttu-id="973f2-111">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="973f2-111">**Description**</span></span>                                          |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------|
| <span data-ttu-id="973f2-112">SetMQSeriesHeaderPropertyComponent\SetMQSeriesHeaderPropertyComponent.sln、</span><span class="sxs-lookup"><span data-stu-id="973f2-112">SetMQSeriesHeaderPropertyComponent\SetMQSeriesHeaderPropertyComponent.sln,</span></span><br /><br /> <span data-ttu-id="973f2-113">SetMQSeriesHeaderPropertyComponent\SetMQSeriesHeaderPropertyComponent.csproj</span><span class="sxs-lookup"><span data-stu-id="973f2-113">SetMQSeriesHeaderPropertyComponent\SetMQSeriesHeaderPropertyComponent.csproj</span></span> |                    <span data-ttu-id="973f2-114">パイプライン コンポーネントのプロジェクト ファイルとソリューション ファイルです。</span><span class="sxs-lookup"><span data-stu-id="973f2-114">The project and solution files for the pipeline component.</span></span>                    |
|                                              <span data-ttu-id="973f2-115">SetMQSeriesHeaderPropertyComponent\CSetMQSeriesHeaderPropertyComponent.cs</span><span class="sxs-lookup"><span data-stu-id="973f2-115">SetMQSeriesHeaderPropertyComponent\CSetMQSeriesHeaderPropertyComponent.cs</span></span>                                              |                      <span data-ttu-id="973f2-116">パイプライン コンポーネントの Visual C#® ソース ファイルです。</span><span class="sxs-lookup"><span data-stu-id="973f2-116">The Visual C#® source file for the pipeline component.</span></span>                      |
|                                                      <span data-ttu-id="973f2-117">SetMQSeriesHeaderPropertyComponent\SetMQSMQMDHdrProps.xml</span><span class="sxs-lookup"><span data-stu-id="973f2-117">SetMQSeriesHeaderPropertyComponent\SetMQSMQMDHdrProps.xml</span></span>                                                      |                 <span data-ttu-id="973f2-118">パイプライン コンポーネントによって読み取られ、使用される MQSeries プロパティです。</span><span class="sxs-lookup"><span data-stu-id="973f2-118">The MQSeries properties read and used by the pipeline component.</span></span>                 |
|   <span data-ttu-id="973f2-119">SetMQSeriesHeaderPropertyPipeline\SetMQSeriesHeaderPropertyPipeline.btproj、</span><span class="sxs-lookup"><span data-stu-id="973f2-119">SetMQSeriesHeaderPropertyPipeline\SetMQSeriesHeaderPropertyPipeline.btproj,</span></span><br /><br /> <span data-ttu-id="973f2-120">SetMQSeriesHeaderPropertyPipeline\SetMQSeriesHeaderPropertyPipeline.sln</span><span class="sxs-lookup"><span data-stu-id="973f2-120">SetMQSeriesHeaderPropertyPipeline\SetMQSeriesHeaderPropertyPipeline.sln</span></span>   |                     <span data-ttu-id="973f2-121">BizTalk パイプラインのプロジェクト ファイルとソリューション ファイルです。</span><span class="sxs-lookup"><span data-stu-id="973f2-121">The project and solution files for the BizTalk pipeline.</span></span>                     |
|                                               <span data-ttu-id="973f2-122">SetMQSeriesHeaderPropertyPipeline\SetMQSeriesHeaderPropertyPipeline.snk</span><span class="sxs-lookup"><span data-stu-id="973f2-122">SetMQSeriesHeaderPropertyPipeline\SetMQSeriesHeaderPropertyPipeline.snk</span></span>                                               |                   <span data-ttu-id="973f2-123">BizTalk パイプライン プロジェクトの厳密な名前のキー ファイルです。</span><span class="sxs-lookup"><span data-stu-id="973f2-123">The strong naming key file for the BizTalk pipeline project.</span></span>                   |
|                                               <span data-ttu-id="973f2-124">SetMQSeriesHeaderPropertyPipeline\SetMQSeriesHeaderPropertyPipeline.btp</span><span class="sxs-lookup"><span data-stu-id="973f2-124">SetMQSeriesHeaderPropertyPipeline\SetMQSeriesHeaderPropertyPipeline.btp</span></span>                                               | <span data-ttu-id="973f2-125">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] パイプラインです。</span><span class="sxs-lookup"><span data-stu-id="973f2-125">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] pipeline.</span></span> |
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="973f2-126">このサンプルの使用方法</span><span class="sxs-lookup"><span data-stu-id="973f2-126">How to Use This Sample</span></span>  
 <span data-ttu-id="973f2-127">アプリケーションを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="973f2-127">To create the application, you must complete the following steps:</span></span>  
  
1. <span data-ttu-id="973f2-128">アプリケーション用のフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="973f2-128">Create the folders for the application.</span></span>  
  
2. <span data-ttu-id="973f2-129">パイプライン コンポーネント用に [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] プロジェクトを変更してコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="973f2-129">Modify and compile the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] project for the pipeline component.</span></span>  
  
3. <span data-ttu-id="973f2-130">コンパイルしたアセンブリとヘッダー ファイルを適切なフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="973f2-130">Copy the compiled assembly and the header file to the appropriate folders.</span></span>  
  
4. <span data-ttu-id="973f2-131">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] パイプライン用に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロジェクトを変更します。</span><span class="sxs-lookup"><span data-stu-id="973f2-131">Modify the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] project for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] pipeline.</span></span>  
  
5. <span data-ttu-id="973f2-132">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] パイプライン プロジェクトをコンパイルして展開します。</span><span class="sxs-lookup"><span data-stu-id="973f2-132">Compile and deploy the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] pipeline project.</span></span>  
  
6. <span data-ttu-id="973f2-133">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の受信場所を設定します。</span><span class="sxs-lookup"><span data-stu-id="973f2-133">Set up a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location.</span></span>  
  
7. <span data-ttu-id="973f2-134">MQSeries キューを作成します。</span><span class="sxs-lookup"><span data-stu-id="973f2-134">Create a MQSeries queue.</span></span>  
  
8. <span data-ttu-id="973f2-135">送信ポートを設定します。</span><span class="sxs-lookup"><span data-stu-id="973f2-135">Set up a send port.</span></span>  
  
9. <span data-ttu-id="973f2-136">受信場所を有効にして送信ポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="973f2-136">Enable the receive location and start the send port.</span></span>  
  
## <a name="creating-the-folders-for-the-application"></a><span data-ttu-id="973f2-137">アプリケーション用のフォルダーの作成</span><span class="sxs-lookup"><span data-stu-id="973f2-137">Creating the Folders for the Application</span></span>  
 <span data-ttu-id="973f2-138">この手順では、アプリケーション用の適切なフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="973f2-138">This procedure creates the appropriate folders for the application.</span></span>  
  
#### <a name="to-create-the-folders-for-the-application"></a><span data-ttu-id="973f2-139">アプリケーション用のフォルダーを作成するには</span><span class="sxs-lookup"><span data-stu-id="973f2-139">To create the folders for the application</span></span>  
  
1.  <span data-ttu-id="973f2-140">という名前のフォルダーを作成する**temp** C:\ ドライブが既に存在しない場合にします。</span><span class="sxs-lookup"><span data-stu-id="973f2-140">Create a folder named **temp** on your C:\ drive if it does not already exist.</span></span>  
  
2.  <span data-ttu-id="973f2-141">下のフォルダーを作成、 **C:\temp**という名前のディレクトリ**Pickup3**します。</span><span class="sxs-lookup"><span data-stu-id="973f2-141">Create a folder under the **C:\temp** directory named **Pickup3**.</span></span>  
  
## <a name="modifying-and-compiling-the-project-for-the-pipeline-component"></a><span data-ttu-id="973f2-142">パイプライン コンポーネント用のプロジェクトの変更とコンパイル</span><span class="sxs-lookup"><span data-stu-id="973f2-142">Modifying and Compiling the Project for the Pipeline Component</span></span>  
 <span data-ttu-id="973f2-143">この手順では、パイプライン コンポーネント用に [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] プロジェクトを変更してコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="973f2-143">This procedure modifies and compiles the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] project for the pipeline component.</span></span>  
  
#### <a name="to-modify-and-compile-the-project-for-the-pipeline-component"></a><span data-ttu-id="973f2-144">パイプライン コンポーネント用にプロジェクトを変更およびコンパイルするには</span><span class="sxs-lookup"><span data-stu-id="973f2-144">To modify and compile the project for the pipeline component</span></span>  
  
1. <span data-ttu-id="973f2-145">ソリューション ファイルをダブルクリックして **\setmqseriesheaderpropertycomponent.sln** でソリューションを開く[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="973f2-145">Double-click the solution file, **SetMQSeriesHeaderPropertyComponent\SetMQSeriesHeaderPropertyComponent.sln** to open the solution in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
2. <span data-ttu-id="973f2-146">クラス ファイルをダブルクリックして **CSetMQSeriesHeaderPropertyComponent.cs** でクラス ファイルを開く[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="973f2-146">Double-click the class file **CSetMQSeriesHeaderPropertyComponent.cs** to open the class file in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
3. <span data-ttu-id="973f2-147">変数を見つけて**samplesDir**、場所にこの変数が設定されていることを確認**C:\temp**します。</span><span class="sxs-lookup"><span data-stu-id="973f2-147">Locate the variable **samplesDir**, verify that this variable is set to the location **C:\temp**.</span></span>  
  
4. <span data-ttu-id="973f2-148">ソリューション エクスプ ローラーでソリューションを右クリックし、をクリックして**ビルド**します。</span><span class="sxs-lookup"><span data-stu-id="973f2-148">Right-click the solution in the Solution Explorer and click **Build**.</span></span> <span data-ttu-id="973f2-149">これは、dll 内にある、プロジェクトのコンパイル、 **SetMQSeriesHeaderPropertyComponent\SetMQSeriesHeaderPropertyComponent\bin\Debug\\** ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="973f2-149">This will compile the project into a dll located in the **SetMQSeriesHeaderPropertyComponent\SetMQSeriesHeaderPropertyComponent\bin\Debug\\** directory.</span></span>  
  
## <a name="copying-the-assembly-and-header-file-to-appropriate-folders"></a><span data-ttu-id="973f2-150">適切なフォルダーへのアセンブリとヘッダー ファイルのコピー</span><span class="sxs-lookup"><span data-stu-id="973f2-150">Copying the Assembly and Header File to Appropriate Folders</span></span>  
 <span data-ttu-id="973f2-151">この手順では、コンパイルしたアセンブリとヘッダー ファイルを適切なフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="973f2-151">This procedure copies the compiled assembly and the header file to the appropriate folders.</span></span>  
  
#### <a name="to-copy-the-compiled-assembly-and-header-file-to-the-appropriate-folders"></a><span data-ttu-id="973f2-152">コンパイルしたアセンブリとヘッダー ファイルを適切なフォルダーにコピーするには</span><span class="sxs-lookup"><span data-stu-id="973f2-152">To copy the compiled assembly and header file to the appropriate folders</span></span>  
  
1. <span data-ttu-id="973f2-153">コンパイル済みのアセンブリをコピー **SetMQSeriesHeaderPropertyComponent.dll** BizTalk パイプライン コンポーネント フォルダーにします。</span><span class="sxs-lookup"><span data-stu-id="973f2-153">Copy the compiled assembly **SetMQSeriesHeaderPropertyComponent.dll** to the BizTalk pipeline components folder.</span></span> <span data-ttu-id="973f2-154">BizTalk パイプライン コンポーネント フォルダーの既定の場所は [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Pipeline Components です。</span><span class="sxs-lookup"><span data-stu-id="973f2-154">The default location for the BizTalk pipeline components folder is [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Pipeline Components.</span></span>  
  
2. <span data-ttu-id="973f2-155">MQHeader プロパティ ファイルをコピー **SetMQSMQMDHdrProps.xml**を**C:\temp**ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="973f2-155">Copy the MQHeader properties file **SetMQSMQMDHdrProps.xml** to the **C:\temp** directory.</span></span>  
  
## <a name="modifying-the-project-for-the-biztalk-server-pipeline"></a><span data-ttu-id="973f2-156">BizTalk Server パイプライン用のプロジェクトの変更</span><span class="sxs-lookup"><span data-stu-id="973f2-156">Modifying the Project for the BizTalk Server Pipeline</span></span>  
 <span data-ttu-id="973f2-157">この手順では、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] パイプライン用に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロジェクトを変更します。</span><span class="sxs-lookup"><span data-stu-id="973f2-157">This procedure modifies the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] project for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] pipeline.</span></span>  
  
#### <a name="to-modify-the-project-for-the-biztalk-server-pipeline"></a><span data-ttu-id="973f2-158">BizTalk Server パイプライン用にプロジェクトを変更するには</span><span class="sxs-lookup"><span data-stu-id="973f2-158">To modify the project for the BizTalk Server pipeline</span></span>  
  
1. <span data-ttu-id="973f2-159">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、ソリューション ファイルをダブルクリックしてソリューションを開いて **\setmqseriesheaderpropertypipeline.sln** します。</span><span class="sxs-lookup"><span data-stu-id="973f2-159">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution by double-clicking the solution file, **SetMQSeriesHeaderPropertyPipeline\SetMQSeriesHeaderPropertyPipeline.sln**.</span></span>  
  
2. <span data-ttu-id="973f2-160">プロジェクトの厳密な名前キー ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="973f2-160">Create a strong name key file for the project.</span></span> <span data-ttu-id="973f2-161">この操作を行うには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="973f2-161">To do that, do the following:</span></span>  
  
   1. <span data-ttu-id="973f2-162">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="973f2-162">Open a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Command prompt.</span></span>  
  
   2. <span data-ttu-id="973f2-163">ディレクトリに移動\<サンプル パス\>\AdaptersUsage\MQSeriesAdapter\MQSSendPipelineComponent します。</span><span class="sxs-lookup"><span data-stu-id="973f2-163">Change directories to \<SamplesPath\>\AdaptersUsage\MQSeriesAdapter\MQSSendPipelineComponent.</span></span>  
  
   3. <span data-ttu-id="973f2-164">次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="973f2-164">Type the following:</span></span>  
  
       `sn -k MQSSendPipelineComponent.snk`  
  
   4. <span data-ttu-id="973f2-165">Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="973f2-165">Press ENTER.</span></span> <span data-ttu-id="973f2-166">これにより、キー ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="973f2-166">This will create the key file.</span></span>  
  
3. <span data-ttu-id="973f2-167">**ソリューション エクスプ ローラー**プロジェクトを右クリックし、クリックして、**プロパティ**プロジェクト デザイナー (中央のウィンドウ) でプロジェクトを起動します。</span><span class="sxs-lookup"><span data-stu-id="973f2-167">In **Solution Explorer**, right-click the project and click **Properties** to launch Project Designer for the project (in the center window).</span></span>  
  
   1.  <span data-ttu-id="973f2-168">プロジェクト デザイナーで、クリックして**署名**タブ。</span><span class="sxs-lookup"><span data-stu-id="973f2-168">In the Project Designer, click **Signing** tab.</span></span>  
  
   2.  <span data-ttu-id="973f2-169">右側のウィンドウで、選択、**アセンブリに署名**オプション.</span><span class="sxs-lookup"><span data-stu-id="973f2-169">In the right-hand pane, select the **Sign the assembly** option..</span></span>  
  
   3.  <span data-ttu-id="973f2-170">ドロップダウン リストをクリックして、**厳密な名前キー ファイルを選択して** をクリックし、**参照**します。</span><span class="sxs-lookup"><span data-stu-id="973f2-170">Click drop-down list for the **Choose a strong name key file** option, and click **Browse**.</span></span>  
  
   4.  <span data-ttu-id="973f2-171">参照する\<サンプル パス\>\AdaptersUsage\MQSeriesAdapter\MQSSendPipelineComponent\MQSSendPipelineComponent.snk、 をクリックして**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="973f2-171">Browse to \<SamplesPath\>\AdaptersUsage\MQSeriesAdapter\MQSSendPipelineComponent\MQSSendPipelineComponent.snk, click **Open**.</span></span>  
  
4. <span data-ttu-id="973f2-172">先ほど作成したパイプライン コンポーネントに既に追加されて、**プリアセンブル**このパイプライン プロジェクトのステージ。</span><span class="sxs-lookup"><span data-stu-id="973f2-172">The pipeline component that you created earlier is already added to the **Pre-Assemble** stage of this pipeline project.</span></span> <span data-ttu-id="973f2-173">このコンポーネントがまだ追加されていない場合は、次の手順に従って追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="973f2-173">If this component was not already added you would need to complete the following steps to add it:</span></span>  
  
   1. <span data-ttu-id="973f2-174">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] IDE、クリックして、**ツールボックス**左側にあるタブ。</span><span class="sxs-lookup"><span data-stu-id="973f2-174">In the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] IDE, click the **Toolbox** tab on the left side.</span></span>  
  
   2. <span data-ttu-id="973f2-175">右クリックし、**ツールボックス**、 をクリック**アイテムの選択**します。</span><span class="sxs-lookup"><span data-stu-id="973f2-175">Right-click the **Toolbox**, and click **Choose Items**.</span></span>  
  
   3. <span data-ttu-id="973f2-176">**ツールボックス アイテムの選択**ダイアログ ボックスで、をクリックして、 **BizTalk パイプライン コンポーネント**] タブで、[、 **MQseries ヘッダー プロパティを設定するカスタム コンポーネント**コンポーネント、およびクリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="973f2-176">In the **Choose Toolbox Items** dialog box, click the **BizTalk Pipeline Components** tab, select the **Custom Component to Set MQseries header properties**component, and then click **OK**.</span></span>  
  
   4. <span data-ttu-id="973f2-177">ドラッグ、 **MQseries ヘッダー プロパティを設定するカスタム コンポーネント**コンポーネントを**プリアセンブル**このパイプラインのステージ。</span><span class="sxs-lookup"><span data-stu-id="973f2-177">Drag the **Custom Component to Set MQseries header properties**component to the **Pre-Assemble** stage of this pipeline.</span></span>  
  
## <a name="compiling-and-deploying-the-pipeline-project"></a><span data-ttu-id="973f2-178">パイプライン プロジェクトのコンパイルと展開</span><span class="sxs-lookup"><span data-stu-id="973f2-178">Compiling and Deploying the Pipeline Project</span></span>  
 <span data-ttu-id="973f2-179">この手順では、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] パイプライン プロジェクトをコンパイルして展開します。</span><span class="sxs-lookup"><span data-stu-id="973f2-179">This procedure compiles and deploys the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] pipeline project.</span></span>  
  
#### <a name="to-compile-and-deploy-the-pipeline-project"></a><span data-ttu-id="973f2-180">パイプライン プロジェクトをコンパイルおよび展開するには</span><span class="sxs-lookup"><span data-stu-id="973f2-180">To compile and deploy the pipeline project</span></span>  
  
1.  <span data-ttu-id="973f2-181">ソリューション エクスプ ローラー ウィンドウで、ソリューションを右クリックし をクリックし、**ソリューションの配置**します。</span><span class="sxs-lookup"><span data-stu-id="973f2-181">In the Solution Explorer window, right-click the solution, and then click **Deploy Solution**.</span></span> <span data-ttu-id="973f2-182">これにより、ソリューションがビルドされ、アセンブリが BizTalk 管理データベースに展開されます。</span><span class="sxs-lookup"><span data-stu-id="973f2-182">This builds the solution and deploys the assembly to the BizTalk Management database.</span></span>  
  
2.  <span data-ttu-id="973f2-183">次の手順に従って、アセンブリが BizTalk 管理データベースに展開されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="973f2-183">Verify the Assembly was deployed to the BizTalk Management database:</span></span>  
  
    1.  <span data-ttu-id="973f2-184">BizTalk 管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="973f2-184">Open the BizTalk Administration Console.</span></span>  
  
    2.  <span data-ttu-id="973f2-185">クリックして展開**BizTalk グループ [\<servername\>:\<管理データベース\>]** をクリックして展開し、**アセンブリ**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="973f2-185">Click to expand **BizTalk Group [\<servername\>:\<management database\>]**, and then click to expand the **Assemblies** folder.</span></span>  
  
         <span data-ttu-id="973f2-186">展開されたパイプライン アセンブリを下に表示されますが、**アセンブリ**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="973f2-186">The deployed pipeline assembly should be visible under the **Assemblies** folder.</span></span>  
  
## <a name="creating-the-receive-location"></a><span data-ttu-id="973f2-187">作成、受信場所</span><span class="sxs-lookup"><span data-stu-id="973f2-187">Creating the Receive Location</span></span>  
 <span data-ttu-id="973f2-188">この手順では、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の受信場所を作成します。</span><span class="sxs-lookup"><span data-stu-id="973f2-188">This procedure creates a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location.</span></span>  
  
#### <a name="to-create-the-receive-location"></a><span data-ttu-id="973f2-189">受信場所を作成するには</span><span class="sxs-lookup"><span data-stu-id="973f2-189">To create the receive location</span></span>  
  
1.  <span data-ttu-id="973f2-190">右クリックし、BizTalk Server 管理コンソールで**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート**。</span><span class="sxs-lookup"><span data-stu-id="973f2-190">In the BizTalk Server Administration Console, right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
2.  <span data-ttu-id="973f2-191">**一方向受信ポートのプロパティ** ダイアログ ボックスで、**名前**ボックスに「MQReply」を入力し、 をクリック**OK**します。</span><span class="sxs-lookup"><span data-stu-id="973f2-191">In the **One-way Receive Port Properties** dialog box, in the **Name** box type "MQReply" and click **OK**.</span></span>  
  
3.  <span data-ttu-id="973f2-192">左側のウィンドウで次のようにクリックします。**受信場所**タブをクリックし、[] をクリックし、**新規**します。</span><span class="sxs-lookup"><span data-stu-id="973f2-192">In the left pane, click **Receive Locations** tab, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="973f2-193">**受信場所のプロパティ** ダイアログ ボックスで、**名前**フィールドに「receivefile」と入力します。</span><span class="sxs-lookup"><span data-stu-id="973f2-193">In the **Receive Location Properties** dialog box, in the **Name** field, type "ReceiveFile".</span></span>  
  
5.  <span data-ttu-id="973f2-194">**トランスポートの種類**ボックスで、**ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="973f2-194">In the **Transport Type** box, select **FILE**.</span></span>  
  
6.  <span data-ttu-id="973f2-195">**受信ハンドラー**フィールドで、 **BizTalkServerApplication**します。</span><span class="sxs-lookup"><span data-stu-id="973f2-195">In the **Receive Handler** field, select **BizTalkServerApplication**.</span></span>  
  
7.  <span data-ttu-id="973f2-196">**受信パイプライン**フィールドで、 **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**します。</span><span class="sxs-lookup"><span data-stu-id="973f2-196">In the **Receive pipeline** field, select **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**.</span></span>  
  
8.  <span data-ttu-id="973f2-197">**受信フォルダー**フィールドに、"C:\temp\Pickup3"を入力します。</span><span class="sxs-lookup"><span data-stu-id="973f2-197">In the **Receive folder** field, type "C:\temp\Pickup3".</span></span>  
  
9. <span data-ttu-id="973f2-198">**ファイル マスク**フィールドに「"\*.\*"。</span><span class="sxs-lookup"><span data-stu-id="973f2-198">In the **File mask** field, type "\*.\*".</span></span>  
  
10. <span data-ttu-id="973f2-199">をクリックして**OK**、順にクリックします**OK**を終了するには、もう一度、**受信場所のプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="973f2-199">Click **OK**, and then click **OK** again to exit the **Receive Location Properties** dialog box.</span></span>  
  
## <a name="creating-a-mqseries-queue-through-the-mqseries-explorer"></a><span data-ttu-id="973f2-200">MQSeries エクスプローラーを使用した MQSeries キューの作成</span><span class="sxs-lookup"><span data-stu-id="973f2-200">Creating a MQSeries Queue Through the MQSeries Explorer</span></span>  
 <span data-ttu-id="973f2-201">MQSeries Server for Windows のインストールに必要なアクセス許可があればは、アダプターのダイアログ ボックスを使用して MQSeries キューを作成し、この次の手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="973f2-201">If you have the required permissions to the MQSeries Server for Windows installation, you can create the MQSeries queue through the adapter dialog boxes, and can skip this next procedure.</span></span>  
  
 <span data-ttu-id="973f2-202">このようなアクセス許可を持っていない場合は、次の手順に従って、IBM WebSphere MQ エクスプローラーを使用してキューを作成できます。</span><span class="sxs-lookup"><span data-stu-id="973f2-202">If you do not have such access, you can use the following procedure to create the queue using the IBM WebSphere MQ Explorer.</span></span>  
  
#### <a name="to-create-a-mqseries-queue-through-the-mqseries-explorer"></a><span data-ttu-id="973f2-203">MQSeries エクスプローラーを使用して MQSeries キューを作成するには</span><span class="sxs-lookup"><span data-stu-id="973f2-203">To create a MQSeries queue through the MQSeries Explorer</span></span>  
  
1.  <span data-ttu-id="973f2-204">クリックして**開始**、 をポイント**プログラム**、 をポイント**IBM WebSphere MQ**、順にクリックします**WebSphere MQ エクスプ ローラー**します。</span><span class="sxs-lookup"><span data-stu-id="973f2-204">Click **Start**, point to **Programs**, point to **IBM WebSphere MQ**, and then click **WebSphere MQ Explorer**.</span></span>  
  
2.  <span data-ttu-id="973f2-205">ダブルクリック**キュー マネージャー**、し、既定のキュー マネージャーをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="973f2-205">Double-click **Queue Managers**, and then double-click the default queue manager.</span></span> <span data-ttu-id="973f2-206">通常、既定のキュー マネージャーの名前**qm _**\<*machine_name* \>場所*machine_name*コンピューターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="973f2-206">The default queue manager is typically named **QM_**\<*machine_name*\> where *machine_name* is the name of your computer.</span></span>  
  
3.  <span data-ttu-id="973f2-207">右クリック**キュー**、 をポイント**新規**、 をクリックし、**ローカル キュー**します。</span><span class="sxs-lookup"><span data-stu-id="973f2-207">Right-click **Queues**, point to **New**, and then click **Local Queue**.</span></span>  
  
4.  <span data-ttu-id="973f2-208">**ローカル キューの作成** ダイアログ ボックスで**キュー名**、型**SETHEADER**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="973f2-208">In **Create Local Queue** dialog box, in **Queue Name**, type **SETHEADER**, and then click **OK**.</span></span>  
  
## <a name="creating-the-send-port-and-mqseries-queue"></a><span data-ttu-id="973f2-209">送信ポートと MQSeries キューの作成</span><span class="sxs-lookup"><span data-stu-id="973f2-209">Creating the Send Port and MQSeries Queue</span></span>  
 <span data-ttu-id="973f2-210">この手順では、出力メッセージ用の送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="973f2-210">This procedure creates the send port for the output message.</span></span> <span data-ttu-id="973f2-211">MQSeries キューは、送信ポートがまだ作成されていない場合に送信ポートを作成したときにも作成されます。</span><span class="sxs-lookup"><span data-stu-id="973f2-211">The MQSeries queue is also created when you create the send port if you have not already created it.</span></span>  
  
#### <a name="to-create-the-send-port-and-mqseries-queue"></a><span data-ttu-id="973f2-212">送信ポートと MQSeries キューを作成するには</span><span class="sxs-lookup"><span data-stu-id="973f2-212">To create the send port and MQSeries queue</span></span>  
  
1.  <span data-ttu-id="973f2-213">右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的な一方向送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="973f2-213">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="973f2-214">**送信ポートのプロパティ** ダイアログ ボックスで、**名前**ボックスに「mqsolicitresponse」.</span><span class="sxs-lookup"><span data-stu-id="973f2-214">In the **Send Port Properties** dialog box, in the **Name** box, type "MQSolicitResponse".</span></span>  
  
3.  <span data-ttu-id="973f2-215">**トランスポートの種類**ボックスで、 **MQSeries**します。</span><span class="sxs-lookup"><span data-stu-id="973f2-215">In the **Transport Type** box, select **MQSeries**.</span></span>  
  
4.  <span data-ttu-id="973f2-216">**送信パイプライン**ボックスで、 **SetMQSeriesHeaderPropertyPipeline.SetMQSeriesHeadersSendPipeline**します。</span><span class="sxs-lookup"><span data-stu-id="973f2-216">In the **Send pipeline** box, select **SetMQSeriesHeaderPropertyPipeline.SetMQSeriesHeadersSendPipeline**.</span></span>  
  
5.  <span data-ttu-id="973f2-217">**フィルター**、次の名前/値ペアを持つ新しいエントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="973f2-217">In **Filters**, add a new entry with the following name/value pairs:</span></span>  
  
    -   <span data-ttu-id="973f2-218">設定**プロパティ**に"BTS します。ReceivePortName"。</span><span class="sxs-lookup"><span data-stu-id="973f2-218">Set **Property** to "BTS.ReceivePortName".</span></span>  
  
    -   <span data-ttu-id="973f2-219">設定**演算子**「= =」にします。</span><span class="sxs-lookup"><span data-stu-id="973f2-219">Set **Operator** to "==".</span></span>  
  
    -   <span data-ttu-id="973f2-220">設定**値**を"ReceiveFile"。</span><span class="sxs-lookup"><span data-stu-id="973f2-220">Set **Value** to "ReceiveFile".</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="973f2-221">これにより、ReceiveFile 受信ポートで受信したメッセージをサブスクライブするように送信ポートが設定されます。</span><span class="sxs-lookup"><span data-stu-id="973f2-221">This sets the send port to subscribe to messages that arrive on the ReceiveFile receive port.</span></span>  
  
6.  <span data-ttu-id="973f2-222">クリックして**トランスポート**します。</span><span class="sxs-lookup"><span data-stu-id="973f2-222">Click **Transport**.</span></span>  
  
7.  <span data-ttu-id="973f2-223">**アドレス (URI)** フィールドで省略記号 (...) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="973f2-223">In the **Address (URI)** field, click the ellipsis (…) button.</span></span>  
  
8.  <span data-ttu-id="973f2-224">**MQSeries トランスポートのプロパティ** ダイアログ ボックスで、**キュー定義**フィールドで省略記号 (...) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="973f2-224">In the **MQSeries Transport Properties** dialog box, in the **Queue Definition** field, click the ellipsis (…) button.</span></span>  
  
9. <span data-ttu-id="973f2-225">**キュー定義** ダイアログ ボックスで、**サーバー名**フィールドに、コンピューター名を入力します。</span><span class="sxs-lookup"><span data-stu-id="973f2-225">In the **Queue Definition** dialog box, in the **Server Name** field, type your computer name.</span></span>  
  
10. <span data-ttu-id="973f2-226">**キュー マネージャー**フィールドで、既定のキュー マネージャーを選択します。</span><span class="sxs-lookup"><span data-stu-id="973f2-226">In the **Queue Manager** field, select the default queue manager.</span></span>  
  
11. <span data-ttu-id="973f2-227">キュー フィールドに「SETHEADER」を入力し、、クリックして**エクスポート**します。</span><span class="sxs-lookup"><span data-stu-id="973f2-227">In the Queue field, type "SETHEADER", and then click **Export**.</span></span>  
  
12. <span data-ttu-id="973f2-228">**エクスポート**ダイアログ ボックスで、 をクリックして**キューの作成**、順にクリックします**ok**または**完了**すべてのダイアログを終了します。</span><span class="sxs-lookup"><span data-stu-id="973f2-228">In the **Export** dialog box, click **Create Queue**, and then click **OK** or **Done** until you have exited all dialog.</span></span>  
  
## <a name="enabling-the-receive-location-and-starting-the-send-port"></a><span data-ttu-id="973f2-229">受信場所の有効化と送信ポートの開始</span><span class="sxs-lookup"><span data-stu-id="973f2-229">Enabling the Receive Location and Starting the Send Port</span></span>  
 <span data-ttu-id="973f2-230">この手順では、受信場所を有効化し、送信ポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="973f2-230">This procedure enables the receive location and start the send port.</span></span>  
  
#### <a name="to-enable-the-receive-location-and-start-the-send-port"></a><span data-ttu-id="973f2-231">受信場所を有効にして送信ポートを開始するには</span><span class="sxs-lookup"><span data-stu-id="973f2-231">To enable the receive location and start the send port</span></span>  
  
1.  <span data-ttu-id="973f2-232">BizTalk Server 管理コンソールで、次のようにクリックします。**受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="973f2-232">In the BizTalk Server Administration console, click **Receive Ports**.</span></span>  
  
2.  <span data-ttu-id="973f2-233">詳細ペインで右クリックし、 **MQIn**受信場所とクリックして**を有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="973f2-233">In the details pane, right-click the **MQIn** receive location and click **Enable**.</span></span>  
  
3.  <span data-ttu-id="973f2-234">詳細ペインで右クリックし、 **SetMQHeader**送信ポートをクリックします**開始**します。</span><span class="sxs-lookup"><span data-stu-id="973f2-234">In the details pane, right-click the **SetMQHeader** send port and click **Start**.</span></span>  
  
## <a name="testing-the-application"></a><span data-ttu-id="973f2-235">アプリケーションのテスト</span><span class="sxs-lookup"><span data-stu-id="973f2-235">Testing the Application</span></span>  
 <span data-ttu-id="973f2-236">この手順では、アプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="973f2-236">This procedure tests the application.</span></span>  
  
#### <a name="to-test-the-application"></a><span data-ttu-id="973f2-237">アプリケーションをテストするには</span><span class="sxs-lookup"><span data-stu-id="973f2-237">To test the application</span></span>  
  
1.  <span data-ttu-id="973f2-238">ファイルを配置、 **C:\Temp\Pickup3**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="973f2-238">Put a file into the **C:\Temp\Pickup3** folder.</span></span>  
  
2.  <span data-ttu-id="973f2-239">WebSphere MQ エクスプローラーを起動し、SETHEADER キューをダブルクリックして、SETHEADER キュー内のメッセージを検証します。</span><span class="sxs-lookup"><span data-stu-id="973f2-239">Launch the WebSphere MQ Explorer and double-click the SETHEADER queue to examine the message(s) in the SETHEADER queue.</span></span>  
  
     <span data-ttu-id="973f2-240">SETHEADER キュー内のメッセージのすべてのコンテキスト プロパティを表示するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="973f2-240">To see all of the context properties for the messages in the SETHEADER queue, complete the following steps:</span></span>  
  
    1.  <span data-ttu-id="973f2-241">ダブルクリックして、 **SETHEADER**を表示するキュー、 **Message Browser**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="973f2-241">Double-click the **SETHEADER** queue to display the **Message Browser** dialog box.</span></span>  
  
    2.  <span data-ttu-id="973f2-242">**Message Browser**ダイアログ ボックスで、をクリックして**列**を表示する、**のメッセージの表示/非表示列** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="973f2-242">In the **Message Browser** dialog box, click **Columns** to display the **Show/Hide Columns for Messages** dialog box.</span></span>  
  
    3.  <span data-ttu-id="973f2-243">**使用可能な列**で表示されるようにするには、各エントリをダブルクリックして、 **Message Browser**クリックしてダイアログ ボックスで、 **ok**します。</span><span class="sxs-lookup"><span data-stu-id="973f2-243">Under **Available Columns**, double-click each entry to make it visible in the **Message Browser** dialog box, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="973f2-244">各メッセージのメッセージ コンテキスト プロパティで表示するか、 **Message Browser**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="973f2-244">The message context properties for each message should be visible in the **Message Browser** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="973f2-245">参照</span><span class="sxs-lookup"><span data-stu-id="973f2-245">See Also</span></span>  
 [<span data-ttu-id="973f2-246">MQSeries アダプタ サンプル</span><span class="sxs-lookup"><span data-stu-id="973f2-246">MQSeries Adapter Samples</span></span>](../core/mqseries-adapter-samples.md)