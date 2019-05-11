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
ms.openlocfilehash: 17ba248941ef6351bd421b30bd0124073e20b791
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528636"
---
# <a name="bam-end-to-end-biztalk-server-sample"></a><span data-ttu-id="10b3e-103">BAM エンド ツー エンド (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="10b3e-103">BAM End-to-End (BizTalk Server Sample)</span></span>
<span data-ttu-id="10b3e-104">エンド ツー エンドのサンプルでは、BAM を使用して (この場合、3 つのオーケストレーションおよびパイプライン) で複数のコンポーネントからのイベントを関連付ける方法を示します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-104">The End-to-End sample demonstrates how to correlate events from multiple components (in this case, three orchestrations and a pipeline) by using BAM.</span></span>  

 <span data-ttu-id="10b3e-105">BAM には、パイプライン コンポーネントとオーケストレーションにまたがるビジネス アクティビティが再構築します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-105">BAM reconstructs the business activity that spans the pipeline component and orchestrations.</span></span> <span data-ttu-id="10b3e-106">最下位レベルでこの動作を呼び出して**EventStream.EnableContinuation**アクティビティの他のイベントが必要とする各実装コンポーネントから。</span><span class="sxs-lookup"><span data-stu-id="10b3e-106">At the lowest level, this works by calls to **EventStream.EnableContinuation** from each implementation component that expects more events for the activity.</span></span> <span data-ttu-id="10b3e-107">呼び出し**EnableContinuation**明示的な Orchestration1 と Orchestration2 が Continuation フォルダーを 1 つのスケジュールと後のスケジュールを ContinuationID フォルダーで追跡プロファイルに追加することで行われた呼び出し中にはです。</span><span class="sxs-lookup"><span data-stu-id="10b3e-107">The call to **EnableContinuation** is explicit, while calls in Orchestration1 and Orchestration2 are made by adding a Continuation folder to the Tracking profile in one schedule, and a ContinuationID folder to the schedule that follows it.</span></span>  

 <span data-ttu-id="10b3e-108">次の図は、このサンプルで使用されるワークフローを示しています。</span><span class="sxs-lookup"><span data-stu-id="10b3e-108">The following diagram illustrates the workflow used in the sample.</span></span>  

 <span data-ttu-id="10b3e-109">![](../core/media/ebiz-sdk-samples-bam-endtoendwkflw.gif "ebiz_sdk_samples_bam_endtoendwkflw")</span><span class="sxs-lookup"><span data-stu-id="10b3e-109">![](../core/media/ebiz-sdk-samples-bam-endtoendwkflw.gif "ebiz_sdk_samples_bam_endtoendwkflw")</span></span>  


## <a name="what-this-sample-does"></a><span data-ttu-id="10b3e-110">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="10b3e-110">What This Sample Does</span></span>  
 <span data-ttu-id="10b3e-111">BAM のエンド ツー エンドのサンプルでは、BAM を使用するパイプラインと複数のオーケストレーションから情報を収集し、1 つのアクティビティを更新する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-111">The BAM end-to-end sample shows how you can use BAM to gather information from a pipeline and multiple orchestrations and update a single activity.</span></span>  

## <a name="how-this-sample-was-designed-and-why"></a><span data-ttu-id="10b3e-112">このサンプルのデザイン方法とその理由</span><span class="sxs-lookup"><span data-stu-id="10b3e-112">How This Sample Was Designed and Why</span></span>  
 <span data-ttu-id="10b3e-113">BAM のエンド ツー エンドのサンプルは、次のアクティビティを示すために設計されました。</span><span class="sxs-lookup"><span data-stu-id="10b3e-113">The BAM end-to-end sample was designed to illustrate the following activities:</span></span>  

-   <span data-ttu-id="10b3e-114">BAM を使用して、パイプライン内で。</span><span class="sxs-lookup"><span data-stu-id="10b3e-114">Using BAM within a pipeline.</span></span>  

-   <span data-ttu-id="10b3e-115">追跡プロファイル エディター (TPE) を使用して、アクティビティ項目をオーケストレーションとメッセージの要素内の図形にマップします。</span><span class="sxs-lookup"><span data-stu-id="10b3e-115">Using the Tracking Profile Editor (TPE) to map activity items to shapes in an orchestration and elements of a message.</span></span>  

-   <span data-ttu-id="10b3e-116">Continuation を使用して、ソリューションの複数の部分は、アクティビティを投稿するときは、アクティビティを維持します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-116">Using continuations to keep an activity active when multiple pieces of a solution contribute to the activity.</span></span>  


<span data-ttu-id="10b3e-117">このサンプルはように動作します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-117">The sample works as follows:</span></span>  

1.  <span data-ttu-id="10b3e-118">入力メッセージがから取得した、 *\<サンプル パス\>* \BamEndToEnd\Input フォルダー。</span><span class="sxs-lookup"><span data-stu-id="10b3e-118">An input message is retrieved from the *\<Samples Path\>* \BamEndToEnd\Input folder.</span></span>  

2.  <span data-ttu-id="10b3e-119">パイプライン コンポーネントでは、メッセージに一意の DocumentID を割り当てるし、新しい BAM アクティビティを開始するために、BAM API を使用します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-119">The pipeline component assigns a unique DocumentID to the message, and uses the BAM API to begin a new BAM activity.</span></span> <span data-ttu-id="10b3e-120">オーケストレーションに使用できるようにする、入力メッセージの別の部分として DocumentID が添付されます。</span><span class="sxs-lookup"><span data-stu-id="10b3e-120">The DocumentID is attached as a separate part of the input message to make it available to the orchestrations.</span></span>  

3.  <span data-ttu-id="10b3e-121">入力メッセージを受信したときに、サービス Orchestration1 がアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="10b3e-121">The service Orchestration1 is activated when the input message is received.</span></span>  

4.  <span data-ttu-id="10b3e-122">Orchestration1 では、入力メッセージが変更され、パラメーターとして Orchestration2 に渡します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-122">Orchestration1 modifies the input message and passes it as a parameter to Orchestration2.</span></span>  

5.  <span data-ttu-id="10b3e-123">Orchestration2 によって入力メッセージが変更され、Orchestration3 をアクティブ化するメッセージ ボックス データベースに送信します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-123">Orchestration2 modifies the input message and sends it to the MessageBox database, which activates Orchestration3.</span></span>  

6.  <span data-ttu-id="10b3e-124">Orchestration3 のメッセージが変更され、フォルダーに書き込みます*\<サンプル パス\>* \BamEndToEnd\Output します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-124">Orchestration3 modifies the message and writes it to the folder *\<Samples Path\>* \BamEndToEnd\Output.</span></span>  

7.  <span data-ttu-id="10b3e-125">各オーケストレーションでは、BAM アクティビティ内のアクティビティ項目を更新します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-125">Each orchestration updates activity items in the BAM activity.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="10b3e-126">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="10b3e-126">Where to Find This Sample</span></span>  
 <span data-ttu-id="10b3e-127">このサンプルで*\<サンプル パス\>* \BAM\BamEndToEnd します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-127">You can find this sample at *\<Samples Path\>* \BAM\BamEndToEnd.</span></span>  

 <span data-ttu-id="10b3e-128">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="10b3e-128">The following table shows the files in this sample and describes their purpose.</span></span>  


|                                        <span data-ttu-id="10b3e-129">ファイル</span><span class="sxs-lookup"><span data-stu-id="10b3e-129">File(s)</span></span>                                        |                                         <span data-ttu-id="10b3e-130">説明</span><span class="sxs-lookup"><span data-stu-id="10b3e-130">Description</span></span>                                          |
|---------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------|
|                                    <span data-ttu-id="10b3e-131">BamEndToEnd.sln</span><span class="sxs-lookup"><span data-stu-id="10b3e-131">BamEndToEnd.sln</span></span>                                    |                               <span data-ttu-id="10b3e-132">BAM のエンド ツー エンドのサンプル ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="10b3e-132">BAM End-to-End sample solution.</span></span>                                |
|                                    <span data-ttu-id="10b3e-133">BamEndToEnd.xls</span><span class="sxs-lookup"><span data-stu-id="10b3e-133">BamEndToEnd.xls</span></span>                                    |                                 <span data-ttu-id="10b3e-134">BAM 定義スタイル シートです。</span><span class="sxs-lookup"><span data-stu-id="10b3e-134">BAM definition style sheet.</span></span>                                  |
|                                    <span data-ttu-id="10b3e-135">BamEndToEnd.xml</span><span class="sxs-lookup"><span data-stu-id="10b3e-135">BamEndToEnd.xml</span></span>                                    |                                     <span data-ttu-id="10b3e-136">BAM 定義 XML。</span><span class="sxs-lookup"><span data-stu-id="10b3e-136">BAM definition XML.</span></span>                                      |
|                                <span data-ttu-id="10b3e-137">BAMEndToEndBinding.xml</span><span class="sxs-lookup"><span data-stu-id="10b3e-137">BAMEndToEndBinding.xml</span></span>                                 |                                         <span data-ttu-id="10b3e-138">BAM バインド。</span><span class="sxs-lookup"><span data-stu-id="10b3e-138">BAM binding.</span></span>                                         |
|                                      <span data-ttu-id="10b3e-139">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="10b3e-139">Cleanup.bat</span></span>                                      |                              <span data-ttu-id="10b3e-140">サンプルの展開解除するバッチ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="10b3e-140">Batch file to undeploy the sample.</span></span>                              |
|                                   <span data-ttu-id="10b3e-141">InputMessage.xml</span><span class="sxs-lookup"><span data-stu-id="10b3e-141">InputMessage.xml</span></span>                                    |                                        <span data-ttu-id="10b3e-142">入力メッセージ。</span><span class="sxs-lookup"><span data-stu-id="10b3e-142">Input message.</span></span>                                        |
|                                       <span data-ttu-id="10b3e-143">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="10b3e-143">Setup.bat</span></span>                                       |                         <span data-ttu-id="10b3e-144">コンパイルして、サンプルを配置するバッチ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="10b3e-144">Batch file to compile and deploy the sample.</span></span>                         |
|                              <span data-ttu-id="10b3e-145">\Components\AssemblyInfo.cs</span><span class="sxs-lookup"><span data-stu-id="10b3e-145">\Components\AssemblyInfo.cs</span></span>                              |                                   <span data-ttu-id="10b3e-146">パイプライン コンポーネント コード。</span><span class="sxs-lookup"><span data-stu-id="10b3e-146">Pipeline component code.</span></span>                                   |
|                       <span data-ttu-id="10b3e-147">\Components\BAMMessagePartPLComponent.cs</span><span class="sxs-lookup"><span data-stu-id="10b3e-147">\Components\BAMMessagePartPLComponent.cs</span></span>                        |                                   <span data-ttu-id="10b3e-148">パイプライン コンポーネント コード。</span><span class="sxs-lookup"><span data-stu-id="10b3e-148">Pipeline component code.</span></span>                                   |
|                             <span data-ttu-id="10b3e-149">\Components\Components.csproj</span><span class="sxs-lookup"><span data-stu-id="10b3e-149">\Components\Components.csproj</span></span>                             |                                 <span data-ttu-id="10b3e-150">パイプライン コンポーネントのプロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="10b3e-150">Pipeline component project.</span></span>                                  |
| <span data-ttu-id="10b3e-151">\Messages\InputMessage01.xml</span><span class="sxs-lookup"><span data-stu-id="10b3e-151">\Messages\InputMessage01.xml</span></span><br /><br /> <span data-ttu-id="10b3e-152">[...]</span><span class="sxs-lookup"><span data-stu-id="10b3e-152">...</span></span><br /><br /> <span data-ttu-id="10b3e-153">\Messages\InputMessage10.xml</span><span class="sxs-lookup"><span data-stu-id="10b3e-153">\Messages\InputMessage10.xml</span></span> |                                    <span data-ttu-id="10b3e-154">サンプル入力メッセージ。</span><span class="sxs-lookup"><span data-stu-id="10b3e-154">Sample input messages.</span></span>                                    |
|                               <span data-ttu-id="10b3e-155">\Services\BAMInbound.btp</span><span class="sxs-lookup"><span data-stu-id="10b3e-155">\Services\BAMInbound.btp</span></span>                                |                                    <span data-ttu-id="10b3e-156">受信パイプライン ファイルです。</span><span class="sxs-lookup"><span data-stu-id="10b3e-156">Inbound pipeline file.</span></span>                                    |
|                              <span data-ttu-id="10b3e-157">\Services\BAMPartSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="10b3e-157">\Services\BAMPartSchema.xsd</span></span>                              |                                   <span data-ttu-id="10b3e-158">BAM パート メッセージ スキーマ。</span><span class="sxs-lookup"><span data-stu-id="10b3e-158">BAM part message schema.</span></span>                                   |
|                             <span data-ttu-id="10b3e-159">\Services\Orchestration1.odx</span><span class="sxs-lookup"><span data-stu-id="10b3e-159">\Services\Orchestration1.odx</span></span>                              |                                        <span data-ttu-id="10b3e-160">オーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="10b3e-160">Orchestration.</span></span>                                        |
|                             <span data-ttu-id="10b3e-161">\Services\Orchestration2.odx</span><span class="sxs-lookup"><span data-stu-id="10b3e-161">\Services\Orchestration2.odx</span></span>                              |                                        <span data-ttu-id="10b3e-162">オーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="10b3e-162">Orchestration.</span></span>                                        |
|                             <span data-ttu-id="10b3e-163">\Services\Orchestration3.odx</span><span class="sxs-lookup"><span data-stu-id="10b3e-163">\Services\Orchestration3.odx</span></span>                              |                                        <span data-ttu-id="10b3e-164">オーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="10b3e-164">Orchestration.</span></span>                                        |
|                             <span data-ttu-id="10b3e-165">\Services\PropertySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="10b3e-165">\Services\PropertySchema.xsd</span></span>                              |                                       <span data-ttu-id="10b3e-166">プロパティ スキーマ : </span><span class="sxs-lookup"><span data-stu-id="10b3e-166">Property schema.</span></span>                                       |
|                                 <span data-ttu-id="10b3e-167">\Services\Schema1.xsd</span><span class="sxs-lookup"><span data-stu-id="10b3e-167">\Services\Schema1.xsd</span></span>                                 |                                       <span data-ttu-id="10b3e-168">メッセージ スキーマです。</span><span class="sxs-lookup"><span data-stu-id="10b3e-168">Message schema.</span></span>                                        |
|                                 <span data-ttu-id="10b3e-169">\Services\Schema2.xsd</span><span class="sxs-lookup"><span data-stu-id="10b3e-169">\Services\Schema2.xsd</span></span>                                 |                                       <span data-ttu-id="10b3e-170">メッセージ スキーマです。</span><span class="sxs-lookup"><span data-stu-id="10b3e-170">Message schema.</span></span>                                        |
|                                 <span data-ttu-id="10b3e-171">Services\Schema3.xsd</span><span class="sxs-lookup"><span data-stu-id="10b3e-171">Services\Schema3.xsd</span></span>                                  |                                       <span data-ttu-id="10b3e-172">メッセージ スキーマです。</span><span class="sxs-lookup"><span data-stu-id="10b3e-172">Message schema.</span></span>                                        |
|                               <span data-ttu-id="10b3e-173">\Services\Services.btproj</span><span class="sxs-lookup"><span data-stu-id="10b3e-173">\Services\Services.btproj</span></span>                               | [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] <span data-ttu-id="10b3e-174">BizTalk ファイル プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="10b3e-174">BizTalk file project.</span></span> |
|                               <span data-ttu-id="10b3e-175">\Services\Transform_1.btm</span><span class="sxs-lookup"><span data-stu-id="10b3e-175">\Services\Transform_1.btm</span></span>                               |                                          <span data-ttu-id="10b3e-176">マップ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="10b3e-176">Map file.</span></span>                                           |
|                               <span data-ttu-id="10b3e-177">\Services\Transform_2.btm</span><span class="sxs-lookup"><span data-stu-id="10b3e-177">\Services\Transform_2.btm</span></span>                               |                                          <span data-ttu-id="10b3e-178">マップ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="10b3e-178">Map file.</span></span>                                           |
|                               <span data-ttu-id="10b3e-179">\Services\Transform_3.btm</span><span class="sxs-lookup"><span data-stu-id="10b3e-179">\Services\Transform_3.btm</span></span>                               |                                          <span data-ttu-id="10b3e-180">マップ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="10b3e-180">Map file.</span></span>                                           |

## <a name="how-to-use-this-sample"></a><span data-ttu-id="10b3e-181">このサンプルの使用方法</span><span class="sxs-lookup"><span data-stu-id="10b3e-181">How to Use This Sample</span></span>  
 <span data-ttu-id="10b3e-182">ビルドして BAM エンド ツー エンドのサンプルを実行するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-182">Use the following procedures to build and run the BAM End-to-End sample:</span></span>  

-   [<span data-ttu-id="10b3e-183">このサンプルをビルドして初期化</span><span class="sxs-lookup"><span data-stu-id="10b3e-183">To build and initialize this sample</span></span>](#To_Build_Sample)  

-   [<span data-ttu-id="10b3e-184">このサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="10b3e-184">To run this sample</span></span>](#To_Run_Sample)  

-   [<span data-ttu-id="10b3e-185">BAM データを表示するには</span><span class="sxs-lookup"><span data-stu-id="10b3e-185">To view the BAM data</span></span>](#To_View_Data)  

##  <a name="To_Build_Sample"></a><span data-ttu-id="10b3e-186">ビルドしてこのサンプルの初期化</span><span class="sxs-lookup"><span data-stu-id="10b3e-186">Build and initialize this sample</span></span>  

1.  <span data-ttu-id="10b3e-187">管理者は、コマンド プロンプトを開き、実行*\<サンプル パス\>* \BAM\BAMEndToEnd\Setup.bat します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-187">Open a command prompt as Administrator, and run *\<Samples Path\>* \BAM\BAMEndToEnd\Setup.bat.</span></span> <span data-ttu-id="10b3e-188">Setup.bat は、ビルドして、このサンプルの BAM インフラストラクチャを初期化します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-188">Setup.bat builds and initializes the BAM infrastructure for this sample.</span></span> <span data-ttu-id="10b3e-189">コマンド プロンプトは開いたままにしておきます。</span><span class="sxs-lookup"><span data-stu-id="10b3e-189">Keep the command prompt open.</span></span>  

2.  <span data-ttu-id="10b3e-190">Orchestration1、Orchestration2、および Orchestration3 を BAM アクティビティにマップする追跡プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-190">Create a tracking profile to map Orchestration1, Orchestration2, and Orchestration3 to the BAM activity.</span></span> <span data-ttu-id="10b3e-191">(詳細な手順がという別の手順では、追跡プロファイルの作成は複雑なプロセスなので**追跡プロファイルを作成する**します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-191">(Because creating the tracking profile is a complex process, the detailed instructions are in a separate procedure called **To create a tracking profile**.</span></span> <span data-ttu-id="10b3e-192">この手順が表示されますこのドキュメントで後述します。)</span><span class="sxs-lookup"><span data-stu-id="10b3e-192">This procedure appears later in this document.)</span></span>  

3.  <span data-ttu-id="10b3e-193">前の手順で作成した BamEndToEnd.btt 追跡プロファイルを展開します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-193">Deploy the tracking profile BamEndToEnd.btt that you created in the previous step.</span></span>  <span data-ttu-id="10b3e-194">コマンド プロンプトでを変更、 *\<サンプル パス\>* \BAM\BamEndToEnd ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="10b3e-194">In the command prompt change to the *\<Samples Path\>* \BAM\BamEndToEnd directory.</span></span> <span data-ttu-id="10b3e-195">追跡プロファイルを展開するには、次の行を入力し、キーを押します**Enter**:</span><span class="sxs-lookup"><span data-stu-id="10b3e-195">To deploy the tracking profile, type the following line, and then press **Enter**:</span></span>  

    `“<BizTalkInstallationPath>\Tracking\bttdeploy” BamEndToEnd.btt`

     <span data-ttu-id="10b3e-196">[追跡プロファイル管理ユーティリティを使って追跡プロファイルを展開する方法](../core/how-to-deploy-tracking-profiles-with-the-tracking-profiles-management-utility.md)詳細に説明します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-196">[How to Deploy Tracking Profiles with the Tracking Profiles Management Utility](../core/how-to-deploy-tracking-profiles-with-the-tracking-profiles-management-utility.md) provides more information.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="10b3e-197">ContinuationID orch1 _ に一致する Continuation がないこと、メッセージを無視することができます。</span><span class="sxs-lookup"><span data-stu-id="10b3e-197">You can ignore the message that the ContinuationID Orch1_ does not have a matching Continuation.</span></span> <span data-ttu-id="10b3e-198">パイプライン コンポーネントでは、追跡プロファイルではなく、orch1 _ という名前の continuation が定義されているため、このメッセージが必要です。</span><span class="sxs-lookup"><span data-stu-id="10b3e-198">This message is expected, because the continuation named Orch1_ is defined in the pipeline component, and not in the tracking profile.</span></span>  

##  <a name="To_Run_Sample"></a><span data-ttu-id="10b3e-199">このサンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-199">Run this sample</span></span>  

<span data-ttu-id="10b3e-200">ファイルをコピー *\<サンプル パス\>* フォルダーに \BamEndToEnd\InputMessage.xml *\<サンプル パス\>* \BamEndToEnd\Input します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-200">Copy the file *\<Samples Path\>* \BamEndToEnd\InputMessage.xml into the folder *\<Samples Path\>* \BamEndToEnd\Input.</span></span> <span data-ttu-id="10b3e-201">入力フォルダーから、数秒後に、メッセージが表示されなくなり、出力メッセージが表示されます、 *\<サンプル パス\>* \BamEndToEnd\Output フォルダー。</span><span class="sxs-lookup"><span data-stu-id="10b3e-201">After a few seconds, the message disappears from the Input folder, and an output message appears in the *\<Samples Path\>* \BamEndToEnd\Output folder.</span></span>  

##  <a name="To_View_Data"></a><span data-ttu-id="10b3e-202">BAM データを表示します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-202">View the BAM data</span></span>  

1.  <span data-ttu-id="10b3e-203">SQL Server Management Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="10b3e-203">Open SQL Server Management Studio.</span></span>  

2.  <span data-ttu-id="10b3e-204">SQL Server Management studio で、サーバーを展開し、**データベース**、展開**BAMPrimaryImport**、順に展開**テーブル**します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-204">In SQL Server Management Studio, expand the server, expand **Databases**, expand **BAMPrimaryImport**, and then expand **Tables**.</span></span>  

3.  <span data-ttu-id="10b3e-205">右クリックして**dbo.bam_EndToEndActivity_Completed**、 をクリックし、**テーブルを開く**します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-205">Right-click **dbo.bam_EndToEndActivity_Completed**, and then click **Open Table**.</span></span> <span data-ttu-id="10b3e-206">SQL Server を使用している場合はクリックして**上位 1000 行を選択する**します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-206">If you are using SQL Server, click **Select top 1000 rows**.</span></span>  

     <span data-ttu-id="10b3e-207">Bam_EndToEndActivity_Completed テーブルの内容は、右側のウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="10b3e-207">The contents of the bam_EndToEndActivity_Completed table are displayed in the right pane.</span></span> <span data-ttu-id="10b3e-208">テーブルの各行は、完了した EndToEndActivity アクティビティを表します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-208">Each row in the table represents an EndToEndActivity activity that has been completed.</span></span>  

#### <a name="rerun-this-sample"></a><span data-ttu-id="10b3e-209">このサンプルを再実行します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-209">Rerun this sample</span></span>  

1. <span data-ttu-id="10b3e-210">管理者は、コマンド プロンプトを開き、変更、 *\<サンプル パス\>* \BAM\BamEndToEnd ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="10b3e-210">Open a command prompt as Administrator, and change to the *\<Samples Path\>* \BAM\BamEndToEnd directory.</span></span> <span data-ttu-id="10b3e-211">次の行を入力します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-211">Type the following line:</span></span>  

   `“C:\Program Files\Microsoft BizTalk Server <version>\Tracking\bttdeploy” BamEndToEnd.btt /remove`  

   > [!NOTE]
   >  <span data-ttu-id="10b3e-212">インストールしなかった場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を C ドライブにインストールされている、ドライブ文字"C"を置き換えます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-212">If you did not install [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to the C drive, replace "C" with the drive letter where you installed [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  

2. <span data-ttu-id="10b3e-213">実行*\<サンプル パス\>* \BAM\BAMEndToEnd\Cleanup.bat します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-213">Run *\<Samples Path\>* \BAM\BAMEndToEnd\Cleanup.bat.</span></span> <span data-ttu-id="10b3e-214">Cleanup.bat は、このサンプルの BAM インフラストラクチャを削除します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-214">Cleanup.bat removes the BAM infrastructure for this sample.</span></span>  

3. <span data-ttu-id="10b3e-215">手順に従います**このサンプルをビルドして初期化**このトピックの「します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-215">Perform the steps in **To build and initialize this sample** section in this topic.</span></span>  

##  <a name="TPE_procedure"></a><span data-ttu-id="10b3e-216">追跡プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-216">Create a tracking profile</span></span>  

1. <span data-ttu-id="10b3e-217">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-217">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)].</span></span> <span data-ttu-id="10b3e-218">右クリックして**追跡プロファイル エディター**、および**管理者として実行**します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-218">Right-click **Tracking Profile Editor**, and **Run as administrator**.</span></span>  

2. <span data-ttu-id="10b3e-219">左側のウィンドウで、**追跡プロファイル エディター**ウィンドウで、をクリックして**ここをクリックすると、BAM アクティビティ定義をインポートする**します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-219">In the left pane of the **Tracking Profile Editor** window, click **Click here to import a BAM Activity Definition**.</span></span>  

3. <span data-ttu-id="10b3e-220">**BAM アクティビティ定義名**のセクション、 **BAM アクティビティ定義のインポート**ダイアログ ボックスで、 **endtoendactivity**、 をクリックし、 **ok**.</span><span class="sxs-lookup"><span data-stu-id="10b3e-220">In the  **BAM Activity Definition Name** section of the **Import BAM Activity Definition** dialog box, select **EndToEndActivity**, and then click **OK**.</span></span>  

4. <span data-ttu-id="10b3e-221">右側のウィンドウで、**追跡プロファイル エディター**ウィンドウで、をクリックして**ここをクリックすると、イベント ソースを選択する**します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-221">In the right pane of the **Tracking Profile Editor** window, click **Click here to select an event source**.</span></span>  

5. <span data-ttu-id="10b3e-222">**アセンブリ名**のセクション、 **イベント ソースの親アセンブリ**ダイアログ ボックスで、 **Microsoft.Samples.BizTalk.BamEndToEnd.Services**、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-222">In the **Assembly Name** section of the **Select Event Source Parent Assembly** dialog box, select **Microsoft.Samples.BizTalk.BamEndToEnd.Services**, and then click **Next**.</span></span>  

6. <span data-ttu-id="10b3e-223">**オーケストレーション名**のセクション、**オーケストレーションの選択**ダイアログ ボックスで、 **BamEndToEnd.Services.Orchestration1**、 をクリックし、 **ok**.</span><span class="sxs-lookup"><span data-stu-id="10b3e-223">In the **Orchestration Name** section of the **Select Orchestration** dialog box, select **BamEndToEnd.Services.Orchestration1**, and then click **OK**.</span></span>  

7. <span data-ttu-id="10b3e-224">左側のウィンドウで、**追跡プロファイル エディター**ウィンドウで、右クリック **[endtoendactivity]**、順にクリックします**新しい ContinuationID**します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-224">In the left pane of the **Tracking Profile Editor** window, right-click **EndToEndActivity**, and then click **New ContinuationID**.</span></span> <span data-ttu-id="10b3e-225">新しい continuation ID の名前を付けます**orch1 _** します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-225">Name the new continuation ID **Orch1_**.</span></span> <span data-ttu-id="10b3e-226">2 つの continuation Id という名前を作成するには、この手順を繰り返します**orch2 _** と**orch3 _** します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-226">Repeat this step to create two more continuation IDs named **Orch2_** and **Orch3_**.</span></span>  

8. <span data-ttu-id="10b3e-227">右クリックして**endtoendactivity**、 をクリックし、**新しい Continuation**します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-227">Right-click **EndToEndActivity**, and then click **New Continuation**.</span></span> <span data-ttu-id="10b3e-228">新しい continuation の名前**orch2 _** します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-228">Name the new continuation **Orch2_**.</span></span> <span data-ttu-id="10b3e-229">という名前のもう 1 つの continuation を作成するには、この手順を繰り返します**orch3 _** します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-229">Repeat this step to create another continuation named **Orch3_**.</span></span>  

9. <span data-ttu-id="10b3e-230">右クリックし、 **Receive1**図形をクリックして**コンテキスト プロパティ スキーマ**します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-230">Right-click the **Receive1** shape, and then click **Context Property Schemas**.</span></span>  

10. <span data-ttu-id="10b3e-231">最後までスクロール、**コンテキスト プロパティ名**、一覧表示し、ダブルクリック**BAMEndToEnd.Services.PropertySchema.DocumentID**します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-231">Scroll to the end of the **Context Property Name** list, and then double-click **BAMEndToEnd.Services.PropertySchema.DocumentID**.</span></span>  

11. <span data-ttu-id="10b3e-232">展開**\<スキーマ\>**、し、ドラッグ**DocumentID**を右側のウィンドウで**orch1 _** 左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="10b3e-232">Expand **\<Schema\>**, and then drag **DocumentID** in the right pane to **Orch1_** in the left pane.</span></span>  

12. <span data-ttu-id="10b3e-233">矢印の付いたフォルダー アイコンをクリックします (![フォルダーと上矢印ボタン](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4"))、オーケストレーションを表示するには、2 回クリックします。</span><span class="sxs-lookup"><span data-stu-id="10b3e-233">Click the folder icon with the arrow (![button with folder and up arrow](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4")) twice to display the orchestration.</span></span>  

13. <span data-ttu-id="10b3e-234">ドラッグ、 **Receive1**右側のウィンドウに図形 **[sbegin1]** 左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="10b3e-234">Drag the **Receive1** shape in the right pane to **SBegin1** in the left pane.</span></span>  

14. <span data-ttu-id="10b3e-235">ドラッグ、 **StartOrchestration_1**右側のウィンドウに図形 **[send1]** 左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="10b3e-235">Drag the **StartOrchestration_1** shape in the right pane to **SEnd1** in the left pane.</span></span>  

15. <span data-ttu-id="10b3e-236">右クリックし、 **StartOrchestration_1**図形をクリックして**メッセージ ペイロード スキーマ**します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-236">Right-click the **StartOrchestration_1** shape, and then click **Message Payload Schemas**.</span></span>  

16. <span data-ttu-id="10b3e-237">値"Message_2"を含む行をダブルクリックして、**メッセージ**列と値"MessageBody"で、**一部**列。</span><span class="sxs-lookup"><span data-stu-id="10b3e-237">Double-click the row that contains the value “Message_2” in the **Message** column and the value “MessageBody” in the **Part** column.</span></span>  

     <span data-ttu-id="10b3e-238">![TPE メッセージ ペイロード スキーマが表示されたメッセージ&#95;2](../core/media/77fbc444-46cf-4d45-8e9c-c330da7ba7d1.gif "77fbc444-46cf-4d45-8e9c-c330da7ba7d1")</span><span class="sxs-lookup"><span data-stu-id="10b3e-238">![TPE Message Payload schema showing message&#95;2](../core/media/77fbc444-46cf-4d45-8e9c-c330da7ba7d1.gif "77fbc444-46cf-4d45-8e9c-c330da7ba7d1")</span></span>  

17. <span data-ttu-id="10b3e-239">展開**Schema2**、し、ドラッグ**Data2**を右側のウィンドウで**Data1**左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="10b3e-239">Expand **Schema2**, and then drag **Data2** in the right pane to **Data1** in the left pane.</span></span>  

18. <span data-ttu-id="10b3e-240">をクリックして**イベント ソースの選択**、] をクリックし、 **[コンテキスト プロパティの**します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-240">Click **Select Event Source**, and then click **Select Context Property**.</span></span>  

19. <span data-ttu-id="10b3e-241">最後までスクロール、**コンテキスト プロパティ名**、一覧表示し、ダブルクリック**BAMEndToEnd.Services.PropertySchema.DocumentID**します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-241">Scroll to the end of the **Context Property Name** list, and then double-click **BAMEndToEnd.Services.PropertySchema.DocumentID**.</span></span>  

20. <span data-ttu-id="10b3e-242">展開**\<スキーマ\>**、し、ドラッグ**DocumentID**を**orch2 _** 左側のウィンドウで継続します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-242">Expand **\<Schema\>**, and then drag **DocumentID** to the **Orch2_** continuation in the left pane.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="10b3e-243">Orch2 _ continuation と orch2 _ continuation ID を混同しないでください。</span><span class="sxs-lookup"><span data-stu-id="10b3e-243">Do not confuse the Orch2_ continuation with the Orch2_ continuation ID.</span></span> <span data-ttu-id="10b3e-244">Continuation ID を表すアイコンには、キーが含まれています (![continuation ID のアイコン](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea"))、continuation を表すアイコンにキー (が含まれていません![continuation のアイコン](../core/media/test.gif "テスト"))。</span><span class="sxs-lookup"><span data-stu-id="10b3e-244">The icon that represents a continuation ID contains a key (![icon for a continuation ID](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea")), whereas the icon that represents a continuation does not contain a key (![icon for a continuation](../core/media/test.gif "test")).</span></span>  

21. <span data-ttu-id="10b3e-245">をクリックして**イベント ソースの選択**、] をクリックし、 **[オーケストレーション スケジュールの**します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-245">Click **Select Event Source**, and then click **Select Orchestration Schedule**.</span></span>  

22. <span data-ttu-id="10b3e-246">**アセンブリ名**のセクション、 **イベント ソースの親アセンブリ**ダイアログ ボックスで、 **Microsoft.Samples.BizTalk.BamEndToEnd.Services**、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-246">In the **Assembly Name** section of the **Select Event Source Parent Assembly** dialog box, select **Microsoft.Samples.BizTalk.BamEndToEnd.Services**, and then click **Next**.</span></span>  

23. <span data-ttu-id="10b3e-247">**オーケストレーション名**のセクション、**オーケストレーションの選択**ダイアログ ボックスで、 **BamEndToEnd.Services.Orchestration2**、 をクリックし、 **ok**.</span><span class="sxs-lookup"><span data-stu-id="10b3e-247">In the **Orchestration Name** section of the **Select Orchestration** dialog box, select **BamEndToEnd.Services.Orchestration2**, and then click **OK**.</span></span>  

24. <span data-ttu-id="10b3e-248">右クリックし、 **ConstructMessage_1**図形をクリックして**メッセージ ペイロード スキーマ**します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-248">Right-click the **ConstructMessage_1** shape, and then click **Message Payload Schemas**.</span></span>  

25. <span data-ttu-id="10b3e-249">値"Message_3"を含む行をダブルクリックして、**メッセージ**列と値に"BAMPart"で、**一部**列。</span><span class="sxs-lookup"><span data-stu-id="10b3e-249">Double-click the row that contains the value “Message_3” in the **Message** column and the value “BAMPart” in the **Part** column.</span></span>  

26. <span data-ttu-id="10b3e-250">展開**BAMPart**、し、ドラッグ**DocumentID**を右側のウィンドウで、 **orch2 _** 左側のウィンドウで continuation ID。</span><span class="sxs-lookup"><span data-stu-id="10b3e-250">Expand **BAMPart**, and then drag **DocumentID** in the right pane to the **Orch2_** continuation ID in the left pane.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="10b3e-251">Orch2 _ continuation と orch2 _ continuation ID を混同しないでください。</span><span class="sxs-lookup"><span data-stu-id="10b3e-251">Do not confuse the Orch2_ continuation with the Orch2_ continuation ID.</span></span> <span data-ttu-id="10b3e-252">Continuation ID を表すアイコンには、キーが含まれています (![continuation ID のアイコン](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea"))、continuation を表すアイコンにキー (が含まれていません![continuation のアイコン](../core/media/test.gif "テスト"))。</span><span class="sxs-lookup"><span data-stu-id="10b3e-252">The icon that represents a continuation ID contains a key (![icon for a continuation ID](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea")), whereas the icon that represents a continuation does not contain a key (![icon for a continuation](../core/media/test.gif "test")).</span></span>  

27. <span data-ttu-id="10b3e-253">矢印の付いたフォルダー アイコンをクリックします (![フォルダーでボタンをクリックし、セットアップ&#45;矢印](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4"))、オーケストレーションを表示するには、2 回です。</span><span class="sxs-lookup"><span data-stu-id="10b3e-253">Click the folder icon with the arrow (![button with folder and up&#45;arrow](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4")) twice to display the orchestration.</span></span>  

28. <span data-ttu-id="10b3e-254">ドラッグ、 **ConstructMessage_1**右側のウィンドウに図形 **[sbegin2]** 左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="10b3e-254">Drag the **ConstructMessage_1** shape in the right pane to **SBegin2** in the left pane.</span></span>  

29. <span data-ttu-id="10b3e-255">ドラッグ、 **Send_1**右側のウィンドウに図形 **[send2]** 左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="10b3e-255">Drag the **Send_1** shape in the right pane to **SEnd2** in the left pane.</span></span>  

30. <span data-ttu-id="10b3e-256">右クリックし、 **Send_1**図形をクリックして**メッセージ ペイロード スキーマ**します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-256">Right-click the **Send_1** shape, and then click **Message Payload Schemas**.</span></span>  

31. <span data-ttu-id="10b3e-257">値"Message_3"を含む行をダブルクリックして、**メッセージ**列と値"MessageBody"で、**一部**列。</span><span class="sxs-lookup"><span data-stu-id="10b3e-257">Double-click the row that contains the value “Message_3” in the **Message** column and the value “MessageBody” in the **Part** column.</span></span>  

32. <span data-ttu-id="10b3e-258">展開**Schema3**、し、ドラッグ**Data3**を右側のウィンドウで**Data2**左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="10b3e-258">Expand **Schema3**, and then drag **Data3** in the right pane to **Data2** in the left pane.</span></span>  

33. <span data-ttu-id="10b3e-259">右ペインの上のドロップダウン リストから選択**メッセージ ペイロード スキーマ**します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-259">From the drop-down list above the right pane, select **Message Payload Schemas**.</span></span>  

34. <span data-ttu-id="10b3e-260">値"Message_3"を含む行をダブルクリックして、**メッセージ**列と値に"BAMPart"で、**一部**列。</span><span class="sxs-lookup"><span data-stu-id="10b3e-260">Double-click the row that contains the value “Message_3” in the **Message** column and the value “BAMPart” in the **Part** column.</span></span>  

35. <span data-ttu-id="10b3e-261">展開**BAMPart**、し、ドラッグ**DocumentID**を右側のウィンドウで、 **orch3 _** 左側のウィンドウで継続します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-261">Expand **BAMPart**, and then drag **DocumentID** in the right pane to the **Orch3_** continuation in the left pane.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="10b3e-262">Orch3 _ continuation と orch3 _ continuation ID を混同しないでください。</span><span class="sxs-lookup"><span data-stu-id="10b3e-262">Do not confuse the Orch3_ continuation with the Orch3_ continuation ID.</span></span> <span data-ttu-id="10b3e-263">Continuation ID を表すアイコンには、キーが含まれています (![continuation ID のアイコン](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea"))、continuation を表すアイコンにキー (が含まれていません![continuation のアイコン](../core/media/test.gif "テスト"))。</span><span class="sxs-lookup"><span data-stu-id="10b3e-263">The icon that represents a continuation ID contains a key (![icon for a continuation ID](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea")), whereas the icon that represents a continuation does not contain a key (![icon for a continuation](../core/media/test.gif "test")).</span></span>  

36. <span data-ttu-id="10b3e-264">をクリックして**イベント ソースの選択**、] をクリックし、 **[オーケストレーション スケジュールの**します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-264">Click **Select Event Source**, and then click **Select Orchestration Schedule**.</span></span>  

37. <span data-ttu-id="10b3e-265">**アセンブリ名**のセクション、 **イベント ソースの親アセンブリ**ダイアログ ボックスで、 **Microsoft.Samples.BizTalk.BamEndToEnd.Services**、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-265">In the **Assembly Name** section of the **Select Event Source Parent Assembly** dialog box, select **Microsoft.Samples.BizTalk.BamEndToEnd.Services**, and then click **Next**.</span></span>  

38. <span data-ttu-id="10b3e-266">**オーケストレーション名**のセクション、**オーケストレーションの選択**ダイアログ ボックスで、 **BamEndToEnd.Services.Orchestration3**、 をクリックし、 **ok**.</span><span class="sxs-lookup"><span data-stu-id="10b3e-266">In the **Orchestration Name** section of the **Select Orchestration** dialog box, select **BamEndToEnd.Services.Orchestration3**, and then click **OK**.</span></span>  

39. <span data-ttu-id="10b3e-267">右クリックし、 **Receive1**図形をクリックして**メッセージ ペイロード スキーマ**します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-267">Right-click the **Receive1** shape, and then click **Message Payload Schemas**.</span></span>  

40. <span data-ttu-id="10b3e-268">値"Message_3"を含む行をダブルクリックして、**メッセージ**列と値に"BAMPart"で、**一部**列。</span><span class="sxs-lookup"><span data-stu-id="10b3e-268">Double-click the row that contains the value “Message_3” in the **Message** column and the value “BAMPart” in the **Part** column.</span></span>  

41. <span data-ttu-id="10b3e-269">展開**BAMPart**、し、ドラッグ**DocumentID**を右側のウィンドウで、 **orch3 _** 左側のウィンドウで continuation ID。</span><span class="sxs-lookup"><span data-stu-id="10b3e-269">Expand **BAMPart**, and then drag **DocumentID** in the right pane to the **Orch3_** continuation ID in the left pane.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="10b3e-270">Orch3 _ continuation と orch3 _ continuation ID を混同しないでください。</span><span class="sxs-lookup"><span data-stu-id="10b3e-270">Do not confuse the Orch3_ continuation with the Orch3_ continuation ID.</span></span> <span data-ttu-id="10b3e-271">Continuation ID を表すアイコンには、キーが含まれています (![continuation ID のアイコン](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea"))、continuation を表すアイコンにキー (が含まれていません![continuation のアイコン](../core/media/test.gif "テスト"))。</span><span class="sxs-lookup"><span data-stu-id="10b3e-271">The icon that represents a continuation ID contains a key (![icon for a continuation ID](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea")), whereas the icon that represents a continuation does not contain a key (![icon for a continuation](../core/media/test.gif "test")).</span></span>  

42. <span data-ttu-id="10b3e-272">矢印の付いたフォルダー アイコンをクリックします (![フォルダーと上矢印ボタン](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4"))、オーケストレーションを表示するには、2 回クリックします。</span><span class="sxs-lookup"><span data-stu-id="10b3e-272">Click the folder icon with the arrow (![button with folder and up arrow](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4")) twice to display the orchestration.</span></span>  

43. <span data-ttu-id="10b3e-273">ドラッグ、 **Receive1**右側のウィンドウに図形 **[sbegin3]** 左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="10b3e-273">Drag the **Receive1** shape in the right pane to **SBegin3** in the left pane.</span></span>  

44. <span data-ttu-id="10b3e-274">ドラッグ、 **Send_1**右側のウィンドウに図形 **[send3]** 左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="10b3e-274">Drag the **Send_1** shape in the right pane to **SEnd3** in the left pane.</span></span>  

45. <span data-ttu-id="10b3e-275">右クリックし、 **Send_1**図形をクリックして**メッセージ ペイロード スキーマ**します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-275">Right-click the **Send_1** shape, and then click **Message Payload Schema**.</span></span>  

46. <span data-ttu-id="10b3e-276">展開**Schema3**、し、ドラッグ**Data3**を右側のウィンドウで**Data3**左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="10b3e-276">Expand **Schema3**, and then drag **Data3** in the right pane to **Data3** in the left pane.</span></span>  

47. <span data-ttu-id="10b3e-277">右クリック**DocumentID**下、 **orch2 _** クリックして、継続**ポート マッピングの設定**します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-277">Right-click **DocumentID** below the **Orch2_** continuation, and then click **Set Port Mappings**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="10b3e-278">Orch2 _ continuation と orch2 _ continuation ID を混同しないでください。</span><span class="sxs-lookup"><span data-stu-id="10b3e-278">Do not confuse the Orch2_ continuation with the Orch2_ continuation ID.</span></span> <span data-ttu-id="10b3e-279">Continuation ID を表すアイコンには、キーが含まれています (![continuation ID のアイコン](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea"))、continuation を表すアイコンにキー (が含まれていません![continuation のアイコン](../core/media/test.gif "テスト"))。</span><span class="sxs-lookup"><span data-stu-id="10b3e-279">The icon that represents a continuation ID contains a key (![icon for a continuation ID](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea")), whereas the icon that represents a continuation does not contain a key (![icon for a continuation](../core/media/test.gif "test")).</span></span>  

48. <span data-ttu-id="10b3e-280">**ポートの選択**のセクション、**ポートの選択**ダイアログ ボックスで、 をクリックして**BamEndToEnd_ReceivePort**、クリックして-不等号 ( **>**)、をクリックし、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-280">In the **Select Ports** section of the **Select Ports** dialog box, click **BamEndToEnd_ReceivePort**, click the greater-than sign (**>**), and then click **OK**.</span></span>  

49. <span data-ttu-id="10b3e-281">追跡プロファイルを保存*\<サンプル パス\>* \BAM\BamEndToEnd\BamEndToEnd.btt します。</span><span class="sxs-lookup"><span data-stu-id="10b3e-281">Save the tracking profile to *\<Samples Path\>* \BAM\BamEndToEnd\BamEndToEnd.btt.</span></span>  

## <a name="important-details"></a><span data-ttu-id="10b3e-282">重要な詳細情報</span><span class="sxs-lookup"><span data-stu-id="10b3e-282">Important details</span></span>  
 <span data-ttu-id="10b3e-283">パイプラインでは、追跡プロファイルはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="10b3e-283">Tracking profiles are not supported for pipelines.</span></span> <span data-ttu-id="10b3e-284">ただし、呼び出し**BeginActivity**パイプライン コンポーネントは、オーケストレーションで ActivityID の使用と同じです。</span><span class="sxs-lookup"><span data-stu-id="10b3e-284">However, the call to **BeginActivity** in the pipeline component is the same as using ActivityID in an orchestration.</span></span> <span data-ttu-id="10b3e-285">呼び出し**EnableContinuation**オーケストレーションでの continuation の使用と同じです。</span><span class="sxs-lookup"><span data-stu-id="10b3e-285">The call to **EnableContinuation** is the same as using a continuation in an orchestration.</span></span>  

## <a name="see-also"></a><span data-ttu-id="10b3e-286">参照</span><span class="sxs-lookup"><span data-stu-id="10b3e-286">See Also</span></span>  
 [<span data-ttu-id="10b3e-287">ビジネス アクティビティの監視 (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="10b3e-287">Business Activity Monitoring (BizTalk Server Samples Folder)</span></span>](../core/business-activity-monitoring-biztalk-server-samples-folder.md)