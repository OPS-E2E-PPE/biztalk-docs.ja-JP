---
title: カスタム パーティの解決 (BizTalk Server サンプル) |Microsoft Docs
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
ms.openlocfilehash: 066d551cc2d802778673492de5de352fbcd48fa9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353351"
---
# <a name="custom-party-resolution-biztalk-server-sample"></a><span data-ttu-id="5a90d-102">カスタム パーティの解決 (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="5a90d-102">Custom Party Resolution (BizTalk Server Sample)</span></span>
<span data-ttu-id="5a90d-103">カスタム パーティの解決サンプルでは、カスタム パーティを解決するカスタム パイプライン コンポーネントを記述する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5a90d-103">The Custom Party Resolution sample demonstrates how to write a custom pipeline component to resolve a custom party.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="5a90d-104">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="5a90d-104">What This Sample Does</span></span>  
 <span data-ttu-id="5a90d-105">カスタム パーティの解決サンプルでは、次の一連の手順を使用してタスクを実現します。</span><span class="sxs-lookup"><span data-stu-id="5a90d-105">The Custom Party Resolution sample accomplishes its task using the following sequence of steps:</span></span>  
  
1.  <span data-ttu-id="5a90d-106">XML ドキュメントは、フォルダーから取得されます。</span><span class="sxs-lookup"><span data-stu-id="5a90d-106">An XML document is retrieved from a folder.</span></span>  
  
2.  <span data-ttu-id="5a90d-107">パイプラインは、パーティを解決します。</span><span class="sxs-lookup"><span data-stu-id="5a90d-107">The pipeline resolves the party.</span></span>  
  
3.  <span data-ttu-id="5a90d-108">XML メッセージは、フォルダーに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="5a90d-108">The XML message is written to a folder.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="5a90d-109">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="5a90d-109">Where to Find This Sample</span></span>  
 <span data-ttu-id="5a90d-110">*\<サンプル パス >* \Pipelines\CustomPartyResolution\\</span><span class="sxs-lookup"><span data-stu-id="5a90d-110">*\<Samples Path>* \Pipelines\CustomPartyResolution\\</span></span>  
  
 <span data-ttu-id="5a90d-111">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="5a90d-111">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="5a90d-112">ファイル</span><span class="sxs-lookup"><span data-stu-id="5a90d-112">File(s)</span></span>|<span data-ttu-id="5a90d-113">説明</span><span class="sxs-lookup"><span data-stu-id="5a90d-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5a90d-114">AssemblyInfo.cs</span><span class="sxs-lookup"><span data-stu-id="5a90d-114">AssemblyInfo.cs</span></span>|<span data-ttu-id="5a90d-115">アセンブリ情報C#ソース ファイル。</span><span class="sxs-lookup"><span data-stu-id="5a90d-115">Assembly information C# source file.</span></span>|  
|<span data-ttu-id="5a90d-116">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="5a90d-116">Cleanup.bat</span></span>|<span data-ttu-id="5a90d-117">クリーンアップ バッチ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="5a90d-117">Cleanup batch file.</span></span>|  
|<span data-ttu-id="5a90d-118">CustomPartyResolution.sln</span><span class="sxs-lookup"><span data-stu-id="5a90d-118">CustomPartyResolution.sln</span></span>|<span data-ttu-id="5a90d-119">ソリューション ファイルです。</span><span class="sxs-lookup"><span data-stu-id="5a90d-119">Solution file.</span></span>|  
|<span data-ttu-id="5a90d-120">CustomPartyResolutionBinding.xml</span><span class="sxs-lookup"><span data-stu-id="5a90d-120">CustomPartyResolutionBinding.xml</span></span>|<span data-ttu-id="5a90d-121">バインド ファイルです。</span><span class="sxs-lookup"><span data-stu-id="5a90d-121">Binding file.</span></span>|  
|<span data-ttu-id="5a90d-122">CustomPartyResolutionPipeline.btp</span><span class="sxs-lookup"><span data-stu-id="5a90d-122">CustomPartyResolutionPipeline.btp</span></span>|<span data-ttu-id="5a90d-123">パイプライン ファイルです。</span><span class="sxs-lookup"><span data-stu-id="5a90d-123">Pipeline file.</span></span>|  
|<span data-ttu-id="5a90d-124">CustomPartyResolutionPipeline.btproj</span><span class="sxs-lookup"><span data-stu-id="5a90d-124">CustomPartyResolutionPipeline.btproj</span></span>|<span data-ttu-id="5a90d-125">パイプライン プロジェクト ファイルです。</span><span class="sxs-lookup"><span data-stu-id="5a90d-125">Pipeline project file.</span></span>|  
|<span data-ttu-id="5a90d-126">CustomPartyResolutionPipelineComponent.cs</span><span class="sxs-lookup"><span data-stu-id="5a90d-126">CustomPartyResolutionPipelineComponent.cs</span></span>|<span data-ttu-id="5a90d-127">パイプライン コンポーネントC#ソース コード。</span><span class="sxs-lookup"><span data-stu-id="5a90d-127">Pipeline component C# source code.</span></span>|  
|<span data-ttu-id="5a90d-128">CustomPartyResolutionPipelineComponent.csproj</span><span class="sxs-lookup"><span data-stu-id="5a90d-128">CustomPartyResolutionPipelineComponent.csproj</span></span>|<span data-ttu-id="5a90d-129">パイプライン コンポーネント Visual Studio プロジェクト ファイルです。</span><span class="sxs-lookup"><span data-stu-id="5a90d-129">Pipeline component Visual Studio project file.</span></span>|  
|<span data-ttu-id="5a90d-130">InboundDocumentSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="5a90d-130">InboundDocumentSchema.xsd</span></span>|<span data-ttu-id="5a90d-131">受信ドキュメント スキーマです。</span><span class="sxs-lookup"><span data-stu-id="5a90d-131">Inbound document schema.</span></span>|  
|<span data-ttu-id="5a90d-132">PartyResolutionStream.cs</span><span class="sxs-lookup"><span data-stu-id="5a90d-132">PartyResolutionStream.cs</span></span>|<span data-ttu-id="5a90d-133">パーティの解決ストリームC#ソース コード。</span><span class="sxs-lookup"><span data-stu-id="5a90d-133">Party resolution stream C# source code.</span></span>|  
|<span data-ttu-id="5a90d-134">RoutingPropertySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="5a90d-134">RoutingPropertySchema.xsd</span></span>|<span data-ttu-id="5a90d-135">ルーティング プロパティ スキーマ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="5a90d-135">Routing property schema file.</span></span>|  
|<span data-ttu-id="5a90d-136">SampleInboundDocumentSchema.xml</span><span class="sxs-lookup"><span data-stu-id="5a90d-136">SampleInboundDocumentSchema.xml</span></span>|<span data-ttu-id="5a90d-137">受信ドキュメント スキーマ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="5a90d-137">Inbound document schema file.</span></span>|  
|<span data-ttu-id="5a90d-138">SampleInboundDocumentSchema_Party1.xml</span><span class="sxs-lookup"><span data-stu-id="5a90d-138">SampleInboundDocumentSchema_Party1.xml</span></span>|<span data-ttu-id="5a90d-139">サンプル データのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="5a90d-139">Sample data instance.</span></span>|  
|<span data-ttu-id="5a90d-140">SampleInboundDocumentSchema_Party2.xml</span><span class="sxs-lookup"><span data-stu-id="5a90d-140">SampleInboundDocumentSchema_Party2.xml</span></span>|<span data-ttu-id="5a90d-141">サンプル データのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="5a90d-141">Sample data instance.</span></span>|  
|<span data-ttu-id="5a90d-142">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="5a90d-142">Setup.bat</span></span>|<span data-ttu-id="5a90d-143">ビルドおよび設定のサンプル パイプライン コンポーネント バッチ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="5a90d-143">Build and setup sample pipeline component batch file.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="5a90d-144">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="5a90d-144">Building and Initializing This Sample</span></span>  
  
#### <a name="to-build-and-initialize-the-custom-party-resolution-sample"></a><span data-ttu-id="5a90d-145">ビルドして、カスタム パーティの解決サンプルの初期化</span><span class="sxs-lookup"><span data-stu-id="5a90d-145">To build and initialize the Custom Party Resolution sample</span></span>  
  
1.  <span data-ttu-id="5a90d-146">コマンド ウィンドウでディレクトリ変更 (**cd**) 次のフォルダーに。</span><span class="sxs-lookup"><span data-stu-id="5a90d-146">In a command window, change directory (**cd**) to the following folder:</span></span>  
  
     <span data-ttu-id="5a90d-147">*\<サンプル パス >* \Pipelines\CustomPartyResolution\\</span><span class="sxs-lookup"><span data-stu-id="5a90d-147">*\<Samples Path>* \Pipelines\CustomPartyResolution\\</span></span>  
  
2.  <span data-ttu-id="5a90d-148">次の操作を実行する、Setup.bat ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="5a90d-148">Run the file Setup.bat, which will perform the following actions:</span></span>  
  
    -   <span data-ttu-id="5a90d-149">このサンプルで使用される入力と出力ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="5a90d-149">Creates the input and output directories used in the sample.</span></span>  
  
    -   <span data-ttu-id="5a90d-150">新しいキー ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="5a90d-150">Generates a new key file.</span></span>  
  
    -   <span data-ttu-id="5a90d-151">ビルドし、カスタム パーティの解決パイプライン コンポーネントを展開します。</span><span class="sxs-lookup"><span data-stu-id="5a90d-151">Builds and deploys the Custom Party Resolution pipeline component.</span></span>  
  
    -   <span data-ttu-id="5a90d-152">ビルドしたパイプライン コンポーネントのコピー、 *\<インストール パス >* \Pipeline Components ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="5a90d-152">Copies the built pipeline component to the *\<Installation Path>* \Pipeline Components directory.</span></span>  
  
    -   <span data-ttu-id="5a90d-153">ポートと受信ポート、送信を作成します。</span><span class="sxs-lookup"><span data-stu-id="5a90d-153">Creates the send and receive ports.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5a90d-154">エラーが報告されていないこと、ビルドおよび初期化プロセス中にこのサンプルを実行する前に確認してください。</span><span class="sxs-lookup"><span data-stu-id="5a90d-154">You should confirm that no errors were reported during the build and initialization process before attempting to run this sample.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="5a90d-155">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="5a90d-155">Running This Sample</span></span>  
  
#### <a name="to-run-the-custom-party-resolution-sample"></a><span data-ttu-id="5a90d-156">カスタム パーティの解決サンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="5a90d-156">To run the Custom Party Resolution sample</span></span>  
  
1.  <span data-ttu-id="5a90d-157">ファイル SampleInboundDocumentSchema_Party1.xml または SampleInboundDocumentSchema_Party2.xml を \In フォルダにコピーします。</span><span class="sxs-lookup"><span data-stu-id="5a90d-157">Copy to file SampleInboundDocumentSchema_Party1.xml or SampleInboundDocumentSchema_Party2.xml to the \In folder.</span></span>  
  
2.  <span data-ttu-id="5a90d-158">結果が \Out フォルダにファイル名に表示されます*guid*.xml です。</span><span class="sxs-lookup"><span data-stu-id="5a90d-158">The results will appear in the \Out folder with the filename *guid*.xml.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a90d-159">参照</span><span class="sxs-lookup"><span data-stu-id="5a90d-159">See Also</span></span>  
 [<span data-ttu-id="5a90d-160">パイプライン (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="5a90d-160">Pipelines (BizTalk Server Samples Folder)</span></span>](../core/pipelines-biztalk-server-samples-folder.md)