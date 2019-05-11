---
title: パイプライン インターフェイスの使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4bb88d0d-23ab-4fdb-bcd2-56050456cf69
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9d76df29720f33d8c7433bc34f9be239cfee0a4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395399"
---
# <a name="using-pipeline-interfaces"></a><span data-ttu-id="e36c9-102">パイプライン インターフェイスの使用</span><span class="sxs-lookup"><span data-stu-id="e36c9-102">Using Pipeline Interfaces</span></span>
<span data-ttu-id="e36c9-103">パイプライン コンポーネントは、BizTalk メッセージング エンジンと対話するための定義済みのインターフェイスのセットを実装する .NET または COM コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="e36c9-103">A pipeline component is a .NET or COM component that implements a set of predefined interfaces for interaction with the BizTalk Messaging Engine.</span></span> <span data-ttu-id="e36c9-104">コンポーネントの機能、に応じて異なるインターフェイスを実装しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="e36c9-104">Depending on the functionality of the component, different interfaces must be implemented.</span></span> <span data-ttu-id="e36c9-105">このトピックでは、これらのインターフェイスとそのメソッドの一部について説明します。</span><span class="sxs-lookup"><span data-stu-id="e36c9-105">This topic discusses these interfaces and some of their methods.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="e36c9-106">COM を使用して、カスタム パイプライン コンポーネントを構築する場合は、マルチ スレッド アパートメント (MTA) モデルを使用するコンポーネントを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e36c9-106">If you are building a custom pipeline component using COM, you must configure your component to use the Multi-Threaded Apartment (MTA) model.</span></span> <span data-ttu-id="e36c9-107">そうでない場合、コンポーネントの呼び出しは E_NOINTERFACE エラーで失敗します。</span><span class="sxs-lookup"><span data-stu-id="e36c9-107">If you do not, invocation of your component will fail with an E_NOINTERFACE error.</span></span>  
  
## <a name="ipipelinecontext"></a><span data-ttu-id="e36c9-108">IPipelineContext</span><span class="sxs-lookup"><span data-stu-id="e36c9-108">IPipelineContext</span></span>  
 <span data-ttu-id="e36c9-109">すべてのパイプライン コンポーネントで使用できる**IPipelineContext**ドキュメント処理に固有のすべてのインターフェイスにアクセスするメソッド。</span><span class="sxs-lookup"><span data-stu-id="e36c9-109">All pipeline components can use **IPipelineContext** methods to access all document processing-specific interfaces.</span></span> <span data-ttu-id="e36c9-110">**IPipelineContext**インターフェイスは、次の機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="e36c9-110">The **IPipelineContext** interface provides the following functionalities:</span></span>  
  
-   <span data-ttu-id="e36c9-111">アンビエント パイプラインとステージの設定を取得するコンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="e36c9-111">Allows components to retrieve the ambient pipeline and stage settings.</span></span>  
  
-   <span data-ttu-id="e36c9-112">メッセージとメッセージ ファクトリを取得するコンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="e36c9-112">Allows components to retrieve message and message factories.</span></span> <span data-ttu-id="e36c9-113">これらのファクトリでは、コンポーネントは、コンポーネントの実行に必要なさまざまなオブジェクトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e36c9-113">With these factories, components can create various objects required for the execution of the component.</span></span>  
  
-   <span data-ttu-id="e36c9-114">ドキュメント仕様を取得するコンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="e36c9-114">Allows components to retrieve the document specifications.</span></span> <span data-ttu-id="e36c9-115">ドキュメント仕様とは、XSD スキーマと注釈を追加します。</span><span class="sxs-lookup"><span data-stu-id="e36c9-115">A document specification is an XSD schema plus additional annotations.</span></span>  
  
## <a name="ibasecomponent"></a><span data-ttu-id="e36c9-116">IBaseComponent</span><span class="sxs-lookup"><span data-stu-id="e36c9-116">IBaseComponent</span></span>  
 <span data-ttu-id="e36c9-117">すべてのパイプライン コンポーネントは、コンポーネントに関する基本的な情報を提供するには、このインターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e36c9-117">All pipeline components need to implement this interface to provide basic information about the component.</span></span>  
  
## <a name="icomponent"></a><span data-ttu-id="e36c9-118">IComponent</span><span class="sxs-lookup"><span data-stu-id="e36c9-118">IComponent</span></span>  
 <span data-ttu-id="e36c9-119">すべてのパイプライン コンポーネントはアセンブラーを除くと、逆アセンブラーからのメッセージを取得するには、このインターフェイスを実装する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]処理エンジンし、エンジンに渡す処理されたメッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="e36c9-119">All pipeline components except assemblers and disassemblers implement this interface to get messages from the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] engine for processing and to pass processed messages back to the engine.</span></span>  
  
 <span data-ttu-id="e36c9-120">**実行します。**</span><span class="sxs-lookup"><span data-stu-id="e36c9-120">**Execute.**</span></span> <span data-ttu-id="e36c9-121">入力メッセージをコンポーネントに渡すし、コンポーネントから処理済みのメッセージを取得する、エンジンによって呼び出されたメソッド。</span><span class="sxs-lookup"><span data-stu-id="e36c9-121">Method called by the engine to pass the input message to the component and retrieve the processed message from the component.</span></span>  
  
## <a name="ipropertybag-ipersistpropertybag"></a><span data-ttu-id="e36c9-122">IPropertyBag、IPersistPropertyBag</span><span class="sxs-lookup"><span data-stu-id="e36c9-122">IPropertyBag, IPersistPropertyBag</span></span>  
 <span data-ttu-id="e36c9-123">パイプライン コンポーネントを実装する必要があります**IPersistPropertyBag**その構成情報を受信します。</span><span class="sxs-lookup"><span data-stu-id="e36c9-123">Pipeline components need to implement **IPersistPropertyBag** to receive its configuration information.</span></span> <span data-ttu-id="e36c9-124">このインターフェイスと**IPropertyBag**は標準的なインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="e36c9-124">This interface and **IPropertyBag** are the standard interfaces.</span></span> <span data-ttu-id="e36c9-125">これらのインターフェイスの詳細については、Microsoft .NET Framework ソフトウェア開発キット (SDK) ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e36c9-125">For more information about these interfaces, refer to the Microsoft .NET Framework Software Development Kit (SDK) documentation.</span></span>  
  
## <a name="idisassemblercomponent"></a><span data-ttu-id="e36c9-126">IDisassemblerComponent</span><span class="sxs-lookup"><span data-stu-id="e36c9-126">IDisassemblerComponent</span></span>  
 <span data-ttu-id="e36c9-127">逆アセンブラー コンポーネントは、入力に 1 つのメッセージを受信し、出力で、0 個以上のメッセージが生成するパイプライン コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="e36c9-127">A disassembling component is a pipeline component that receives one message on input and produces zero or more messages on output.</span></span> <span data-ttu-id="e36c9-128">逆アセンブラー コンポーネントは、個別のドキュメントにメッセージのインターチェンジの分割に使用されます。</span><span class="sxs-lookup"><span data-stu-id="e36c9-128">Disassembling components are used to split interchanges of messages into individual documents.</span></span> <span data-ttu-id="e36c9-129">逆アセンブラー コンポーネントのメソッドを実装する必要があります、 **IDisassemblerComponent**からのメッセージを取得するインターフェイス[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]にドキュメントがバックアップ処理のため、逆アセンブルした[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="e36c9-129">A disassembler component must implement the methods of the **IDisassemblerComponent** interface to get messages from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for processing and to pass disassembled documents back to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
|<span data-ttu-id="e36c9-130">方法</span><span class="sxs-lookup"><span data-stu-id="e36c9-130">Method</span></span>|<span data-ttu-id="e36c9-131">説明</span><span class="sxs-lookup"><span data-stu-id="e36c9-131">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="e36c9-132">**逆アセンブルします。**</span><span class="sxs-lookup"><span data-stu-id="e36c9-132">**Disassemble**</span></span>|<span data-ttu-id="e36c9-133">受信ドキュメントの逆アセンブルを実行します。 **pInMsg**します。</span><span class="sxs-lookup"><span data-stu-id="e36c9-133">Performs the disassembling of the incoming document **pInMsg**.</span></span>|  
|<span data-ttu-id="e36c9-134">**GetNext**</span><span class="sxs-lookup"><span data-stu-id="e36c9-134">**GetNext**</span></span>|<span data-ttu-id="e36c9-135">逆アセンブラーを実行して生成されたメッセージ セットから次のメッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="e36c9-135">Gets the next message from the message set that resulted from disassembler execution.</span></span> <span data-ttu-id="e36c9-136">返します**NULL**以上メッセージがある場合。</span><span class="sxs-lookup"><span data-stu-id="e36c9-136">Returns **NULL** if there are no more messages.</span></span>|  
  
 <span data-ttu-id="e36c9-137">回復可能なインターチェンジ処理をサポートする逆アセンブラー コンポーネントを作成する場合は、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="e36c9-137">If you are writing a disassembler component that will support Recoverable Interchange Processing, you must do the following:</span></span>  
  
1.  <span data-ttu-id="e36c9-138">VirtualStream() でラップすることによって、シーク可能な入力ストリームを行います。</span><span class="sxs-lookup"><span data-stu-id="e36c9-138">Make the input streams seekable by wrapping them in a VirtualStream().</span></span>  
  
2.  <span data-ttu-id="e36c9-139">GetNext() でメッセージが不適切な場合を判断するロジックがあります。</span><span class="sxs-lookup"><span data-stu-id="e36c9-139">In GetNext(), have logic to determine when a message is bad.</span></span> <span data-ttu-id="e36c9-140">メッセージが不良に設定して、BTS の場合は。MessageDestination ="SuspendQueue"と GetNext() でメッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="e36c9-140">If a message is bad, set BTS.MessageDestination = "SuspendQueue" and return the message in GetNext().</span></span>  
  
3.  <span data-ttu-id="e36c9-141">メッセージが適切に設定 BTS の場合は。SuspendMessageOnRoutingFailure = True と GetNext() でメッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="e36c9-141">If the message is good, set BTS.SuspendMessageOnRoutingFailure = True and return the message in GetNext().</span></span>  
  
## <a name="iassemblercomponent"></a><span data-ttu-id="e36c9-142">IAssemblerComponent</span><span class="sxs-lookup"><span data-stu-id="e36c9-142">IAssemblerComponent</span></span>  
 <span data-ttu-id="e36c9-143">アセンブラー コンポーネントは、パイプライン コンポーネントの入力に複数のメッセージを受信し、出力の 1 つのメッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="e36c9-143">An assembling component is a pipeline component that receives several messages on input and produces one message on output.</span></span> <span data-ttu-id="e36c9-144">アセンブラー コンポーネントは、メッセージのインターチェンジ バッチに個々 のドキュメントを収集するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e36c9-144">Assembling components are used to collect individual documents into the message interchange batch.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e36c9-145">このリリースで[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、アセンブル機能が使用されないため、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]常に 1 つのドキュメントをコンポーネントの入力に渡します。</span><span class="sxs-lookup"><span data-stu-id="e36c9-145">In this release of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], assembling functionality is not used, so [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] always passes one document to the component input.</span></span>  
  
 <span data-ttu-id="e36c9-146">アセンブラー コンポーネントを実装して、 **IAssemblerComponent**メソッドによって呼び出される、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実行時にエンジン。</span><span class="sxs-lookup"><span data-stu-id="e36c9-146">An assembler component implements the **IAssemblerComponent** methods that are called by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] engine at run time.</span></span>  
  
|<span data-ttu-id="e36c9-147">方法</span><span class="sxs-lookup"><span data-stu-id="e36c9-147">Method</span></span>|<span data-ttu-id="e36c9-148">説明</span><span class="sxs-lookup"><span data-stu-id="e36c9-148">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="e36c9-149">**AddDocument**</span><span class="sxs-lookup"><span data-stu-id="e36c9-149">**AddDocument**</span></span>|<span data-ttu-id="e36c9-150">ドキュメントを追加します**pInMsg**インターチェンジに含まれるメッセージの一覧にします。</span><span class="sxs-lookup"><span data-stu-id="e36c9-150">Adds the document **pInMsg** to the list of messages that will be included in the interchange.</span></span>|  
|<span data-ttu-id="e36c9-151">**アセンブル**</span><span class="sxs-lookup"><span data-stu-id="e36c9-151">**Assemble**</span></span>|<span data-ttu-id="e36c9-152">前のメソッドによって追加されたメッセージからインターチェンジを構築します。</span><span class="sxs-lookup"><span data-stu-id="e36c9-152">Builds the interchange from the messages that were added by the previous method.</span></span> <span data-ttu-id="e36c9-153">アセンブルされたメッセージへのポインターを返します。</span><span class="sxs-lookup"><span data-stu-id="e36c9-153">Returns a pointer to the assembled message.</span></span>|  
  
## <a name="iprobemessage"></a><span data-ttu-id="e36c9-154">IProbeMessage</span><span class="sxs-lookup"><span data-stu-id="e36c9-154">IProbeMessage</span></span>  
 <span data-ttu-id="e36c9-155">任意のパイプライン コンポーネント (全般、アセンブル、または逆アセンブル) を実装できます**IProbeMessage**メッセージ プローブ機能が必要な場合。</span><span class="sxs-lookup"><span data-stu-id="e36c9-155">Any pipeline component (general, assembling, or disassembling) can implement **IProbeMessage** if it requires message probing functionality.</span></span> <span data-ttu-id="e36c9-156">プローブ コンポーネントがされているパイプライン ステージで使用される**FirstMatch**実行モード。</span><span class="sxs-lookup"><span data-stu-id="e36c9-156">A probing component is used in the pipeline stages that have **FirstMatch** execution mode.</span></span> <span data-ttu-id="e36c9-157">、このような段階的に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンポーネントへのメッセージを提供し、**プローブ**メソッドは、コンポーネントのかどうか、メッセージの形式を認識を確認するメッセージの先頭を検査します。</span><span class="sxs-lookup"><span data-stu-id="e36c9-157">In such stages, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] gives the message to the component, and the **Probe** method examines the beginning of the message to determine if the component recognizes the format of the message.</span></span>  
  
|<span data-ttu-id="e36c9-158">方法</span><span class="sxs-lookup"><span data-stu-id="e36c9-158">Method</span></span>|<span data-ttu-id="e36c9-159">説明</span><span class="sxs-lookup"><span data-stu-id="e36c9-159">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="e36c9-160">**プローブ**</span><span class="sxs-lookup"><span data-stu-id="e36c9-160">**Probe**</span></span>|<span data-ttu-id="e36c9-161">このメソッドは**pInMsg**メッセージ、および返します**True**形式が認識された場合または**False**それ以外の場合。</span><span class="sxs-lookup"><span data-stu-id="e36c9-161">This method takes **pInMsg** message, and returns **True** if the format is recognized or **False** otherwise.</span></span>|  
  
## <a name="inameditem"></a><span data-ttu-id="e36c9-162">INamedItem</span><span class="sxs-lookup"><span data-stu-id="e36c9-162">INamedItem</span></span>  
 <span data-ttu-id="e36c9-163">これは、マネージ コードとアンマネージ コードからドキュメント スキーマにアクセスするためのヘルパー インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="e36c9-163">This is a helper interface for accessing document schemas from managed and unmanaged code.</span></span>  
  
## <a name="inameditemlist"></a><span data-ttu-id="e36c9-164">INamedItemList</span><span class="sxs-lookup"><span data-stu-id="e36c9-164">INamedItemList</span></span>  
 <span data-ttu-id="e36c9-165">これは、マネージ コードとアンマネージ コードからドキュメント スキーマにアクセスするためのヘルパー インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="e36c9-165">This is a helper interface for accessing document schemas from managed and unmanaged code.</span></span>  
  
## <a name="idocumentspec"></a><span data-ttu-id="e36c9-166">IDocumentSpec</span><span class="sxs-lookup"><span data-stu-id="e36c9-166">IDocumentSpec</span></span>  
 <span data-ttu-id="e36c9-167">パイプライン コンポーネントのメソッドを使用できる、 **IDocumentSpec**し、コンテンツのプロパティをコンテキストと、ドキュメント スキーマへのアクセスに移動するなどのドキュメントに固有の操作を実行するためのインターフェイスします。</span><span class="sxs-lookup"><span data-stu-id="e36c9-167">Pipeline components can use methods of the **IDocumentSpec** interface to perform document-specific actions, such as moving content properties to context and back, accessing document schemas, and so on.</span></span>  
  
|<span data-ttu-id="e36c9-168">方法</span><span class="sxs-lookup"><span data-stu-id="e36c9-168">Method</span></span>|<span data-ttu-id="e36c9-169">説明</span><span class="sxs-lookup"><span data-stu-id="e36c9-169">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="e36c9-170">**DocType**</span><span class="sxs-lookup"><span data-stu-id="e36c9-170">**DocType**</span></span>|<span data-ttu-id="e36c9-171">現在のドキュメントの種類を返します。</span><span class="sxs-lookup"><span data-stu-id="e36c9-171">Returns the type of the current document.</span></span>|  
|<span data-ttu-id="e36c9-172">**しない docspecname を含む**</span><span class="sxs-lookup"><span data-stu-id="e36c9-172">**DocSpecName**</span></span>|<span data-ttu-id="e36c9-173">現在のドキュメントの仕様の名前を返します。</span><span class="sxs-lookup"><span data-stu-id="e36c9-173">Returns the specification name of the current document.</span></span>|  
|<span data-ttu-id="e36c9-174">**GetSchemaCollection**</span><span class="sxs-lookup"><span data-stu-id="e36c9-174">**GetSchemaCollection**</span></span>|<span data-ttu-id="e36c9-175">現在のドキュメントのドキュメント スキーマの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="e36c9-175">Returns the list of document schemas for the current document.</span></span>|  
|<span data-ttu-id="e36c9-176">**GetBodyPath**</span><span class="sxs-lookup"><span data-stu-id="e36c9-176">**GetBodyPath**</span></span>|<span data-ttu-id="e36c9-177">ボディ部が開始されるドキュメント内のノードに、XPath を返します。</span><span class="sxs-lookup"><span data-stu-id="e36c9-177">Returns the XPath to the node in the document where the body part begins.</span></span>|  
|<span data-ttu-id="e36c9-178">**GetDistinguishedPropertyAnnotationEnumerator**</span><span class="sxs-lookup"><span data-stu-id="e36c9-178">**GetDistinguishedPropertyAnnotationEnumerator**</span></span>|<span data-ttu-id="e36c9-179">すべての識別フィールド プロパティ注釈のディクショナリ列挙子を返します。</span><span class="sxs-lookup"><span data-stu-id="e36c9-179">Returns a dictionary enumerator of all distinguished field property annotations.</span></span>|  
|<span data-ttu-id="e36c9-180">**GetPropertyAnnotationEnumerator**</span><span class="sxs-lookup"><span data-stu-id="e36c9-180">**GetPropertyAnnotationEnumerator**</span></span>|<span data-ttu-id="e36c9-181">すべてのプロパティ注釈の列挙子を返します。</span><span class="sxs-lookup"><span data-stu-id="e36c9-181">Returns an enumerator of all property annotations.</span></span>|  
  
## <a name="icomponentui"></a><span data-ttu-id="e36c9-182">IComponentUI</span><span class="sxs-lookup"><span data-stu-id="e36c9-182">IComponentUI</span></span>  
 <span data-ttu-id="e36c9-183">パイプライン コンポーネントは、パイプライン デザイナー環境で使用するには、このインターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e36c9-183">Pipeline components must implement this interface to be used within the Pipeline Designer environment.</span></span>  
  
|<span data-ttu-id="e36c9-184">方法</span><span class="sxs-lookup"><span data-stu-id="e36c9-184">Method</span></span>|<span data-ttu-id="e36c9-185">説明</span><span class="sxs-lookup"><span data-stu-id="e36c9-185">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="e36c9-186">**アイコン**</span><span class="sxs-lookup"><span data-stu-id="e36c9-186">**Icon**</span></span>|<span data-ttu-id="e36c9-187">このコンポーネントに関連付けられているアイコンを提供します。</span><span class="sxs-lookup"><span data-stu-id="e36c9-187">Provides the icon that is associated with this component.</span></span>|  
|<span data-ttu-id="e36c9-188">**[検証]**</span><span class="sxs-lookup"><span data-stu-id="e36c9-188">**Validate**</span></span>|<span data-ttu-id="e36c9-189">パイプライン デザイナーでは、すべての構成プロパティが正しく設定されていることを確認するパイプラインのコンパイル前にこのメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e36c9-189">Pipeline Designer calls this method before pipeline compilation to verify that all the configuration properties are set correctly.</span></span>|  
  
 <span data-ttu-id="e36c9-190">**アイコン**プロパティが返す、 **IntPtr**します。</span><span class="sxs-lookup"><span data-stu-id="e36c9-190">The **Icon** property returns an **IntPtr**.</span></span> <span data-ttu-id="e36c9-191">次C#を返す方法を示します、 **IntPtr**します。</span><span class="sxs-lookup"><span data-stu-id="e36c9-191">The following C# example shows how to return an **IntPtr**.</span></span>  
  
```csharp  
static   ResourceManager resManager = new ResourceManager("ResourceManager", Assembly.GetExecutingAssembly());  
...  
[Browsable(false)]  
public IntPtr Icon  
{  
   get  
   {  
      return ((Bitmap)resManager.GetObject("MyIcon")).GetHicon();  
   }  
}  
```  
  
 <span data-ttu-id="e36c9-192">詳細については、次を参照してください。 **IComponentUI インターフェイス (COM)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="e36c9-192">For more information, see **IComponentUI Interface (COM)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="e36c9-193">参照</span><span class="sxs-lookup"><span data-stu-id="e36c9-193">See Also</span></span>  
 <span data-ttu-id="e36c9-194">[カスタム パイプライン コンポーネントの開発](../core/developing-custom-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="e36c9-194">[Developing Custom Pipeline Components](../core/developing-custom-pipeline-components.md) </span></span>  
 [<span data-ttu-id="e36c9-195">CustomComponent (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="e36c9-195">CustomComponent (BizTalk Server Sample)</span></span>](../core/customcomponent-biztalk-server-sample.md)