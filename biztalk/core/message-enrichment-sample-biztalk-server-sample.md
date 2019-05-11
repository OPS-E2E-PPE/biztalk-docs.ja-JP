---
title: メッセージ強化サンプル (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a41ed707-dbdb-46b7-97a6-86fdbc8ad285
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d987164eeb855bfc991e9b4f1b0c8b444b99407b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65325119"
---
# <a name="message-enrichment-sample-biztalk-server-sample"></a><span data-ttu-id="52e53-102">メッセージ強化サンプル (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="52e53-102">Message Enrichment Sample (BizTalk Server Sample)</span></span>
<span data-ttu-id="52e53-103">メッセージ強化サンプルでは、X12 と EDIFACT ドキュメントのトランザクション セット メッセージにインターチェンジ ヘッダーを追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="52e53-103">The Message Enrichment sample demonstrates how to append interchange headers to transaction-set messages for X12 and EDIFACT documents.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="52e53-104">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="52e53-104">What This Sample Does</span></span>  
 <span data-ttu-id="52e53-105">このサンプルでは、edifact では、UNA、UNB、および UNG ヘッダーと x12 の場合、ISA ヘッダーをトランザクション セットに追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="52e53-105">This sample demonstrates how to append UNA, UNB, and UNG headers for EDIFACT, and ISA headers for X12, to transaction sets.</span></span> <span data-ttu-id="52e53-106">具体的には、このサンプルは以下の処理を行います。</span><span class="sxs-lookup"><span data-stu-id="52e53-106">Specifically, this sample does the following:</span></span>  
  
1.  <span data-ttu-id="52e53-107">\Message Enrichment\In フォルダーにテスト メッセージをドロップすると、受信ポートは、ピックアップする、処理、および、MessageBox にドロップします。</span><span class="sxs-lookup"><span data-stu-id="52e53-107">When you drop the test message to the \Message Enrichment\In folder, the receive port picks it up, processes it, and drops it in the MessageBox.</span></span>  
  
2.  <span data-ttu-id="52e53-108">MessageEnrichmentOrchestration から取得し、テスト メッセージ、メッセージ ボックスでは、受信図形に対して設定するフィルター式に基づいてメッセージをサブスクライブしています。</span><span class="sxs-lookup"><span data-stu-id="52e53-108">The MessageEnrichmentOrchestration picks the test message up from the MessageBox, because it subscribes to messages based on a filter expression set on its receive shape.</span></span>  
  
3.  <span data-ttu-id="52e53-109">オーケストレーションは、メッセージのコンテキスト プロパティからインターチェンジ ヘッダーを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="52e53-109">The orchestration reads the interchange headers from the context properties of the message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="52e53-110">UNA と UNG ヘッダーは、メッセージのコンテキスト プロパティでない可能性がありますので、EDIFACT メッセージのオプションです。</span><span class="sxs-lookup"><span data-stu-id="52e53-110">UNA and UNG headers are optional in an EDIFACT message, so can be missing in the context properties of a message.</span></span>  
  
4.  <span data-ttu-id="52e53-111">オーケストレーションでは、インターチェンジ ヘッダーとメッセージ本文の両方を 1 つの新しいメッセージに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="52e53-111">The orchestration writes both the interchange headers and the message body into a single new message.</span></span>  
  
5.  <span data-ttu-id="52e53-112">オーケストレーションは、メッセージには、ReceivePortNameCorrelationType 関連付けの種類に設定されている追加のプロパティを昇格させます。</span><span class="sxs-lookup"><span data-stu-id="52e53-112">The orchestration promotes additional properties that are set in the ReceivePortNameCorrelationType correlation type onto the message.</span></span> <span data-ttu-id="52e53-113">サブスクリプションに必要なプロパティの一覧を選択するオーケストレーションのユーザーは、します。</span><span class="sxs-lookup"><span data-stu-id="52e53-113">These allow users of the orchestration to select a list of the properties they need for their subscription.</span></span> <span data-ttu-id="52e53-114">これらのプロパティは、メッセージの構築図形で記述されます。</span><span class="sxs-lookup"><span data-stu-id="52e53-114">These properties are written in a construct message shape.</span></span> <span data-ttu-id="52e53-115">元のメッセージに書き込まれたすべてのコンテキスト プロパティは、新しいメッセージに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="52e53-115">Not all context properties that were written to the original message are written to the new message.</span></span>  
  
6.  <span data-ttu-id="52e53-116">オーケストレーションは、メッセージ ボックスに新しいメッセージを削除します。</span><span class="sxs-lookup"><span data-stu-id="52e53-116">The orchestration drops the new message into the MessageBox.</span></span>  
  
7.  <span data-ttu-id="52e53-117">送信ポートでは、新しいメッセージを取得して、\Message Enrichment\Out フォルダーにファイル アダプターを経由して送信します。</span><span class="sxs-lookup"><span data-stu-id="52e53-117">The send port picks up the new message and sends it via the FILE adapter to the \Message Enrichment\Out folder.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="52e53-118">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="52e53-118">Where to Find This Sample</span></span>  
 <span data-ttu-id="52e53-119">このサンプルにある、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストール フォルダー。[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Sdk \samples\edi\message Enrichment。</span><span class="sxs-lookup"><span data-stu-id="52e53-119">This sample is located in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation folder: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\EDI\Message Enrichment.</span></span>  
  
 <span data-ttu-id="52e53-120">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="52e53-120">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="52e53-121">ファイル</span><span class="sxs-lookup"><span data-stu-id="52e53-121">File(s)</span></span>|<span data-ttu-id="52e53-122">説明</span><span class="sxs-lookup"><span data-stu-id="52e53-122">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="52e53-123">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="52e53-123">Cleanup.bat</span></span>|<span data-ttu-id="52e53-124">この例のシナリオの展開を解除します。</span><span class="sxs-lookup"><span data-stu-id="52e53-124">Undeploys the example scenario.</span></span> <span data-ttu-id="52e53-125">成功するために必要がありますいないオーケストレーションのアクティブなインスタンス。</span><span class="sxs-lookup"><span data-stu-id="52e53-125">In order for it to succeed there must be no active instances of the orchestration.</span></span> <span data-ttu-id="52e53-126">それ以外の場合、これは失敗します。</span><span class="sxs-lookup"><span data-stu-id="52e53-126">Otherwise, it will fail.</span></span>|  
|<span data-ttu-id="52e53-127">MessageEnrichment.sln</span><span class="sxs-lookup"><span data-stu-id="52e53-127">MessageEnrichment.sln</span></span>|<span data-ttu-id="52e53-128">MessageEnrichment と MessageEnrichmentLibrary プロジェクトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="52e53-128">Contains the MessageEnrichment and MessageEnrichmentLibrary projects.</span></span>|  
|<span data-ttu-id="52e53-129">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="52e53-129">Setup.bat</span></span>|<span data-ttu-id="52e53-130">受信ポート、送信ポート、およびオーケストレーションで構成されるシナリオの例をデプロイします。</span><span class="sxs-lookup"><span data-stu-id="52e53-130">Deploys an example scenario that consists of a receive port, send port, and orchestration.</span></span>|  
|<span data-ttu-id="52e53-131">EDIFACT_example.edi</span><span class="sxs-lookup"><span data-stu-id="52e53-131">EDIFACT_example.edi</span></span>|<span data-ttu-id="52e53-132">入力の EDIFACT メッセージです。</span><span class="sxs-lookup"><span data-stu-id="52e53-132">An input EDIFACT message.</span></span>|  
|<span data-ttu-id="52e53-133">X12_example.edi</span><span class="sxs-lookup"><span data-stu-id="52e53-133">X12_example.edi</span></span>|<span data-ttu-id="52e53-134">入力 X12 メッセージ。</span><span class="sxs-lookup"><span data-stu-id="52e53-134">An input X12 message.</span></span>|  
|<span data-ttu-id="52e53-135">MessageEnrichment.btproj</span><span class="sxs-lookup"><span data-stu-id="52e53-135">MessageEnrichment.btproj</span></span>|<span data-ttu-id="52e53-136">MessageEnrichment のオーケストレーションとスキーマを含むプロジェクト。</span><span class="sxs-lookup"><span data-stu-id="52e53-136">The project containing the MessageEnrichment orchestrations and schemas.</span></span>|  
|<span data-ttu-id="52e53-137">MessageEnrichmentBindings.xml</span><span class="sxs-lookup"><span data-stu-id="52e53-137">MessageEnrichmentBindings.xml</span></span>|<span data-ttu-id="52e53-138">オーケストレーション、ポート、および、パーティのバインドを含んでいるファイルです。</span><span class="sxs-lookup"><span data-stu-id="52e53-138">The file containing bindings for the orchestration, the ports, and the parties.</span></span>|  
|<span data-ttu-id="52e53-139">MessageEnrichmentOrchestration.odx</span><span class="sxs-lookup"><span data-stu-id="52e53-139">MessageEnrichmentOrchestration.odx</span></span>|<span data-ttu-id="52e53-140">このオーケストレーションは、メッセージにヘッダーを追加します。</span><span class="sxs-lookup"><span data-stu-id="52e53-140">The orchestration that appends the headers to the message.</span></span>|  
|<span data-ttu-id="52e53-141">MessageEnrichmentOrchestration.odx.cs</span><span class="sxs-lookup"><span data-stu-id="52e53-141">MessageEnrichmentOrchestration.odx.cs</span></span>|<span data-ttu-id="52e53-142">メッセージにヘッダーを追加するオーケストレーション コードです。</span><span class="sxs-lookup"><span data-stu-id="52e53-142">The orchestration code that appends the headers to the message.</span></span>|  
|<span data-ttu-id="52e53-143">EFACT_D98B_APERAK.xsd</span><span class="sxs-lookup"><span data-stu-id="52e53-143">EFACT_D98B_APERAK.xsd</span></span>|<span data-ttu-id="52e53-144">入力メッセージの EDIFACT スキーマです。</span><span class="sxs-lookup"><span data-stu-id="52e53-144">The EDIFACT schema for the input message.</span></span>|  
|<span data-ttu-id="52e53-145">Enriched_EFACT_D98B_APERAK.xsd</span><span class="sxs-lookup"><span data-stu-id="52e53-145">Enriched_EFACT_D98B_APERAK.xsd</span></span>|<span data-ttu-id="52e53-146">出力メッセージの EDIFACT スキーマです。</span><span class="sxs-lookup"><span data-stu-id="52e53-146">The EDIFACT schema for the output message.</span></span>|  
|<span data-ttu-id="52e53-147">X12_00401_864.xsd</span><span class="sxs-lookup"><span data-stu-id="52e53-147">X12_00401_864.xsd</span></span>|<span data-ttu-id="52e53-148">X12 入力メッセージのスキーマ。</span><span class="sxs-lookup"><span data-stu-id="52e53-148">The X12 schema for the input message.</span></span>|  
|<span data-ttu-id="52e53-149">Enriched_X12_00401_864.xsd</span><span class="sxs-lookup"><span data-stu-id="52e53-149">Enriched_X12_00401_864.xsd</span></span>|<span data-ttu-id="52e53-150">X12 出力メッセージのスキーマ。</span><span class="sxs-lookup"><span data-stu-id="52e53-150">The X12 schema for the output message.</span></span>|  
|<span data-ttu-id="52e53-151">Headers.xsd</span><span class="sxs-lookup"><span data-stu-id="52e53-151">Headers.xsd</span></span>|<span data-ttu-id="52e53-152">入力メッセージに追加されるヘッダーのスキーマです。</span><span class="sxs-lookup"><span data-stu-id="52e53-152">The schemas for the headers added to the input messages.</span></span>|  
|<span data-ttu-id="52e53-153">MessageEnrichmentLibrary.csproj</span><span class="sxs-lookup"><span data-stu-id="52e53-153">MessageEnrichmentLibrary.csproj</span></span>|<span data-ttu-id="52e53-154">Headers.cs、OrchestrationUtilities.cs、および parseheaders.cs の各ファイルを含むプロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="52e53-154">The project containing the Headers.cs, OrchestrationUtilities.cs, and ParseHeaders.cs files.</span></span>|  
|<span data-ttu-id="52e53-155">Headers.cs</span><span class="sxs-lookup"><span data-stu-id="52e53-155">Headers.cs</span></span>|<span data-ttu-id="52e53-156">ヘッダーのデータを表すクラスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="52e53-156">Includes classes representing headers data.</span></span>|  
|<span data-ttu-id="52e53-157">OrchestrationUtilities.cs</span><span class="sxs-lookup"><span data-stu-id="52e53-157">OrchestrationUtilities.cs</span></span>|<span data-ttu-id="52e53-158">オーケストレーションによって使用されるユーティリティ メソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="52e53-158">Includes utility methods used by orchestration.</span></span>|  
|<span data-ttu-id="52e53-159">Parseheaders.cs の各</span><span class="sxs-lookup"><span data-stu-id="52e53-159">ParseHeaders.cs</span></span>|<span data-ttu-id="52e53-160">新しいメッセージで使用される UNA の既定値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="52e53-160">Includes the default values for UNA that are used in the new messages.</span></span> <span data-ttu-id="52e53-161">これらの値は、parseheaders.cs の SerializeEDIFACTHeaders メソッドから取得されます。</span><span class="sxs-lookup"><span data-stu-id="52e53-161">These values are taken from the SerializeEDIFACTHeaders method in ParseHeaders.cs.</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="52e53-162">このサンプルの使用方法</span><span class="sxs-lookup"><span data-stu-id="52e53-162">How to Use This Sample</span></span>  
 <span data-ttu-id="52e53-163">EDI トランザクション セット メッセージにインターチェンジ ヘッダーを追加するために必要なアクションの動作例としては、このサンプルを使用します。</span><span class="sxs-lookup"><span data-stu-id="52e53-163">Use this sample as a working example of the actions required to append interchange headers to EDI transaction-set messages.</span></span>  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="52e53-164">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="52e53-164">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="52e53-165">をビルドし、メッセージ強化サンプルを初期化する必要がありますを構築し、このサンプルでは、BizTalk プロジェクトを配置、場所と受信ポートを構成を 2 つの異なる送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="52e53-165">To build and initialize the Message Enrichment sample, you need to build and deploy the BizTalk project for this sample, configure the receive port and location, and configure two different send ports.</span></span>  
  
#### <a name="to-build-and-deploy-the-biztalk-project-for-this-sample"></a><span data-ttu-id="52e53-166">このサンプルの BizTalk プロジェクト ビルドおよび配置するには</span><span class="sxs-lookup"><span data-stu-id="52e53-166">To build and deploy the BizTalk project for this sample</span></span>  
  
1. <span data-ttu-id="52e53-167">Notepad.Exe を使用して開く[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \samples\edi\messageenrichment\\</span><span class="sxs-lookup"><span data-stu-id="52e53-167">Using Notepad.Exe, open [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\EDI\MessageEnrichment\\</span></span>  
   <span data-ttu-id="52e53-168">MessageEnrichment\properties\AssemblyInfo.cs し、ファイルの下部にある次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="52e53-168">MessageEnrichment\properties\AssemblyInfo.cs and add the following line at the bottom of the file:</span></span>  
  
   ```  
   [assembly: Microsoft.XLANGs.BaseTypes.BizTalkAssembly(typeof(Microsoft.BizTalk.XLANGs.BTXEngine.BTXService))]  
   ```  
  
2. <span data-ttu-id="52e53-169">変更した AssemblyInfo.cs ファイルを保存し、メモ帳を終了します。</span><span class="sxs-lookup"><span data-stu-id="52e53-169">Save the modified AssemblyInfo.cs file and then exit Notepad.</span></span>  
  
3. <span data-ttu-id="52e53-170">コマンド ウィンドウでは、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="52e53-170">In a command window, move to the following folder:</span></span>  
  
    [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="52e53-171">SDK\Samples\EDI\Message Enrichment</span><span class="sxs-lookup"><span data-stu-id="52e53-171">SDK\Samples\EDI\Message Enrichment</span></span>  
  
4. <span data-ttu-id="52e53-172">実行**Setup.bat**、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="52e53-172">Run **Setup.bat**, which performs the following actions:</span></span>  
  
   -   <span data-ttu-id="52e53-173">受信側を作成します (**で**) と送信 (**アウト**) \MessageEnrichment フォルダーに、このサンプル用のフォルダー。</span><span class="sxs-lookup"><span data-stu-id="52e53-173">Creates the receive (**in**) and send (**out**) folders for this sample in the \MessageEnrichment folder.</span></span>  
  
   -   <span data-ttu-id="52e53-174">キーのペアを \testkey.snk に書き込みます</span><span class="sxs-lookup"><span data-stu-id="52e53-174">Writes a key pair to MessageEnrichmentLibrary\testkey.snk</span></span>  
  
   -   <span data-ttu-id="52e53-175">ビルドし、MessageEnrichmentLibrary.btproj プロジェクトをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="52e53-175">Builds and deploys the MessageEnrichmentLibrary.btproj project.</span></span>  
  
   -   <span data-ttu-id="52e53-176">ビルドし、MessageEnrichment.btproj プロジェクトをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="52e53-176">Builds and deploys the MessageEnrichment.btproj project.</span></span>  
  
   -   <span data-ttu-id="52e53-177">MessageEnrichmentBindings.xml のバインド情報を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="52e53-177">Reads binding information in MessageEnrichmentBindings.xml.</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="52e53-178">このプロジェクトのバインドでは、BizTalk ホストが信頼されている認証としてマークされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="52e53-178">The binding for this project requires that the BizTalk host is marked as Authentication Trusted.</span></span>  <span data-ttu-id="52e53-179">これを使用して、信頼されていないホストで、するには、messageenrichmentbindings.xml し、変更、HostTrusted ="true"のエントリを HostTrusted ="false"。</span><span class="sxs-lookup"><span data-stu-id="52e53-179">In order to use this with a host that is not trusted, modify the MessageEnrichmentBindings.xml and change the HostTrusted=”true” entries to HostTrusted=”false”.</span></span>  
  
   -   <span data-ttu-id="52e53-180">オーケストレーションのバインドを更新します。</span><span class="sxs-lookup"><span data-stu-id="52e53-180">Updates orchestration bindings.</span></span>  
  
   -   <span data-ttu-id="52e53-181">更新プログラムは、送信ポート、送信ポート グループ、および受信ポート。</span><span class="sxs-lookup"><span data-stu-id="52e53-181">Updates send ports, send port groups, and receive ports.</span></span>  
  
   -   <span data-ttu-id="52e53-182">パーティと参加状況を更新します。</span><span class="sxs-lookup"><span data-stu-id="52e53-182">Updates parties and enlistments.</span></span>  
  
   -   <span data-ttu-id="52e53-183">送信ポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="52e53-183">Starts the send port.</span></span>  
  
   -   <span data-ttu-id="52e53-184">受信場所を有効にします。</span><span class="sxs-lookup"><span data-stu-id="52e53-184">Enables the receive location.</span></span>  
  
   -   <span data-ttu-id="52e53-185">参加させ、オーケストレーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="52e53-185">Enlists and starts the orchestration.</span></span>  
  
   <span data-ttu-id="52e53-186">BizTalk Server は、このサンプルで動作するようになりました。</span><span class="sxs-lookup"><span data-stu-id="52e53-186">BizTalk Server is ready now to work with this sample.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="52e53-187">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="52e53-187">Running This Sample</span></span>  
 <span data-ttu-id="52e53-188">Message Enrichment サンプルを実行するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="52e53-188">Use the following procedure to run the Message Enrichment sample.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="52e53-189">このサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="52e53-189">To run this sample</span></span>  
  
1.  <span data-ttu-id="52e53-190">EDIFACT_examples.edi ファイルを \MessageEnrichment\Instances フォルダーから \MessageEnrichment\In フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="52e53-190">Copy the EDIFACT_examples.edi file from the \MessageEnrichment\Instances folder into the \MessageEnrichment\In folder.</span></span>  
  
2.  <span data-ttu-id="52e53-191">EDIFACT_examples.edi ファイルが \MessageEnrichment\In フォルダーが表示されなくなり、\MessageEnrichment\Out フォルダーに表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="52e53-191">Verify that the EDIFACT_examples.edi files disappears from the \MessageEnrichment\In folder, and appears in the \MessageEnrichment\Out folder.</span></span>  
  
3.  <span data-ttu-id="52e53-192">\MessageEnrichment\Out フォルダーにファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="52e53-192">Open the file in the \MessageEnrichment\Out folder.</span></span> <span data-ttu-id="52e53-193">\MessageEnrichment\Instances フォルダーにファイルが EDIFACT_examples.edi の XML 表現が出力ファイルに EDIFACT UNA、UNB、および UNG ヘッダーがあることを除き、EDIFACT_examples.edi ファイルと同じ内容があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="52e53-193">Verify that it is an XML representation of the EDIFACT_examples.edi file in the \MessageEnrichment\Instances folder, and that is has the same contents as the EDIFACT_examples.edi file, with the exception that the output file has EDIFACT UNA, UNB, and UNG headers.</span></span>  
  
4.  <span data-ttu-id="52e53-194">\MessageEnrichment\Instances フォルダーの X12_examples.edi ファイルには、手順 1. および 2. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="52e53-194">Repeat steps 1 and 2 with the X12_examples.edi file from the \MessageEnrichment\Instances folder.</span></span>  
  
5.  <span data-ttu-id="52e53-195">\MessageEnrichment\Out フォルダーに新しいファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="52e53-195">Open the new file in the \MessageEnrichment\Out folder.</span></span> <span data-ttu-id="52e53-196">\MessageEnrichment\Instances フォルダーにファイルが X12_examples.edi の XML 表現が X12_examples.edi ファイル、出力ファイルに X12 例外として同じ内容があることを確認 ISA ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="52e53-196">Verify that it is an XML representation of the X12_examples.edi file in the \MessageEnrichment\Instances folder, and that is has the same contents as the X12_examples.edi file, with the exception that the output file has X12 ISA headers.</span></span>  
  
## <a name="classes-or-methods-used-in-this-sample"></a><span data-ttu-id="52e53-197">クラスまたはメソッドのこのサンプルで使用</span><span class="sxs-lookup"><span data-stu-id="52e53-197">Classes or Methods Used in This Sample</span></span>  
 <span data-ttu-id="52e53-198">なし</span><span class="sxs-lookup"><span data-stu-id="52e53-198">None</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52e53-199">参照</span><span class="sxs-lookup"><span data-stu-id="52e53-199">See Also</span></span>  
 [<span data-ttu-id="52e53-200">EDI および AS2 (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="52e53-200">EDI and AS2 (BizTalk Server Samples Folder)</span></span>](../core/edi-and-as2-biztalk-server-samples-folder.md)