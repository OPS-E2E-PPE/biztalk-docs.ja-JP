---
title: スキーマ リゾルバ コンポーネント (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Flat File Disassembler [pipeline component], examples
- examples, schemas
- schemas, examples
- examples, Flat File Disassembler [pipeline component]
ms.assetid: 9ef68988-c4ee-42d5-83b5-a5c978b2007d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d34ef9109c95ae853c9d3b8319961a7c22d73628
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396911"
---
# <a name="schema-resolver-component-biztalk-server-sample"></a><span data-ttu-id="e8d4b-102">スキーマ リゾルバ コンポーネント (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="e8d4b-102">Schema Resolver Component (BizTalk Server Sample)</span></span>
<span data-ttu-id="e8d4b-103">スキーマ リゾルバ コンポーネント サンプルは、の機能を拡張する方法を示します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]フラット ファイル逆アセンブラー コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="e8d4b-103">The Schema Resolver Component sample demonstrates how to extend the functionality of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] flat file disassembler component.</span></span>  
  
 <span data-ttu-id="e8d4b-104">通常、フラット ファイル逆アセンブラー コンポーネントではデザイン時に解析スキーマを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8d4b-104">The flat file disassembler component normally requires you to define a parsing schema at design time.</span></span> <span data-ttu-id="e8d4b-105">同じ受信場所で異なるフラット ファイル ドキュメントを受信する場合は、通常、受信パイプライン、スキーマごとに 1 つで複数のフラット ファイル逆アセンブラを含めます。</span><span class="sxs-lookup"><span data-stu-id="e8d4b-105">So if you expect to receive different flat file documents on the same receive location, you typically include several flat file disassemblers in the receive pipeline, one for each schema.</span></span> <span data-ttu-id="e8d4b-106">実行時に、パイプライン プローブ機能を使用して、適切な逆アセンブラ コンポーネントが選択されます。</span><span class="sxs-lookup"><span data-stu-id="e8d4b-106">At run time, the correct disassembler component is selected using a pipeline probing mechanism.</span></span> <span data-ttu-id="e8d4b-107">ただし、この方法は多数のフラット ファイル スキーマがあるため、パイプラインのパフォーマンスが低下ごとの対応する逆アセンブラー コンポーネントのプローブに負荷がかかるです。</span><span class="sxs-lookup"><span data-stu-id="e8d4b-107">However, this approach is expensive if you have many flat file schemas because probing for every corresponding disassembler component degrades pipeline performance.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="e8d4b-108">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="e8d4b-108">What This Sample Does</span></span>  
 <span data-ttu-id="e8d4b-109">スキーマ リゾルバ コンポーネントは、フラット ファイル逆アセンブラーのスキーマを選択した場合の代替方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e8d4b-109">The Schema Resolver component demonstrates an alternative method of selecting the schema for a flat file disassembler.</span></span> <span data-ttu-id="e8d4b-110">このサンプルで 4 つのスキーマが定義されているし、各スキーマのメッセージの最初の 2 つの文字が一意です。</span><span class="sxs-lookup"><span data-stu-id="e8d4b-110">In this sample, four schemas are defined and the first two characters of a message for each schema are unique.</span></span> <span data-ttu-id="e8d4b-111">一意の最初の 2 つの文字と、対応するスキーマの間のマッピングが定義されます。</span><span class="sxs-lookup"><span data-stu-id="e8d4b-111">A mapping is defined between the unique first two characters and the corresponding schema.</span></span> <span data-ttu-id="e8d4b-112">スキーマ リゾルバ コンポーネントには、入力メッセージが指定された場合、最初の 2 つの文字を読み取り、対応するドキュメントを使用するスキーマが決定、メッセージ コンテキストにスキーマ情報を保存し、標準のフラット ファイルを呼び出す逆アセンブラー コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="e8d4b-112">When the input message is given to the Schema Resolver component, it reads the first two characters, determines which schema to use for the corresponding document, saves the schema information on the message context, and then calls into the standard flat file disassembler component.</span></span> <span data-ttu-id="e8d4b-113">標準のフラット ファイル逆アセンブラー コンポーネントは、メッセージ コンテキストからスキーマ情報を読み取るし、そのスキーマを使用して、ドキュメントの解析。</span><span class="sxs-lookup"><span data-stu-id="e8d4b-113">The standard flat file disassembler component reads the schema information from the message context and uses that schema to parse the document.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="e8d4b-114">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="e8d4b-114">Where to Find This Sample</span></span>  
 <span data-ttu-id="e8d4b-115">*\<パスのサンプル\>* \Pipelines\SchemaResolverComponent\\</span><span class="sxs-lookup"><span data-stu-id="e8d4b-115">*\<Samples Path\>* \Pipelines\SchemaResolverComponent\\</span></span>  
  
 <span data-ttu-id="e8d4b-116">次の表では、このサンプルで使用されるファイルが表示され、その目的について説明します。</span><span class="sxs-lookup"><span data-stu-id="e8d4b-116">The following table shows the files used in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="e8d4b-117">ファイル</span><span class="sxs-lookup"><span data-stu-id="e8d4b-117">File(s)</span></span>|<span data-ttu-id="e8d4b-118">説明</span><span class="sxs-lookup"><span data-stu-id="e8d4b-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e8d4b-119">SchemaResolverSample.sln</span><span class="sxs-lookup"><span data-stu-id="e8d4b-119">SchemaResolverSample.sln</span></span>|<span data-ttu-id="e8d4b-120">カスタム パイプライン コンポーネントを実行する BizTalk プロジェクトのソリューションです。</span><span class="sxs-lookup"><span data-stu-id="e8d4b-120">Solution for the BizTalk project that exercises the custom pipeline component.</span></span>|  
|<span data-ttu-id="e8d4b-121">SchemaResolverSample.btproj</span><span class="sxs-lookup"><span data-stu-id="e8d4b-121">SchemaResolverSample.btproj</span></span>|<span data-ttu-id="e8d4b-122">カスタム パイプライン コンポーネントを実行する BizTalk プロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="e8d4b-122">BizTalk project that exercises the custom pipeline component.</span></span>|  
|<span data-ttu-id="e8d4b-123">SchemaResolverRP.btp</span><span class="sxs-lookup"><span data-stu-id="e8d4b-123">SchemaResolverRP.btp</span></span>|<span data-ttu-id="e8d4b-124">カスタム コンポーネントを含むパイプラインを受信します。</span><span class="sxs-lookup"><span data-stu-id="e8d4b-124">Receive pipeline that contains the custom component.</span></span>|  
|<span data-ttu-id="e8d4b-125">PurchaseOrder.xsd, PurchaseRequest.xsd, SalesOrder.xsd, SalesRequest.xsd</span><span class="sxs-lookup"><span data-stu-id="e8d4b-125">PurchaseOrder.xsd, PurchaseRequest.xsd, SalesOrder.xsd, SalesRequest.xsd</span></span>|<span data-ttu-id="e8d4b-126">フラット ファイル スキーマです。</span><span class="sxs-lookup"><span data-stu-id="e8d4b-126">Flat file schemas.</span></span>|  
|<span data-ttu-id="e8d4b-127">POInstance.txt、PRInstance.txt、SOInstance.txt、SRInstance.txt</span><span class="sxs-lookup"><span data-stu-id="e8d4b-127">POInstance.txt, PRInstance.txt, SOInstance.txt, SRInstance.txt</span></span>|<span data-ttu-id="e8d4b-128">対応するフラット ファイル ドキュメント インスタンスです。</span><span class="sxs-lookup"><span data-stu-id="e8d4b-128">Corresponding flat file document instances.</span></span>|  
|<span data-ttu-id="e8d4b-129">SchemaResolverFlatFileDasm.sln</span><span class="sxs-lookup"><span data-stu-id="e8d4b-129">SchemaResolverFlatFileDasm.sln</span></span>|<span data-ttu-id="e8d4b-130">パイプライン コンポーネントの実装のためのソリューションです。</span><span class="sxs-lookup"><span data-stu-id="e8d4b-130">Solution for the implementation of the pipeline component.</span></span>|  
|<span data-ttu-id="e8d4b-131">SchemaResolverFlatFileDasm.csproj</span><span class="sxs-lookup"><span data-stu-id="e8d4b-131">SchemaResolverFlatFileDasm.csproj</span></span>|<span data-ttu-id="e8d4b-132">C#パイプライン コンポーネントの実装用のプロジェクト。</span><span class="sxs-lookup"><span data-stu-id="e8d4b-132">C# project for the implementation of the pipeline component.</span></span>|  
|<span data-ttu-id="e8d4b-133">SchemaResolverFlatFileDasmComp.cs</span><span class="sxs-lookup"><span data-stu-id="e8d4b-133">SchemaResolverFlatFileDasmComp.cs</span></span>|<span data-ttu-id="e8d4b-134">パイプライン コンポーネントの実装です。</span><span class="sxs-lookup"><span data-stu-id="e8d4b-134">Implementation of the pipeline component.</span></span>|  
|<span data-ttu-id="e8d4b-135">SeekableReadOnlyStream.cs</span><span class="sxs-lookup"><span data-stu-id="e8d4b-135">SeekableReadOnlyStream.cs</span></span>|<span data-ttu-id="e8d4b-136">コンポーネントによって使用されるシーク可能な読み取り専用ストリームの実装です。</span><span class="sxs-lookup"><span data-stu-id="e8d4b-136">Implementation of the seekable read-only stream used by component.</span></span>|  
|<span data-ttu-id="e8d4b-137">VirtualStream.cs</span><span class="sxs-lookup"><span data-stu-id="e8d4b-137">VirtualStream.cs</span></span>|<span data-ttu-id="e8d4b-138">パイプライン コンポーネントによって使用される仮想ストリームの実装です。</span><span class="sxs-lookup"><span data-stu-id="e8d4b-138">Implementation of the virtual stream used by pipeline component.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="e8d4b-139">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="e8d4b-139">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="e8d4b-140">次の手順を使用して、ビルドして、スキーマ リゾルバ コンポーネント サンプルを初期化します。</span><span class="sxs-lookup"><span data-stu-id="e8d4b-140">Use the following procedure to build and initialize the Schema Resolver Component sample.</span></span>  
  
#### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="e8d4b-141">このサンプルを作成および初期化するには</span><span class="sxs-lookup"><span data-stu-id="e8d4b-141">To build and initialize this sample</span></span>  
  
1.  <span data-ttu-id="e8d4b-142">コマンド ウィンドウでは、次のフォルダーにディレクトリ (cd) を変更します。</span><span class="sxs-lookup"><span data-stu-id="e8d4b-142">In a command window, change directory (cd) to the following folder:</span></span>  
  
     <span data-ttu-id="e8d4b-143">*\<パスのサンプル\>* \Pipelines\SchemaResolverComponent</span><span class="sxs-lookup"><span data-stu-id="e8d4b-143">*\<Samples Path\>* \Pipelines\SchemaResolverComponent</span></span>  
  
2.  <span data-ttu-id="e8d4b-144">ファイルは、次の操作を実行します。 Setup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="e8d4b-144">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="e8d4b-145">コンポーネントをビルドします。</span><span class="sxs-lookup"><span data-stu-id="e8d4b-145">Builds the component.</span></span>  
  
    -   <span data-ttu-id="e8d4b-146">コンポーネント アセンブリを BizTalk \Pipeline components フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="e8d4b-146">Copies the component assembly into the BizTalk \Pipeline components folder.</span></span>  
  
    -   <span data-ttu-id="e8d4b-147">ビルドし、サンプル BizTalk プロジェクトをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="e8d4b-147">Builds and deploys the sample BizTalk project.</span></span>  
  
    -   <span data-ttu-id="e8d4b-148">受信場所と送信ポートを構成し、それらを開始します。</span><span class="sxs-lookup"><span data-stu-id="e8d4b-148">Configures the receive location and send port, and starts them.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e8d4b-149">エラーが報告されていないこと、ビルドおよび初期化プロセス中にこのサンプルを実行する前に確認してください。</span><span class="sxs-lookup"><span data-stu-id="e8d4b-149">You should confirm that no errors were reported during the build and initialization process before attempting to run this sample.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="e8d4b-150">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="e8d4b-150">Running This Sample</span></span>  
 <span data-ttu-id="e8d4b-151">スキーマ リゾルバ コンポーネント サンプルを実行するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="e8d4b-151">Use the following procedure to run the Schema Resolver Component sample.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="e8d4b-152">このサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="e8d4b-152">To run this sample</span></span>  
  
1.  <span data-ttu-id="e8d4b-153">POInstance.txt、PRInstance.txt、SOInstance.txt、SRInstance.txt ファイルを受信場所にドロップ\<*インストール パス*\>\SDK\Samples\Pipelines\SchemaResolverComponent\In</span><span class="sxs-lookup"><span data-stu-id="e8d4b-153">Drop the POInstance.txt, PRInstance.txt, SOInstance.txt, and SRInstance.txt files into the receive location \<*Installation Path*\>\SDK\Samples\Pipelines\SchemaResolverComponent\In</span></span>  
  
2.  <span data-ttu-id="e8d4b-154">書き込まれた 4 つの .xml ファイルを確認、 \<Installdir\>\SDK\Samples\Pipelines\SchemaResolverComponent\Out フォルダ。</span><span class="sxs-lookup"><span data-stu-id="e8d4b-154">Observe the four .xml files written to the \<Installdir\>\SDK\Samples\Pipelines\SchemaResolverComponent\Out folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8d4b-155">参照</span><span class="sxs-lookup"><span data-stu-id="e8d4b-155">See Also</span></span>  
 [<span data-ttu-id="e8d4b-156">パイプライン (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="e8d4b-156">Pipelines (BizTalk Server Samples Folder)</span></span>](../core/pipelines-biztalk-server-samples-folder.md)