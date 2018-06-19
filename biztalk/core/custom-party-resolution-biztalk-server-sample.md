---
title: カスタム パーティの解決 (BizTalk Server サンプル) |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, parties
- pipeline components [custom], examples
- pipeline components [custom], parties
- examples, pipeline components [custom]
- parties, pipeline components [custom]
- parties, custom
ms.assetid: 1f88450f-5fe9-486d-bfb8-fd11181c78b4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7b88d8126a1d63760888edbcd7691ad4bd76426
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238698"
---
# <a name="custom-party-resolution-biztalk-server-sample"></a><span data-ttu-id="f7c2b-102">カスタム パーティの解決 (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="f7c2b-102">Custom Party Resolution (BizTalk Server Sample)</span></span>
<span data-ttu-id="f7c2b-103">カスタム パーティの解決サンプルでは、カスタム パイプライン コンポーネントを作成し、カスタム パーティを解決する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f7c2b-103">The Custom Party Resolution sample demonstrates how to write a custom pipeline component to resolve a custom party.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="f7c2b-104">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="f7c2b-104">What This Sample Does</span></span>  
 <span data-ttu-id="f7c2b-105">カスタム パーティの解決サンプルでは、次の一連の手順を使用してタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="f7c2b-105">The Custom Party Resolution sample accomplishes its task using the following sequence of steps:</span></span>  
  
1.  <span data-ttu-id="f7c2b-106">XML ドキュメントがフォルダから取得されます。</span><span class="sxs-lookup"><span data-stu-id="f7c2b-106">An XML document is retrieved from a folder.</span></span>  
  
2.  <span data-ttu-id="f7c2b-107">パイプラインによりパーティが解決されます。</span><span class="sxs-lookup"><span data-stu-id="f7c2b-107">The pipeline resolves the party.</span></span>  
  
3.  <span data-ttu-id="f7c2b-108">XML メッセージがフォルダに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="f7c2b-108">The XML message is written to a folder.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="f7c2b-109">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="f7c2b-109">Where to Find This Sample</span></span>  
 <span data-ttu-id="f7c2b-110">*\<サンプル パス >* \Pipelines\CustomPartyResolution\\</span><span class="sxs-lookup"><span data-stu-id="f7c2b-110">*\<Samples Path>* \Pipelines\CustomPartyResolution\\</span></span>  
  
 <span data-ttu-id="f7c2b-111">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="f7c2b-111">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="f7c2b-112">ファイル</span><span class="sxs-lookup"><span data-stu-id="f7c2b-112">File(s)</span></span>|<span data-ttu-id="f7c2b-113">Description</span><span class="sxs-lookup"><span data-stu-id="f7c2b-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f7c2b-114">AssemblyInfo.cs</span><span class="sxs-lookup"><span data-stu-id="f7c2b-114">AssemblyInfo.cs</span></span>|<span data-ttu-id="f7c2b-115">C# ソース ファイルのアセンブリ情報です。</span><span class="sxs-lookup"><span data-stu-id="f7c2b-115">Assembly information C# source file.</span></span>|  
|<span data-ttu-id="f7c2b-116">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="f7c2b-116">Cleanup.bat</span></span>|<span data-ttu-id="f7c2b-117">クリーンアップ バッチ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="f7c2b-117">Cleanup batch file.</span></span>|  
|<span data-ttu-id="f7c2b-118">CustomPartyResolution.sln</span><span class="sxs-lookup"><span data-stu-id="f7c2b-118">CustomPartyResolution.sln</span></span>|<span data-ttu-id="f7c2b-119">ソリューション ファイルです。</span><span class="sxs-lookup"><span data-stu-id="f7c2b-119">Solution file.</span></span>|  
|<span data-ttu-id="f7c2b-120">CustomPartyResolutionBinding.xml</span><span class="sxs-lookup"><span data-stu-id="f7c2b-120">CustomPartyResolutionBinding.xml</span></span>|<span data-ttu-id="f7c2b-121">バインド ファイルです。</span><span class="sxs-lookup"><span data-stu-id="f7c2b-121">Binding file.</span></span>|  
|<span data-ttu-id="f7c2b-122">CustomPartyResolutionPipeline.btp</span><span class="sxs-lookup"><span data-stu-id="f7c2b-122">CustomPartyResolutionPipeline.btp</span></span>|<span data-ttu-id="f7c2b-123">パイプライン ファイルです。</span><span class="sxs-lookup"><span data-stu-id="f7c2b-123">Pipeline file.</span></span>|  
|<span data-ttu-id="f7c2b-124">CustomPartyResolutionPipeline.btproj</span><span class="sxs-lookup"><span data-stu-id="f7c2b-124">CustomPartyResolutionPipeline.btproj</span></span>|<span data-ttu-id="f7c2b-125">パイプライン プロジェクト ファイルです。</span><span class="sxs-lookup"><span data-stu-id="f7c2b-125">Pipeline project file.</span></span>|  
|<span data-ttu-id="f7c2b-126">CustomPartyResolutionPipelineComponent.cs</span><span class="sxs-lookup"><span data-stu-id="f7c2b-126">CustomPartyResolutionPipelineComponent.cs</span></span>|<span data-ttu-id="f7c2b-127">パイプライン コンポーネント C# ソース コードです。</span><span class="sxs-lookup"><span data-stu-id="f7c2b-127">Pipeline component C# source code.</span></span>|  
|<span data-ttu-id="f7c2b-128">CustomPartyResolutionPipelineComponent.csproj</span><span class="sxs-lookup"><span data-stu-id="f7c2b-128">CustomPartyResolutionPipelineComponent.csproj</span></span>|<span data-ttu-id="f7c2b-129">パイプライン コンポーネント Visual Studio プロジェクト ファイルです。</span><span class="sxs-lookup"><span data-stu-id="f7c2b-129">Pipeline component Visual Studio project file.</span></span>|  
|<span data-ttu-id="f7c2b-130">InboundDocumentSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="f7c2b-130">InboundDocumentSchema.xsd</span></span>|<span data-ttu-id="f7c2b-131">受信ドキュメント スキーマです。</span><span class="sxs-lookup"><span data-stu-id="f7c2b-131">Inbound document schema.</span></span>|  
|<span data-ttu-id="f7c2b-132">PartyResolutionStream.cs</span><span class="sxs-lookup"><span data-stu-id="f7c2b-132">PartyResolutionStream.cs</span></span>|<span data-ttu-id="f7c2b-133">パーティの解決ストリーム C# ソース コードです。</span><span class="sxs-lookup"><span data-stu-id="f7c2b-133">Party resolution stream C# source code.</span></span>|  
|<span data-ttu-id="f7c2b-134">RoutingPropertySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="f7c2b-134">RoutingPropertySchema.xsd</span></span>|<span data-ttu-id="f7c2b-135">ルーティング プロパティ スキーマ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="f7c2b-135">Routing property schema file.</span></span>|  
|<span data-ttu-id="f7c2b-136">SampleInboundDocumentSchema.xml</span><span class="sxs-lookup"><span data-stu-id="f7c2b-136">SampleInboundDocumentSchema.xml</span></span>|<span data-ttu-id="f7c2b-137">受信ドキュメント スキーマ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="f7c2b-137">Inbound document schema file.</span></span>|  
|<span data-ttu-id="f7c2b-138">SampleInboundDocumentSchema_Party1.xml</span><span class="sxs-lookup"><span data-stu-id="f7c2b-138">SampleInboundDocumentSchema_Party1.xml</span></span>|<span data-ttu-id="f7c2b-139">サンプル データ インスタンスです。</span><span class="sxs-lookup"><span data-stu-id="f7c2b-139">Sample data instance.</span></span>|  
|<span data-ttu-id="f7c2b-140">SampleInboundDocumentSchema_Party2.xml</span><span class="sxs-lookup"><span data-stu-id="f7c2b-140">SampleInboundDocumentSchema_Party2.xml</span></span>|<span data-ttu-id="f7c2b-141">サンプル データ インスタンスです。</span><span class="sxs-lookup"><span data-stu-id="f7c2b-141">Sample data instance.</span></span>|  
|<span data-ttu-id="f7c2b-142">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="f7c2b-142">Setup.bat</span></span>|<span data-ttu-id="f7c2b-143">サンプル パイプライン コンポーネント バッチ ファイルをビルドおよび設定します。</span><span class="sxs-lookup"><span data-stu-id="f7c2b-143">Build and setup sample pipeline component batch file.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="f7c2b-144">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="f7c2b-144">Building and Initializing This Sample</span></span>  
  
#### <a name="to-build-and-initialize-the-custom-party-resolution-sample"></a><span data-ttu-id="f7c2b-145">カスタム パーティの解決サンプルをビルドおよび初期化するには</span><span class="sxs-lookup"><span data-stu-id="f7c2b-145">To build and initialize the Custom Party Resolution sample</span></span>  
  
1.  <span data-ttu-id="f7c2b-146">コマンド ウィンドウでディレクトリ変更 (**cd**) 次のフォルダーに。</span><span class="sxs-lookup"><span data-stu-id="f7c2b-146">In a command window, change directory (**cd**) to the following folder:</span></span>  
  
     <span data-ttu-id="f7c2b-147">*\<サンプル パス >* \Pipelines\CustomPartyResolution\\</span><span class="sxs-lookup"><span data-stu-id="f7c2b-147">*\<Samples Path>* \Pipelines\CustomPartyResolution\\</span></span>  
  
2.  <span data-ttu-id="f7c2b-148">ファイル Setup.bat を実行します。処理内容は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f7c2b-148">Run the file Setup.bat, which will perform the following actions:</span></span>  
  
    -   <span data-ttu-id="f7c2b-149">サンプルで使用される入力ディレクトリと出力ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="f7c2b-149">Creates the input and output directories used in the sample.</span></span>  
  
    -   <span data-ttu-id="f7c2b-150">新しいキー ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="f7c2b-150">Generates a new key file.</span></span>  
  
    -   <span data-ttu-id="f7c2b-151">カスタム パーティの解決パイプライン コンポーネントをビルドおよび展開します。</span><span class="sxs-lookup"><span data-stu-id="f7c2b-151">Builds and deploys the Custom Party Resolution pipeline component.</span></span>  
  
    -   <span data-ttu-id="f7c2b-152">ビルドしたパイプライン コンポーネントへのコピー、 *\<インストール パス >* \Pipeline Components ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="f7c2b-152">Copies the built pipeline component to the *\<Installation Path>* \Pipeline Components directory.</span></span>  
  
    -   <span data-ttu-id="f7c2b-153">送信ポートおよび受信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="f7c2b-153">Creates the send and receive ports.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f7c2b-154">このサンプルを実行する前に、ビルド処理および初期化処理でエラーが報告されていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f7c2b-154">You should confirm that no errors were reported during the build and initialization process before attempting to run this sample.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="f7c2b-155">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="f7c2b-155">Running This Sample</span></span>  
  
#### <a name="to-run-the-custom-party-resolution-sample"></a><span data-ttu-id="f7c2b-156">カスタム パーティの解決サンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="f7c2b-156">To run the Custom Party Resolution sample</span></span>  
  
1.  <span data-ttu-id="f7c2b-157">ファイル SampleInboundDocumentSchema_Party1.xml または SampleInboundDocumentSchema_Party2.xml を \In フォルダにコピーします。</span><span class="sxs-lookup"><span data-stu-id="f7c2b-157">Copy to file SampleInboundDocumentSchema_Party1.xml or SampleInboundDocumentSchema_Party2.xml to the \In folder.</span></span>  
  
2.  <span data-ttu-id="f7c2b-158">その結果が \Out フォルダにファイル名で表示されます*guid*.xml です。</span><span class="sxs-lookup"><span data-stu-id="f7c2b-158">The results will appear in the \Out folder with the filename *guid*.xml.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7c2b-159">参照</span><span class="sxs-lookup"><span data-stu-id="f7c2b-159">See Also</span></span>  
 [<span data-ttu-id="f7c2b-160">パイプライン (BizTalk Server Samples フォルダ)</span><span class="sxs-lookup"><span data-stu-id="f7c2b-160">Pipelines (BizTalk Server Samples Folder)</span></span>](../core/pipelines-biztalk-server-samples-folder.md)