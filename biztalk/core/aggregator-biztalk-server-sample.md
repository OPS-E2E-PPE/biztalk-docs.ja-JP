---
title: "アグリゲーター (BizTalk Server サンプル) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- examples, orchestrations
- pipelines, examples
- orchestrations, messages
- examples, pipelines
- messages, correlating to orchestrations
ms.assetid: eb8121df-4f5b-4f36-8228-4b5ad1abfb4e
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 493f4d28214a815aca88f214e5efb9cd883e7192
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="aggregator-biztalk-server-sample"></a><span data-ttu-id="d8607-102">アグリゲーター (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="d8607-102">Aggregator (BizTalk Server Sample)</span></span>
<span data-ttu-id="d8607-103">このサンプルの目的は、オーケストレーションとパイプラインを使用してメッセージ アグリゲーション機能を構築することです。</span><span class="sxs-lookup"><span data-stu-id="d8607-103">The purpose of this sample is to build a message aggregation functionality using orchestration and pipelines.</span></span> <span data-ttu-id="d8607-104">特に、以下のことを行うオーケストレーションを構築します。</span><span class="sxs-lookup"><span data-stu-id="d8607-104">Specifically we will build an orchestration that:</span></span>  
  
1.  <span data-ttu-id="d8607-105">関連付けられた複数のメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="d8607-105">Receives a set of correlated messages.</span></span> <span data-ttu-id="d8607-106">各メッセージは、メッセージのコンテンツから取り出した宛先パートナーの URI 情報に基づいて関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="d8607-106">Messages are correlated based on the destination partner URI information that is extracted from message content.</span></span>  
  
2.  <span data-ttu-id="d8607-107">XML 送信パイプラインを実行することで、受信したメッセージを単一のインターチェンジ バッチにアグリゲートします。</span><span class="sxs-lookup"><span data-stu-id="d8607-107">Aggregates received messages into a single interchange batch by executing an XML send pipeline.</span></span>  
  
3.  <span data-ttu-id="d8607-108">1 分ごとか、アグリゲートするのに十分なメッセージを受信した場合はすぐに XML インターチェンジ メッセージを生成します。</span><span class="sxs-lookup"><span data-stu-id="d8607-108">Produces an XML interchange message every minute or as soon as it has enough messages to aggregate.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="d8607-109">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="d8607-109">Where to Find This Sample</span></span>  
 <span data-ttu-id="d8607-110">*\<パスのサンプル\>*\Pipelines\Aggregator</span><span class="sxs-lookup"><span data-stu-id="d8607-110">*\<Samples Path\>*\Pipelines\Aggregator</span></span>  
  
 <span data-ttu-id="d8607-111">次の表に、このサンプルのファイル一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="d8607-111">The following table lists the files for this sample.</span></span>  
  
|<span data-ttu-id="d8607-112">ファイル</span><span class="sxs-lookup"><span data-stu-id="d8607-112">File(s)</span></span>|<span data-ttu-id="d8607-113">Description</span><span class="sxs-lookup"><span data-stu-id="d8607-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d8607-114">Aggregator.sln</span><span class="sxs-lookup"><span data-stu-id="d8607-114">Aggregator.sln</span></span>|<span data-ttu-id="d8607-115">サンプルの Visual Studio ソリューション ファイルです。</span><span class="sxs-lookup"><span data-stu-id="d8607-115">Visual Studio solution file for the sample.</span></span>|  
|<span data-ttu-id="d8607-116">AggretatorBinding.xml</span><span class="sxs-lookup"><span data-stu-id="d8607-116">AggretatorBinding.xml</span></span>|<span data-ttu-id="d8607-117">サンプルのバインド ファイルです。</span><span class="sxs-lookup"><span data-stu-id="d8607-117">Binding file for the sample.</span></span>|  
|<span data-ttu-id="d8607-118">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="d8607-118">Cleanup.bat</span></span>|<span data-ttu-id="d8607-119">アセンブリを展開解除し、グローバル アセンブリ キャッシュ (GAC) から削除するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d8607-119">Used to undeploy assemblies and remove them from the global assembly cache (GAC).</span></span> <span data-ttu-id="d8607-120">送信ポートと受信ポートが削除されます。</span><span class="sxs-lookup"><span data-stu-id="d8607-120">Removes send and receive ports.</span></span> <span data-ttu-id="d8607-121">必要に応じて、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。</span><span class="sxs-lookup"><span data-stu-id="d8607-121">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="d8607-122">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="d8607-122">Setup.bat</span></span>|<span data-ttu-id="d8607-123">このサンプルをビルドおよび初期化するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d8607-123">Used to build and initialize this sample.</span></span>|  
|<span data-ttu-id="d8607-124">Aggregate フォルダー内: </span><span class="sxs-lookup"><span data-stu-id="d8607-124">In Aggregate folder:</span></span><br /><br /> <span data-ttu-id="d8607-125">Aggregate.btproj</span><span class="sxs-lookup"><span data-stu-id="d8607-125">Aggregate.btproj</span></span>|<span data-ttu-id="d8607-126">オーケストレーションをアグリゲートするための BizTalk プロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="d8607-126">BizTalk project for aggregating orchestration.</span></span>|  
|<span data-ttu-id="d8607-127">Aggregator フォルダー内: </span><span class="sxs-lookup"><span data-stu-id="d8607-127">In Aggregator folder:</span></span><br /><br /> <span data-ttu-id="d8607-128">Aggregate.odx</span><span class="sxs-lookup"><span data-stu-id="d8607-128">Aggregate.odx</span></span>|<span data-ttu-id="d8607-129">関連付けられているメッセージを 1 か所に集め、送信パイプラインを実行して単一のインターチェンジに組み立てるオーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="d8607-129">Orchestration that collects correlated messages together and then executes send pipeline to assemble them into a single interchange.</span></span>|  
|<span data-ttu-id="d8607-130">Aggregate フォルダー内: </span><span class="sxs-lookup"><span data-stu-id="d8607-130">In Aggregate folder:</span></span><br /><br /> <span data-ttu-id="d8607-131">SuspendMessage.odx</span><span class="sxs-lookup"><span data-stu-id="d8607-131">SuspendMessage.odx</span></span>|<span data-ttu-id="d8607-132">アグリゲート オーケストレーション内で処理できない保留メッセージに対して使用するオーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="d8607-132">Orchestration used for suspending messages that cannot be processed within aggregating orchestration.</span></span>|  
|<span data-ttu-id="d8607-133">PipelinesAndSchemas フォルダー内: </span><span class="sxs-lookup"><span data-stu-id="d8607-133">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="d8607-134">FFReceivePipeline.btp</span><span class="sxs-lookup"><span data-stu-id="d8607-134">FFReceivePipeline.btp</span></span>|<span data-ttu-id="d8607-135">フラット ファイル逆アセンブラーを使用した受信パイプラインです。</span><span class="sxs-lookup"><span data-stu-id="d8607-135">Receive pipeline with flat file disassembler.</span></span>|  
|<span data-ttu-id="d8607-136">PipelinesAndSchemas フォルダー内: </span><span class="sxs-lookup"><span data-stu-id="d8607-136">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="d8607-137">Instance1.txt、Instance2.txt、Instance3.txt、Instance4.txt</span><span class="sxs-lookup"><span data-stu-id="d8607-137">Instance1.txt, Instance2.txt, Instance3.txt, Instance4.txt</span></span>|<span data-ttu-id="d8607-138">サンプルのドキュメント インスタンスです。</span><span class="sxs-lookup"><span data-stu-id="d8607-138">Document instances for the sample.</span></span> <span data-ttu-id="d8607-139">Instance1.txt と Instance2.txt は、宛先パートナーのインターチェンジに追加する必要があります[http://www.contoso.com](http://www.contoso.com/) Instance3.txt と Instance4.txt は、宛先パートナーのインターチェンジに追加する必要があります[http://www.northwind.com](http://www.northwind.com/)です。</span><span class="sxs-lookup"><span data-stu-id="d8607-139">Instance1.txt and Instance2.txt should be added to an interchange for destination partner [http://www.contoso.com](http://www.contoso.com/) while Instance3.txt and Instance4.txt should be added to an interchange for destination partner [http://www.northwind.com](http://www.northwind.com/).</span></span>|  
|<span data-ttu-id="d8607-140">PipelinesAndSchemas フォルダー内: </span><span class="sxs-lookup"><span data-stu-id="d8607-140">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="d8607-141">Invoice.xsd、InvoiceEnvelope.xsd</span><span class="sxs-lookup"><span data-stu-id="d8607-141">Invoice.xsd, InvoiceEnvelope.xsd</span></span>|<span data-ttu-id="d8607-142">出力インターチェンジのドキュメント スキーマとエンベロープ スキーマです。</span><span class="sxs-lookup"><span data-stu-id="d8607-142">Document schema and envelope schema for output interchange.</span></span>|  
|<span data-ttu-id="d8607-143">PipelinesAndSchemas フォルダー内: </span><span class="sxs-lookup"><span data-stu-id="d8607-143">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="d8607-144">PipelinesAndSchemas.btproj</span><span class="sxs-lookup"><span data-stu-id="d8607-144">PipelinesAndSchemas.btproj</span></span>|<span data-ttu-id="d8607-145">スキーマとパイプラインの BizTalk プロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="d8607-145">BizTalk project for the schemas and pipelines.</span></span>|  
|<span data-ttu-id="d8607-146">PipelinesAndSchemas フォルダー内: </span><span class="sxs-lookup"><span data-stu-id="d8607-146">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="d8607-147">PropertySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="d8607-147">PropertySchema.xsd</span></span>|<span data-ttu-id="d8607-148">サンプルのプロパティ スキーマです。</span><span class="sxs-lookup"><span data-stu-id="d8607-148">Property schema for the sample.</span></span>|  
|<span data-ttu-id="d8607-149">PipelinesAndSchemas フォルダー内: </span><span class="sxs-lookup"><span data-stu-id="d8607-149">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="d8607-150">XMLAggregatingPipeline.btp</span><span class="sxs-lookup"><span data-stu-id="d8607-150">XMLAggregatingPipeline.btp</span></span>|<span data-ttu-id="d8607-151">収集されたメッセージを XML インターチェンジに組み立てるために、オーケストレーションから実行される送信パイプラインです。</span><span class="sxs-lookup"><span data-stu-id="d8607-151">Send pipeline that is executed from orchestration to assemble collected messages into an XML interchange.</span></span>|  
  
## <a name="building-and-initializing-the-sample"></a><span data-ttu-id="d8607-152">サンプルのビルドおよび初期化</span><span class="sxs-lookup"><span data-stu-id="d8607-152">Building and Initializing the Sample</span></span>  
 <span data-ttu-id="d8607-153">次の手順を使用して、アグリゲーターのサンプルをビルドおよび初期化します。</span><span class="sxs-lookup"><span data-stu-id="d8607-153">Use the following procedure to build and initialize the Aggregator sample.</span></span>  
  
#### <a name="to-build-and-initialize-the-aggregator-sample"></a><span data-ttu-id="d8607-154">アグリゲーターのサンプルをビルドおよび初期化するには</span><span class="sxs-lookup"><span data-stu-id="d8607-154">To build and initialize the Aggregator sample</span></span>  
  
1.  <span data-ttu-id="d8607-155">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="d8607-155">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="d8607-156">\<パスのサンプル\>\Pipelines\Aggregator</span><span class="sxs-lookup"><span data-stu-id="d8607-156">\<Samples Path\>\Pipelines\Aggregator</span></span>  
  
2.  <span data-ttu-id="d8607-157">次の操作を実行する Setup.bat ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="d8607-157">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="d8607-158">次のフォルダに、このサンプル用の入力 (In) フォルダと出力 (Out) フォルダを作成します。</span><span class="sxs-lookup"><span data-stu-id="d8607-158">Creates the input (In) and output (Out) folders for this sample in the folder:</span></span>  
  
         <span data-ttu-id="d8607-159">\<パスのサンプル\>\Pipelines\Aggregator</span><span class="sxs-lookup"><span data-stu-id="d8607-159">\<Samples Path\>\Pipelines\Aggregator</span></span>  
  
    -   <span data-ttu-id="d8607-160">このサンプル用の [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] プロジェクトをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="d8607-160">Compiles the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] projects for this sample.</span></span>  
  
    -   <span data-ttu-id="d8607-161">新しいアプリケーション Aggregator Sample を作成し、そこにサンプル アセンブリを展開します。</span><span class="sxs-lookup"><span data-stu-id="d8607-161">Creates a new application called "Aggregator Sample" and deploys the sample assemblies into it.</span></span>  
  
    -   <span data-ttu-id="d8607-162">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の受信場所、送信ポート、および受信ポートを作成しバインドします。</span><span class="sxs-lookup"><span data-stu-id="d8607-162">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location, and the send and receive ports.</span></span>  
  
    -   <span data-ttu-id="d8607-163">オーケストレーションを参加させて開始し、受信場所を有効化し、送信ポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="d8607-163">Enlists and starts orchestration, enables the receive location, and starts the send port.</span></span>  
  
         <span data-ttu-id="d8607-164">開き、Setup.bat ファイルを実行せずにこのサンプルのプロジェクトをビルドする場合は、まず、.NET Framework の厳密名ユーティリティ (sn.exe) を使用して、厳密な名前のキー ペアを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8607-164">If you choose to open and build the projects in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name utility (sn.exe).</span></span> <span data-ttu-id="d8607-165">このキー ペアが結果として得られるアセンブリの署名に使用されるを使用します。</span><span class="sxs-lookup"><span data-stu-id="d8607-165">Use this key pair is used to sign the resulting assemblies.</span></span>  
  
3.  <span data-ttu-id="d8607-166">このサンプルを実行する前に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] がビルド プロセス中または初期化プロセス中にエラーを報告していないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d8607-166">Before attempting to run this sample, confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process.</span></span>  
  
     <span data-ttu-id="d8607-167">Setup.bat によって行われた変更を元に戻すには、Cleanup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="d8607-167">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="d8607-168">Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。</span><span class="sxs-lookup"><span data-stu-id="d8607-168">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  
  
## <a name="running-the-sample"></a><span data-ttu-id="d8607-169">サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="d8607-169">Running the Sample</span></span>  
 <span data-ttu-id="d8607-170">次の手順を使用して、アグリゲーターのサンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="d8607-170">Use the following procedure to run the Aggregator sample.</span></span>  
  
#### <a name="to-run-the-aggregator-sample"></a><span data-ttu-id="d8607-171">アグリゲーターのサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="d8607-171">To run the Aggregator sample</span></span>  
  
1.  <span data-ttu-id="d8607-172">PipelinesAndSchemas フォルダーにあるファイル Instance1.txt と Instance2.txt を開き、その内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="d8607-172">Open Instance1.txt and Instance2.txt files located in PipelinesAndSchemas folder to inspect their content.</span></span>  
  
     <span data-ttu-id="d8607-173">どちらのファイルも、DestinationPartnerURI 要素に通知には、値 http://www.contoso.com が含まれています。この値は、それらを 1 つのインターチェンジに追加することができるようにこれら 2 つのメッセージを同時に関連付けるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d8607-173">Notice that in both files the DestinationPartnerURI element contains the value http://www.contoso.com. This value will be used to correlate these two messages together so that they can be added to one interchange.</span></span>  
  
     <span data-ttu-id="d8607-174">同様に、ファイル Instance3.txt と Instance4.txt にも、DestinationPatnerURI 要素に http://www.northwind.com が設定されています。</span><span class="sxs-lookup"><span data-stu-id="d8607-174">Similarly Instance3.txt and Instance4.txt files have DestinationPatnerURI element set to http://www.northwind.com.</span></span>  
  
     <span data-ttu-id="d8607-175">これら 2 つのメッセージが、別の 1 つのインターチェンジに追加されます。</span><span class="sxs-lookup"><span data-stu-id="d8607-175">These two messages together will be added to a different interchange.</span></span>  
  
2.  <span data-ttu-id="d8607-176">テキスト ファイル Instance1.txt、Instance2.txt、Instance3.txt、Instance4.txt のコピーを、フォルダー In に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="d8607-176">Paste copies of the text files Instance1.txt, Instance2.txt, Instance3.txt, and Instance4.txt into the folder In.</span></span>  
  
3.  <span data-ttu-id="d8607-177">アグリゲート オーケストレーションにより、10 個のメッセージを収集するか、1 分のタイムアウトが経過した後に、出力インターチェンジが生成されます。</span><span class="sxs-lookup"><span data-stu-id="d8607-177">Aggregating orchestrations produce output interchanges as soon as they collect 10 messages or after timeout of 1 minute.</span></span> <span data-ttu-id="d8607-178">そのため、Out フォルダー内にはファイルが遅れて作成されます。</span><span class="sxs-lookup"><span data-stu-id="d8607-178">Because of that, the files in the Out folder may appear with delay.</span></span>  
  
     <span data-ttu-id="d8607-179">タイムアウトを避けるには、4 つの入力ファイルをさらに 4 回貼り付けます。これにより、アグリゲート オーケストレーションによるインターチェンジの生成が起動されます。</span><span class="sxs-lookup"><span data-stu-id="d8607-179">To avoid the timeout, you can paste the four input files four more times, which would trigger the aggregating orchestrations to produce the interchanges.</span></span>  
  
4.  <span data-ttu-id="d8607-180">フォルダー Out に作成される XML ファイルを参照します。宛先パートナー URI ごとに 1 つ、合計 2 つのファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="d8607-180">Observe the XML files created in the folder Out. There should be two files – one per each destination partner URI.</span></span>  
  
     <span data-ttu-id="d8607-181">いずれかのファイルを開いて内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="d8607-181">Open one of the file to inspect its content.</span></span> <span data-ttu-id="d8607-182">ファイルには XML インターチェンジが 1 つ格納されており、その中には 1 つのエンベロープがあり、さらにその中に 2 つの XML ドキュメントがあります。</span><span class="sxs-lookup"><span data-stu-id="d8607-182">The file should contain an XML interchange that consists of an envelope and two XML documents within it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d8607-183">サンプル実装では、コンボイ シナリオにおいて、高負荷時に "配布されましたが、消費されませんでした" または "メッセージを破棄して完了" のエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="d8607-183">The sample implementation may cause "Delivered, not consumed messages" or "Completed with discarded messages" under high load in a convoy scenario.</span></span> <span data-ttu-id="d8607-184">これは、メッセージが終了途中のビジネス プロセスにルーティングされた場合や、予期せぬメッセージがビジネス プロセスに到着した場合に必ず発生します。</span><span class="sxs-lookup"><span data-stu-id="d8607-184">This occurs any time a message routes to a business process that is in the process of ending, or any time unexpected messages arrive into a business process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8607-185">参照</span><span class="sxs-lookup"><span data-stu-id="d8607-185">See Also</span></span>  
 [<span data-ttu-id="d8607-186">パイプライン (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="d8607-186">Pipelines (BizTalk Server Samples Folder)</span></span>](../core/pipelines-biztalk-server-samples-folder.md)