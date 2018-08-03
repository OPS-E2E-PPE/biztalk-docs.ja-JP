---
title: BizTalk Server で BAM エンド ツー エンドのサンプル |Microsoft Docs
description: BizTalk Server でビジネス アクティビティの監視を使用して複数のコンポーネントからイベントを関連付ける方法のシナリオ
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 81406038-7f3f-499f-a003-12423d92c44b
caps.latest.revision: 35
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fca4bd709a872df739d82fbdfbeabc78df9d09f0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006499"
---
# <a name="bam-end-to-end-biztalk-server-sample"></a><span data-ttu-id="a6adf-103">BAM End-to-End (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="a6adf-103">BAM End-to-End (BizTalk Server Sample)</span></span>
<span data-ttu-id="a6adf-104">エンド ツー エンドのサンプルでは、BAM を使用して (この場合、3 つのオーケストレーションおよびパイプライン) で複数のコンポーネントからのイベントを関連付ける方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-104">The End-to-End sample demonstrates how to correlate events from multiple components (in this case, three orchestrations and a pipeline) by using BAM.</span></span>  

 <span data-ttu-id="a6adf-105">BAM によって、パイプライン コンポーネントとオーケストレーションにまたがるビジネス アクティビティが再構築されます。</span><span class="sxs-lookup"><span data-stu-id="a6adf-105">BAM reconstructs the business activity that spans the pipeline component and orchestrations.</span></span> <span data-ttu-id="a6adf-106">最下位レベルでこの動作を呼び出して**EventStream.EnableContinuation**アクティビティの他のイベントが必要とする各実装コンポーネントから。</span><span class="sxs-lookup"><span data-stu-id="a6adf-106">At the lowest level, this works by calls to **EventStream.EnableContinuation** from each implementation component that expects more events for the activity.</span></span> <span data-ttu-id="a6adf-107">呼び出し**EnableContinuation**明示的な Orchestration1 と Orchestration2 が Continuation フォルダーを 1 つのスケジュールと後のスケジュールを ContinuationID フォルダーで追跡プロファイルに追加することで行われた呼び出し中にはです。</span><span class="sxs-lookup"><span data-stu-id="a6adf-107">The call to **EnableContinuation** is explicit, while calls in Orchestration1 and Orchestration2 are made by adding a Continuation folder to the Tracking profile in one schedule, and a ContinuationID folder to the schedule that follows it.</span></span>  

 <span data-ttu-id="a6adf-108">次の図は、このサンプルのワークフローを示します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-108">The following diagram illustrates the workflow used in the sample.</span></span>  

 <span data-ttu-id="a6adf-109">![](../core/media/ebiz-sdk-samples-bam-endtoendwkflw.gif "ebiz_sdk_samples_bam_endtoendwkflw")</span><span class="sxs-lookup"><span data-stu-id="a6adf-109">![](../core/media/ebiz-sdk-samples-bam-endtoendwkflw.gif "ebiz_sdk_samples_bam_endtoendwkflw")</span></span>  


## <a name="what-this-sample-does"></a><span data-ttu-id="a6adf-110">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="a6adf-110">What This Sample Does</span></span>  
 <span data-ttu-id="a6adf-111">BAM End-to-End サンプルでは、BAM を使用し、1 つのパイプラインと複数のオーケストレーションから情報を収集して単一のアクティビティを更新する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-111">The BAM end-to-end sample shows how you can use BAM to gather information from a pipeline and multiple orchestrations and update a single activity.</span></span>  

## <a name="how-this-sample-was-designed-and-why"></a><span data-ttu-id="a6adf-112">このサンプルをデザインした方法とその理由</span><span class="sxs-lookup"><span data-stu-id="a6adf-112">How This Sample Was Designed and Why</span></span>  
 <span data-ttu-id="a6adf-113">BAM End-to-End サンプルは、次のアクティビティを示すようにデザインされています。</span><span class="sxs-lookup"><span data-stu-id="a6adf-113">The BAM end-to-end sample was designed to illustrate the following activities:</span></span>  

-   <span data-ttu-id="a6adf-114">パイプライン内の BAM の使用</span><span class="sxs-lookup"><span data-stu-id="a6adf-114">Using BAM within a pipeline.</span></span>  

-   <span data-ttu-id="a6adf-115">追跡プロファイル エディター (TPE) を使用したオーケストレーション内の図形とメッセージの要素へのアクティビティ項目のマップ</span><span class="sxs-lookup"><span data-stu-id="a6adf-115">Using the Tracking Profile Editor (TPE) to map activity items to shapes in an orchestration and elements of a message.</span></span>  

-   <span data-ttu-id="a6adf-116">複数のソリューションがアクティビティに関連する場合における、Continuation を使用したアクティビティのアクティブ状態の維持</span><span class="sxs-lookup"><span data-stu-id="a6adf-116">Using continuations to keep an activity active when multiple pieces of a solution contribute to the activity.</span></span>  


<span data-ttu-id="a6adf-117">このサンプルの動作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a6adf-117">The sample works as follows:</span></span>  

1.  <span data-ttu-id="a6adf-118">入力メッセージがから取得した、 *\<サンプル パス\>* \BamEndToEnd\Input フォルダー。</span><span class="sxs-lookup"><span data-stu-id="a6adf-118">An input message is retrieved from the *\<Samples Path\>* \BamEndToEnd\Input folder.</span></span>  

2.  <span data-ttu-id="a6adf-119">パイプライン コンポーネントによって、一意の DocumentID がメッセージに割り当てられ、BAM API を使用して新しい BAM アクティビティが開始されます。</span><span class="sxs-lookup"><span data-stu-id="a6adf-119">The pipeline component assigns a unique DocumentID to the message, and uses the BAM API to begin a new BAM activity.</span></span> <span data-ttu-id="a6adf-120">オーケストレーションで利用できるように、入力メッセージの個別の部分として DocumentID が添付されます。</span><span class="sxs-lookup"><span data-stu-id="a6adf-120">The DocumentID is attached as a separate part of the input message to make it available to the orchestrations.</span></span>  

3.  <span data-ttu-id="a6adf-121">入力メッセージが受信されると、サービス Orchestration1 がアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="a6adf-121">The service Orchestration1 is activated when the input message is received.</span></span>  

4.  <span data-ttu-id="a6adf-122">Orchestration1 によって入力メッセージが変更され、パラメーターとして Orchestration2 に渡されます。</span><span class="sxs-lookup"><span data-stu-id="a6adf-122">Orchestration1 modifies the input message and passes it as a parameter to Orchestration2.</span></span>  

5.  <span data-ttu-id="a6adf-123">Orchestration2 によって入力メッセージが変更され、Orchestration3 をアクティブ化するメッセージ ボックス データベースに送信されます。</span><span class="sxs-lookup"><span data-stu-id="a6adf-123">Orchestration2 modifies the input message and sends it to the MessageBox database, which activates Orchestration3.</span></span>  

6.  <span data-ttu-id="a6adf-124">Orchestration3 のメッセージが変更され、フォルダーに書き込みます*\<サンプル パス\>* \BamEndToEnd\Output します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-124">Orchestration3 modifies the message and writes it to the folder *\<Samples Path\>* \BamEndToEnd\Output.</span></span>  

7.  <span data-ttu-id="a6adf-125">各オーケストレーションによって BAM アクティビティ内のアクティビティ項目が更新されます。</span><span class="sxs-lookup"><span data-stu-id="a6adf-125">Each orchestration updates activity items in the BAM activity.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="a6adf-126">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="a6adf-126">Where to Find This Sample</span></span>  
 <span data-ttu-id="a6adf-127">このサンプルで*\<サンプル パス\>* \BAM\BamEndToEnd します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-127">You can find this sample at *\<Samples Path\>* \BAM\BamEndToEnd.</span></span>  

 <span data-ttu-id="a6adf-128">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="a6adf-128">The following table shows the files in this sample and describes their purpose.</span></span>  


|                                        <span data-ttu-id="a6adf-129">ファイル</span><span class="sxs-lookup"><span data-stu-id="a6adf-129">File(s)</span></span>                                        |                                         <span data-ttu-id="a6adf-130">説明</span><span class="sxs-lookup"><span data-stu-id="a6adf-130">Description</span></span>                                          |
|---------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------|
|                                    <span data-ttu-id="a6adf-131">BamEndToEnd.sln</span><span class="sxs-lookup"><span data-stu-id="a6adf-131">BamEndToEnd.sln</span></span>                                    |                               <span data-ttu-id="a6adf-132">BAM End-to-End サンプル ソリューション。</span><span class="sxs-lookup"><span data-stu-id="a6adf-132">BAM End-to-End sample solution.</span></span>                                |
|                                    <span data-ttu-id="a6adf-133">BamEndToEnd.xls</span><span class="sxs-lookup"><span data-stu-id="a6adf-133">BamEndToEnd.xls</span></span>                                    |                                 <span data-ttu-id="a6adf-134">BAM 定義スタイルシート。</span><span class="sxs-lookup"><span data-stu-id="a6adf-134">BAM definition style sheet.</span></span>                                  |
|                                    <span data-ttu-id="a6adf-135">BamEndToEnd.xml</span><span class="sxs-lookup"><span data-stu-id="a6adf-135">BamEndToEnd.xml</span></span>                                    |                                     <span data-ttu-id="a6adf-136">BAM 定義 XML。</span><span class="sxs-lookup"><span data-stu-id="a6adf-136">BAM definition XML.</span></span>                                      |
|                                <span data-ttu-id="a6adf-137">BAMEndToEndBinding.xml</span><span class="sxs-lookup"><span data-stu-id="a6adf-137">BAMEndToEndBinding.xml</span></span>                                 |                                         <span data-ttu-id="a6adf-138">BAM バインド。</span><span class="sxs-lookup"><span data-stu-id="a6adf-138">BAM binding.</span></span>                                         |
|                                      <span data-ttu-id="a6adf-139">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="a6adf-139">Cleanup.bat</span></span>                                      |                              <span data-ttu-id="a6adf-140">サンプルの展開解除を行うバッチ ファイル。</span><span class="sxs-lookup"><span data-stu-id="a6adf-140">Batch file to undeploy the sample.</span></span>                              |
|                                   <span data-ttu-id="a6adf-141">InputMessage.xml</span><span class="sxs-lookup"><span data-stu-id="a6adf-141">InputMessage.xml</span></span>                                    |                                        <span data-ttu-id="a6adf-142">入力メッセージ。</span><span class="sxs-lookup"><span data-stu-id="a6adf-142">Input message.</span></span>                                        |
|                                       <span data-ttu-id="a6adf-143">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="a6adf-143">Setup.bat</span></span>                                       |                         <span data-ttu-id="a6adf-144">サンプルをコンパイルし、展開するバッチ ファイル。</span><span class="sxs-lookup"><span data-stu-id="a6adf-144">Batch file to compile and deploy the sample.</span></span>                         |
|                              <span data-ttu-id="a6adf-145">\Components\AssemblyInfo.cs</span><span class="sxs-lookup"><span data-stu-id="a6adf-145">\Components\AssemblyInfo.cs</span></span>                              |                                   <span data-ttu-id="a6adf-146">パイプライン コンポーネント コード。</span><span class="sxs-lookup"><span data-stu-id="a6adf-146">Pipeline component code.</span></span>                                   |
|                       <span data-ttu-id="a6adf-147">\Components\BAMMessagePartPLComponent.cs</span><span class="sxs-lookup"><span data-stu-id="a6adf-147">\Components\BAMMessagePartPLComponent.cs</span></span>                        |                                   <span data-ttu-id="a6adf-148">パイプライン コンポーネント コード。</span><span class="sxs-lookup"><span data-stu-id="a6adf-148">Pipeline component code.</span></span>                                   |
|                             <span data-ttu-id="a6adf-149">\Components\Components.csproj</span><span class="sxs-lookup"><span data-stu-id="a6adf-149">\Components\Components.csproj</span></span>                             |                                 <span data-ttu-id="a6adf-150">パイプライン コンポーネント プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="a6adf-150">Pipeline component project.</span></span>                                  |
| <span data-ttu-id="a6adf-151">\Messages\InputMessage01.xml</span><span class="sxs-lookup"><span data-stu-id="a6adf-151">\Messages\InputMessage01.xml</span></span><br /><br /> <span data-ttu-id="a6adf-152">[...]</span><span class="sxs-lookup"><span data-stu-id="a6adf-152">...</span></span><br /><br /> <span data-ttu-id="a6adf-153">\Messages\InputMessage10.xml</span><span class="sxs-lookup"><span data-stu-id="a6adf-153">\Messages\InputMessage10.xml</span></span> |                                    <span data-ttu-id="a6adf-154">サンプル入力メッセージ。</span><span class="sxs-lookup"><span data-stu-id="a6adf-154">Sample input messages.</span></span>                                    |
|                               <span data-ttu-id="a6adf-155">\Services\BAMInbound.btp</span><span class="sxs-lookup"><span data-stu-id="a6adf-155">\Services\BAMInbound.btp</span></span>                                |                                    <span data-ttu-id="a6adf-156">受信パイプライン ファイル。</span><span class="sxs-lookup"><span data-stu-id="a6adf-156">Inbound pipeline file.</span></span>                                    |
|                              <span data-ttu-id="a6adf-157">\Services\BAMPartSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="a6adf-157">\Services\BAMPartSchema.xsd</span></span>                              |                                   <span data-ttu-id="a6adf-158">BAM パート メッセージ スキーマ。</span><span class="sxs-lookup"><span data-stu-id="a6adf-158">BAM part message schema.</span></span>                                   |
|                             <span data-ttu-id="a6adf-159">\Services\Orchestration1.odx</span><span class="sxs-lookup"><span data-stu-id="a6adf-159">\Services\Orchestration1.odx</span></span>                              |                                        <span data-ttu-id="a6adf-160">オーケストレーション。</span><span class="sxs-lookup"><span data-stu-id="a6adf-160">Orchestration.</span></span>                                        |
|                             <span data-ttu-id="a6adf-161">\Services\Orchestration2.odx</span><span class="sxs-lookup"><span data-stu-id="a6adf-161">\Services\Orchestration2.odx</span></span>                              |                                        <span data-ttu-id="a6adf-162">オーケストレーション。</span><span class="sxs-lookup"><span data-stu-id="a6adf-162">Orchestration.</span></span>                                        |
|                             <span data-ttu-id="a6adf-163">\Services\Orchestration3.odx</span><span class="sxs-lookup"><span data-stu-id="a6adf-163">\Services\Orchestration3.odx</span></span>                              |                                        <span data-ttu-id="a6adf-164">オーケストレーション。</span><span class="sxs-lookup"><span data-stu-id="a6adf-164">Orchestration.</span></span>                                        |
|                             <span data-ttu-id="a6adf-165">\Services\PropertySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="a6adf-165">\Services\PropertySchema.xsd</span></span>                              |                                       <span data-ttu-id="a6adf-166">プロパティ スキーマ : </span><span class="sxs-lookup"><span data-stu-id="a6adf-166">Property schema.</span></span>                                       |
|                                 <span data-ttu-id="a6adf-167">\Services\Schema1.xsd</span><span class="sxs-lookup"><span data-stu-id="a6adf-167">\Services\Schema1.xsd</span></span>                                 |                                       <span data-ttu-id="a6adf-168">メッセージ スキーマ。</span><span class="sxs-lookup"><span data-stu-id="a6adf-168">Message schema.</span></span>                                        |
|                                 <span data-ttu-id="a6adf-169">\Services\Schema2.xsd</span><span class="sxs-lookup"><span data-stu-id="a6adf-169">\Services\Schema2.xsd</span></span>                                 |                                       <span data-ttu-id="a6adf-170">メッセージ スキーマ。</span><span class="sxs-lookup"><span data-stu-id="a6adf-170">Message schema.</span></span>                                        |
|                                 <span data-ttu-id="a6adf-171">Services\Schema3.xsd</span><span class="sxs-lookup"><span data-stu-id="a6adf-171">Services\Schema3.xsd</span></span>                                  |                                       <span data-ttu-id="a6adf-172">メッセージ スキーマ。</span><span class="sxs-lookup"><span data-stu-id="a6adf-172">Message schema.</span></span>                                        |
|                               <span data-ttu-id="a6adf-173">\Services\Services.btproj</span><span class="sxs-lookup"><span data-stu-id="a6adf-173">\Services\Services.btproj</span></span>                               | [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]<span data-ttu-id="a6adf-174"> BizTalk ファイル プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="a6adf-174"> BizTalk file project.</span></span> |
|                               <span data-ttu-id="a6adf-175">\Services\Transform_1.btm</span><span class="sxs-lookup"><span data-stu-id="a6adf-175">\Services\Transform_1.btm</span></span>                               |                                          <span data-ttu-id="a6adf-176">マップ ファイル。</span><span class="sxs-lookup"><span data-stu-id="a6adf-176">Map file.</span></span>                                           |
|                               <span data-ttu-id="a6adf-177">\Services\Transform_2.btm</span><span class="sxs-lookup"><span data-stu-id="a6adf-177">\Services\Transform_2.btm</span></span>                               |                                          <span data-ttu-id="a6adf-178">マップ ファイル。</span><span class="sxs-lookup"><span data-stu-id="a6adf-178">Map file.</span></span>                                           |
|                               <span data-ttu-id="a6adf-179">\Services\Transform_3.btm</span><span class="sxs-lookup"><span data-stu-id="a6adf-179">\Services\Transform_3.btm</span></span>                               |                                          <span data-ttu-id="a6adf-180">マップ ファイル。</span><span class="sxs-lookup"><span data-stu-id="a6adf-180">Map file.</span></span>                                           |

## <a name="how-to-use-this-sample"></a><span data-ttu-id="a6adf-181">このサンプルの使用方法</span><span class="sxs-lookup"><span data-stu-id="a6adf-181">How to Use This Sample</span></span>  
 <span data-ttu-id="a6adf-182">次の手順を使用して、BAM End-to-End サンプルをビルドおよび実行します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-182">Use the following procedures to build and run the BAM End-to-End sample:</span></span>  

-   [<span data-ttu-id="a6adf-183">このサンプルをビルドして初期化</span><span class="sxs-lookup"><span data-stu-id="a6adf-183">To build and initialize this sample</span></span>](#To_Build_Sample)  

-   [<span data-ttu-id="a6adf-184">このサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="a6adf-184">To run this sample</span></span>](#To_Run_Sample)  

-   [<span data-ttu-id="a6adf-185">BAM データを表示するには</span><span class="sxs-lookup"><span data-stu-id="a6adf-185">To view the BAM data</span></span>](#To_View_Data)  

##  <a name="To_Build_Sample"></a><span data-ttu-id="a6adf-186">ビルドしてこのサンプルの初期化</span><span class="sxs-lookup"><span data-stu-id="a6adf-186">Build and initialize this sample</span></span>  

1.  <span data-ttu-id="a6adf-187">管理者は、コマンド プロンプトを開き、実行*\<サンプル パス\>* \BAM\BAMEndToEnd\Setup.bat します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-187">Open a command prompt as Administrator, and run *\<Samples Path\>* \BAM\BAMEndToEnd\Setup.bat.</span></span> <span data-ttu-id="a6adf-188">Setup.bat は、このサンプルの BAM インフラストラクチャをビルドして初期化します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-188">Setup.bat builds and initializes the BAM infrastructure for this sample.</span></span> <span data-ttu-id="a6adf-189">コマンド プロンプトは開いたままにします。</span><span class="sxs-lookup"><span data-stu-id="a6adf-189">Keep the command prompt open.</span></span>  

2.  <span data-ttu-id="a6adf-190">Orchestration1、Orchestration2、および Orchestration3 を BAM アクティビティにマップするための追跡プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-190">Create a tracking profile to map Orchestration1, Orchestration2, and Orchestration3 to the BAM activity.</span></span> <span data-ttu-id="a6adf-191">(詳細な手順がという別の手順では、追跡プロファイルの作成は複雑なプロセスなので**追跡プロファイルを作成する**します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-191">(Because creating the tracking profile is a complex process, the detailed instructions are in a separate procedure called **To create a tracking profile**.</span></span> <span data-ttu-id="a6adf-192">この手順については、このドキュメントの後半で説明します)。</span><span class="sxs-lookup"><span data-stu-id="a6adf-192">This procedure appears later in this document.)</span></span>  

3.  <span data-ttu-id="a6adf-193">前の手順で作成した追跡プロファイル BamEndToEnd.btt を展開します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-193">Deploy the tracking profile BamEndToEnd.btt that you created in the previous step.</span></span>  <span data-ttu-id="a6adf-194">コマンド プロンプトでを変更、 *\<サンプル パス\>* \BAM\BamEndToEnd ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="a6adf-194">In the command prompt change to the *\<Samples Path\>* \BAM\BamEndToEnd directory.</span></span> <span data-ttu-id="a6adf-195">追跡プロファイルを展開するには、次の行を入力し、キーを押します**Enter**:</span><span class="sxs-lookup"><span data-stu-id="a6adf-195">To deploy the tracking profile, type the following line, and then press **Enter**:</span></span>  

    `“<BizTalkInstallationPath>\Tracking\bttdeploy” BamEndToEnd.btt`

     <span data-ttu-id="a6adf-196">[追跡プロファイル管理ユーティリティを使って追跡プロファイルを展開する方法](../core/how-to-deploy-tracking-profiles-with-the-tracking-profiles-management-utility.md)詳細に説明します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-196">[How to Deploy Tracking Profiles with the Tracking Profiles Management Utility](../core/how-to-deploy-tracking-profiles-with-the-tracking-profiles-management-utility.md) provides more information.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="a6adf-197">ContinuationID Orch1_ に一致する Continuation がないことを示すメッセージは無視できます。</span><span class="sxs-lookup"><span data-stu-id="a6adf-197">You can ignore the message that the ContinuationID Orch1_ does not have a matching Continuation.</span></span> <span data-ttu-id="a6adf-198">Orch1_ という名前の Continuation は追跡プロファイルではなくパイプライン コンポーネントで定義されているので、このメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a6adf-198">This message is expected, because the continuation named Orch1_ is defined in the pipeline component, and not in the tracking profile.</span></span>  

##  <a name="To_Run_Sample"></a><span data-ttu-id="a6adf-199">このサンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-199">Run this sample</span></span>  

<span data-ttu-id="a6adf-200">ファイルをコピー *\<サンプル パス\>* フォルダーに \BamEndToEnd\InputMessage.xml *\<サンプル パス\>* \BamEndToEnd\Input します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-200">Copy the file *\<Samples Path\>* \BamEndToEnd\InputMessage.xml into the folder *\<Samples Path\>* \BamEndToEnd\Input.</span></span> <span data-ttu-id="a6adf-201">入力フォルダーから、数秒後に、メッセージが表示されなくなり、出力メッセージが表示されます、 *\<サンプル パス\>* \BamEndToEnd\Output フォルダー。</span><span class="sxs-lookup"><span data-stu-id="a6adf-201">After a few seconds, the message disappears from the Input folder, and an output message appears in the *\<Samples Path\>* \BamEndToEnd\Output folder.</span></span>  

##  <a name="To_View_Data"></a><span data-ttu-id="a6adf-202">BAM データを表示します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-202">View the BAM data</span></span>  

1.  <span data-ttu-id="a6adf-203">SQL Server Management Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="a6adf-203">Open SQL Server Management Studio.</span></span>  

2.  <span data-ttu-id="a6adf-204">SQL Server Management studio で、サーバーを展開し、**データベース**、展開**BAMPrimaryImport**、順に展開**テーブル**します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-204">In SQL Server Management Studio, expand the server, expand **Databases**, expand **BAMPrimaryImport**, and then expand **Tables**.</span></span>  

3.  <span data-ttu-id="a6adf-205">右クリックして**dbo.bam_EndToEndActivity_Completed**、 をクリックし、**テーブルを開く**します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-205">Right-click **dbo.bam_EndToEndActivity_Completed**, and then click **Open Table**.</span></span> <span data-ttu-id="a6adf-206">SQL Server を使用している場合はクリックして**上位 1000 行を選択する**します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-206">If you are using SQL Server, click **Select top 1000 rows**.</span></span>  

     <span data-ttu-id="a6adf-207">bam_EndToEndActivity_Completed テーブルの内容が右ペインに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a6adf-207">The contents of the bam_EndToEndActivity_Completed table are displayed in the right pane.</span></span> <span data-ttu-id="a6adf-208">このテーブルの各行は、完了した EndToEndActivity アクティビティを表します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-208">Each row in the table represents an EndToEndActivity activity that has been completed.</span></span>  

#### <a name="rerun-this-sample"></a><span data-ttu-id="a6adf-209">このサンプルを再実行します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-209">Rerun this sample</span></span>  

1. <span data-ttu-id="a6adf-210">管理者は、コマンド プロンプトを開き、変更、 *\<サンプル パス\>* \BAM\BamEndToEnd ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="a6adf-210">Open a command prompt as Administrator, and change to the *\<Samples Path\>* \BAM\BamEndToEnd directory.</span></span> <span data-ttu-id="a6adf-211">次の行を入力します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-211">Type the following line:</span></span>  

   `“C:\Program Files\Microsoft BizTalk Server <version>\Tracking\bttdeploy” BamEndToEnd.btt /remove`  

   > [!NOTE]
   >  <span data-ttu-id="a6adf-212">インストールしなかった場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を C ドライブにインストールされている、ドライブ文字"C"を置き換えます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-212">If you did not install [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to the C drive, replace "C" with the drive letter where you installed [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  

2. <span data-ttu-id="a6adf-213">実行*\<サンプル パス\>* \BAM\BAMEndToEnd\Cleanup.bat します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-213">Run *\<Samples Path\>* \BAM\BAMEndToEnd\Cleanup.bat.</span></span> <span data-ttu-id="a6adf-214">Cleanup.bat は、このサンプルの BAM インフラストラクチャを削除します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-214">Cleanup.bat removes the BAM infrastructure for this sample.</span></span>  

3. <span data-ttu-id="a6adf-215">手順に従います**このサンプルをビルドして初期化**このトピックの「します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-215">Perform the steps in **To build and initialize this sample** section in this topic.</span></span>  

##  <a name="TPE_procedure"></a><span data-ttu-id="a6adf-216">追跡プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-216">Create a tracking profile</span></span>  

1. <span data-ttu-id="a6adf-217">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-217">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)].</span></span> <span data-ttu-id="a6adf-218">右クリックして**追跡プロファイル エディター**、および**管理者として実行**します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-218">Right-click **Tracking Profile Editor**, and **Run as administrator**.</span></span>  

2. <span data-ttu-id="a6adf-219">左側のウィンドウで、**追跡プロファイル エディター**ウィンドウで、をクリックして**ここをクリックすると、BAM アクティビティ定義をインポートする**します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-219">In the left pane of the **Tracking Profile Editor** window, click **Click here to import a BAM Activity Definition**.</span></span>  

3. <span data-ttu-id="a6adf-220">**BAM アクティビティ定義名**のセクション、 **BAM アクティビティ定義のインポート**ダイアログ ボックスで、 **endtoendactivity**、 をクリックし、 **ok**.</span><span class="sxs-lookup"><span data-stu-id="a6adf-220">In the  **BAM Activity Definition Name** section of the **Import BAM Activity Definition** dialog box, select **EndToEndActivity**, and then click **OK**.</span></span>  

4. <span data-ttu-id="a6adf-221">右側のウィンドウで、**追跡プロファイル エディター**ウィンドウで、をクリックして**ここをクリックすると、イベント ソースを選択する**します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-221">In the right pane of the **Tracking Profile Editor** window, click **Click here to select an event source**.</span></span>  

5. <span data-ttu-id="a6adf-222">**アセンブリ名**のセクション、 **イベント ソースの親アセンブリ**ダイアログ ボックスで、 **Microsoft.Samples.BizTalk.BamEndToEnd.Services**、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-222">In the **Assembly Name** section of the **Select Event Source Parent Assembly** dialog box, select **Microsoft.Samples.BizTalk.BamEndToEnd.Services**, and then click **Next**.</span></span>  

6. <span data-ttu-id="a6adf-223">**オーケストレーション名**のセクション、**オーケストレーションの選択**ダイアログ ボックスで、 **BamEndToEnd.Services.Orchestration1**、 をクリックし、 **ok**.</span><span class="sxs-lookup"><span data-stu-id="a6adf-223">In the **Orchestration Name** section of the **Select Orchestration** dialog box, select **BamEndToEnd.Services.Orchestration1**, and then click **OK**.</span></span>  

7. <span data-ttu-id="a6adf-224">左側のウィンドウで、**追跡プロファイル エディター**ウィンドウで、右クリック **[endtoendactivity]**、順にクリックします**新しい ContinuationID**します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-224">In the left pane of the **Tracking Profile Editor** window, right-click **EndToEndActivity**, and then click **New ContinuationID**.</span></span> <span data-ttu-id="a6adf-225">新しい continuation ID の名前を付けます**orch1 _** します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-225">Name the new continuation ID **Orch1_**.</span></span> <span data-ttu-id="a6adf-226">2 つの continuation Id という名前を作成するには、この手順を繰り返します**orch2 _** と**orch3 _** します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-226">Repeat this step to create two more continuation IDs named **Orch2_** and **Orch3_**.</span></span>  

8. <span data-ttu-id="a6adf-227">右クリックして**endtoendactivity**、 をクリックし、**新しい Continuation**します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-227">Right-click **EndToEndActivity**, and then click **New Continuation**.</span></span> <span data-ttu-id="a6adf-228">新しい continuation の名前**orch2 _** します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-228">Name the new continuation **Orch2_**.</span></span> <span data-ttu-id="a6adf-229">という名前のもう 1 つの continuation を作成するには、この手順を繰り返します**orch3 _** します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-229">Repeat this step to create another continuation named **Orch3_**.</span></span>  

9. <span data-ttu-id="a6adf-230">右クリックし、 **Receive1**図形をクリックして**コンテキスト プロパティ スキーマ**します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-230">Right-click the **Receive1** shape, and then click **Context Property Schemas**.</span></span>  

10. <span data-ttu-id="a6adf-231">最後までスクロール、**コンテキスト プロパティ名**、一覧表示し、ダブルクリック**BAMEndToEnd.Services.PropertySchema.DocumentID**します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-231">Scroll to the end of the **Context Property Name** list, and then double-click **BAMEndToEnd.Services.PropertySchema.DocumentID**.</span></span>  

11. <span data-ttu-id="a6adf-232">展開**\<スキーマ\>**、し、ドラッグ**DocumentID**を右側のウィンドウで**orch1 _** 左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="a6adf-232">Expand **\<Schema\>**, and then drag **DocumentID** in the right pane to **Orch1_** in the left pane.</span></span>  

12. <span data-ttu-id="a6adf-233">矢印の付いたフォルダー アイコンをクリックします (![フォルダーと上矢印ボタン](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4"))、オーケストレーションを表示するには、2 回クリックします。</span><span class="sxs-lookup"><span data-stu-id="a6adf-233">Click the folder icon with the arrow (![button with folder and up arrow](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4")) twice to display the orchestration.</span></span>  

13. <span data-ttu-id="a6adf-234">ドラッグ、 **Receive1**右側のウィンドウに図形 **[sbegin1]** 左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="a6adf-234">Drag the **Receive1** shape in the right pane to **SBegin1** in the left pane.</span></span>  

14. <span data-ttu-id="a6adf-235">ドラッグ、 **StartOrchestration_1**右側のウィンドウに図形 **[send1]** 左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="a6adf-235">Drag the **StartOrchestration_1** shape in the right pane to **SEnd1** in the left pane.</span></span>  

15. <span data-ttu-id="a6adf-236">右クリックし、 **StartOrchestration_1**図形をクリックして**メッセージ ペイロード スキーマ**します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-236">Right-click the **StartOrchestration_1** shape, and then click **Message Payload Schemas**.</span></span>  

16. <span data-ttu-id="a6adf-237">値"Message_2"を含む行をダブルクリックして、**メッセージ**列と値"MessageBody"で、**一部**列。</span><span class="sxs-lookup"><span data-stu-id="a6adf-237">Double-click the row that contains the value “Message_2” in the **Message** column and the value “MessageBody” in the **Part** column.</span></span>  

     <span data-ttu-id="a6adf-238">![TPE メッセージ ペイロード スキーマが表示されたメッセージ&#95;2](../core/media/77fbc444-46cf-4d45-8e9c-c330da7ba7d1.gif "77fbc444-46cf-4d45-8e9c-c330da7ba7d1")</span><span class="sxs-lookup"><span data-stu-id="a6adf-238">![TPE Message Payload schema showing message&#95;2](../core/media/77fbc444-46cf-4d45-8e9c-c330da7ba7d1.gif "77fbc444-46cf-4d45-8e9c-c330da7ba7d1")</span></span>  

17. <span data-ttu-id="a6adf-239">展開**Schema2**、し、ドラッグ**Data2**を右側のウィンドウで**Data1**左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="a6adf-239">Expand **Schema2**, and then drag **Data2** in the right pane to **Data1** in the left pane.</span></span>  

18. <span data-ttu-id="a6adf-240">をクリックして**イベント ソースの選択**、] をクリックし、 **[コンテキスト プロパティの**します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-240">Click **Select Event Source**, and then click **Select Context Property**.</span></span>  

19. <span data-ttu-id="a6adf-241">最後までスクロール、**コンテキスト プロパティ名**、一覧表示し、ダブルクリック**BAMEndToEnd.Services.PropertySchema.DocumentID**します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-241">Scroll to the end of the **Context Property Name** list, and then double-click **BAMEndToEnd.Services.PropertySchema.DocumentID**.</span></span>  

20. <span data-ttu-id="a6adf-242">展開**\<スキーマ\>**、し、ドラッグ**DocumentID**を**orch2 _** 左側のウィンドウで継続します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-242">Expand **\<Schema\>**, and then drag **DocumentID** to the **Orch2_** continuation in the left pane.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="a6adf-243">Orch2_ Continuation と Orch2_ Continuation ID を混同しないように注意してください。</span><span class="sxs-lookup"><span data-stu-id="a6adf-243">Do not confuse the Orch2_ continuation with the Orch2_ continuation ID.</span></span> <span data-ttu-id="a6adf-244">Continuation ID を表すアイコンには、キーが含まれています (![continuation ID のアイコン](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea"))、continuation を表すアイコンにキー (が含まれていません![continuation のアイコン](../core/media/test.gif "テスト"))。</span><span class="sxs-lookup"><span data-stu-id="a6adf-244">The icon that represents a continuation ID contains a key (![icon for a continuation ID](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea")), whereas the icon that represents a continuation does not contain a key (![icon for a continuation](../core/media/test.gif "test")).</span></span>  

21. <span data-ttu-id="a6adf-245">をクリックして**イベント ソースの選択**、] をクリックし、 **[オーケストレーション スケジュールの**します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-245">Click **Select Event Source**, and then click **Select Orchestration Schedule**.</span></span>  

22. <span data-ttu-id="a6adf-246">**アセンブリ名**のセクション、 **イベント ソースの親アセンブリ**ダイアログ ボックスで、 **Microsoft.Samples.BizTalk.BamEndToEnd.Services**、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-246">In the **Assembly Name** section of the **Select Event Source Parent Assembly** dialog box, select **Microsoft.Samples.BizTalk.BamEndToEnd.Services**, and then click **Next**.</span></span>  

23. <span data-ttu-id="a6adf-247">**オーケストレーション名**のセクション、**オーケストレーションの選択**ダイアログ ボックスで、 **BamEndToEnd.Services.Orchestration2**、 をクリックし、 **ok**.</span><span class="sxs-lookup"><span data-stu-id="a6adf-247">In the **Orchestration Name** section of the **Select Orchestration** dialog box, select **BamEndToEnd.Services.Orchestration2**, and then click **OK**.</span></span>  

24. <span data-ttu-id="a6adf-248">右クリックし、 **ConstructMessage_1**図形をクリックして**メッセージ ペイロード スキーマ**します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-248">Right-click the **ConstructMessage_1** shape, and then click **Message Payload Schemas**.</span></span>  

25. <span data-ttu-id="a6adf-249">値"Message_3"を含む行をダブルクリックして、**メッセージ**列と値に"BAMPart"で、**一部**列。</span><span class="sxs-lookup"><span data-stu-id="a6adf-249">Double-click the row that contains the value “Message_3” in the **Message** column and the value “BAMPart” in the **Part** column.</span></span>  

26. <span data-ttu-id="a6adf-250">展開**BAMPart**、し、ドラッグ**DocumentID**を右側のウィンドウで、 **orch2 _** 左側のウィンドウで continuation ID。</span><span class="sxs-lookup"><span data-stu-id="a6adf-250">Expand **BAMPart**, and then drag **DocumentID** in the right pane to the **Orch2_** continuation ID in the left pane.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="a6adf-251">Orch2_ Continuation と Orch2_ Continuation ID を混同しないように注意してください。</span><span class="sxs-lookup"><span data-stu-id="a6adf-251">Do not confuse the Orch2_ continuation with the Orch2_ continuation ID.</span></span> <span data-ttu-id="a6adf-252">Continuation ID を表すアイコンには、キーが含まれています (![continuation ID のアイコン](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea"))、continuation を表すアイコンにキー (が含まれていません![continuation のアイコン](../core/media/test.gif "テスト"))。</span><span class="sxs-lookup"><span data-stu-id="a6adf-252">The icon that represents a continuation ID contains a key (![icon for a continuation ID](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea")), whereas the icon that represents a continuation does not contain a key (![icon for a continuation](../core/media/test.gif "test")).</span></span>  

27. <span data-ttu-id="a6adf-253">矢印の付いたフォルダー アイコンをクリックします (![フォルダーでボタンをクリックし、セットアップ&#45;矢印](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4"))、オーケストレーションを表示するには、2 回です。</span><span class="sxs-lookup"><span data-stu-id="a6adf-253">Click the folder icon with the arrow (![button with folder and up&#45;arrow](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4")) twice to display the orchestration.</span></span>  

28. <span data-ttu-id="a6adf-254">ドラッグ、 **ConstructMessage_1**右側のウィンドウに図形 **[sbegin2]** 左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="a6adf-254">Drag the **ConstructMessage_1** shape in the right pane to **SBegin2** in the left pane.</span></span>  

29. <span data-ttu-id="a6adf-255">ドラッグ、 **Send_1**右側のウィンドウに図形 **[send2]** 左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="a6adf-255">Drag the **Send_1** shape in the right pane to **SEnd2** in the left pane.</span></span>  

30. <span data-ttu-id="a6adf-256">右クリックし、 **Send_1**図形をクリックして**メッセージ ペイロード スキーマ**します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-256">Right-click the **Send_1** shape, and then click **Message Payload Schemas**.</span></span>  

31. <span data-ttu-id="a6adf-257">値"Message_3"を含む行をダブルクリックして、**メッセージ**列と値"MessageBody"で、**一部**列。</span><span class="sxs-lookup"><span data-stu-id="a6adf-257">Double-click the row that contains the value “Message_3” in the **Message** column and the value “MessageBody” in the **Part** column.</span></span>  

32. <span data-ttu-id="a6adf-258">展開**Schema3**、し、ドラッグ**Data3**を右側のウィンドウで**Data2**左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="a6adf-258">Expand **Schema3**, and then drag **Data3** in the right pane to **Data2** in the left pane.</span></span>  

33. <span data-ttu-id="a6adf-259">右ペインの上のドロップダウン リストから選択**メッセージ ペイロード スキーマ**します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-259">From the drop-down list above the right pane, select **Message Payload Schemas**.</span></span>  

34. <span data-ttu-id="a6adf-260">値"Message_3"を含む行をダブルクリックして、**メッセージ**列と値に"BAMPart"で、**一部**列。</span><span class="sxs-lookup"><span data-stu-id="a6adf-260">Double-click the row that contains the value “Message_3” in the **Message** column and the value “BAMPart” in the **Part** column.</span></span>  

35. <span data-ttu-id="a6adf-261">展開**BAMPart**、し、ドラッグ**DocumentID**を右側のウィンドウで、 **orch3 _** 左側のウィンドウで継続します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-261">Expand **BAMPart**, and then drag **DocumentID** in the right pane to the **Orch3_** continuation in the left pane.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="a6adf-262">Orch3_ Continuation と Orch3_ Continuation ID を混同しないように注意してください。</span><span class="sxs-lookup"><span data-stu-id="a6adf-262">Do not confuse the Orch3_ continuation with the Orch3_ continuation ID.</span></span> <span data-ttu-id="a6adf-263">Continuation ID を表すアイコンには、キーが含まれています (![continuation ID のアイコン](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea"))、continuation を表すアイコンにキー (が含まれていません![continuation のアイコン](../core/media/test.gif "テスト"))。</span><span class="sxs-lookup"><span data-stu-id="a6adf-263">The icon that represents a continuation ID contains a key (![icon for a continuation ID](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea")), whereas the icon that represents a continuation does not contain a key (![icon for a continuation](../core/media/test.gif "test")).</span></span>  

36. <span data-ttu-id="a6adf-264">をクリックして**イベント ソースの選択**、] をクリックし、 **[オーケストレーション スケジュールの**します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-264">Click **Select Event Source**, and then click **Select Orchestration Schedule**.</span></span>  

37. <span data-ttu-id="a6adf-265">**アセンブリ名**のセクション、 **イベント ソースの親アセンブリ**ダイアログ ボックスで、 **Microsoft.Samples.BizTalk.BamEndToEnd.Services**、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-265">In the **Assembly Name** section of the **Select Event Source Parent Assembly** dialog box, select **Microsoft.Samples.BizTalk.BamEndToEnd.Services**, and then click **Next**.</span></span>  

38. <span data-ttu-id="a6adf-266">**オーケストレーション名**のセクション、**オーケストレーションの選択**ダイアログ ボックスで、 **BamEndToEnd.Services.Orchestration3**、 をクリックし、 **ok**.</span><span class="sxs-lookup"><span data-stu-id="a6adf-266">In the **Orchestration Name** section of the **Select Orchestration** dialog box, select **BamEndToEnd.Services.Orchestration3**, and then click **OK**.</span></span>  

39. <span data-ttu-id="a6adf-267">右クリックし、 **Receive1**図形をクリックして**メッセージ ペイロード スキーマ**します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-267">Right-click the **Receive1** shape, and then click **Message Payload Schemas**.</span></span>  

40. <span data-ttu-id="a6adf-268">値"Message_3"を含む行をダブルクリックして、**メッセージ**列と値に"BAMPart"で、**一部**列。</span><span class="sxs-lookup"><span data-stu-id="a6adf-268">Double-click the row that contains the value “Message_3” in the **Message** column and the value “BAMPart” in the **Part** column.</span></span>  

41. <span data-ttu-id="a6adf-269">展開**BAMPart**、し、ドラッグ**DocumentID**を右側のウィンドウで、 **orch3 _** 左側のウィンドウで continuation ID。</span><span class="sxs-lookup"><span data-stu-id="a6adf-269">Expand **BAMPart**, and then drag **DocumentID** in the right pane to the **Orch3_** continuation ID in the left pane.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="a6adf-270">Orch3_ Continuation と Orch3_ Continuation ID を混同しないように注意してください。</span><span class="sxs-lookup"><span data-stu-id="a6adf-270">Do not confuse the Orch3_ continuation with the Orch3_ continuation ID.</span></span> <span data-ttu-id="a6adf-271">Continuation ID を表すアイコンには、キーが含まれています (![continuation ID のアイコン](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea"))、continuation を表すアイコンにキー (が含まれていません![continuation のアイコン](../core/media/test.gif "テスト"))。</span><span class="sxs-lookup"><span data-stu-id="a6adf-271">The icon that represents a continuation ID contains a key (![icon for a continuation ID](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea")), whereas the icon that represents a continuation does not contain a key (![icon for a continuation](../core/media/test.gif "test")).</span></span>  

42. <span data-ttu-id="a6adf-272">矢印の付いたフォルダー アイコンをクリックします (![フォルダーと上矢印ボタン](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4"))、オーケストレーションを表示するには、2 回クリックします。</span><span class="sxs-lookup"><span data-stu-id="a6adf-272">Click the folder icon with the arrow (![button with folder and up arrow](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4")) twice to display the orchestration.</span></span>  

43. <span data-ttu-id="a6adf-273">ドラッグ、 **Receive1**右側のウィンドウに図形 **[sbegin3]** 左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="a6adf-273">Drag the **Receive1** shape in the right pane to **SBegin3** in the left pane.</span></span>  

44. <span data-ttu-id="a6adf-274">ドラッグ、 **Send_1**右側のウィンドウに図形 **[send3]** 左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="a6adf-274">Drag the **Send_1** shape in the right pane to **SEnd3** in the left pane.</span></span>  

45. <span data-ttu-id="a6adf-275">右クリックし、 **Send_1**図形をクリックして**メッセージ ペイロード スキーマ**します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-275">Right-click the **Send_1** shape, and then click **Message Payload Schema**.</span></span>  

46. <span data-ttu-id="a6adf-276">展開**Schema3**、し、ドラッグ**Data3**を右側のウィンドウで**Data3**左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="a6adf-276">Expand **Schema3**, and then drag **Data3** in the right pane to **Data3** in the left pane.</span></span>  

47. <span data-ttu-id="a6adf-277">右クリック**DocumentID**下、 **orch2 _** クリックして、継続**ポート マッピングの設定**します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-277">Right-click **DocumentID** below the **Orch2_** continuation, and then click **Set Port Mappings**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="a6adf-278">Orch2_ Continuation と Orch2_ Continuation ID を混同しないように注意してください。</span><span class="sxs-lookup"><span data-stu-id="a6adf-278">Do not confuse the Orch2_ continuation with the Orch2_ continuation ID.</span></span> <span data-ttu-id="a6adf-279">Continuation ID を表すアイコンには、キーが含まれています (![continuation ID のアイコン](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea"))、continuation を表すアイコンにキー (が含まれていません![continuation のアイコン](../core/media/test.gif "テスト"))。</span><span class="sxs-lookup"><span data-stu-id="a6adf-279">The icon that represents a continuation ID contains a key (![icon for a continuation ID](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea")), whereas the icon that represents a continuation does not contain a key (![icon for a continuation](../core/media/test.gif "test")).</span></span>  

48. <span data-ttu-id="a6adf-280">**ポートの選択**のセクション、**ポートの選択**ダイアログ ボックスで、 をクリックして**BamEndToEnd_ReceivePort**、クリックして-不等号 ( **>**)、をクリックし、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-280">In the **Select Ports** section of the **Select Ports** dialog box, click **BamEndToEnd_ReceivePort**, click the greater-than sign (**>**), and then click **OK**.</span></span>  

49. <span data-ttu-id="a6adf-281">追跡プロファイルを保存*\<サンプル パス\>* \BAM\BamEndToEnd\BamEndToEnd.btt します。</span><span class="sxs-lookup"><span data-stu-id="a6adf-281">Save the tracking profile to *\<Samples Path\>* \BAM\BamEndToEnd\BamEndToEnd.btt.</span></span>  

## <a name="important-details"></a><span data-ttu-id="a6adf-282">重要な詳細情報</span><span class="sxs-lookup"><span data-stu-id="a6adf-282">Important details</span></span>  
 <span data-ttu-id="a6adf-283">追跡プロファイルは、パイプラインではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a6adf-283">Tracking profiles are not supported for pipelines.</span></span> <span data-ttu-id="a6adf-284">ただし、呼び出し**BeginActivity**パイプライン コンポーネントは、オーケストレーションで ActivityID の使用と同じです。</span><span class="sxs-lookup"><span data-stu-id="a6adf-284">However, the call to **BeginActivity** in the pipeline component is the same as using ActivityID in an orchestration.</span></span> <span data-ttu-id="a6adf-285">呼び出し**EnableContinuation**オーケストレーションでの continuation の使用と同じです。</span><span class="sxs-lookup"><span data-stu-id="a6adf-285">The call to **EnableContinuation** is the same as using a continuation in an orchestration.</span></span>  

## <a name="see-also"></a><span data-ttu-id="a6adf-286">参照</span><span class="sxs-lookup"><span data-stu-id="a6adf-286">See Also</span></span>  
 [<span data-ttu-id="a6adf-287">ビジネス アクティビティの監視 (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="a6adf-287">Business Activity Monitoring (BizTalk Server Samples Folder)</span></span>](../core/business-activity-monitoring-biztalk-server-samples-folder.md)