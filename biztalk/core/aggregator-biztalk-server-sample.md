---
title: アグリゲーター (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- examples, orchestrations
- pipelines, examples
- orchestrations, messages
- examples, pipelines
- messages, correlating to orchestrations
ms.assetid: eb8121df-4f5b-4f36-8228-4b5ad1abfb4e
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 127eb496a6949c0bbf3d6756324f38286e127ea3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360088"
---
# <a name="aggregator-biztalk-server-sample"></a><span data-ttu-id="45f63-102">アグリゲーター (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="45f63-102">Aggregator (BizTalk Server Sample)</span></span>
<span data-ttu-id="45f63-103">このサンプルでは、オーケストレーションとパイプラインを使用してメッセージ集計機能を構築します。</span><span class="sxs-lookup"><span data-stu-id="45f63-103">The purpose of this sample is to build a message aggregation functionality using orchestration and pipelines.</span></span> <span data-ttu-id="45f63-104">具体的には行うオーケストレーションを構築します。</span><span class="sxs-lookup"><span data-stu-id="45f63-104">Specifically we will build an orchestration that:</span></span>  
  
1.  <span data-ttu-id="45f63-105">一連の関連するメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="45f63-105">Receives a set of correlated messages.</span></span> <span data-ttu-id="45f63-106">メッセージは宛先パートナーのメッセージのコンテンツから抽出された URI 情報に基づいて関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="45f63-106">Messages are correlated based on the destination partner URI information that is extracted from message content.</span></span>  
  
2.  <span data-ttu-id="45f63-107">XML を実行することによって、1 つのインターチェンジ バッチにメッセージを受信した集計は、パイプラインを送信します。</span><span class="sxs-lookup"><span data-stu-id="45f63-107">Aggregates received messages into a single interchange batch by executing an XML send pipeline.</span></span>  
  
3.  <span data-ttu-id="45f63-108">1 分ごとに、XML インターチェンジ メッセージを生成またはと即座に十分なメッセージを集計します。</span><span class="sxs-lookup"><span data-stu-id="45f63-108">Produces an XML interchange message every minute or as soon as it has enough messages to aggregate.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="45f63-109">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="45f63-109">Where to Find This Sample</span></span>  
 <span data-ttu-id="45f63-110">*\<パスのサンプル\>* \Pipelines\Aggregator</span><span class="sxs-lookup"><span data-stu-id="45f63-110">*\<Samples Path\>* \Pipelines\Aggregator</span></span>  
  
 <span data-ttu-id="45f63-111">次の表では、このサンプルのファイルを示します。</span><span class="sxs-lookup"><span data-stu-id="45f63-111">The following table lists the files for this sample.</span></span>  
  
|<span data-ttu-id="45f63-112">ファイル</span><span class="sxs-lookup"><span data-stu-id="45f63-112">File(s)</span></span>|<span data-ttu-id="45f63-113">説明</span><span class="sxs-lookup"><span data-stu-id="45f63-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="45f63-114">Aggregator.sln</span><span class="sxs-lookup"><span data-stu-id="45f63-114">Aggregator.sln</span></span>|<span data-ttu-id="45f63-115">サンプルの Visual Studio ソリューション ファイルです。</span><span class="sxs-lookup"><span data-stu-id="45f63-115">Visual Studio solution file for the sample.</span></span>|  
|<span data-ttu-id="45f63-116">AggretatorBinding.xml</span><span class="sxs-lookup"><span data-stu-id="45f63-116">AggretatorBinding.xml</span></span>|<span data-ttu-id="45f63-117">サンプルのバインド ファイルです。</span><span class="sxs-lookup"><span data-stu-id="45f63-117">Binding file for the sample.</span></span>|  
|<span data-ttu-id="45f63-118">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="45f63-118">Cleanup.bat</span></span>|<span data-ttu-id="45f63-119">アセンブリを展開解除し、グローバル アセンブリ キャッシュ (GAC) から削除するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="45f63-119">Used to undeploy assemblies and remove them from the global assembly cache (GAC).</span></span> <span data-ttu-id="45f63-120">送信ポートと受信ポートが削除されます。</span><span class="sxs-lookup"><span data-stu-id="45f63-120">Removes send and receive ports.</span></span> <span data-ttu-id="45f63-121">必要に応じて、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。</span><span class="sxs-lookup"><span data-stu-id="45f63-121">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="45f63-122">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="45f63-122">Setup.bat</span></span>|<span data-ttu-id="45f63-123">このサンプルをビルドおよび初期化するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="45f63-123">Used to build and initialize this sample.</span></span>|  
|<span data-ttu-id="45f63-124">Aggregate フォルダー内。</span><span class="sxs-lookup"><span data-stu-id="45f63-124">In Aggregate folder:</span></span><br /><br /> <span data-ttu-id="45f63-125">Aggregate.btproj</span><span class="sxs-lookup"><span data-stu-id="45f63-125">Aggregate.btproj</span></span>|<span data-ttu-id="45f63-126">アグリゲート オーケストレーションの BizTalk プロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="45f63-126">BizTalk project for aggregating orchestration.</span></span>|  
|<span data-ttu-id="45f63-127">Aggregator フォルダー内。</span><span class="sxs-lookup"><span data-stu-id="45f63-127">In Aggregator folder:</span></span><br /><br /> <span data-ttu-id="45f63-128">」の Aggregate.odx</span><span class="sxs-lookup"><span data-stu-id="45f63-128">Aggregate.odx</span></span>|<span data-ttu-id="45f63-129">関連付けられたメッセージをまとめて収集しを実行するオーケストレーションは、1 つのインターチェンジにアセンブルするためのパイプラインを送信します。</span><span class="sxs-lookup"><span data-stu-id="45f63-129">Orchestration that collects correlated messages together and then executes send pipeline to assemble them into a single interchange.</span></span>|  
|<span data-ttu-id="45f63-130">Aggregate フォルダー内。</span><span class="sxs-lookup"><span data-stu-id="45f63-130">In Aggregate folder:</span></span><br /><br /> <span data-ttu-id="45f63-131">SuspendMessage.odx</span><span class="sxs-lookup"><span data-stu-id="45f63-131">SuspendMessage.odx</span></span>|<span data-ttu-id="45f63-132">アグリゲート オーケストレーション内で処理できないメッセージを中断するためのオーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="45f63-132">Orchestration used for suspending messages that cannot be processed within aggregating orchestration.</span></span>|  
|<span data-ttu-id="45f63-133">PipelinesAndSchemas フォルダー内: </span><span class="sxs-lookup"><span data-stu-id="45f63-133">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="45f63-134">FFReceivePipeline.btp</span><span class="sxs-lookup"><span data-stu-id="45f63-134">FFReceivePipeline.btp</span></span>|<span data-ttu-id="45f63-135">受信フラット ファイル逆アセンブラーでは、パイプラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="45f63-135">Receive pipeline with flat file disassembler.</span></span>|  
|<span data-ttu-id="45f63-136">PipelinesAndSchemas フォルダー内: </span><span class="sxs-lookup"><span data-stu-id="45f63-136">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="45f63-137">Instance1.txt, Instance2.txt, Instance3.txt, Instance4.txt</span><span class="sxs-lookup"><span data-stu-id="45f63-137">Instance1.txt, Instance2.txt, Instance3.txt, Instance4.txt</span></span>|<span data-ttu-id="45f63-138">サンプルのドキュメント インスタンスです。</span><span class="sxs-lookup"><span data-stu-id="45f63-138">Document instances for the sample.</span></span> <span data-ttu-id="45f63-139">Instance1.txt と Instance2.txt は、宛先パートナーのインターチェンジに追加する必要があります [http://www.contoso.com](http://www.contoso.com/) Instance3.txt と Instance4.txt は、宛先パートナーのインターチェンジに追加する必要があります [http://www.northwind.com](http://www.northwind.com/) .</span><span class="sxs-lookup"><span data-stu-id="45f63-139">Instance1.txt and Instance2.txt should be added to an interchange for destination partner [http://www.contoso.com](http://www.contoso.com/) while Instance3.txt and Instance4.txt should be added to an interchange for destination partner [http://www.northwind.com](http://www.northwind.com/).</span></span>|  
|<span data-ttu-id="45f63-140">PipelinesAndSchemas フォルダー内: </span><span class="sxs-lookup"><span data-stu-id="45f63-140">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="45f63-141">Invoice.xsd, InvoiceEnvelope.xsd</span><span class="sxs-lookup"><span data-stu-id="45f63-141">Invoice.xsd, InvoiceEnvelope.xsd</span></span>|<span data-ttu-id="45f63-142">ドキュメント スキーマと出力インターチェンジのエンベロープ スキーマ。</span><span class="sxs-lookup"><span data-stu-id="45f63-142">Document schema and envelope schema for output interchange.</span></span>|  
|<span data-ttu-id="45f63-143">PipelinesAndSchemas フォルダー内: </span><span class="sxs-lookup"><span data-stu-id="45f63-143">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="45f63-144">PipelinesAndSchemas.btproj</span><span class="sxs-lookup"><span data-stu-id="45f63-144">PipelinesAndSchemas.btproj</span></span>|<span data-ttu-id="45f63-145">スキーマとパイプラインの BizTalk プロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="45f63-145">BizTalk project for the schemas and pipelines.</span></span>|  
|<span data-ttu-id="45f63-146">PipelinesAndSchemas フォルダー内: </span><span class="sxs-lookup"><span data-stu-id="45f63-146">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="45f63-147">PropertySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="45f63-147">PropertySchema.xsd</span></span>|<span data-ttu-id="45f63-148">サンプルのプロパティ スキーマです。</span><span class="sxs-lookup"><span data-stu-id="45f63-148">Property schema for the sample.</span></span>|  
|<span data-ttu-id="45f63-149">PipelinesAndSchemas フォルダー内: </span><span class="sxs-lookup"><span data-stu-id="45f63-149">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="45f63-150">XMLAggregatingPipeline.btp</span><span class="sxs-lookup"><span data-stu-id="45f63-150">XMLAggregatingPipeline.btp</span></span>|<span data-ttu-id="45f63-151">収集されたメッセージを XML インターチェンジにアセンブルするオーケストレーションから実行されるパイプラインを送信します。</span><span class="sxs-lookup"><span data-stu-id="45f63-151">Send pipeline that is executed from orchestration to assemble collected messages into an XML interchange.</span></span>|  
  
## <a name="building-and-initializing-the-sample"></a><span data-ttu-id="45f63-152">サンプルのビルドおよび初期化</span><span class="sxs-lookup"><span data-stu-id="45f63-152">Building and Initializing the Sample</span></span>  
 <span data-ttu-id="45f63-153">次の手順を使用して、ビルドして、アグリゲーターのサンプルを初期化します。</span><span class="sxs-lookup"><span data-stu-id="45f63-153">Use the following procedure to build and initialize the Aggregator sample.</span></span>  
  
#### <a name="to-build-and-initialize-the-aggregator-sample"></a><span data-ttu-id="45f63-154">ビルドして、アグリゲーターのサンプルの初期化</span><span class="sxs-lookup"><span data-stu-id="45f63-154">To build and initialize the Aggregator sample</span></span>  
  
1. <span data-ttu-id="45f63-155">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="45f63-155">In a command window, navigate to the following folder:</span></span>  
  
    <span data-ttu-id="45f63-156">\<パスのサンプル\>\Pipelines\Aggregator</span><span class="sxs-lookup"><span data-stu-id="45f63-156">\<Samples Path\>\Pipelines\Aggregator</span></span>  
  
2. <span data-ttu-id="45f63-157">ファイルは、次の操作を実行します。 Setup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="45f63-157">Run the file Setup.bat, which performs the following actions:</span></span>  
  
   - <span data-ttu-id="45f63-158">入力 (In) フォルダと出力 (Out) フォルダーに、このサンプル用のフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="45f63-158">Creates the input (In) and output (Out) folders for this sample in the folder:</span></span>  
  
      <span data-ttu-id="45f63-159">\<パスのサンプル\>\Pipelines\Aggregator</span><span class="sxs-lookup"><span data-stu-id="45f63-159">\<Samples Path\>\Pipelines\Aggregator</span></span>  
  
   - <span data-ttu-id="45f63-160">このサンプル用の [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] プロジェクトをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="45f63-160">Compiles the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] projects for this sample.</span></span>  
  
   - <span data-ttu-id="45f63-161">Aggregator Sample をという新しいアプリケーションを作成し、そこにサンプル アセンブリを展開します。</span><span class="sxs-lookup"><span data-stu-id="45f63-161">Creates a new application called "Aggregator Sample" and deploys the sample assemblies into it.</span></span>  
  
   - <span data-ttu-id="45f63-162">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の受信場所、送信ポート、および受信ポートを作成しバインドします。</span><span class="sxs-lookup"><span data-stu-id="45f63-162">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location, and the send and receive ports.</span></span>  
  
   - <span data-ttu-id="45f63-163">参加しオーケストレーションを開始、により、受信場所および送信ポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="45f63-163">Enlists and starts orchestration, enables the receive location, and starts the send port.</span></span>  
  
      <span data-ttu-id="45f63-164">開き、Setup.bat ファイルを実行することがなくこのサンプルでは、プロジェクトをビルドする場合は、まず、.NET Framework の厳密名ユーティリティ (sn.exe) を使用して厳密な名前キーのペアを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45f63-164">If you choose to open and build the projects in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name utility (sn.exe).</span></span> <span data-ttu-id="45f63-165">このキー ペアが結果として得られるアセンブリの署名に使用されるを使用します。</span><span class="sxs-lookup"><span data-stu-id="45f63-165">Use this key pair is used to sign the resulting assemblies.</span></span>  
  
3. <span data-ttu-id="45f63-166">このサンプルを実行する前に、ことを確認します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]でビルドおよび初期化プロセス中にエラーが報告されません。</span><span class="sxs-lookup"><span data-stu-id="45f63-166">Before attempting to run this sample, confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process.</span></span>  
  
    <span data-ttu-id="45f63-167">Setup.bat によって行われた変更を元に戻すには、Cleanup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="45f63-167">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="45f63-168">Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。</span><span class="sxs-lookup"><span data-stu-id="45f63-168">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  
  
## <a name="running-the-sample"></a><span data-ttu-id="45f63-169">サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="45f63-169">Running the Sample</span></span>  
 <span data-ttu-id="45f63-170">アグリゲーターのサンプルを実行するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="45f63-170">Use the following procedure to run the Aggregator sample.</span></span>  
  
#### <a name="to-run-the-aggregator-sample"></a><span data-ttu-id="45f63-171">アグリゲーターのサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="45f63-171">To run the Aggregator sample</span></span>  
  
1.  <span data-ttu-id="45f63-172">開いているファイル Instance1.txt と Instance2.txt PipelinesAndSchemas フォルダーにその内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="45f63-172">Open Instance1.txt and Instance2.txt files located in PipelinesAndSchemas folder to inspect their content.</span></span>  
  
     <span data-ttu-id="45f63-173">どちらのファイルも、DestinationPartnerURI 要素に通知には、値が含まれています。 http://www.contoso.comします。</span><span class="sxs-lookup"><span data-stu-id="45f63-173">Notice that in both files the DestinationPartnerURI element contains the value http://www.contoso.com.</span></span> <span data-ttu-id="45f63-174">この値は、1 つのインターチェンジに追加できるようにこれら 2 つのメッセージをまとめて関連付けるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="45f63-174">This value will be used to correlate these two messages together so that they can be added to one interchange.</span></span>  
  
     <span data-ttu-id="45f63-175">同様に、DestinationPatnerURI 要素に設定のあるファイル Instance3.txt と Instance4.txt http://www.northwind.com します。</span><span class="sxs-lookup"><span data-stu-id="45f63-175">Similarly Instance3.txt and Instance4.txt files have DestinationPatnerURI element set to http://www.northwind.com.</span></span>  
  
     <span data-ttu-id="45f63-176">これら 2 つのメッセージが、別の 1 つのインターチェンジに追加されます。</span><span class="sxs-lookup"><span data-stu-id="45f63-176">These two messages together will be added to a different interchange.</span></span>  
  
2.  <span data-ttu-id="45f63-177">テキスト ファイル Instance1.txt、Instance2.txt、Instance3.txt、Instance4.txt のコピーをフォルダーに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="45f63-177">Paste copies of the text files Instance1.txt, Instance2.txt, Instance3.txt, and Instance4.txt into the folder In.</span></span>  
  
3.  <span data-ttu-id="45f63-178">アグリゲート オーケストレーションは、10 個のメッセージを収集するとすぐに、または 1 分のタイムアウト後に、出力インターチェンジを生成します。</span><span class="sxs-lookup"><span data-stu-id="45f63-178">Aggregating orchestrations produce output interchanges as soon as they collect 10 messages or after timeout of 1 minute.</span></span> <span data-ttu-id="45f63-179">そのため、遅延が Out フォルダにファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="45f63-179">Because of that, the files in the Out folder may appear with delay.</span></span>  
  
     <span data-ttu-id="45f63-180">タイムアウトを避けるためには、さらに 4 回、アグリゲート オーケストレーションによるインターチェンジの生成をトリガーする 4 つの入力ファイルを貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="45f63-180">To avoid the timeout, you can paste the four input files four more times, which would trigger the aggregating orchestrations to produce the interchanges.</span></span>  
  
4.  <span data-ttu-id="45f63-181">Out フォルダに作成された XML ファイルを確認します。2 つのファイル-宛先パートナー URI ごとに 1 つがあります。</span><span class="sxs-lookup"><span data-stu-id="45f63-181">Observe the XML files created in the folder Out. There should be two files – one per each destination partner URI.</span></span>  
  
     <span data-ttu-id="45f63-182">その内容を確認するファイルのいずれかを開きます。</span><span class="sxs-lookup"><span data-stu-id="45f63-182">Open one of the file to inspect its content.</span></span> <span data-ttu-id="45f63-183">ファイルは、エンベロープとその中の 2 つの XML ドキュメントで構成される XML インターチェンジに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="45f63-183">The file should contain an XML interchange that consists of an envelope and two XML documents within it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="45f63-184">「配信済み、消費されませんでした」が発生する可能性があります、サンプルの実装またはコンボイ シナリオでの高負荷の下で「メッセージを破棄して完了」です。</span><span class="sxs-lookup"><span data-stu-id="45f63-184">The sample implementation may cause "Delivered, not consumed messages" or "Completed with discarded messages" under high load in a convoy scenario.</span></span> <span data-ttu-id="45f63-185">これは、メッセージの到着、ビジネス プロセスを終了、途中のビジネスへのルートを処理するメッセージがいつや、予期せぬに発生します。</span><span class="sxs-lookup"><span data-stu-id="45f63-185">This occurs any time a message routes to a business process that is in the process of ending, or any time unexpected messages arrive into a business process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45f63-186">参照</span><span class="sxs-lookup"><span data-stu-id="45f63-186">See Also</span></span>  
 [<span data-ttu-id="45f63-187">パイプライン (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="45f63-187">Pipelines (BizTalk Server Samples Folder)</span></span>](../core/pipelines-biztalk-server-samples-folder.md)