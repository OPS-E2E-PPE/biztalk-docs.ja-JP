---
title: "メッセージ強化サンプル (BizTalk Server サンプル) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a41ed707-dbdb-46b7-97a6-86fdbc8ad285
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3413345c4e2d0a2ce4cd7ee1cb5ebda50b1dea7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="message-enrichment-sample-biztalk-server-sample"></a><span data-ttu-id="39031-102">メッセージ強化サンプル (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="39031-102">Message Enrichment Sample (BizTalk Server Sample)</span></span>
<span data-ttu-id="39031-103">このメッセージ強化サンプルでは、X12 ドキュメントおよび EDIFACT ドキュメント用のインターチェンジ ヘッダーをトランザクション セット メッセージに追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="39031-103">The Message Enrichment sample demonstrates how to append interchange headers to transaction-set messages for X12 and EDIFACT documents.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="39031-104">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="39031-104">What This Sample Does</span></span>  
 <span data-ttu-id="39031-105">このサンプルでは、EDIFACT 用の UNA、UNB、および UNG ヘッダーと X12 用の ISA ヘッダーをトランザクション セットに追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="39031-105">This sample demonstrates how to append UNA, UNB, and UNG headers for EDIFACT, and ISA headers for X12, to transaction sets.</span></span> <span data-ttu-id="39031-106">具体的には、このサンプルは以下の処理を行います。</span><span class="sxs-lookup"><span data-stu-id="39031-106">Specifically, this sample does the following:</span></span>  
  
1.  <span data-ttu-id="39031-107">テスト メッセージを \Message Enrichment\In フォルダーにドロップすると、受信ポートがそのメッセージを取得して処理し、MessageBox にドロップします。</span><span class="sxs-lookup"><span data-stu-id="39031-107">When you drop the test message to the \Message Enrichment\In folder, the receive port picks it up, processes it, and drops it in the MessageBox.</span></span>  
  
2.  <span data-ttu-id="39031-108">MessageEnrichmentOrchestration は、受信図形に対して設定されているフィルター式に基づいてメッセージにサブスクライブするため、このテスト メッセージを MessageBox から取得します。</span><span class="sxs-lookup"><span data-stu-id="39031-108">The MessageEnrichmentOrchestration picks the test message up from the MessageBox, because it subscribes to messages based on a filter expression set on its receive shape.</span></span>  
  
3.  <span data-ttu-id="39031-109">オーケストレーションは、このメッセージのコンテキスト プロパティからインターチェンジ ヘッダーを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="39031-109">The orchestration reads the interchange headers from the context properties of the message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="39031-110">UNA ヘッダーと UNG ヘッダーは EDIFACT メッセージに含まれている必要がないため、メッセージのコンテキスト プロパティに含まれていない場合があります。</span><span class="sxs-lookup"><span data-stu-id="39031-110">UNA and UNG headers are optional in an EDIFACT message, so can be missing in the context properties of a message.</span></span>  
  
4.  <span data-ttu-id="39031-111">オーケストレーションは、インターチェンジ ヘッダーとメッセージ本文の両方を単一の新規メッセージに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="39031-111">The orchestration writes both the interchange headers and the message body into a single new message.</span></span>  
  
5.  <span data-ttu-id="39031-112">オーケストレーションは、ReceivePortNameCorrelationType 関連付けの種類で設定されている追加のプロパティをメッセージに昇格させます。</span><span class="sxs-lookup"><span data-stu-id="39031-112">The orchestration promotes additional properties that are set in the ReceivePortNameCorrelationType correlation type onto the message.</span></span> <span data-ttu-id="39031-113">これにより、オーケストレーションのユーザーは、サブスクリプションに必要なプロパティの一覧を選択できるようになります。</span><span class="sxs-lookup"><span data-stu-id="39031-113">These allow users of the orchestration to select a list of the properties they need for their subscription.</span></span> <span data-ttu-id="39031-114">これらのプロパティは、メッセージの構築図形に書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="39031-114">These properties are written in a construct message shape.</span></span> <span data-ttu-id="39031-115">元のメッセージに書き込まれたすべてのコンテキスト プロパティが新規メッセージに書き込まれるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="39031-115">Not all context properties that were written to the original message are written to the new message.</span></span>  
  
6.  <span data-ttu-id="39031-116">オーケストレーションは、新規メッセージを MessageBox にドロップします。</span><span class="sxs-lookup"><span data-stu-id="39031-116">The orchestration drops the new message into the MessageBox.</span></span>  
  
7.  <span data-ttu-id="39031-117">送信ポートは、新規メッセージを取得し、ファイル アダプター経由で \Message Enrichment\Out フォルダーに送信します。</span><span class="sxs-lookup"><span data-stu-id="39031-117">The send port picks up the new message and sends it via the FILE adapter to the \Message Enrichment\Out folder.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="39031-118">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="39031-118">Where to Find This Sample</span></span>  
 <span data-ttu-id="39031-119">このサンプルに格納、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストール フォルダー: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \samples\edi\message Enrichment。</span><span class="sxs-lookup"><span data-stu-id="39031-119">This sample is located in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation folder: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\EDI\Message Enrichment.</span></span>  
  
 <span data-ttu-id="39031-120">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="39031-120">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="39031-121">ファイル</span><span class="sxs-lookup"><span data-stu-id="39031-121">File(s)</span></span>|<span data-ttu-id="39031-122">Description</span><span class="sxs-lookup"><span data-stu-id="39031-122">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="39031-123">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="39031-123">Cleanup.bat</span></span>|<span data-ttu-id="39031-124">サンプル シナリオの展開を解除します。</span><span class="sxs-lookup"><span data-stu-id="39031-124">Undeploys the example scenario.</span></span> <span data-ttu-id="39031-125">このファイルが正しく実行されるには、オーケストレーションのアクティブなインスタンスがないことが必要です。</span><span class="sxs-lookup"><span data-stu-id="39031-125">In order for it to succeed there must be no active instances of the orchestration.</span></span> <span data-ttu-id="39031-126">アクティブなインスタンスがある場合、ファイルは正しく実行されません。</span><span class="sxs-lookup"><span data-stu-id="39031-126">Otherwise, it will fail.</span></span>|  
|<span data-ttu-id="39031-127">MessageEnrichment.sln</span><span class="sxs-lookup"><span data-stu-id="39031-127">MessageEnrichment.sln</span></span>|<span data-ttu-id="39031-128">MessageEnrichment プロジェクトと MessageEnrichmentLibrary プロジェクトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="39031-128">Contains the MessageEnrichment and MessageEnrichmentLibrary projects.</span></span>|  
|<span data-ttu-id="39031-129">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="39031-129">Setup.bat</span></span>|<span data-ttu-id="39031-130">受信ポート、送信ポート、およびオーケストレーションから構成されるサンプル シナリオを展開します。</span><span class="sxs-lookup"><span data-stu-id="39031-130">Deploys an example scenario that consists of a receive port, send port, and orchestration.</span></span>|  
|<span data-ttu-id="39031-131">EDIFACT_example.edi</span><span class="sxs-lookup"><span data-stu-id="39031-131">EDIFACT_example.edi</span></span>|<span data-ttu-id="39031-132">入力 EDIFACT メッセージです。</span><span class="sxs-lookup"><span data-stu-id="39031-132">An input EDIFACT message.</span></span>|  
|<span data-ttu-id="39031-133">X12_example.edi</span><span class="sxs-lookup"><span data-stu-id="39031-133">X12_example.edi</span></span>|<span data-ttu-id="39031-134">入力 X12 メッセージです。</span><span class="sxs-lookup"><span data-stu-id="39031-134">An input X12 message.</span></span>|  
|<span data-ttu-id="39031-135">MessageEnrichment.btproj</span><span class="sxs-lookup"><span data-stu-id="39031-135">MessageEnrichment.btproj</span></span>|<span data-ttu-id="39031-136">MessageEnrichment のオーケストレーションとスキーマが含まれたプロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="39031-136">The project containing the MessageEnrichment orchestrations and schemas.</span></span>|  
|<span data-ttu-id="39031-137">MessageEnrichmentBindings.xml</span><span class="sxs-lookup"><span data-stu-id="39031-137">MessageEnrichmentBindings.xml</span></span>|<span data-ttu-id="39031-138">オーケストレーション、ポート、およびパーティのバインドが含まれたファイルです。</span><span class="sxs-lookup"><span data-stu-id="39031-138">The file containing bindings for the orchestration, the ports, and the parties.</span></span>|  
|<span data-ttu-id="39031-139">MessageEnrichmentOrchestration.odx</span><span class="sxs-lookup"><span data-stu-id="39031-139">MessageEnrichmentOrchestration.odx</span></span>|<span data-ttu-id="39031-140">ヘッダーをメッセージに追加するオーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="39031-140">The orchestration that appends the headers to the message.</span></span>|  
|<span data-ttu-id="39031-141">MessageEnrichmentOrchestration.odx.cs</span><span class="sxs-lookup"><span data-stu-id="39031-141">MessageEnrichmentOrchestration.odx.cs</span></span>|<span data-ttu-id="39031-142">ヘッダーをメッセージに追加するオーケストレーション コードです。</span><span class="sxs-lookup"><span data-stu-id="39031-142">The orchestration code that appends the headers to the message.</span></span>|  
|<span data-ttu-id="39031-143">EFACT_D98B_APERAK.xsd</span><span class="sxs-lookup"><span data-stu-id="39031-143">EFACT_D98B_APERAK.xsd</span></span>|<span data-ttu-id="39031-144">入力メッセージの EDIFACT スキーマです。</span><span class="sxs-lookup"><span data-stu-id="39031-144">The EDIFACT schema for the input message.</span></span>|  
|<span data-ttu-id="39031-145">Enriched_EFACT_D98B_APERAK.xsd</span><span class="sxs-lookup"><span data-stu-id="39031-145">Enriched_EFACT_D98B_APERAK.xsd</span></span>|<span data-ttu-id="39031-146">出力メッセージの EDIFACT スキーマです。</span><span class="sxs-lookup"><span data-stu-id="39031-146">The EDIFACT schema for the output message.</span></span>|  
|<span data-ttu-id="39031-147">X12_00401_864.xsd</span><span class="sxs-lookup"><span data-stu-id="39031-147">X12_00401_864.xsd</span></span>|<span data-ttu-id="39031-148">入力メッセージの X12 スキーマです。</span><span class="sxs-lookup"><span data-stu-id="39031-148">The X12 schema for the input message.</span></span>|  
|<span data-ttu-id="39031-149">Enriched_X12_00401_864.xsd</span><span class="sxs-lookup"><span data-stu-id="39031-149">Enriched_X12_00401_864.xsd</span></span>|<span data-ttu-id="39031-150">出力メッセージの X12 スキーマです。</span><span class="sxs-lookup"><span data-stu-id="39031-150">The X12 schema for the output message.</span></span>|  
|<span data-ttu-id="39031-151">Headers.xsd</span><span class="sxs-lookup"><span data-stu-id="39031-151">Headers.xsd</span></span>|<span data-ttu-id="39031-152">入力メッセージに追加されるヘッダーのスキーマです。</span><span class="sxs-lookup"><span data-stu-id="39031-152">The schemas for the headers added to the input messages.</span></span>|  
|<span data-ttu-id="39031-153">MessageEnrichmentLibrary.csproj</span><span class="sxs-lookup"><span data-stu-id="39031-153">MessageEnrichmentLibrary.csproj</span></span>|<span data-ttu-id="39031-154">Headers.cs、OrchestrationUtilities.cs、および ParseHeaders.cs の各ファイルが含まれたプロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="39031-154">The project containing the Headers.cs, OrchestrationUtilities.cs, and ParseHeaders.cs files.</span></span>|  
|<span data-ttu-id="39031-155">Headers.cs</span><span class="sxs-lookup"><span data-stu-id="39031-155">Headers.cs</span></span>|<span data-ttu-id="39031-156">ヘッダー データを表すクラスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="39031-156">Includes classes representing headers data.</span></span>|  
|<span data-ttu-id="39031-157">OrchestrationUtilities.cs</span><span class="sxs-lookup"><span data-stu-id="39031-157">OrchestrationUtilities.cs</span></span>|<span data-ttu-id="39031-158">オーケストレーションによって使用されるユーティリティ メソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="39031-158">Includes utility methods used by orchestration.</span></span>|  
|<span data-ttu-id="39031-159">ParseHeaders.cs</span><span class="sxs-lookup"><span data-stu-id="39031-159">ParseHeaders.cs</span></span>|<span data-ttu-id="39031-160">新規メッセージで使用される UNA の既定値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="39031-160">Includes the default values for UNA that are used in the new messages.</span></span> <span data-ttu-id="39031-161">これらの値は、ParseHeaders.cs の SerializeEDIFACTHeaders メソッドから取得されます。</span><span class="sxs-lookup"><span data-stu-id="39031-161">These values are taken from the SerializeEDIFACTHeaders method in ParseHeaders.cs.</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="39031-162">このサンプルの使用方法</span><span class="sxs-lookup"><span data-stu-id="39031-162">How to Use This Sample</span></span>  
 <span data-ttu-id="39031-163">このサンプルは、インターチェンジ ヘッダーを EDI トランザクション セット メッセージに追加するために必要なアクションの実行例として使用します。</span><span class="sxs-lookup"><span data-stu-id="39031-163">Use this sample as a working example of the actions required to append interchange headers to EDI transaction-set messages.</span></span>  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="39031-164">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="39031-164">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="39031-165">Message Enrichment サンプルをビルドして初期化するには、このサンプルの BizTalk プロジェクトをビルドして展開し、受信ポートと受信場所を構成して、2 つの異なる送信ポートを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39031-165">To build and initialize the Message Enrichment sample, you need to build and deploy the BizTalk project for this sample, configure the receive port and location, and configure two different send ports.</span></span>  
  
#### <a name="to-build-and-deploy-the-biztalk-project-for-this-sample"></a><span data-ttu-id="39031-166">このサンプルの BizTalk プロジェクトをビルドして展開するには</span><span class="sxs-lookup"><span data-stu-id="39031-166">To build and deploy the BizTalk project for this sample</span></span>  
  
1.  <span data-ttu-id="39031-167">Notepad.Exe を使用して開きます[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \samples\edi\messageenrichment\\</span><span class="sxs-lookup"><span data-stu-id="39031-167">Using Notepad.Exe, open [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\EDI\MessageEnrichment\\</span></span>  
    <span data-ttu-id="39031-168">MessageEnrichment\properties\AssemblyInfo.cs し、ファイルの下部にある次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="39031-168">MessageEnrichment\properties\AssemblyInfo.cs and add the following line at the bottom of the file:</span></span>  
  
    ```  
    [assembly: Microsoft.XLANGs.BaseTypes.BizTalkAssembly(typeof(Microsoft.BizTalk.XLANGs.BTXEngine.BTXService))]  
    ```  
  
2.  <span data-ttu-id="39031-169">変更した AssemblyInfo.cs ファイルを保存し、メモ帳を終了します。</span><span class="sxs-lookup"><span data-stu-id="39031-169">Save the modified AssemblyInfo.cs file and then exit Notepad.</span></span>  
  
3.  <span data-ttu-id="39031-170">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="39031-170">In a command window, move to the following folder:</span></span>  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="39031-171">SDK\Samples\EDI\Message Enrichment</span><span class="sxs-lookup"><span data-stu-id="39031-171">SDK\Samples\EDI\Message Enrichment</span></span>  
  
4.  <span data-ttu-id="39031-172">実行**Setup.bat**、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="39031-172">Run **Setup.bat**, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="39031-173">受信 (**で**) と送信 (**アウト**) \MessageEnrichment フォルダーに、このサンプル用のフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="39031-173">Creates the receive (**in**) and send (**out**) folders for this sample in the \MessageEnrichment folder.</span></span>  
  
    -   <span data-ttu-id="39031-174">キーのペアを MessageEnrichmentLibrary\testkey.snk に書き込みます。</span><span class="sxs-lookup"><span data-stu-id="39031-174">Writes a key pair to MessageEnrichmentLibrary\testkey.snk</span></span>  
  
    -   <span data-ttu-id="39031-175">MessageEnrichmentLibrary.btproj プロジェクトを構築し、展開します。</span><span class="sxs-lookup"><span data-stu-id="39031-175">Builds and deploys the MessageEnrichmentLibrary.btproj project.</span></span>  
  
    -   <span data-ttu-id="39031-176">MessageEnrichment.btproj プロジェクトを構築して展開します。</span><span class="sxs-lookup"><span data-stu-id="39031-176">Builds and deploys the MessageEnrichment.btproj project.</span></span>  
  
    -   <span data-ttu-id="39031-177">MessageEnrichmentBindings.xml のバインド情報を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="39031-177">Reads binding information in MessageEnrichmentBindings.xml.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="39031-178">このプロジェクトのバインドでは、BizTalk ホストが信頼された認証として設定されていることが必要です。</span><span class="sxs-lookup"><span data-stu-id="39031-178">The binding for this project requires that the BizTalk host is marked as Authentication Trusted.</span></span>  <span data-ttu-id="39031-179">信頼されていないホストでバインドを使用するためには、MessageEnrichmentBindings.xml で HostTrusted="true" エントリを HostTrusted="false" に変更します。</span><span class="sxs-lookup"><span data-stu-id="39031-179">In order to use this with a host that is not trusted, modify the MessageEnrichmentBindings.xml and change the HostTrusted=”true” entries to HostTrusted=”false”.</span></span>  
  
    -   <span data-ttu-id="39031-180">オーケストレーションのバインドを更新します。</span><span class="sxs-lookup"><span data-stu-id="39031-180">Updates orchestration bindings.</span></span>  
  
    -   <span data-ttu-id="39031-181">送信ポート、送信ポート グループ、および受信ポートを更新します。</span><span class="sxs-lookup"><span data-stu-id="39031-181">Updates send ports, send port groups, and receive ports.</span></span>  
  
    -   <span data-ttu-id="39031-182">パーティと参加状況を更新します。</span><span class="sxs-lookup"><span data-stu-id="39031-182">Updates parties and enlistments.</span></span>  
  
    -   <span data-ttu-id="39031-183">送信ポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="39031-183">Starts the send port.</span></span>  
  
    -   <span data-ttu-id="39031-184">受信場所を有効にします。</span><span class="sxs-lookup"><span data-stu-id="39031-184">Enables the receive location.</span></span>  
  
    -   <span data-ttu-id="39031-185">オーケストレーションを登録して開始します。</span><span class="sxs-lookup"><span data-stu-id="39031-185">Enlists and starts the orchestration.</span></span>  
  
 <span data-ttu-id="39031-186">BizTalk Server でこのサンプルを使用する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="39031-186">BizTalk Server is ready now to work with this sample.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="39031-187">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="39031-187">Running This Sample</span></span>  
 <span data-ttu-id="39031-188">Message Enrichment サンプルを実行するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="39031-188">Use the following procedure to run the Message Enrichment sample.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="39031-189">このサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="39031-189">To run this sample</span></span>  
  
1.  <span data-ttu-id="39031-190">EDIFACT_examples.edi ファイルを \MessageEnrichment\Instances フォルダーから \MessageEnrichment\In フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="39031-190">Copy the EDIFACT_examples.edi file from the \MessageEnrichment\Instances folder into the \MessageEnrichment\In folder.</span></span>  
  
2.  <span data-ttu-id="39031-191">EDIFACT_examples.edi ファイルが \MessageEnrichment\In フォルダーに表示されなくなり、\MessageEnrichment\Out フォルダーに表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="39031-191">Verify that the EDIFACT_examples.edi files disappears from the \MessageEnrichment\In folder, and appears in the \MessageEnrichment\Out folder.</span></span>  
  
3.  <span data-ttu-id="39031-192">\MessageEnrichment\Out フォルダーのファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="39031-192">Open the file in the \MessageEnrichment\Out folder.</span></span> <span data-ttu-id="39031-193">ファイルが \MessageEnrichment\Instances フォルダーにある EDIFACT_examples.edi ファイルの XML 表記であることを確認します。また、出力ファイルに EDIFACT UNA、UNB、および UNG の各ヘッダーがあることを除き、ファイルのコンテンツが EDIFACT_examples.edi ファイルと同じであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="39031-193">Verify that it is an XML representation of the EDIFACT_examples.edi file in the \MessageEnrichment\Instances folder, and that is has the same contents as the EDIFACT_examples.edi file, with the exception that the output file has EDIFACT UNA, UNB, and UNG headers.</span></span>  
  
4.  <span data-ttu-id="39031-194">\MessageEnrichment\Instances フォルダーの X12_examples.edi ファイルに対して手順 1. と 2. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="39031-194">Repeat steps 1 and 2 with the X12_examples.edi file from the \MessageEnrichment\Instances folder.</span></span>  
  
5.  <span data-ttu-id="39031-195">\MessageEnrichment\Out フォルダーの新規ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="39031-195">Open the new file in the \MessageEnrichment\Out folder.</span></span> <span data-ttu-id="39031-196">ファイルが \MessageEnrichment\Instances フォルダーにある X12_examples.edi file ファイルの XML 表記であることを確認します。また、出力ファイルに X12 ISA ヘッダーがあることを除き、ファイルのコンテンツが X12_examples.edi ファイルと同じであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="39031-196">Verify that it is an XML representation of the X12_examples.edi file in the \MessageEnrichment\Instances folder, and that is has the same contents as the X12_examples.edi file, with the exception that the output file has X12 ISA headers.</span></span>  
  
## <a name="classes-or-methods-used-in-this-sample"></a><span data-ttu-id="39031-197">このサンプルで使用されるクラスまたはメソッド</span><span class="sxs-lookup"><span data-stu-id="39031-197">Classes or Methods Used in This Sample</span></span>  
 <span data-ttu-id="39031-198">なし</span><span class="sxs-lookup"><span data-stu-id="39031-198">None</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39031-199">参照</span><span class="sxs-lookup"><span data-stu-id="39031-199">See Also</span></span>  
 [<span data-ttu-id="39031-200">EDI および AS2 (BizTalk Server Samples フォルダ)</span><span class="sxs-lookup"><span data-stu-id="39031-200">EDI and AS2 (BizTalk Server Samples Folder)</span></span>](../core/edi-and-as2-biztalk-server-samples-folder.md)