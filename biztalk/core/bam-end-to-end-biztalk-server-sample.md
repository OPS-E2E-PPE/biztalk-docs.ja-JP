---
title: "BizTalk Server で BAM エンド ツー エンドのサンプル |Microsoft ドキュメント"
description: "BizTalk Server でビジネス アクティビティの監視を使用して複数のコンポーネントからイベントを関連付ける方法のシナリオ"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 81406038-7f3f-499f-a003-12423d92c44b
caps.latest.revision: "35"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21cf3bcfae53d3204a1b4de23c1476591be2b453
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="bam-end-to-end-biztalk-server-sample"></a><span data-ttu-id="5c90e-103">BAM End-to-End (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="5c90e-103">BAM End-to-End (BizTalk Server Sample)</span></span>
<span data-ttu-id="5c90e-104">エンド ツー エンドの例では、BAM を使用して、複数のコンポーネント (この場合は、3 つのオーケストレーションとパイプライン) からのイベントを関連付ける方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5c90e-104">The End-to-End sample demonstrates how to correlate events from multiple components (in this case, three orchestrations and a pipeline) by using BAM.</span></span>  
  
 <span data-ttu-id="5c90e-105">BAM によって、パイプライン コンポーネントとオーケストレーションにまたがるビジネス アクティビティが再構築されます。</span><span class="sxs-lookup"><span data-stu-id="5c90e-105">BAM reconstructs the business activity that spans the pipeline component and orchestrations.</span></span> <span data-ttu-id="5c90e-106">最下位のレベルへの呼び出しによって機能**EventStream.EnableContinuation**各実装コンポーネント、アクティビティの複数のイベントを受け取るからです。</span><span class="sxs-lookup"><span data-stu-id="5c90e-106">At the lowest level, this works by calls to **EventStream.EnableContinuation** from each implementation component that expects more events for the activity.</span></span> <span data-ttu-id="5c90e-107">呼び出し**EnableContinuation**明示的な Orchestration1 と Orchestration2 が 1 つのスケジュールとされるスケジュールを ContinuationID フォルダーに追跡プロファイルに Continuation フォルダーを追加することによって行われた呼び出し中にはです。</span><span class="sxs-lookup"><span data-stu-id="5c90e-107">The call to **EnableContinuation** is explicit, while calls in Orchestration1 and Orchestration2 are made by adding a Continuation folder to the Tracking profile in one schedule, and a ContinuationID folder to the schedule that follows it.</span></span>  
  
 <span data-ttu-id="5c90e-108">次の図は、このサンプルのワークフローを示します。</span><span class="sxs-lookup"><span data-stu-id="5c90e-108">The following diagram illustrates the workflow used in the sample.</span></span>  
  
 ![](../core/media/ebiz-sdk-samples-bam-endtoendwkflw.gif "ebiz_sdk_samples_bam_endtoendwkflw")  

  
## <a name="what-this-sample-does"></a><span data-ttu-id="5c90e-109">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="5c90e-109">What This Sample Does</span></span>  
 <span data-ttu-id="5c90e-110">BAM End-to-End サンプルでは、BAM を使用し、1 つのパイプラインと複数のオーケストレーションから情報を収集して単一のアクティビティを更新する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5c90e-110">The BAM end-to-end sample shows how you can use BAM to gather information from a pipeline and multiple orchestrations and update a single activity.</span></span>  
  
## <a name="how-this-sample-was-designed-and-why"></a><span data-ttu-id="5c90e-111">このサンプルをデザインした方法とその理由</span><span class="sxs-lookup"><span data-stu-id="5c90e-111">How This Sample Was Designed and Why</span></span>  
 <span data-ttu-id="5c90e-112">BAM End-to-End サンプルは、次のアクティビティを示すようにデザインされています。</span><span class="sxs-lookup"><span data-stu-id="5c90e-112">The BAM end-to-end sample was designed to illustrate the following activities:</span></span>  
  
-   <span data-ttu-id="5c90e-113">パイプライン内の BAM の使用</span><span class="sxs-lookup"><span data-stu-id="5c90e-113">Using BAM within a pipeline.</span></span>  
  
-   <span data-ttu-id="5c90e-114">追跡プロファイル エディター (TPE) を使用したオーケストレーション内の図形とメッセージの要素へのアクティビティ項目のマップ</span><span class="sxs-lookup"><span data-stu-id="5c90e-114">Using the Tracking Profile Editor (TPE) to map activity items to shapes in an orchestration and elements of a message.</span></span>  
  
-   <span data-ttu-id="5c90e-115">複数のソリューションがアクティビティに関連する場合における、Continuation を使用したアクティビティのアクティブ状態の維持</span><span class="sxs-lookup"><span data-stu-id="5c90e-115">Using continuations to keep an activity active when multiple pieces of a solution contribute to the activity.</span></span>  
  

<span data-ttu-id="5c90e-116">このサンプルの動作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5c90e-116">The sample works as follows:</span></span>  
  
1.  <span data-ttu-id="5c90e-117">入力メッセージを取得、 *\<サンプル パス >*\BamEndToEnd\Input フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="5c90e-117">An input message is retrieved from the *\<Samples Path>*\BamEndToEnd\Input folder.</span></span>  
  
2.  <span data-ttu-id="5c90e-118">パイプライン コンポーネントによって、一意の DocumentID がメッセージに割り当てられ、BAM API を使用して新しい BAM アクティビティが開始されます。</span><span class="sxs-lookup"><span data-stu-id="5c90e-118">The pipeline component assigns a unique DocumentID to the message, and uses the BAM API to begin a new BAM activity.</span></span> <span data-ttu-id="5c90e-119">オーケストレーションで利用できるように、入力メッセージの個別の部分として DocumentID が添付されます。</span><span class="sxs-lookup"><span data-stu-id="5c90e-119">The DocumentID is attached as a separate part of the input message to make it available to the orchestrations.</span></span>  
  
3.  <span data-ttu-id="5c90e-120">入力メッセージが受信されると、サービス Orchestration1 がアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="5c90e-120">The service Orchestration1 is activated when the input message is received.</span></span>  
  
4.  <span data-ttu-id="5c90e-121">Orchestration1 によって入力メッセージが変更され、パラメーターとして Orchestration2 に渡されます。</span><span class="sxs-lookup"><span data-stu-id="5c90e-121">Orchestration1 modifies the input message and passes it as a parameter to Orchestration2.</span></span>  
  
5.  <span data-ttu-id="5c90e-122">Orchestration2 によって入力メッセージが変更され、Orchestration3 をアクティブ化するメッセージ ボックス データベースに送信されます。</span><span class="sxs-lookup"><span data-stu-id="5c90e-122">Orchestration2 modifies the input message and sends it to the MessageBox database, which activates Orchestration3.</span></span>  
  
6.  <span data-ttu-id="5c90e-123">Orchestration3 によってメッセージが変更され、フォルダーに書き込まれます*\<サンプル パス >*\BamEndToEnd\Output です。</span><span class="sxs-lookup"><span data-stu-id="5c90e-123">Orchestration3 modifies the message and writes it to the folder *\<Samples Path>*\BamEndToEnd\Output.</span></span>  
  
7.  <span data-ttu-id="5c90e-124">各オーケストレーションによって BAM アクティビティ内のアクティビティ項目が更新されます。</span><span class="sxs-lookup"><span data-stu-id="5c90e-124">Each orchestration updates activity items in the BAM activity.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="5c90e-125">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="5c90e-125">Where to Find This Sample</span></span>  
 <span data-ttu-id="5c90e-126">このサンプルを見つけることができます*\<サンプル パス >*\BAM\BamEndToEnd です。</span><span class="sxs-lookup"><span data-stu-id="5c90e-126">You can find this sample at *\<Samples Path>*\BAM\BamEndToEnd.</span></span>  
  
 <span data-ttu-id="5c90e-127">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="5c90e-127">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="5c90e-128">ファイル</span><span class="sxs-lookup"><span data-stu-id="5c90e-128">File(s)</span></span>|<span data-ttu-id="5c90e-129">Description</span><span class="sxs-lookup"><span data-stu-id="5c90e-129">Description</span></span>|  
|----|---|  
|<span data-ttu-id="5c90e-130">BamEndToEnd.sln</span><span class="sxs-lookup"><span data-stu-id="5c90e-130">BamEndToEnd.sln</span></span>|<span data-ttu-id="5c90e-131">BAM End-to-End サンプル ソリューション。</span><span class="sxs-lookup"><span data-stu-id="5c90e-131">BAM End-to-End sample solution.</span></span>|  
|<span data-ttu-id="5c90e-132">BamEndToEnd.xls</span><span class="sxs-lookup"><span data-stu-id="5c90e-132">BamEndToEnd.xls</span></span>|<span data-ttu-id="5c90e-133">BAM 定義スタイルシート。</span><span class="sxs-lookup"><span data-stu-id="5c90e-133">BAM definition style sheet.</span></span>|  
|<span data-ttu-id="5c90e-134">BamEndToEnd.xml</span><span class="sxs-lookup"><span data-stu-id="5c90e-134">BamEndToEnd.xml</span></span>|<span data-ttu-id="5c90e-135">BAM 定義 XML。</span><span class="sxs-lookup"><span data-stu-id="5c90e-135">BAM definition XML.</span></span>|  
|<span data-ttu-id="5c90e-136">BAMEndToEndBinding.xml</span><span class="sxs-lookup"><span data-stu-id="5c90e-136">BAMEndToEndBinding.xml</span></span>|<span data-ttu-id="5c90e-137">BAM バインド。</span><span class="sxs-lookup"><span data-stu-id="5c90e-137">BAM binding.</span></span>|  
|<span data-ttu-id="5c90e-138">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="5c90e-138">Cleanup.bat</span></span>|<span data-ttu-id="5c90e-139">サンプルの展開解除を行うバッチ ファイル。</span><span class="sxs-lookup"><span data-stu-id="5c90e-139">Batch file to undeploy the sample.</span></span>|  
|<span data-ttu-id="5c90e-140">InputMessage.xml</span><span class="sxs-lookup"><span data-stu-id="5c90e-140">InputMessage.xml</span></span>|<span data-ttu-id="5c90e-141">入力メッセージ。</span><span class="sxs-lookup"><span data-stu-id="5c90e-141">Input message.</span></span>|  
|<span data-ttu-id="5c90e-142">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="5c90e-142">Setup.bat</span></span>|<span data-ttu-id="5c90e-143">サンプルをコンパイルし、展開するバッチ ファイル。</span><span class="sxs-lookup"><span data-stu-id="5c90e-143">Batch file to compile and deploy the sample.</span></span>|  
|<span data-ttu-id="5c90e-144">\Components\AssemblyInfo.cs</span><span class="sxs-lookup"><span data-stu-id="5c90e-144">\Components\AssemblyInfo.cs</span></span>|<span data-ttu-id="5c90e-145">パイプライン コンポーネント コード。</span><span class="sxs-lookup"><span data-stu-id="5c90e-145">Pipeline component code.</span></span>|  
|<span data-ttu-id="5c90e-146">\Components\BAMMessagePartPLComponent.cs</span><span class="sxs-lookup"><span data-stu-id="5c90e-146">\Components\BAMMessagePartPLComponent.cs</span></span>|<span data-ttu-id="5c90e-147">パイプライン コンポーネント コード。</span><span class="sxs-lookup"><span data-stu-id="5c90e-147">Pipeline component code.</span></span>|  
|<span data-ttu-id="5c90e-148">\Components\Components.csproj</span><span class="sxs-lookup"><span data-stu-id="5c90e-148">\Components\Components.csproj</span></span>|<span data-ttu-id="5c90e-149">パイプライン コンポーネント プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="5c90e-149">Pipeline component project.</span></span>|  
|<span data-ttu-id="5c90e-150">\Messages\InputMessage01.xml</span><span class="sxs-lookup"><span data-stu-id="5c90e-150">\Messages\InputMessage01.xml</span></span><br /><br /> <span data-ttu-id="5c90e-151">[...]</span><span class="sxs-lookup"><span data-stu-id="5c90e-151">...</span></span><br /><br /> <span data-ttu-id="5c90e-152">\Messages\InputMessage10.xml</span><span class="sxs-lookup"><span data-stu-id="5c90e-152">\Messages\InputMessage10.xml</span></span>|<span data-ttu-id="5c90e-153">サンプル入力メッセージ。</span><span class="sxs-lookup"><span data-stu-id="5c90e-153">Sample input messages.</span></span>|  
|<span data-ttu-id="5c90e-154">\Services\BAMInbound.btp</span><span class="sxs-lookup"><span data-stu-id="5c90e-154">\Services\BAMInbound.btp</span></span>|<span data-ttu-id="5c90e-155">受信パイプライン ファイル。</span><span class="sxs-lookup"><span data-stu-id="5c90e-155">Inbound pipeline file.</span></span>|  
|<span data-ttu-id="5c90e-156">\Services\BAMPartSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="5c90e-156">\Services\BAMPartSchema.xsd</span></span>|<span data-ttu-id="5c90e-157">BAM パート メッセージ スキーマ。</span><span class="sxs-lookup"><span data-stu-id="5c90e-157">BAM part message schema.</span></span>|  
|<span data-ttu-id="5c90e-158">\Services\Orchestration1.odx</span><span class="sxs-lookup"><span data-stu-id="5c90e-158">\Services\Orchestration1.odx</span></span>|<span data-ttu-id="5c90e-159">オーケストレーション。</span><span class="sxs-lookup"><span data-stu-id="5c90e-159">Orchestration.</span></span>|  
|<span data-ttu-id="5c90e-160">\Services\Orchestration2.odx</span><span class="sxs-lookup"><span data-stu-id="5c90e-160">\Services\Orchestration2.odx</span></span>|<span data-ttu-id="5c90e-161">オーケストレーション。</span><span class="sxs-lookup"><span data-stu-id="5c90e-161">Orchestration.</span></span>|  
|<span data-ttu-id="5c90e-162">\Services\Orchestration3.odx</span><span class="sxs-lookup"><span data-stu-id="5c90e-162">\Services\Orchestration3.odx</span></span>|<span data-ttu-id="5c90e-163">オーケストレーション。</span><span class="sxs-lookup"><span data-stu-id="5c90e-163">Orchestration.</span></span>|  
|<span data-ttu-id="5c90e-164">\Services\PropertySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="5c90e-164">\Services\PropertySchema.xsd</span></span>|<span data-ttu-id="5c90e-165">プロパティ スキーマ : </span><span class="sxs-lookup"><span data-stu-id="5c90e-165">Property schema.</span></span>|  
|<span data-ttu-id="5c90e-166">\Services\Schema1.xsd</span><span class="sxs-lookup"><span data-stu-id="5c90e-166">\Services\Schema1.xsd</span></span>|<span data-ttu-id="5c90e-167">メッセージ スキーマ。</span><span class="sxs-lookup"><span data-stu-id="5c90e-167">Message schema.</span></span>|  
|<span data-ttu-id="5c90e-168">\Services\Schema2.xsd</span><span class="sxs-lookup"><span data-stu-id="5c90e-168">\Services\Schema2.xsd</span></span>|<span data-ttu-id="5c90e-169">メッセージ スキーマ。</span><span class="sxs-lookup"><span data-stu-id="5c90e-169">Message schema.</span></span>|  
<span data-ttu-id="5c90e-170">Services\Schema3.xsd</span><span class="sxs-lookup"><span data-stu-id="5c90e-170">Services\Schema3.xsd</span></span>|<span data-ttu-id="5c90e-171">メッセージ スキーマ。</span><span class="sxs-lookup"><span data-stu-id="5c90e-171">Message schema.</span></span>|  
|<span data-ttu-id="5c90e-172">\Services\Services.btproj</span><span class="sxs-lookup"><span data-stu-id="5c90e-172">\Services\Services.btproj</span></span>|[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]<span data-ttu-id="5c90e-173"> BizTalk ファイル プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="5c90e-173"> BizTalk file project.</span></span>|  
|<span data-ttu-id="5c90e-174">\Services\Transform_1.btm</span><span class="sxs-lookup"><span data-stu-id="5c90e-174">\Services\Transform_1.btm</span></span>|<span data-ttu-id="5c90e-175">マップ ファイル。</span><span class="sxs-lookup"><span data-stu-id="5c90e-175">Map file.</span></span>|  
|<span data-ttu-id="5c90e-176">\Services\Transform_2.btm</span><span class="sxs-lookup"><span data-stu-id="5c90e-176">\Services\Transform_2.btm</span></span>|<span data-ttu-id="5c90e-177">マップ ファイル。</span><span class="sxs-lookup"><span data-stu-id="5c90e-177">Map file.</span></span>|  
|<span data-ttu-id="5c90e-178">\Services\Transform_3.btm</span><span class="sxs-lookup"><span data-stu-id="5c90e-178">\Services\Transform_3.btm</span></span>|<span data-ttu-id="5c90e-179">マップ ファイル。</span><span class="sxs-lookup"><span data-stu-id="5c90e-179">Map file.</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="5c90e-180">このサンプルの使用方法</span><span class="sxs-lookup"><span data-stu-id="5c90e-180">How to Use This Sample</span></span>  
 <span data-ttu-id="5c90e-181">次の手順を使用して、BAM End-to-End サンプルをビルドおよび実行します。</span><span class="sxs-lookup"><span data-stu-id="5c90e-181">Use the following procedures to build and run the BAM End-to-End sample:</span></span>  
  
-   [<span data-ttu-id="5c90e-182">このサンプルをビルドして初期化</span><span class="sxs-lookup"><span data-stu-id="5c90e-182">To build and initialize this sample</span></span>](#To_Build_Sample)  
  
-   [<span data-ttu-id="5c90e-183">このサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="5c90e-183">To run this sample</span></span>](#To_Run_Sample)  
  
-   [<span data-ttu-id="5c90e-184">BAM データを表示するには</span><span class="sxs-lookup"><span data-stu-id="5c90e-184">To view the BAM data</span></span>](#To_View_Data)  
  
##  <span data-ttu-id="5c90e-185"><a name="To_Build_Sample"></a>ビルドおよび初期化するこのサンプル</span><span class="sxs-lookup"><span data-stu-id="5c90e-185"><a name="To_Build_Sample"></a>Build and initialize this sample</span></span>  
  
1.  <span data-ttu-id="5c90e-186">管理者は、コマンド プロンプトを開き、実行*\<サンプル パス >*\BAM\BAMEndToEnd\Setup.bat です。</span><span class="sxs-lookup"><span data-stu-id="5c90e-186">Open a command prompt as Administrator, and run *\<Samples Path>*\BAM\BAMEndToEnd\Setup.bat.</span></span> <span data-ttu-id="5c90e-187">Setup.bat は、このサンプルの BAM インフラストラクチャをビルドして初期化します。</span><span class="sxs-lookup"><span data-stu-id="5c90e-187">Setup.bat builds and initializes the BAM infrastructure for this sample.</span></span> <span data-ttu-id="5c90e-188">コマンド プロンプトは開いたままにします。</span><span class="sxs-lookup"><span data-stu-id="5c90e-188">Keep the command prompt open.</span></span>  
  
2.  <span data-ttu-id="5c90e-189">Orchestration1、Orchestration2、および Orchestration3 を BAM アクティビティにマップするための追跡プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="5c90e-189">Create a tracking profile to map Orchestration1, Orchestration2, and Orchestration3 to the BAM activity.</span></span> <span data-ttu-id="5c90e-190">(という別の手順の方法の詳細については、追跡プロファイルの作成は複雑なプロセスなので**追跡プロファイルを作成する**です。</span><span class="sxs-lookup"><span data-stu-id="5c90e-190">(Because creating the tracking profile is a complex process, the detailed instructions are in a separate procedure called **To create a tracking profile**.</span></span> <span data-ttu-id="5c90e-191">この手順については、このドキュメントの後半で説明します)。</span><span class="sxs-lookup"><span data-stu-id="5c90e-191">This procedure appears later in this document.)</span></span>  
  
3.  <span data-ttu-id="5c90e-192">前の手順で作成した追跡プロファイル BamEndToEnd.btt を展開します。</span><span class="sxs-lookup"><span data-stu-id="5c90e-192">Deploy the tracking profile BamEndToEnd.btt that you created in the previous step.</span></span>  <span data-ttu-id="5c90e-193">コマンド プロンプトでを変更、 *\<サンプル パス >*\BAM\BamEndToEnd ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="5c90e-193">In the command prompt change to the *\<Samples Path>*\BAM\BamEndToEnd directory.</span></span> <span data-ttu-id="5c90e-194">追跡プロファイルを展開する次の行を入力し、キーを押します**Enter**:</span><span class="sxs-lookup"><span data-stu-id="5c90e-194">To deploy the tracking profile, type the following line, and then press **Enter**:</span></span>  
  
    `“<BizTalkInstallationPath>\Tracking\bttdeploy” BamEndToEnd.btt`
  
     <span data-ttu-id="5c90e-195">[追跡プロファイル管理ユーティリティを使って追跡プロファイルを展開する方法](../core/how-to-deploy-tracking-profiles-with-the-tracking-profiles-management-utility.md)詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="5c90e-195">[How to Deploy Tracking Profiles with the Tracking Profiles Management Utility](../core/how-to-deploy-tracking-profiles-with-the-tracking-profiles-management-utility.md) provides more information.</span></span>
  
    > [!IMPORTANT]
    >  <span data-ttu-id="5c90e-196">ContinuationID Orch1_ に一致する Continuation がないことを示すメッセージは無視できます。</span><span class="sxs-lookup"><span data-stu-id="5c90e-196">You can ignore the message that the ContinuationID Orch1_ does not have a matching Continuation.</span></span> <span data-ttu-id="5c90e-197">Orch1_ という名前の Continuation は追跡プロファイルではなくパイプライン コンポーネントで定義されているので、このメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5c90e-197">This message is expected, because the continuation named Orch1_ is defined in the pipeline component, and not in the tracking profile.</span></span>  
  
##  <span data-ttu-id="5c90e-198"><a name="To_Run_Sample"></a>このサンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="5c90e-198"><a name="To_Run_Sample"></a>Run this sample</span></span>  
  
<span data-ttu-id="5c90e-199">ファイルをコピー *\<サンプル パス >*フォルダーに \BamEndToEnd\InputMessage.xml *\<サンプル パス >*\BamEndToEnd\Input です。</span><span class="sxs-lookup"><span data-stu-id="5c90e-199">Copy the file *\<Samples Path>*\BamEndToEnd\InputMessage.xml into the folder *\<Samples Path>*\BamEndToEnd\Input.</span></span> <span data-ttu-id="5c90e-200">Input フォルダーから、数秒後に、メッセージが表示されなくなります、出力メッセージが表示されます、 *\<サンプル パス >*\BamEndToEnd\Output フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="5c90e-200">After a few seconds, the message disappears from the Input folder, and an output message appears in the *\<Samples Path>*\BamEndToEnd\Output folder.</span></span>  
  
##  <span data-ttu-id="5c90e-201"><a name="To_View_Data"></a>BAM データを表示します。</span><span class="sxs-lookup"><span data-stu-id="5c90e-201"><a name="To_View_Data"></a>View the BAM data</span></span>  
  
1.  <span data-ttu-id="5c90e-202">SQL Server Management Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="5c90e-202">Open SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="5c90e-203">SQL Server Management Studio で、サーバーを展開し、**データベース**、展開**BAMPrimaryImport**の順に展開および**テーブル**です。</span><span class="sxs-lookup"><span data-stu-id="5c90e-203">In SQL Server Management Studio, expand the server, expand **Databases**, expand **BAMPrimaryImport**, and then expand **Tables**.</span></span>  
  
3.  <span data-ttu-id="5c90e-204">右クリック**dbo.bam_EndToEndActivity_Completed**、クリックして**テーブルを開く**です。</span><span class="sxs-lookup"><span data-stu-id="5c90e-204">Right-click **dbo.bam_EndToEndActivity_Completed**, and then click **Open Table**.</span></span> <span data-ttu-id="5c90e-205">使用している場合[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]をクリックして**上位 1000 行を選択して**です。</span><span class="sxs-lookup"><span data-stu-id="5c90e-205">If you are using [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)], click **Select top 1000 rows**.</span></span>  
  
     <span data-ttu-id="5c90e-206">bam_EndToEndActivity_Completed テーブルの内容が右ペインに表示されます。</span><span class="sxs-lookup"><span data-stu-id="5c90e-206">The contents of the bam_EndToEndActivity_Completed table are displayed in the right pane.</span></span> <span data-ttu-id="5c90e-207">このテーブルの各行は、完了した EndToEndActivity アクティビティを表します。</span><span class="sxs-lookup"><span data-stu-id="5c90e-207">Each row in the table represents an EndToEndActivity activity that has been completed.</span></span>  
  
#### <a name="rerun-this-sample"></a><span data-ttu-id="5c90e-208">このサンプルを再実行します。</span><span class="sxs-lookup"><span data-stu-id="5c90e-208">Rerun this sample</span></span>  
  
1.  <span data-ttu-id="5c90e-209">管理者は、コマンド プロンプトを開き、変更、 *\<サンプル パス >*\BAM\BamEndToEnd ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="5c90e-209">Open a command prompt as Administrator, and change to the *\<Samples Path>*\BAM\BamEndToEnd directory.</span></span> <span data-ttu-id="5c90e-210">次の行を入力します。</span><span class="sxs-lookup"><span data-stu-id="5c90e-210">Type the following line:</span></span>  
  
    `“C:\Program Files\Microsoft BizTalk Server <version>\Tracking\bttdeploy” BamEndToEnd.btt /remove`  
  
    > [!NOTE]
    >  <span data-ttu-id="5c90e-211">インストールしていない場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]C ドライブにインストールしたドライブ文字"C"を置き換えます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="5c90e-211">If you did not install [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to the C drive, replace "C" with the drive letter where you installed [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="5c90e-212">実行*\<サンプル パス >*\BAM\BAMEndToEnd\Cleanup.bat です。</span><span class="sxs-lookup"><span data-stu-id="5c90e-212">Run *\<Samples Path>*\BAM\BAMEndToEnd\Cleanup.bat.</span></span> <span data-ttu-id="5c90e-213">Cleanup.bat は、このサンプルの BAM インフラストラクチャを削除します。</span><span class="sxs-lookup"><span data-stu-id="5c90e-213">Cleanup.bat removes the BAM infrastructure for this sample.</span></span>  
  
3.  <span data-ttu-id="5c90e-214">手順に従います**このサンプルをビルドして初期化**」セクションを参照します。</span><span class="sxs-lookup"><span data-stu-id="5c90e-214">Perform the steps in **To build and initialize this sample** section in this topic.</span></span>  
  
##  <span data-ttu-id="5c90e-215"><a name="TPE_procedure"></a>追跡プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="5c90e-215"><a name="TPE_procedure"></a>Create a tracking profile</span></span>  
  
1.  <span data-ttu-id="5c90e-216">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="5c90e-216">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)].</span></span> <span data-ttu-id="5c90e-217">右クリック**追跡プロファイル エディター**、および**管理者として実行**です。</span><span class="sxs-lookup"><span data-stu-id="5c90e-217">Right-click **Tracking Profile Editor**, and **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="5c90e-218">左側のウィンドウで、**追跡プロファイル エディター**ウィンドウで、をクリックして**ここをクリックして、BAM アクティビティ定義をインポートする**です。</span><span class="sxs-lookup"><span data-stu-id="5c90e-218">In the left pane of the **Tracking Profile Editor** window, click **Click here to import a BAM Activity Definition**.</span></span>  
  
3.  <span data-ttu-id="5c90e-219">**BAM アクティビティ定義名**のセクションで、 **BAM アクティビティ定義のインポート**ダイアログ ボックスで、 **[endtoendactivity]**、クリックして**[ok]**.</span><span class="sxs-lookup"><span data-stu-id="5c90e-219">In the  **BAM Activity Definition Name** section of the **Import BAM Activity Definition** dialog box, select **EndToEndActivity**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="5c90e-220">右側のペインで、**追跡プロファイル エディター**ウィンドウで、をクリックして**ここをクリックすると、イベント ソースを選択する**です。</span><span class="sxs-lookup"><span data-stu-id="5c90e-220">In the right pane of the **Tracking Profile Editor** window, click **Click here to select an event source**.</span></span>  
  
5.  <span data-ttu-id="5c90e-221">**アセンブリ名**のセクションで、**イベント ソースの親アセンブリの選択**ダイアログ ボックスで、 **Microsoft.Samples.BizTalk.BamEndToEnd.Services**をクリックし、**次**です。</span><span class="sxs-lookup"><span data-stu-id="5c90e-221">In the **Assembly Name** section of the **Select Event Source Parent Assembly** dialog box, select **Microsoft.Samples.BizTalk.BamEndToEnd.Services**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="5c90e-222">**オーケストレーション名**のセクション、**オーケストレーションの選択**ダイアログ ボックスで、**で BamEndToEnd.Services.Orchestration1**、順にクリック**OK**.</span><span class="sxs-lookup"><span data-stu-id="5c90e-222">In the **Orchestration Name** section of the **Select Orchestration** dialog box, select **BamEndToEnd.Services.Orchestration1**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="5c90e-223">左側のウィンドウで、**追跡プロファイル エディター**ウィンドウを右クリックして**endtoendactivity**、クリックして**新しい continuationid**です。</span><span class="sxs-lookup"><span data-stu-id="5c90e-223">In the left pane of the **Tracking Profile Editor** window, right-click **EndToEndActivity**, and then click **New ContinuationID**.</span></span> <span data-ttu-id="5c90e-224">新しい continuation ID の名前を付けます**orch1 _**です。</span><span class="sxs-lookup"><span data-stu-id="5c90e-224">Name the new continuation ID **Orch1_**.</span></span> <span data-ttu-id="5c90e-225">2 つの continuation Id という名前を作成するには、この手順を繰り返します**orch2 _**と**orch3 _**です。</span><span class="sxs-lookup"><span data-stu-id="5c90e-225">Repeat this step to create two more continuation IDs named **Orch2_** and **Orch3_**.</span></span>  
  
8.  <span data-ttu-id="5c90e-226">右クリック**[endtoendactivity]**、クリックして**新しい Continuation**です。</span><span class="sxs-lookup"><span data-stu-id="5c90e-226">Right-click **EndToEndActivity**, and then click **New Continuation**.</span></span> <span data-ttu-id="5c90e-227">新しい continuation の名前**orch2 _**です。</span><span class="sxs-lookup"><span data-stu-id="5c90e-227">Name the new continuation **Orch2_**.</span></span> <span data-ttu-id="5c90e-228">という continuation も作成するには、この手順を繰り返します**orch3 _**です。</span><span class="sxs-lookup"><span data-stu-id="5c90e-228">Repeat this step to create another continuation named **Orch3_**.</span></span>  
  
9. <span data-ttu-id="5c90e-229">右クリックし、 **Receive1**図形をクリックして**コンテキスト プロパティ スキーマ**です。</span><span class="sxs-lookup"><span data-stu-id="5c90e-229">Right-click the **Receive1** shape, and then click **Context Property Schemas**.</span></span>  
  
10. <span data-ttu-id="5c90e-230">末尾にスクロール、**コンテキスト プロパティ名**、一覧表示し、ダブルクリック**BAMEndToEnd.Services.PropertySchema.DocumentID**です。</span><span class="sxs-lookup"><span data-stu-id="5c90e-230">Scroll to the end of the **Context Property Name** list, and then double-click **BAMEndToEnd.Services.PropertySchema.DocumentID**.</span></span>  
  
11. <span data-ttu-id="5c90e-231">展開**\<スキーマ >**、し、ドラッグ**DocumentID**を右側のウィンドウで**orch1 _**左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="5c90e-231">Expand **\<Schema>**, and then drag **DocumentID** in the right pane to **Orch1_** in the left pane.</span></span>  
  
12. <span data-ttu-id="5c90e-232">矢印の付いたフォルダー アイコンをクリックして (![フォルダーと上矢印ボタン](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4"))、オーケストレーションを表示するには、2 回クリックします。</span><span class="sxs-lookup"><span data-stu-id="5c90e-232">Click the folder icon with the arrow (![button with folder and up arrow](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4")) twice to display the orchestration.</span></span>  
  
13. <span data-ttu-id="5c90e-233">ドラッグ、 **Receive1**図形を右側のペインで**[sbegin1]**左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="5c90e-233">Drag the **Receive1** shape in the right pane to **SBegin1** in the left pane.</span></span>  
  
14. <span data-ttu-id="5c90e-234">ドラッグ、 **StartOrchestration_1**図形を右側のペインで**[send1]**左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="5c90e-234">Drag the **StartOrchestration_1** shape in the right pane to **SEnd1** in the left pane.</span></span>  
  
15. <span data-ttu-id="5c90e-235">右クリックし、 **StartOrchestration_1**図形をクリックして**メッセージ ペイロード スキーマ**です。</span><span class="sxs-lookup"><span data-stu-id="5c90e-235">Right-click the **StartOrchestration_1** shape, and then click **Message Payload Schemas**.</span></span>  
  
16. <span data-ttu-id="5c90e-236">値"Message_2"を含む行をダブルクリックして、**メッセージ**列と値"MessageBody"で、**一部**列です。</span><span class="sxs-lookup"><span data-stu-id="5c90e-236">Double-click the row that contains the value “Message_2” in the **Message** column and the value “MessageBody” in the **Part** column.</span></span>  
  
     <span data-ttu-id="5c90e-237">![TPE メッセージ ペイロード スキーマ メッセージ &#95; 2.](../core/media/77fbc444-46cf-4d45-8e9c-c330da7ba7d1.gif "77fbc444-46cf-4d45-8e9c-c330da7ba7d1")</span><span class="sxs-lookup"><span data-stu-id="5c90e-237">![TPE Message Payload schema showing message&#95;2](../core/media/77fbc444-46cf-4d45-8e9c-c330da7ba7d1.gif "77fbc444-46cf-4d45-8e9c-c330da7ba7d1")</span></span>  
  
17. <span data-ttu-id="5c90e-238">展開**Schema2**、し、ドラッグ**Data2**を右側のウィンドウで**Data1**左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="5c90e-238">Expand **Schema2**, and then drag **Data2** in the right pane to **Data1** in the left pane.</span></span>  
  
18. <span data-ttu-id="5c90e-239">をクリックして**イベント ソースの選択**、クリックして**コンテキスト プロパティの**します。</span><span class="sxs-lookup"><span data-stu-id="5c90e-239">Click **Select Event Source**, and then click **Select Context Property**.</span></span>  
  
19. <span data-ttu-id="5c90e-240">末尾にスクロール、**コンテキスト プロパティ名**、一覧表示し、ダブルクリック**BAMEndToEnd.Services.PropertySchema.DocumentID**です。</span><span class="sxs-lookup"><span data-stu-id="5c90e-240">Scroll to the end of the **Context Property Name** list, and then double-click **BAMEndToEnd.Services.PropertySchema.DocumentID**.</span></span>  
  
20. <span data-ttu-id="5c90e-241">展開**\<スキーマ >**、し、ドラッグ**DocumentID**を**orch2 _**左側のウィンドウで継続します。</span><span class="sxs-lookup"><span data-stu-id="5c90e-241">Expand **\<Schema>**, and then drag **DocumentID** to the **Orch2_** continuation in the left pane.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5c90e-242">Orch2_ Continuation と Orch2_ Continuation ID を混同しないように注意してください。</span><span class="sxs-lookup"><span data-stu-id="5c90e-242">Do not confuse the Orch2_ continuation with the Orch2_ continuation ID.</span></span> <span data-ttu-id="5c90e-243">Continuation ID を表すアイコンには、キーが含まれています (![continuation ID のアイコン](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea"))、continuation を表すアイコンには、キー (が含まれていません。![continuation のアイコン](../core/media/test.gif "テスト"))。</span><span class="sxs-lookup"><span data-stu-id="5c90e-243">The icon that represents a continuation ID contains a key (![icon for a continuation ID](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea")), whereas the icon that represents a continuation does not contain a key (![icon for a continuation](../core/media/test.gif "test")).</span></span>  
  
21. <span data-ttu-id="5c90e-244">をクリックして**イベント ソースの選択**、クリックして**オーケストレーション スケジュールの**します。</span><span class="sxs-lookup"><span data-stu-id="5c90e-244">Click **Select Event Source**, and then click **Select Orchestration Schedule**.</span></span>  
  
22. <span data-ttu-id="5c90e-245">**アセンブリ名**のセクションで、**イベント ソースの親アセンブリの選択**ダイアログ ボックスで、 **Microsoft.Samples.BizTalk.BamEndToEnd.Services**をクリックし、**次**です。</span><span class="sxs-lookup"><span data-stu-id="5c90e-245">In the **Assembly Name** section of the **Select Event Source Parent Assembly** dialog box, select **Microsoft.Samples.BizTalk.BamEndToEnd.Services**, and then click **Next**.</span></span>  
  
23. <span data-ttu-id="5c90e-246">**オーケストレーション名**のセクション、**オーケストレーションの選択**ダイアログ ボックスで、**で BamEndToEnd.Services.Orchestration2**、順にクリック**OK**.</span><span class="sxs-lookup"><span data-stu-id="5c90e-246">In the **Orchestration Name** section of the **Select Orchestration** dialog box, select **BamEndToEnd.Services.Orchestration2**, and then click **OK**.</span></span>  
  
24. <span data-ttu-id="5c90e-247">右クリックし、 **ConstructMessage_1**図形をクリックして**メッセージ ペイロード スキーマ**です。</span><span class="sxs-lookup"><span data-stu-id="5c90e-247">Right-click the **ConstructMessage_1** shape, and then click **Message Payload Schemas**.</span></span>  
  
25. <span data-ttu-id="5c90e-248">値"Message_3"を含む行をダブルクリックして、**メッセージ**列と値に"BAMPart"で、**一部**列です。</span><span class="sxs-lookup"><span data-stu-id="5c90e-248">Double-click the row that contains the value “Message_3” in the **Message** column and the value “BAMPart” in the **Part** column.</span></span>  
  
26. <span data-ttu-id="5c90e-249">展開**BAMPart**、し、ドラッグ**DocumentID**を右側のウィンドウで、 **orch2 _**左側のウィンドウで continuation ID。</span><span class="sxs-lookup"><span data-stu-id="5c90e-249">Expand **BAMPart**, and then drag **DocumentID** in the right pane to the **Orch2_** continuation ID in the left pane.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5c90e-250">Orch2_ Continuation と Orch2_ Continuation ID を混同しないように注意してください。</span><span class="sxs-lookup"><span data-stu-id="5c90e-250">Do not confuse the Orch2_ continuation with the Orch2_ continuation ID.</span></span> <span data-ttu-id="5c90e-251">Continuation ID を表すアイコンには、キーが含まれています (![continuation ID のアイコン](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea"))、continuation を表すアイコンには、キー (が含まれていません。![continuation のアイコン](../core/media/test.gif "テスト"))。</span><span class="sxs-lookup"><span data-stu-id="5c90e-251">The icon that represents a continuation ID contains a key (![icon for a continuation ID](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea")), whereas the icon that represents a continuation does not contain a key (![icon for a continuation](../core/media/test.gif "test")).</span></span>  
  
27. <span data-ttu-id="5c90e-252">矢印の付いたフォルダー アイコンをクリックして (![フォルダーとし、上のボタン &#45; 矢印](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4"))、オーケストレーションを表示するには、2 回クリックします。</span><span class="sxs-lookup"><span data-stu-id="5c90e-252">Click the folder icon with the arrow (![button with folder and up&#45;arrow](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4")) twice to display the orchestration.</span></span>  
  
28. <span data-ttu-id="5c90e-253">ドラッグ、 **ConstructMessage_1**図形を右側のペインで**[sbegin2]**左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="5c90e-253">Drag the **ConstructMessage_1** shape in the right pane to **SBegin2** in the left pane.</span></span>  
  
29. <span data-ttu-id="5c90e-254">ドラッグ、 **Send_1**図形を右側のペインで**[send2]**左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="5c90e-254">Drag the **Send_1** shape in the right pane to **SEnd2** in the left pane.</span></span>  
  
30. <span data-ttu-id="5c90e-255">右クリックし、 **Send_1**図形をクリックして**メッセージ ペイロード スキーマ**です。</span><span class="sxs-lookup"><span data-stu-id="5c90e-255">Right-click the **Send_1** shape, and then click **Message Payload Schemas**.</span></span>  
  
31. <span data-ttu-id="5c90e-256">値"Message_3"を含む行をダブルクリックして、**メッセージ**列と値"MessageBody"で、**一部**列です。</span><span class="sxs-lookup"><span data-stu-id="5c90e-256">Double-click the row that contains the value “Message_3” in the **Message** column and the value “MessageBody” in the **Part** column.</span></span>  
  
32. <span data-ttu-id="5c90e-257">展開**Schema3**、し、ドラッグ**Data3**を右側のウィンドウで**Data2**左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="5c90e-257">Expand **Schema3**, and then drag **Data3** in the right pane to **Data2** in the left pane.</span></span>  
  
33. <span data-ttu-id="5c90e-258">右側のペインの上にドロップ ダウン リストから選択**メッセージ ペイロード スキーマ**です。</span><span class="sxs-lookup"><span data-stu-id="5c90e-258">From the drop-down list above the right pane, select **Message Payload Schemas**.</span></span>  
  
34. <span data-ttu-id="5c90e-259">値"Message_3"を含む行をダブルクリックして、**メッセージ**列と値に"BAMPart"で、**一部**列です。</span><span class="sxs-lookup"><span data-stu-id="5c90e-259">Double-click the row that contains the value “Message_3” in the **Message** column and the value “BAMPart” in the **Part** column.</span></span>  
  
35. <span data-ttu-id="5c90e-260">展開**BAMPart**、し、ドラッグ**DocumentID**を右側のウィンドウで、 **orch3 _**左側のウィンドウで継続します。</span><span class="sxs-lookup"><span data-stu-id="5c90e-260">Expand **BAMPart**, and then drag **DocumentID** in the right pane to the **Orch3_** continuation in the left pane.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5c90e-261">Orch3_ Continuation と Orch3_ Continuation ID を混同しないように注意してください。</span><span class="sxs-lookup"><span data-stu-id="5c90e-261">Do not confuse the Orch3_ continuation with the Orch3_ continuation ID.</span></span> <span data-ttu-id="5c90e-262">Continuation ID を表すアイコンには、キーが含まれています (![continuation ID のアイコン](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea"))、continuation を表すアイコンには、キー (が含まれていません。![continuation のアイコン](../core/media/test.gif "テスト"))。</span><span class="sxs-lookup"><span data-stu-id="5c90e-262">The icon that represents a continuation ID contains a key (![icon for a continuation ID](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea")), whereas the icon that represents a continuation does not contain a key (![icon for a continuation](../core/media/test.gif "test")).</span></span>  
  
36. <span data-ttu-id="5c90e-263">をクリックして**イベント ソースの選択**、クリックして**オーケストレーション スケジュールの**します。</span><span class="sxs-lookup"><span data-stu-id="5c90e-263">Click **Select Event Source**, and then click **Select Orchestration Schedule**.</span></span>  
  
37. <span data-ttu-id="5c90e-264">**アセンブリ名**のセクションで、**イベント ソースの親アセンブリの選択**ダイアログ ボックスで、 **Microsoft.Samples.BizTalk.BamEndToEnd.Services**をクリックし、**次**です。</span><span class="sxs-lookup"><span data-stu-id="5c90e-264">In the **Assembly Name** section of the **Select Event Source Parent Assembly** dialog box, select **Microsoft.Samples.BizTalk.BamEndToEnd.Services**, and then click **Next**.</span></span>  
  
38. <span data-ttu-id="5c90e-265">**オーケストレーション名**のセクション、**オーケストレーションの選択**ダイアログ ボックスで、**で BamEndToEnd.Services.Orchestration3**、順にクリック**OK**.</span><span class="sxs-lookup"><span data-stu-id="5c90e-265">In the **Orchestration Name** section of the **Select Orchestration** dialog box, select **BamEndToEnd.Services.Orchestration3**, and then click **OK**.</span></span>  
  
39. <span data-ttu-id="5c90e-266">右クリックし、 **Receive1**図形をクリックして**メッセージ ペイロード スキーマ**です。</span><span class="sxs-lookup"><span data-stu-id="5c90e-266">Right-click the **Receive1** shape, and then click **Message Payload Schemas**.</span></span>  
  
40. <span data-ttu-id="5c90e-267">値"Message_3"を含む行をダブルクリックして、**メッセージ**列と値に"BAMPart"で、**一部**列です。</span><span class="sxs-lookup"><span data-stu-id="5c90e-267">Double-click the row that contains the value “Message_3” in the **Message** column and the value “BAMPart” in the **Part** column.</span></span>  
  
41. <span data-ttu-id="5c90e-268">展開**BAMPart**、し、ドラッグ**DocumentID**を右側のウィンドウで、 **orch3 _**左側のウィンドウで continuation ID。</span><span class="sxs-lookup"><span data-stu-id="5c90e-268">Expand **BAMPart**, and then drag **DocumentID** in the right pane to the **Orch3_** continuation ID in the left pane.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5c90e-269">Orch3_ Continuation と Orch3_ Continuation ID を混同しないように注意してください。</span><span class="sxs-lookup"><span data-stu-id="5c90e-269">Do not confuse the Orch3_ continuation with the Orch3_ continuation ID.</span></span> <span data-ttu-id="5c90e-270">Continuation ID を表すアイコンには、キーが含まれています (![continuation ID のアイコン](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea"))、continuation を表すアイコンには、キー (が含まれていません。![continuation のアイコン](../core/media/test.gif "テスト"))。</span><span class="sxs-lookup"><span data-stu-id="5c90e-270">The icon that represents a continuation ID contains a key (![icon for a continuation ID](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea")), whereas the icon that represents a continuation does not contain a key (![icon for a continuation](../core/media/test.gif "test")).</span></span>  
  
42. <span data-ttu-id="5c90e-271">矢印の付いたフォルダー アイコンをクリックして (![フォルダーと上矢印ボタン](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4"))、オーケストレーションを表示するには、2 回クリックします。</span><span class="sxs-lookup"><span data-stu-id="5c90e-271">Click the folder icon with the arrow (![button with folder and up arrow](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4")) twice to display the orchestration.</span></span>  
  
43. <span data-ttu-id="5c90e-272">ドラッグ、 **Receive1**図形を右側のペインで**[sbegin3]**左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="5c90e-272">Drag the **Receive1** shape in the right pane to **SBegin3** in the left pane.</span></span>  
  
44. <span data-ttu-id="5c90e-273">ドラッグ、 **Send_1**図形を右側のペインで**[send3]**左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="5c90e-273">Drag the **Send_1** shape in the right pane to **SEnd3** in the left pane.</span></span>  
  
45. <span data-ttu-id="5c90e-274">右クリックし、 **Send_1**図形をクリックして**メッセージ ペイロード スキーマ**です。</span><span class="sxs-lookup"><span data-stu-id="5c90e-274">Right-click the **Send_1** shape, and then click **Message Payload Schema**.</span></span>  
  
46. <span data-ttu-id="5c90e-275">展開**Schema3**、し、ドラッグ**Data3**を右側のウィンドウで**Data3**左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="5c90e-275">Expand **Schema3**, and then drag **Data3** in the right pane to **Data3** in the left pane.</span></span>  
  
47. <span data-ttu-id="5c90e-276">右クリック**DocumentID**下、 **orch2 _**継続をクリックして**ポート マッピング**です。</span><span class="sxs-lookup"><span data-stu-id="5c90e-276">Right-click **DocumentID** below the **Orch2_** continuation, and then click **Set Port Mappings**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5c90e-277">Orch2_ Continuation と Orch2_ Continuation ID を混同しないように注意してください。</span><span class="sxs-lookup"><span data-stu-id="5c90e-277">Do not confuse the Orch2_ continuation with the Orch2_ continuation ID.</span></span> <span data-ttu-id="5c90e-278">Continuation ID を表すアイコンには、キーが含まれています (![continuation ID のアイコン](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea"))、continuation を表すアイコンには、キー (が含まれていません。![continuation のアイコン](../core/media/test.gif "テスト"))。</span><span class="sxs-lookup"><span data-stu-id="5c90e-278">The icon that represents a continuation ID contains a key (![icon for a continuation ID](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea")), whereas the icon that represents a continuation does not contain a key (![icon for a continuation](../core/media/test.gif "test")).</span></span>  
  
48. <span data-ttu-id="5c90e-279">**ポートの選択**のセクションで、**ポートの選択**ダイアログ ボックスで、をクリックして**BamEndToEnd_ReceivePort**、大きい をクリックして-不等号 ( **>**)、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="5c90e-279">In the **Select Ports** section of the **Select Ports** dialog box, click **BamEndToEnd_ReceivePort**, click the greater-than sign (**>**), and then click **OK**.</span></span>  
  
49. <span data-ttu-id="5c90e-280">追跡プロファイルを保存*\<サンプル パス >*\BAM\BamEndToEnd\BamEndToEnd.btt です。</span><span class="sxs-lookup"><span data-stu-id="5c90e-280">Save the tracking profile to *\<Samples Path>*\BAM\BamEndToEnd\BamEndToEnd.btt.</span></span>  
  
## <a name="important-details"></a><span data-ttu-id="5c90e-281">重要な詳細情報</span><span class="sxs-lookup"><span data-stu-id="5c90e-281">Important details</span></span>  
 <span data-ttu-id="5c90e-282">追跡プロファイルは、パイプラインではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5c90e-282">Tracking profiles are not supported for pipelines.</span></span> <span data-ttu-id="5c90e-283">ただしへの呼び出し**BeginActivity**パイプライン コンポーネントは、同じようにオーケストレーションで ActivityID を使用します。</span><span class="sxs-lookup"><span data-stu-id="5c90e-283">However, the call to **BeginActivity** in the pipeline component is the same as using ActivityID in an orchestration.</span></span> <span data-ttu-id="5c90e-284">呼び出し**EnableContinuation**オーケストレーションでの continuation の使用と同じです。</span><span class="sxs-lookup"><span data-stu-id="5c90e-284">The call to **EnableContinuation** is the same as using a continuation in an orchestration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c90e-285">参照</span><span class="sxs-lookup"><span data-stu-id="5c90e-285">See Also</span></span>  
 [<span data-ttu-id="5c90e-286">ビジネス アクティビティ監視 (BizTalk Server Samples フォルダ)</span><span class="sxs-lookup"><span data-stu-id="5c90e-286">Business Activity Monitoring (BizTalk Server Samples Folder)</span></span>](../core/business-activity-monitoring-biztalk-server-samples-folder.md)