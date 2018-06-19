---
title: パイプライン インターフェイスを使用して |Microsoft ドキュメント
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
ms.openlocfilehash: c365a8d7bdf37564d3d9b2dceac1c8615e126ebc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289146"
---
# <a name="using-pipeline-interfaces"></a><span data-ttu-id="acd51-102">パイプライン インターフェイスを使用します。</span><span class="sxs-lookup"><span data-stu-id="acd51-102">Using Pipeline Interfaces</span></span>
<span data-ttu-id="acd51-103">パイプライン コンポーネントは、BizTalk メッセージング エンジンとの対話用にあらかじめ定義された一連のインターフェイスを実装する .NET コンポーネントまたは COM コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="acd51-103">A pipeline component is a .NET or COM component that implements a set of predefined interfaces for interaction with the BizTalk Messaging Engine.</span></span> <span data-ttu-id="acd51-104">実装する必要のあるインターフェイスは、コンポーネントの機能によって異なります。</span><span class="sxs-lookup"><span data-stu-id="acd51-104">Depending on the functionality of the component, different interfaces must be implemented.</span></span> <span data-ttu-id="acd51-105">このトピックでは、これらのインターフェイスとそのメソッドの一部について説明します。</span><span class="sxs-lookup"><span data-stu-id="acd51-105">This topic discusses these interfaces and some of their methods.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="acd51-106">COM を使用してカスタム パイプライン コンポーネントを作成する場合は、マルチスレッド アパートメント (MTA) モデルを使用するようにコンポーネントを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="acd51-106">If you are building a custom pipeline component using COM, you must configure your component to use the Multi-Threaded Apartment (MTA) model.</span></span> <span data-ttu-id="acd51-107">この構成を行わないと、コンポーネントの呼び出しは失敗し、E_NOINTERFACE エラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="acd51-107">If you do not, invocation of your component will fail with an E_NOINTERFACE error.</span></span>  
  
## <a name="ipipelinecontext"></a><span data-ttu-id="acd51-108">IPipelineContext</span><span class="sxs-lookup"><span data-stu-id="acd51-108">IPipelineContext</span></span>  
 <span data-ttu-id="acd51-109">すべてのパイプライン コンポーネントで使用できる**IPipelineContext**ドキュメント処理に固有のすべてのインターフェイスにアクセスするメソッド。</span><span class="sxs-lookup"><span data-stu-id="acd51-109">All pipeline components can use **IPipelineContext** methods to access all document processing-specific interfaces.</span></span> <span data-ttu-id="acd51-110">**IPipelineContext**インターフェイスには、次の機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="acd51-110">The **IPipelineContext** interface provides the following functionalities:</span></span>  
  
-   <span data-ttu-id="acd51-111">アンビエント パイプラインとステージの設定をコンポーネントで取得できるようにします。</span><span class="sxs-lookup"><span data-stu-id="acd51-111">Allows components to retrieve the ambient pipeline and stage settings.</span></span>  
  
-   <span data-ttu-id="acd51-112">メッセージとメッセージ ファクトリをコンポーネントで取得できるようにします。</span><span class="sxs-lookup"><span data-stu-id="acd51-112">Allows components to retrieve message and message factories.</span></span> <span data-ttu-id="acd51-113">コンポーネントでこれらのファクトリを使用することにより、コンポーネントの実行に必要なさまざまなオブジェクトを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="acd51-113">With these factories, components can create various objects required for the execution of the component.</span></span>  
  
-   <span data-ttu-id="acd51-114">ドキュメント仕様をコンポーネントで取得できるようにします。</span><span class="sxs-lookup"><span data-stu-id="acd51-114">Allows components to retrieve the document specifications.</span></span> <span data-ttu-id="acd51-115">ドキュメント仕様とは、XSD スキーマに注釈を加えたものを指します。</span><span class="sxs-lookup"><span data-stu-id="acd51-115">A document specification is an XSD schema plus additional annotations.</span></span>  
  
## <a name="ibasecomponent"></a><span data-ttu-id="acd51-116">IBaseComponent</span><span class="sxs-lookup"><span data-stu-id="acd51-116">IBaseComponent</span></span>  
 <span data-ttu-id="acd51-117">コンポーネントの基本情報を指定するために、すべてのパイプライン コンポーネントに実装する必要のあるインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="acd51-117">All pipeline components need to implement this interface to provide basic information about the component.</span></span>  
  
## <a name="icomponent"></a><span data-ttu-id="acd51-118">IComponent</span><span class="sxs-lookup"><span data-stu-id="acd51-118">IComponent</span></span>  
 <span data-ttu-id="acd51-119">処理するメッセージを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] エンジンから取得し、処理されたメッセージをエンジンに返すために、アセンブラーと逆アセンブラーを除くすべてのパイプライン コンポーネントに実装されるインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="acd51-119">All pipeline components except assemblers and disassemblers implement this interface to get messages from the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] engine for processing and to pass processed messages back to the engine.</span></span>  
  
 <span data-ttu-id="acd51-120">**実行します。**</span><span class="sxs-lookup"><span data-stu-id="acd51-120">**Execute.**</span></span> <span data-ttu-id="acd51-121">入力メッセージをコンポーネントに渡し、処理されたメッセージをコンポーネントから取得するために、エンジンによって呼び出されるメソッドです。</span><span class="sxs-lookup"><span data-stu-id="acd51-121">Method called by the engine to pass the input message to the component and retrieve the processed message from the component.</span></span>  
  
## <a name="ipropertybag-ipersistpropertybag"></a><span data-ttu-id="acd51-122">IPropertyBag、IPersistPropertyBag</span><span class="sxs-lookup"><span data-stu-id="acd51-122">IPropertyBag, IPersistPropertyBag</span></span>  
 <span data-ttu-id="acd51-123">パイプライン コンポーネントを実装する必要があります**IPersistPropertyBag**その構成情報を受信します。</span><span class="sxs-lookup"><span data-stu-id="acd51-123">Pipeline components need to implement **IPersistPropertyBag** to receive its configuration information.</span></span> <span data-ttu-id="acd51-124">このインターフェイスと**IPropertyBag**は標準のインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="acd51-124">This interface and **IPropertyBag** are the standard interfaces.</span></span> <span data-ttu-id="acd51-125">これらのインターフェイスの詳細については、Microsoft .NET Framework ソフトウェア開発キット (SDK) のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="acd51-125">For more information about these interfaces, refer to the Microsoft .NET Framework Software Development Kit (SDK) documentation.</span></span>  
  
## <a name="idisassemblercomponent"></a><span data-ttu-id="acd51-126">IDisassemblerComponent</span><span class="sxs-lookup"><span data-stu-id="acd51-126">IDisassemblerComponent</span></span>  
 <span data-ttu-id="acd51-127">逆アセンブラー コンポーネントは、入力時に 1 通のメッセージを受け取り、出力時に 0 通以上のメッセージを生成するパイプライン コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="acd51-127">A disassembling component is a pipeline component that receives one message on input and produces zero or more messages on output.</span></span> <span data-ttu-id="acd51-128">逆アセンブラー コンポーネントは、メッセージのインターチェンジを個別のドキュメントに分割するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="acd51-128">Disassembling components are used to split interchanges of messages into individual documents.</span></span> <span data-ttu-id="acd51-129">逆アセンブラー コンポーネントのメソッドを実装する必要があります、 **IDisassemblerComponent**からのメッセージを取得するインターフェイス[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]処理との逆アセンブルしたドキュメント バックアップ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="acd51-129">A disassembler component must implement the methods of the **IDisassemblerComponent** interface to get messages from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for processing and to pass disassembled documents back to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
|<span data-ttu-id="acd51-130">方法</span><span class="sxs-lookup"><span data-stu-id="acd51-130">Method</span></span>|<span data-ttu-id="acd51-131">Description</span><span class="sxs-lookup"><span data-stu-id="acd51-131">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="acd51-132">**逆アセンブルします。**</span><span class="sxs-lookup"><span data-stu-id="acd51-132">**Disassemble**</span></span>|<span data-ttu-id="acd51-133">受信ドキュメントの逆アセンブルを実行**pInMsg**です。</span><span class="sxs-lookup"><span data-stu-id="acd51-133">Performs the disassembling of the incoming document **pInMsg**.</span></span>|  
|<span data-ttu-id="acd51-134">**GetNext**</span><span class="sxs-lookup"><span data-stu-id="acd51-134">**GetNext**</span></span>|<span data-ttu-id="acd51-135">逆アセンブラーを実行して生成されたメッセージ セットから次のメッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="acd51-135">Gets the next message from the message set that resulted from disassembler execution.</span></span> <span data-ttu-id="acd51-136">返します**NULL**これ以上メッセージがある場合。</span><span class="sxs-lookup"><span data-stu-id="acd51-136">Returns **NULL** if there are no more messages.</span></span>|  
  
 <span data-ttu-id="acd51-137">回復可能なインターチェンジ処理をサポートする逆アセンブラー コンポーネントを記述する場合は、次の作業を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="acd51-137">If you are writing a disassembler component that will support Recoverable Interchange Processing, you must do the following:</span></span>  
  
1.  <span data-ttu-id="acd51-138">入力ストリームを VirtualStream() でラップすることによって、シークできるようにします。</span><span class="sxs-lookup"><span data-stu-id="acd51-138">Make the input streams seekable by wrapping them in a VirtualStream().</span></span>  
  
2.  <span data-ttu-id="acd51-139">GetNext() 内に、メッセージに問題があるかどうかを判断するロジックを記述します。</span><span class="sxs-lookup"><span data-stu-id="acd51-139">In GetNext(), have logic to determine when a message is bad.</span></span> <span data-ttu-id="acd51-140">メッセージに問題がある場合は、BTS.MessageDestination = "SuspendQueue" と設定して GetNext() でそのメッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="acd51-140">If a message is bad, set BTS.MessageDestination = "SuspendQueue" and return the message in GetNext().</span></span>  
  
3.  <span data-ttu-id="acd51-141">メッセージに問題がない場合は、BTS.SuspendMessageOnRoutingFailure = True と設定して GetNext() でメッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="acd51-141">If the message is good, set BTS.SuspendMessageOnRoutingFailure = True and return the message in GetNext().</span></span>  
  
## <a name="iassemblercomponent"></a><span data-ttu-id="acd51-142">IAssemblerComponent</span><span class="sxs-lookup"><span data-stu-id="acd51-142">IAssemblerComponent</span></span>  
 <span data-ttu-id="acd51-143">アセンブラー コンポーネントは、入力時に複数のメッセージを受け取り、出力時に 1 通のメッセージを生成するパイプライン コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="acd51-143">An assembling component is a pipeline component that receives several messages on input and produces one message on output.</span></span> <span data-ttu-id="acd51-144">アセンブラー コンポーネントは、個別のドキュメントをまとめてメッセージ インターチェンジのバッチを作成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="acd51-144">Assembling components are used to collect individual documents into the message interchange batch.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="acd51-145">このリリースの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ではアセンブル機能は使用されていないため、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は常に 1 つのドキュメントをコンポーネントの入力として渡します。</span><span class="sxs-lookup"><span data-stu-id="acd51-145">In this release of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], assembling functionality is not used, so [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] always passes one document to the component input.</span></span>  
  
 <span data-ttu-id="acd51-146">アセンブラー コンポーネントを実装して、 **IAssemblerComponent**メソッドによって呼び出される、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実行時にエンジンです。</span><span class="sxs-lookup"><span data-stu-id="acd51-146">An assembler component implements the **IAssemblerComponent** methods that are called by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] engine at run time.</span></span>  
  
|<span data-ttu-id="acd51-147">方法</span><span class="sxs-lookup"><span data-stu-id="acd51-147">Method</span></span>|<span data-ttu-id="acd51-148">Description</span><span class="sxs-lookup"><span data-stu-id="acd51-148">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="acd51-149">**AddDocument**</span><span class="sxs-lookup"><span data-stu-id="acd51-149">**AddDocument**</span></span>|<span data-ttu-id="acd51-150">ドキュメントに追加**pInMsg**インターチェンジに含まれるメッセージの一覧にします。</span><span class="sxs-lookup"><span data-stu-id="acd51-150">Adds the document **pInMsg** to the list of messages that will be included in the interchange.</span></span>|  
|<span data-ttu-id="acd51-151">**アセンブル**</span><span class="sxs-lookup"><span data-stu-id="acd51-151">**Assemble**</span></span>|<span data-ttu-id="acd51-152">前のメソッドによって追加されたメッセージからインターチェンジを構築します。</span><span class="sxs-lookup"><span data-stu-id="acd51-152">Builds the interchange from the messages that were added by the previous method.</span></span> <span data-ttu-id="acd51-153">アセンブルされたメッセージへのポインターを返します。</span><span class="sxs-lookup"><span data-stu-id="acd51-153">Returns a pointer to the assembled message.</span></span>|  
  
## <a name="iprobemessage"></a><span data-ttu-id="acd51-154">IProbeMessage</span><span class="sxs-lookup"><span data-stu-id="acd51-154">IProbeMessage</span></span>  
 <span data-ttu-id="acd51-155">任意のパイプライン コンポーネント (全般、アセンブル、または逆アセンブル) を実装できます**IProbeMessage**メッセージ プローブ機能が必要とする場合。</span><span class="sxs-lookup"><span data-stu-id="acd51-155">Any pipeline component (general, assembling, or disassembling) can implement **IProbeMessage** if it requires message probing functionality.</span></span> <span data-ttu-id="acd51-156">プローブ コンポーネントはされているパイプライン ステージで使用**FirstMatch**実行モードです。</span><span class="sxs-lookup"><span data-stu-id="acd51-156">A probing component is used in the pipeline stages that have **FirstMatch** execution mode.</span></span> <span data-ttu-id="acd51-157">、このような段階的に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンポーネントへのメッセージを提供し、**プローブ**メソッドは、コンポーネントにメッセージの形式が認識されるかどうかを決定するメッセージの先頭を検査します。</span><span class="sxs-lookup"><span data-stu-id="acd51-157">In such stages, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] gives the message to the component, and the **Probe** method examines the beginning of the message to determine if the component recognizes the format of the message.</span></span>  
  
|<span data-ttu-id="acd51-158">方法</span><span class="sxs-lookup"><span data-stu-id="acd51-158">Method</span></span>|<span data-ttu-id="acd51-159">Description</span><span class="sxs-lookup"><span data-stu-id="acd51-159">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="acd51-160">**プローブ**</span><span class="sxs-lookup"><span data-stu-id="acd51-160">**Probe**</span></span>|<span data-ttu-id="acd51-161">このメソッドは、 **pInMsg**メッセージ、および返します**True**形式が認識された場合または**False**それ以外の場合。</span><span class="sxs-lookup"><span data-stu-id="acd51-161">This method takes **pInMsg** message, and returns **True** if the format is recognized or **False** otherwise.</span></span>|  
  
## <a name="inameditem"></a><span data-ttu-id="acd51-162">INamedItem</span><span class="sxs-lookup"><span data-stu-id="acd51-162">INamedItem</span></span>  
 <span data-ttu-id="acd51-163">マネージ コードおよびアンマネージ コードからドキュメント スキーマにアクセスするためのヘルパー インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="acd51-163">This is a helper interface for accessing document schemas from managed and unmanaged code.</span></span>  
  
## <a name="inameditemlist"></a><span data-ttu-id="acd51-164">INamedItemList</span><span class="sxs-lookup"><span data-stu-id="acd51-164">INamedItemList</span></span>  
 <span data-ttu-id="acd51-165">マネージ コードおよびアンマネージ コードからドキュメント スキーマにアクセスするためのヘルパー インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="acd51-165">This is a helper interface for accessing document schemas from managed and unmanaged code.</span></span>  
  
## <a name="idocumentspec"></a><span data-ttu-id="acd51-166">IDocumentSpec</span><span class="sxs-lookup"><span data-stu-id="acd51-166">IDocumentSpec</span></span>  
 <span data-ttu-id="acd51-167">パイプライン コンポーネントのメソッドを使用できる、 **IDocumentSpec**コンテキストと、ドキュメント スキーマにアクセスするコンテンツのプロパティの移動など、ドキュメントに固有の操作を実行するためのインターフェイスし、などです。</span><span class="sxs-lookup"><span data-stu-id="acd51-167">Pipeline components can use methods of the **IDocumentSpec** interface to perform document-specific actions, such as moving content properties to context and back, accessing document schemas, and so on.</span></span>  
  
|<span data-ttu-id="acd51-168">方法</span><span class="sxs-lookup"><span data-stu-id="acd51-168">Method</span></span>|<span data-ttu-id="acd51-169">Description</span><span class="sxs-lookup"><span data-stu-id="acd51-169">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="acd51-170">**DocType**</span><span class="sxs-lookup"><span data-stu-id="acd51-170">**DocType**</span></span>|<span data-ttu-id="acd51-171">現在のドキュメントの型を返します。</span><span class="sxs-lookup"><span data-stu-id="acd51-171">Returns the type of the current document.</span></span>|  
|<span data-ttu-id="acd51-172">**DocSpecName**</span><span class="sxs-lookup"><span data-stu-id="acd51-172">**DocSpecName**</span></span>|<span data-ttu-id="acd51-173">現在のドキュメントの仕様名を返します。</span><span class="sxs-lookup"><span data-stu-id="acd51-173">Returns the specification name of the current document.</span></span>|  
|<span data-ttu-id="acd51-174">**GetSchemaCollection**</span><span class="sxs-lookup"><span data-stu-id="acd51-174">**GetSchemaCollection**</span></span>|<span data-ttu-id="acd51-175">現在のドキュメントのドキュメント スキーマの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="acd51-175">Returns the list of document schemas for the current document.</span></span>|  
|<span data-ttu-id="acd51-176">**GetBodyPath**</span><span class="sxs-lookup"><span data-stu-id="acd51-176">**GetBodyPath**</span></span>|<span data-ttu-id="acd51-177">ボディ部が開始されるドキュメント内ノードへの XPath を返します。</span><span class="sxs-lookup"><span data-stu-id="acd51-177">Returns the XPath to the node in the document where the body part begins.</span></span>|  
|<span data-ttu-id="acd51-178">**GetDistinguishedPropertyAnnotationEnumerator**</span><span class="sxs-lookup"><span data-stu-id="acd51-178">**GetDistinguishedPropertyAnnotationEnumerator**</span></span>|<span data-ttu-id="acd51-179">すべての識別フィールド プロパティ注釈のディクショナリ列挙子を返します。</span><span class="sxs-lookup"><span data-stu-id="acd51-179">Returns a dictionary enumerator of all distinguished field property annotations.</span></span>|  
|<span data-ttu-id="acd51-180">**GetPropertyAnnotationEnumerator**</span><span class="sxs-lookup"><span data-stu-id="acd51-180">**GetPropertyAnnotationEnumerator**</span></span>|<span data-ttu-id="acd51-181">すべてのプロパティ注釈の列挙子を返します。</span><span class="sxs-lookup"><span data-stu-id="acd51-181">Returns an enumerator of all property annotations.</span></span>|  
  
## <a name="icomponentui"></a><span data-ttu-id="acd51-182">IComponentUI</span><span class="sxs-lookup"><span data-stu-id="acd51-182">IComponentUI</span></span>  
 <span data-ttu-id="acd51-183">パイプライン コンポーネントをパイプライン デザイナー環境で使用できるようにするには、このインターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="acd51-183">Pipeline components must implement this interface to be used within the Pipeline Designer environment.</span></span>  
  
|<span data-ttu-id="acd51-184">方法</span><span class="sxs-lookup"><span data-stu-id="acd51-184">Method</span></span>|<span data-ttu-id="acd51-185">Description</span><span class="sxs-lookup"><span data-stu-id="acd51-185">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="acd51-186">**アイコン**</span><span class="sxs-lookup"><span data-stu-id="acd51-186">**Icon**</span></span>|<span data-ttu-id="acd51-187">このコンポーネントに関連付けられたアイコンを指定します。</span><span class="sxs-lookup"><span data-stu-id="acd51-187">Provides the icon that is associated with this component.</span></span>|  
|<span data-ttu-id="acd51-188">**[検証]**</span><span class="sxs-lookup"><span data-stu-id="acd51-188">**Validate**</span></span>|<span data-ttu-id="acd51-189">パイプライン デザイナーは、パイプラインのコンパイル前にこのメソッドを呼び出して、すべての構成プロパティが正しく設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="acd51-189">Pipeline Designer calls this method before pipeline compilation to verify that all the configuration properties are set correctly.</span></span>|  
  
 <span data-ttu-id="acd51-190">**アイコン**プロパティから返される、 **IntPtr**です。</span><span class="sxs-lookup"><span data-stu-id="acd51-190">The **Icon** property returns an **IntPtr**.</span></span> <span data-ttu-id="acd51-191">次の c# の例を返す方法を示しています、 **IntPtr**です。</span><span class="sxs-lookup"><span data-stu-id="acd51-191">The following C# example shows how to return an **IntPtr**.</span></span>  
  
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
  
 <span data-ttu-id="acd51-192">詳細については、次を参照してください。 **IComponentUI インターフェイス (COM)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="acd51-192">For more information, see **IComponentUI Interface (COM)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="acd51-193">参照</span><span class="sxs-lookup"><span data-stu-id="acd51-193">See Also</span></span>  
 <span data-ttu-id="acd51-194">[カスタム パイプライン コンポーネントの開発](../core/developing-custom-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="acd51-194">[Developing Custom Pipeline Components](../core/developing-custom-pipeline-components.md) </span></span>  
 [<span data-ttu-id="acd51-195">CustomComponent (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="acd51-195">CustomComponent (BizTalk Server Sample)</span></span>](../core/customcomponent-biztalk-server-sample.md)