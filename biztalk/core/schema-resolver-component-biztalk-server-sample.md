---
title: "スキーマ リゾルバ コンポーネント (BizTalk Server サンプル) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Flat File Disassembler [pipeline component], examples
- examples, schemas
- schemas, examples
- examples, Flat File Disassembler [pipeline component]
ms.assetid: 9ef68988-c4ee-42d5-83b5-a5c978b2007d
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37ec562cbc64d15e66d2f265c52606817169bb85
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="schema-resolver-component-biztalk-server-sample"></a><span data-ttu-id="51731-102">スキーマ リゾルバ コンポーネント (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="51731-102">Schema Resolver Component (BizTalk Server Sample)</span></span>
<span data-ttu-id="51731-103">スキーマ リゾルバ コンポーネントのサンプルは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] フラット ファイル逆アセンブラ コンポーネントの機能を拡張する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="51731-103">The Schema Resolver Component sample demonstrates how to extend the functionality of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] flat file disassembler component.</span></span>  
  
 <span data-ttu-id="51731-104">フラット ファイル逆アセンブラ コンポーネントでは、通常デザイン時に解析スキーマを定義することが必要です。</span><span class="sxs-lookup"><span data-stu-id="51731-104">The flat file disassembler component normally requires you to define a parsing schema at design time.</span></span> <span data-ttu-id="51731-105">そのため、同じ受信場所で異なるフラット ファイル ドキュメントを受信する場合は、受信パイプラインに複数のフラット ファイル逆アセンブラ (つまりスキーマごとに 1 つのフラット ファイル逆アセンブラ) を含めます。</span><span class="sxs-lookup"><span data-stu-id="51731-105">So if you expect to receive different flat file documents on the same receive location, you typically include several flat file disassemblers in the receive pipeline, one for each schema.</span></span> <span data-ttu-id="51731-106">実行時に、パイプライン プローブ機能を使用して、適切な逆アセンブラ コンポーネントが選択されます。</span><span class="sxs-lookup"><span data-stu-id="51731-106">At run time, the correct disassembler component is selected using a pipeline probing mechanism.</span></span> <span data-ttu-id="51731-107">ただし、多数のフラット ファイル スキーマがある場合は、このアプローチのコストが高くなります。これは、対応するそれぞれの逆アセンブラ コンポーネントをプローブすることで、パイプラインのパフォーマンスが低下するためです。</span><span class="sxs-lookup"><span data-stu-id="51731-107">However, this approach is expensive if you have many flat file schemas because probing for every corresponding disassembler component degrades pipeline performance.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="51731-108">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="51731-108">What This Sample Does</span></span>  
 <span data-ttu-id="51731-109">スキーマ リゾルバ コンポーネントは、フラット ファイル逆アセンブラ コンポーネントのスキーマを選択する、もう 1 つの方法を示します。</span><span class="sxs-lookup"><span data-stu-id="51731-109">The Schema Resolver component demonstrates an alternative method of selecting the schema for a flat file disassembler.</span></span> <span data-ttu-id="51731-110">このサンプルでは、4 つのスキーマが定義されており、各スキーマのメッセージの最初の 2 文字は一意です。</span><span class="sxs-lookup"><span data-stu-id="51731-110">In this sample, four schemas are defined and the first two characters of a message for each schema are unique.</span></span> <span data-ttu-id="51731-111">一意である最初の 2 文字、および対応するスキーマの間でマッピングが定義されます。</span><span class="sxs-lookup"><span data-stu-id="51731-111">A mapping is defined between the unique first two characters and the corresponding schema.</span></span> <span data-ttu-id="51731-112">入力メッセージがスキーマ リゾルバ コンポーネントに提供されると、最初の 2 文字が読み取られ、対応するドキュメントに使用するスキーマが決定されて、メッセージ コンテキストでスキーマ情報が保存された後に、標準のフラット ファイル逆アセンブラ コンポーネントが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="51731-112">When the input message is given to the Schema Resolver component, it reads the first two characters, determines which schema to use for the corresponding document, saves the schema information on the message context, and then calls into the standard flat file disassembler component.</span></span> <span data-ttu-id="51731-113">標準フラット ファイル逆アセンブラ コンポーネントはメッセージ コンテキストからスキーマ情報を読み取り、そのスキーマを使用してドキュメントを解析します。</span><span class="sxs-lookup"><span data-stu-id="51731-113">The standard flat file disassembler component reads the schema information from the message context and uses that schema to parse the document.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="51731-114">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="51731-114">Where to Find This Sample</span></span>  
 <span data-ttu-id="51731-115">*\<サンプル パス >*\Pipelines\SchemaResolverComponent\\</span><span class="sxs-lookup"><span data-stu-id="51731-115">*\<Samples Path>*\Pipelines\SchemaResolverComponent\\</span></span>  
  
 <span data-ttu-id="51731-116">次の表は、このサンプルで使用したファイルを示し、その目的を説明しています。</span><span class="sxs-lookup"><span data-stu-id="51731-116">The following table shows the files used in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="51731-117">ファイル</span><span class="sxs-lookup"><span data-stu-id="51731-117">File(s)</span></span>|<span data-ttu-id="51731-118">Description</span><span class="sxs-lookup"><span data-stu-id="51731-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="51731-119">SchemaResolverSample.sln</span><span class="sxs-lookup"><span data-stu-id="51731-119">SchemaResolverSample.sln</span></span>|<span data-ttu-id="51731-120">カスタム パイプライン コンポーネントを実行する BizTalk プロジェクトのソリューション。</span><span class="sxs-lookup"><span data-stu-id="51731-120">Solution for the BizTalk project that exercises the custom pipeline component.</span></span>|  
|<span data-ttu-id="51731-121">SchemaResolverSample.btproj</span><span class="sxs-lookup"><span data-stu-id="51731-121">SchemaResolverSample.btproj</span></span>|<span data-ttu-id="51731-122">カスタム パイプライン コンポーネントを実行する BizTalk プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="51731-122">BizTalk project that exercises the custom pipeline component.</span></span>|  
|<span data-ttu-id="51731-123">SchemaResolverRP.btp</span><span class="sxs-lookup"><span data-stu-id="51731-123">SchemaResolverRP.btp</span></span>|<span data-ttu-id="51731-124">カスタム コンポーネントを含む受信パイプライン。</span><span class="sxs-lookup"><span data-stu-id="51731-124">Receive pipeline that contains the custom component.</span></span>|  
|<span data-ttu-id="51731-125">PurchaseOrder.xsd、PurchaseRequest.xsd、SalesOrder.xsd、SalesRequest.xsd</span><span class="sxs-lookup"><span data-stu-id="51731-125">PurchaseOrder.xsd, PurchaseRequest.xsd, SalesOrder.xsd, SalesRequest.xsd</span></span>|<span data-ttu-id="51731-126">フラット ファイル スキーマ。</span><span class="sxs-lookup"><span data-stu-id="51731-126">Flat file schemas.</span></span>|  
|<span data-ttu-id="51731-127">POInstance.txt、PRInstance.txt、SOInstance.txt、SRInstance.txt</span><span class="sxs-lookup"><span data-stu-id="51731-127">POInstance.txt, PRInstance.txt, SOInstance.txt, SRInstance.txt</span></span>|<span data-ttu-id="51731-128">対応するフラット ファイル ドキュメント インスタンス。</span><span class="sxs-lookup"><span data-stu-id="51731-128">Corresponding flat file document instances.</span></span>|  
|<span data-ttu-id="51731-129">SchemaResolverFlatFileDasm.sln</span><span class="sxs-lookup"><span data-stu-id="51731-129">SchemaResolverFlatFileDasm.sln</span></span>|<span data-ttu-id="51731-130">パイプライン コンポーネントの実装のソリューション。</span><span class="sxs-lookup"><span data-stu-id="51731-130">Solution for the implementation of the pipeline component.</span></span>|  
|<span data-ttu-id="51731-131">SchemaResolverFlatFileDasm.csproj</span><span class="sxs-lookup"><span data-stu-id="51731-131">SchemaResolverFlatFileDasm.csproj</span></span>|<span data-ttu-id="51731-132">パイプライン コンポーネントの実装の C# プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="51731-132">C# project for the implementation of the pipeline component.</span></span>|  
|<span data-ttu-id="51731-133">SchemaResolverFlatFileDasmComp.cs</span><span class="sxs-lookup"><span data-stu-id="51731-133">SchemaResolverFlatFileDasmComp.cs</span></span>|<span data-ttu-id="51731-134">パイプライン コンポーネントの実装。</span><span class="sxs-lookup"><span data-stu-id="51731-134">Implementation of the pipeline component.</span></span>|  
|<span data-ttu-id="51731-135">SeekableReadOnlyStream.cs</span><span class="sxs-lookup"><span data-stu-id="51731-135">SeekableReadOnlyStream.cs</span></span>|<span data-ttu-id="51731-136">コンポーネントで使用するシーク可能な読み取り専用ストリームの実装。</span><span class="sxs-lookup"><span data-stu-id="51731-136">Implementation of the seekable read-only stream used by component.</span></span>|  
|<span data-ttu-id="51731-137">VirtualStream.cs</span><span class="sxs-lookup"><span data-stu-id="51731-137">VirtualStream.cs</span></span>|<span data-ttu-id="51731-138">パイプライン コンポーネントで使用する仮想ストリームの実装。</span><span class="sxs-lookup"><span data-stu-id="51731-138">Implementation of the virtual stream used by pipeline component.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="51731-139">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="51731-139">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="51731-140">次の手順を使用して、スキーマ リゾルバ コンポーネント サンプルをビルドおよび初期化します。</span><span class="sxs-lookup"><span data-stu-id="51731-140">Use the following procedure to build and initialize the Schema Resolver Component sample.</span></span>  
  
#### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="51731-141">このサンプルを作成および初期化するには</span><span class="sxs-lookup"><span data-stu-id="51731-141">To build and initialize this sample</span></span>  
  
1.  <span data-ttu-id="51731-142">コマンド ウィンドウで、ディレクトリを次のフォルダに変更します (cd)。</span><span class="sxs-lookup"><span data-stu-id="51731-142">In a command window, change directory (cd) to the following folder:</span></span>  
  
     <span data-ttu-id="51731-143">*\<サンプル パス >*\Pipelines\SchemaResolverComponent</span><span class="sxs-lookup"><span data-stu-id="51731-143">*\<Samples Path>*\Pipelines\SchemaResolverComponent</span></span>  
  
2.  <span data-ttu-id="51731-144">次の操作を実行する Setup.bat ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="51731-144">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="51731-145">コンポーネントをビルドします。</span><span class="sxs-lookup"><span data-stu-id="51731-145">Builds the component.</span></span>  
  
    -   <span data-ttu-id="51731-146">コンポーネント アセンブリを BizTalk \Pipeline \Pipeline components フォルダにコピーします。</span><span class="sxs-lookup"><span data-stu-id="51731-146">Copies the component assembly into the BizTalk \Pipeline components folder.</span></span>  
  
    -   <span data-ttu-id="51731-147">サンプル BizTalk プロジェクトをビルドして展開します。</span><span class="sxs-lookup"><span data-stu-id="51731-147">Builds and deploys the sample BizTalk project.</span></span>  
  
    -   <span data-ttu-id="51731-148">受信場所と送信ポートを構成し、それらを開始します。</span><span class="sxs-lookup"><span data-stu-id="51731-148">Configures the receive location and send port, and starts them.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="51731-149">このサンプルを実行する前に、ビルド処理および初期化処理でエラーが報告されていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="51731-149">You should confirm that no errors were reported during the build and initialization process before attempting to run this sample.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="51731-150">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="51731-150">Running This Sample</span></span>  
 <span data-ttu-id="51731-151">次の手順を使用して、スキーマ リゾルバ コンポーネント サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="51731-151">Use the following procedure to run the Schema Resolver Component sample.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="51731-152">このサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="51731-152">To run this sample</span></span>  
  
1.  <span data-ttu-id="51731-153">POInstance.txt、PRInstance.txt、SOInstance.txt、および SRInstance.txt ファイルを受信場所にドロップ\<*インストール パス*> \SDK\Samples\Pipelines\SchemaResolverComponent\In</span><span class="sxs-lookup"><span data-stu-id="51731-153">Drop the POInstance.txt, PRInstance.txt, SOInstance.txt, and SRInstance.txt files into the receive location \<*Installation Path*>\SDK\Samples\Pipelines\SchemaResolverComponent\In</span></span>  
  
2.  <span data-ttu-id="51731-154">書き込まれた 4 つの .xml ファイルを確認、 \<Installdir > \SDK\Samples\Pipelines\SchemaResolverComponent\Out フォルダです。</span><span class="sxs-lookup"><span data-stu-id="51731-154">Observe the four .xml files written to the \<Installdir>\SDK\Samples\Pipelines\SchemaResolverComponent\Out folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51731-155">参照</span><span class="sxs-lookup"><span data-stu-id="51731-155">See Also</span></span>  
 [<span data-ttu-id="51731-156">パイプライン (BizTalk Server Samples フォルダ)</span><span class="sxs-lookup"><span data-stu-id="51731-156">Pipelines (BizTalk Server Samples Folder)</span></span>](../core/pipelines-biztalk-server-samples-folder.md)