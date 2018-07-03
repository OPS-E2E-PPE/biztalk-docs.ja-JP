---
title: BizTalk Server を使用して SAP で Rfc を呼び出す |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RFCs, invoking using BizTalk Server
ms.assetid: cc859ca2-aa9a-48fd-a941-ae28bee96f06
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 381cbebae5e87e459b8283c90b4bbc0de9afb1cc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988787"
---
# <a name="invoke-rfcs-in-sap-using-biztalk-server"></a><span data-ttu-id="c97b2-102">BizTalk Server を使用して SAP で Rfc を呼び出す</span><span class="sxs-lookup"><span data-stu-id="c97b2-102">Invoke RFCs in SAP using BizTalk Server</span></span>
<span data-ttu-id="c97b2-103">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]アダプター クライアントによって呼び出すことができる操作として、SAP システムによって公開されている Rfc 明らかになります。</span><span class="sxs-lookup"><span data-stu-id="c97b2-103">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces the RFCs exposed by an SAP system as operations that can be invoked by an adapter client.</span></span> <span data-ttu-id="c97b2-104">このセクションを使用して SAP システムでの RFC を呼び出すための説明、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] microsoft[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-104">This section provides instructions on invoking an RFC in an SAP system by using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] with Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="c97b2-105">方法の詳細については[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]RFC を呼び出すことは、SAP システムにサポートを参照してください[SAP で Rfc に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-rfcs-in-sap.md)します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-105">For more information about how the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports invoking an RFC in an SAP system, see [Operations on RFCs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-rfcs-in-sap.md).</span></span> <span data-ttu-id="c97b2-106">RFC を呼び出すための SOAP メッセージの構造の詳細については、次を参照してください。 [RFC 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-106">For more information about the structure of SOAP message for invoking an RFC, see [Message Schemas for RFC Operations](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md).</span></span>  
  
## <a name="how-to-invoke-an-rfc-in-an-sap-system"></a><span data-ttu-id="c97b2-107">SAP システムでの RFC を呼び出す方法でしょうか。</span><span class="sxs-lookup"><span data-stu-id="c97b2-107">How to Invoke an RFC in an SAP system?</span></span>  
 <span data-ttu-id="c97b2-108">使用して SAP システムに対する演算を実行、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明されている手順のタスクが含まれます[SAP アプリケーションを作成する構成要素](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-108">Performing an operation on an SAP system using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] involves procedural tasks described in [Building blocks to create SAP applications](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md).</span></span> <span data-ttu-id="c97b2-109">これらのタスクは、SAP システムの RFC を呼び出すには。</span><span class="sxs-lookup"><span data-stu-id="c97b2-109">To invoke an RFC in an SAP system, these tasks are:</span></span>  
  
1. <span data-ttu-id="c97b2-110">BizTalk プロジェクトを作成し、SAP システムが呼び出す RFC のスキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-110">Create a BizTalk project and generate schema for the RFC you want to invoke in the SAP system.</span></span>  
  
2. <span data-ttu-id="c97b2-111">SAP システムからメッセージを送受信するための BizTalk プロジェクトでは、メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-111">Create messages in the BizTalk project for sending and receiving messages from the SAP system.</span></span>  
  
3. <span data-ttu-id="c97b2-112">SAP システムでの RFC を呼び出すオーケストレーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-112">Create an orchestration to invoke an RFC in the SAP system.</span></span>  
  
4. <span data-ttu-id="c97b2-113">ビルドし、BizTalk プロジェクトを配置します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-113">Build and deploy the BizTalk project.</span></span>  
  
5. <span data-ttu-id="c97b2-114">BizTalk 物理を作成してアプリケーションの送信および受信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-114">Configure the BizTalk application by creating physical send and receive ports.</span></span>  
  
6. <span data-ttu-id="c97b2-115">BizTalk アプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-115">Start the BizTalk application.</span></span>  
  
   <span data-ttu-id="c97b2-116">このトピックでは、これらのタスクを実行する手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-116">This topic provides instructions to perform these tasks.</span></span>  
  
## <a name="generating-schema"></a><span data-ttu-id="c97b2-117">スキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-117">Generating Schema</span></span>  
 <span data-ttu-id="c97b2-118">このトピックでは、SAP システムでの RFC を呼び出す方法を示すためにスキーマを生成*RFC_CUSTOMER_GET*します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-118">In this topic, to demonstrate how to invoke an RFC in an SAP system, we generate the schema for *RFC_CUSTOMER_GET*.</span></span> <span data-ttu-id="c97b2-119">参照してください[参照、検索、および SAP の RFC 操作のメタデータを取得](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md)スキーマを生成する方法の詳細について。</span><span class="sxs-lookup"><span data-stu-id="c97b2-119">See [Browse, Search, and get Metadata for RFC Operations in SAP](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md) for more information about how to generate schema.</span></span>  
  
## <a name="defining-messages-and-message-types"></a><span data-ttu-id="c97b2-120">メッセージおよびメッセージの種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-120">Defining Messages and Message Types</span></span>  
 <span data-ttu-id="c97b2-121">以前に生成したスキーマには、オーケストレーション内のメッセージに必要な「型」について説明します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-121">The schema that you generated earlier describes the "types" required for the messages in the orchestration.</span></span> <span data-ttu-id="c97b2-122">メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。</span><span class="sxs-lookup"><span data-stu-id="c97b2-122">A message is typically a variable, the type for which is defined by the corresponding schema.</span></span> <span data-ttu-id="c97b2-123">BizTalk プロジェクトのオーケストレーションからメッセージを生成したスキーマをリンクする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c97b2-123">You must link the schema you generated to the messages from the Orchestration view of the BizTalk project.</span></span>  
  
 <span data-ttu-id="c97b2-124">このトピックでは、2 つのメッセージを作成する必要があります: 1 つに、SAP システムと他の応答を受信する要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-124">For this topic, you must create two messages—one to send a request to the SAP system and the other to receive a response.</span></span>  
  
 <span data-ttu-id="c97b2-125">メッセージを作成し、スキーマにリンクするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-125">Perform the following steps to create messages and link them to the schema.</span></span>  
  
#### <a name="to-create-messages-and-link-to-schema"></a><span data-ttu-id="c97b2-126">メッセージを作成し、スキーマにリンクするには</span><span class="sxs-lookup"><span data-stu-id="c97b2-126">To create messages and link to schema</span></span>  
  
1.  <span data-ttu-id="c97b2-127">オーケストレーションの種類を BizTalk プロジェクトを開くまだ開いていない場合。</span><span class="sxs-lookup"><span data-stu-id="c97b2-127">Open the orchestration view the BizTalk project, if not already open.</span></span> <span data-ttu-id="c97b2-128">をクリックして**ビュー**、 をポイント**その他の Windows**、 をクリック**オーケストレーション**します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-128">Click **View**, point to **Other Windows**, and click **Orchestration View**.</span></span>  
  
2.  <span data-ttu-id="c97b2-129">**オーケストレーション**、右クリック**メッセージ**、順にクリックします**新しいメッセージ**します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-129">In the **Orchestration View**, right-click **Messages**, and then click **New Message**.</span></span>  
  
3.  <span data-ttu-id="c97b2-130">右クリックし、新規メッセージを作成および選択**プロパティ ウィンドウ**します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-130">Right-click the newly create message and select **Properties Window**.</span></span>  
  
4.  <span data-ttu-id="c97b2-131">**プロパティ**ウィンドウ **[message_1]** 次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c97b2-131">In the **Properties** pane for **Message_1**, do the following.</span></span>  
  
    |<span data-ttu-id="c97b2-132">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c97b2-132">Use this</span></span>|<span data-ttu-id="c97b2-133">目的</span><span class="sxs-lookup"><span data-stu-id="c97b2-133">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="c97b2-134">[Identifier]</span><span class="sxs-lookup"><span data-stu-id="c97b2-134">Identifier</span></span>|<span data-ttu-id="c97b2-135">型**要求**します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-135">Type **Request**.</span></span>|  
    |<span data-ttu-id="c97b2-136">メッセージ型</span><span class="sxs-lookup"><span data-stu-id="c97b2-136">Message Type</span></span>|<span data-ttu-id="c97b2-137">ドロップダウン リストから展開**スキーマ**、選択と*InvokeRFC.SAPBindingSchema.RFC_CUSTOMER_GET*ここで、 *InvokeRFC* BizTalk プロジェクトの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-137">From the drop-down list, expand **Schemas**, and select *InvokeRFC.SAPBindingSchema.RFC_CUSTOMER_GET*, where *InvokeRFC* is the name of your BizTalk project.</span></span>  <span data-ttu-id="c97b2-138">*SAPBindingSchema*に対して生成されたスキーマは、 *RFC_CUSTOMER_GET*します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-138">*SAPBindingSchema* is the schema generated for *RFC_CUSTOMER_GET*.</span></span>|  
  
5.  <span data-ttu-id="c97b2-139">新しいメッセージを作成する前の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-139">Repeat the previous step to create a new message.</span></span> <span data-ttu-id="c97b2-140">**プロパティ**ウィンドウで、新しいメッセージの場合は、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-140">In the **Properties** pane for the new message, do the following.</span></span>  
  
    |<span data-ttu-id="c97b2-141">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c97b2-141">Use this</span></span>|<span data-ttu-id="c97b2-142">目的</span><span class="sxs-lookup"><span data-stu-id="c97b2-142">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="c97b2-143">[Identifier]</span><span class="sxs-lookup"><span data-stu-id="c97b2-143">Identifier</span></span>|<span data-ttu-id="c97b2-144">型**応答**します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-144">Type **Response**.</span></span>|  
    |<span data-ttu-id="c97b2-145">メッセージ型</span><span class="sxs-lookup"><span data-stu-id="c97b2-145">Message Type</span></span>|<span data-ttu-id="c97b2-146">ドロップダウン リストから展開**スキーマ**、選択および*InvokeRFC.SAPBindingSchema.RFC_CUSTOMER_GETResponse*します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-146">From the drop-down list, expand **Schemas**, and select *InvokeRFC.SAPBindingSchema.RFC_CUSTOMER_GETResponse*.</span></span>|  
  
## <a name="setting-up-the-orchestration"></a><span data-ttu-id="c97b2-147">オーケストレーションのセットアップ</span><span class="sxs-lookup"><span data-stu-id="c97b2-147">Setting up the Orchestration</span></span>  
 <span data-ttu-id="c97b2-148">使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]SAP システムでの Rfc を呼び出すためです。</span><span class="sxs-lookup"><span data-stu-id="c97b2-148">You must create a BizTalk orchestration to use [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] for invoking RFCs in the SAP system.</span></span> <span data-ttu-id="c97b2-149">このオーケストレーションでの要求メッセージを削除する、定義されている受信場所。</span><span class="sxs-lookup"><span data-stu-id="c97b2-149">In this orchestration, you drop a request message at a defined receive location.</span></span> <span data-ttu-id="c97b2-150">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]メッセージを使用して、SAP システムに渡します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-150">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] consumes the message and passes it on to the SAP system.</span></span> <span data-ttu-id="c97b2-151">SAP システムからの応答は、別の場所に保存されます。</span><span class="sxs-lookup"><span data-stu-id="c97b2-151">The response from the SAP system is saved to another location.</span></span> <span data-ttu-id="c97b2-152">SAP システムでの呼び出し元の Rfc の一般的なオーケストレーションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c97b2-152">A typical orchestration for invoking RFCs in an SAP system would contain:</span></span>  
  
- <span data-ttu-id="c97b2-153">SAP システムにメッセージを送信し、応答を受信する図形を送受信します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-153">Send and Receive shapes to send messages to the SAP system and receive responses.</span></span>  
  
- <span data-ttu-id="c97b2-154">SAP システムに送信する要求メッセージを受信するポートは一方向の受信します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-154">A one-way receive port to receive request messages to send to the SAP system.</span></span>  
  
- <span data-ttu-id="c97b2-155">SAP システムに要求メッセージを送信し、応答を受信するポートを双方向に送信します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-155">A two-way send port to send request messages to the SAP system and receive responses.</span></span>  
  
- <span data-ttu-id="c97b2-156">SAP システムからフォルダーに、応答を送信する一方向の送信ポート。</span><span class="sxs-lookup"><span data-stu-id="c97b2-156">A one-way send port to send the responses from the SAP system to a folder.</span></span>  
  
  <span data-ttu-id="c97b2-157">サンプル オーケストレーションには、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="c97b2-157">A sample orchestration resembles the following:</span></span>  
  
  <span data-ttu-id="c97b2-158">![オーケストレーション ポートが接続された](../../adapters-and-accelerators/adapter-sap/media/c228e79f-02e8-4de3-b447-8703caa28d3b.gif "c228e79f-02e8-4de3-b447-8703caa28d3b")</span><span class="sxs-lookup"><span data-stu-id="c97b2-158">![Orchestration with ports connected](../../adapters-and-accelerators/adapter-sap/media/c228e79f-02e8-4de3-b447-8703caa28d3b.gif "c228e79f-02e8-4de3-b447-8703caa28d3b")</span></span>  
  
### <a name="adding-message-shapes"></a><span data-ttu-id="c97b2-159">メッセージの構築図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-159">Adding Message Shapes</span></span>  
 <span data-ttu-id="c97b2-160">メッセージの構築図形のごとに、次のプロパティを指定することを確認します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-160">Make sure you specify the following properties for each of the message shapes.</span></span> <span data-ttu-id="c97b2-161">表示される名前、*図形*前のオーケストレーションに表示される、列は、メッセージの構築図形の名前。</span><span class="sxs-lookup"><span data-stu-id="c97b2-161">The names listed in the *Shape* column are the names of the message shapes as displayed in the preceding orchestration.</span></span>  
  
|<span data-ttu-id="c97b2-162">図形</span><span class="sxs-lookup"><span data-stu-id="c97b2-162">Shape</span></span>|<span data-ttu-id="c97b2-163">図形の種類</span><span class="sxs-lookup"><span data-stu-id="c97b2-163">Shape Type</span></span>|<span data-ttu-id="c97b2-164">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="c97b2-164">Properties</span></span>|  
|-----------|----------------|----------------|  
|<span data-ttu-id="c97b2-165">Receive_Request</span><span class="sxs-lookup"><span data-stu-id="c97b2-165">Receive_Request</span></span>|<span data-ttu-id="c97b2-166">Receive</span><span class="sxs-lookup"><span data-stu-id="c97b2-166">Receive</span></span>|<span data-ttu-id="c97b2-167">-設定**名前**に*Receive_Request*</span><span class="sxs-lookup"><span data-stu-id="c97b2-167">-   Set **Name** to *Receive_Request*</span></span><br /><span data-ttu-id="c97b2-168">-設定**アクティブ**に*は True。*</span><span class="sxs-lookup"><span data-stu-id="c97b2-168">-   Set **Activate** to *True*</span></span>|  
|<span data-ttu-id="c97b2-169">Send_LOB</span><span class="sxs-lookup"><span data-stu-id="c97b2-169">Send_LOB</span></span>|<span data-ttu-id="c97b2-170">Send</span><span class="sxs-lookup"><span data-stu-id="c97b2-170">Send</span></span>|<span data-ttu-id="c97b2-171">-設定**名前**に*Send_LOB*</span><span class="sxs-lookup"><span data-stu-id="c97b2-171">-   Set **Name** to *Send_LOB*</span></span>|  
|<span data-ttu-id="c97b2-172">Receive_LOB</span><span class="sxs-lookup"><span data-stu-id="c97b2-172">Receive_LOB</span></span>|<span data-ttu-id="c97b2-173">Receive</span><span class="sxs-lookup"><span data-stu-id="c97b2-173">Receive</span></span>|<span data-ttu-id="c97b2-174">-設定**名前**に*Receive_LOB*</span><span class="sxs-lookup"><span data-stu-id="c97b2-174">-   Set **Name** to *Receive_LOB*</span></span><br /><span data-ttu-id="c97b2-175">-設定**アクティブ**に*False*</span><span class="sxs-lookup"><span data-stu-id="c97b2-175">-   Set **Activate** to *False*</span></span>|  
|<span data-ttu-id="c97b2-176">Send_Response</span><span class="sxs-lookup"><span data-stu-id="c97b2-176">Send_Response</span></span>|<span data-ttu-id="c97b2-177">Send</span><span class="sxs-lookup"><span data-stu-id="c97b2-177">Send</span></span>|<span data-ttu-id="c97b2-178">-設定**名前**に*Send_Response*</span><span class="sxs-lookup"><span data-stu-id="c97b2-178">-   Set **Name** to *Send_Response*</span></span>|  
  
### <a name="adding-ports"></a><span data-ttu-id="c97b2-179">ポートの追加</span><span class="sxs-lookup"><span data-stu-id="c97b2-179">Adding Ports</span></span>  
 <span data-ttu-id="c97b2-180">ごとの論理ポートには、次のプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-180">Specify the following properties for each of the logical ports.</span></span> <span data-ttu-id="c97b2-181">表示される名前、*ポート*列は、ポートの名前、オーケストレーションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c97b2-181">The names listed in the *Port* column are the names of the ports as displayed in the orchestration.</span></span>  
  
|<span data-ttu-id="c97b2-182">Port</span><span class="sxs-lookup"><span data-stu-id="c97b2-182">Port</span></span>|<span data-ttu-id="c97b2-183">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="c97b2-183">Properties</span></span>|  
|----------|----------------|  
|<span data-ttu-id="c97b2-184">ReceiveMsgPort</span><span class="sxs-lookup"><span data-stu-id="c97b2-184">ReceiveMsgPort</span></span>|<span data-ttu-id="c97b2-185">-設定**識別子**に*ReceiveMsgPort*</span><span class="sxs-lookup"><span data-stu-id="c97b2-185">-   Set **Identifier** to *ReceiveMsgPort*</span></span><br /><span data-ttu-id="c97b2-186">-設定**型**に*ReceiveMsgPortType*</span><span class="sxs-lookup"><span data-stu-id="c97b2-186">-   Set **Type** to *ReceiveMsgPortType*</span></span><br /><span data-ttu-id="c97b2-187">-設定**通信パターン**に*一方向*</span><span class="sxs-lookup"><span data-stu-id="c97b2-187">-   Set **Communication Pattern** to *One-Way*</span></span><br /><span data-ttu-id="c97b2-188">-設定**通信方向**に*受信*</span><span class="sxs-lookup"><span data-stu-id="c97b2-188">-   Set **Communication Direction** to *Receive*</span></span>|  
|<span data-ttu-id="c97b2-189">SendToLOBPort</span><span class="sxs-lookup"><span data-stu-id="c97b2-189">SendToLOBPort</span></span>|<span data-ttu-id="c97b2-190">-設定**識別子**に*SendToLOBPort*</span><span class="sxs-lookup"><span data-stu-id="c97b2-190">-   Set **Identifier** to *SendToLOBPort*</span></span><br /><span data-ttu-id="c97b2-191">-設定**型**に*SendToLOBPortType*</span><span class="sxs-lookup"><span data-stu-id="c97b2-191">-   Set **Type** to *SendToLOBPortType*</span></span><br /><span data-ttu-id="c97b2-192">-設定**通信パターン**に*要求-応答*</span><span class="sxs-lookup"><span data-stu-id="c97b2-192">-   Set **Communication Pattern** to *Request-Response*</span></span><br /><span data-ttu-id="c97b2-193">-設定**通信方向**に*送受信*</span><span class="sxs-lookup"><span data-stu-id="c97b2-193">-   Set **Communication Direction** to *Send-Receive*</span></span>|  
|<span data-ttu-id="c97b2-194">SendMsgPort</span><span class="sxs-lookup"><span data-stu-id="c97b2-194">SendMsgPort</span></span>|<span data-ttu-id="c97b2-195">-設定**識別子**に*SendMsgPort*</span><span class="sxs-lookup"><span data-stu-id="c97b2-195">-   Set **Identifier** to *SendMsgPort*</span></span><br /><span data-ttu-id="c97b2-196">-設定**型**に*SendMsgPortType*</span><span class="sxs-lookup"><span data-stu-id="c97b2-196">-   Set **Type** to *SendMsgPortType*</span></span><br /><span data-ttu-id="c97b2-197">-設定**通信パターン**に*一方向*</span><span class="sxs-lookup"><span data-stu-id="c97b2-197">-   Set **Communication Pattern** to *One-Way*</span></span><br /><span data-ttu-id="c97b2-198">-設定**通信方向**に*送信*</span><span class="sxs-lookup"><span data-stu-id="c97b2-198">-   Set **Communication Direction** to *Send*</span></span>|  
  
## <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a><span data-ttu-id="c97b2-199">アクション図形のメッセージを指定し、ポートに接続</span><span class="sxs-lookup"><span data-stu-id="c97b2-199">Specify Messages for Action Shapes and Connect to Ports</span></span>  
 <span data-ttu-id="c97b2-200">次の表には、プロパティとメッセージのアクション図形とポートにリンクすることを指定するために設定するには、その値を指定します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-200">The following table specifies the properties and their values to be set to specify messages for action shapes and linking them to the ports.</span></span> <span data-ttu-id="c97b2-201">表示される名前、*図形*前のオーケストレーションに表示される、列は、メッセージの構築図形の名前。</span><span class="sxs-lookup"><span data-stu-id="c97b2-201">The names listed in the *Shape* column are the names of the message shapes as displayed in the preceding orchestration.</span></span>  
  
|<span data-ttu-id="c97b2-202">図形</span><span class="sxs-lookup"><span data-stu-id="c97b2-202">Shape</span></span>|<span data-ttu-id="c97b2-203">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="c97b2-203">Properties</span></span>|  
|-----------|----------------|  
|<span data-ttu-id="c97b2-204">Receive_Request</span><span class="sxs-lookup"><span data-stu-id="c97b2-204">Receive_Request</span></span>|<span data-ttu-id="c97b2-205">-設定**メッセージ**に*要求*</span><span class="sxs-lookup"><span data-stu-id="c97b2-205">-   Set **Message** to *Request*</span></span><br /><span data-ttu-id="c97b2-206">-設定**操作**に*ReceiveMsgPort.Operation_1.Request*</span><span class="sxs-lookup"><span data-stu-id="c97b2-206">-   Set **Operation** to *ReceiveMsgPort.Operation_1.Request*</span></span>|  
|<span data-ttu-id="c97b2-207">Send_LOB</span><span class="sxs-lookup"><span data-stu-id="c97b2-207">Send_LOB</span></span>|<span data-ttu-id="c97b2-208">-設定**メッセージ**に*要求*</span><span class="sxs-lookup"><span data-stu-id="c97b2-208">-   Set **Message** to *Request*</span></span><br /><span data-ttu-id="c97b2-209">-設定**操作**に*SendToLOBPort.Operation_1.Request*</span><span class="sxs-lookup"><span data-stu-id="c97b2-209">-   Set **Operation** to *SendToLOBPort.Operation_1.Request*</span></span>|  
|<span data-ttu-id="c97b2-210">Receive_LOB</span><span class="sxs-lookup"><span data-stu-id="c97b2-210">Receive_LOB</span></span>|<span data-ttu-id="c97b2-211">-設定**メッセージ**に*応答*</span><span class="sxs-lookup"><span data-stu-id="c97b2-211">-   Set **Message** to *Response*</span></span><br /><span data-ttu-id="c97b2-212">-設定**操作**に*SendToLOBPort.Operation_1.Response*</span><span class="sxs-lookup"><span data-stu-id="c97b2-212">-   Set **Operation** to *SendToLOBPort.Operation_1.Response*</span></span>|  
|<span data-ttu-id="c97b2-213">Send_Response</span><span class="sxs-lookup"><span data-stu-id="c97b2-213">Send_Response</span></span>|<span data-ttu-id="c97b2-214">-設定**メッセージ**に*応答*</span><span class="sxs-lookup"><span data-stu-id="c97b2-214">-   Set **Message** to *Response*</span></span><br /><span data-ttu-id="c97b2-215">-設定**操作**に*SendMsgPort.Operation_1.Request*</span><span class="sxs-lookup"><span data-stu-id="c97b2-215">-   Set **Operation** to *SendMsgPort.Operation_1.Request*</span></span>|  
  
 <span data-ttu-id="c97b2-216">これらのプロパティを指定したら、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-216">After you have specified these properties, the message shapes and ports are connected and your orchestration is complete.</span></span>  
  
 <span data-ttu-id="c97b2-217">ここで、BizTalk ソリューションをビルドしに配置する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-217">You must now build the BizTalk solution and deploy it to a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="c97b2-218">詳細については、次を参照してください。[を実行しているオーケストレーションのビルドと](../../core/building-and-running-orchestrations.md)します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-218">For more information, see [Building and Running Orchestrations](../../core/building-and-running-orchestrations.md).</span></span>
  
## <a name="configuring-the-biztalk-application"></a><span data-ttu-id="c97b2-219">BizTalk アプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-219">Configuring the BizTalk Application</span></span>  
 <span data-ttu-id="c97b2-220">先ほど作成したオーケストレーションが 下にある BizTalk プロジェクトを配置した後、**オーケストレーション**BizTalk Server 管理コンソール ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="c97b2-220">After you have deployed the BizTalk project, the orchestration you created earlier is listed under the **Orchestrations** pane in the BizTalk Server Administration console.</span></span> <span data-ttu-id="c97b2-221">BizTalk Server 管理コンソールを使用して、アプリケーションを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c97b2-221">You must use the BizTalk Server Administration console to configure the application.</span></span> <span data-ttu-id="c97b2-222">アプリケーションを構成する方法の詳細については、次を参照してください。[アプリケーションを構成する方法](../../core/how-to-configure-an-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-222">For more information about configuring an application, see [How to Configure an Application](../../core/how-to-configure-an-application.md).</span></span>
  
 <span data-ttu-id="c97b2-223">アプリケーションを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c97b2-223">Configuring an application involves:</span></span>  
  
- <span data-ttu-id="c97b2-224">アプリケーションのホストを選択します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-224">Selecting a host for the application.</span></span>  
  
- <span data-ttu-id="c97b2-225">BizTalk Server 管理コンソールで物理ポートにオーケストレーションで作成したポートをマッピングします。</span><span class="sxs-lookup"><span data-stu-id="c97b2-225">Mapping the ports that you created in your orchestration to physical ports in the BizTalk Server Administration console.</span></span> <span data-ttu-id="c97b2-226">このオーケストレーションの次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="c97b2-226">For this orchestration you must:</span></span>  
  
  - <span data-ttu-id="c97b2-227">ハード ディスクと、要求メッセージをドロップする場所、対応するファイル ポートでの場所を定義します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-227">Define a location on the hard disk and a corresponding file port where you will drop a request message.</span></span> <span data-ttu-id="c97b2-228">BizTalk オーケストレーションは要求メッセージを使用し、SAP システムに送信します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-228">The BizTalk orchestration will consume the request message and send it to the SAP system.</span></span>  
  
  - <span data-ttu-id="c97b2-229">ハード ディスクと、対応するファイル ポートを BizTalk オーケストレーションでの SAP システムからの応答を含む応答メッセージをドロップする場所の場所を定義します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-229">Define a location on the hard disk and a corresponding file port where the BizTalk orchestration will drop the response message containing the response from the SAP system.</span></span>  
  
  - <span data-ttu-id="c97b2-230">SAP システムにメッセージを送信する物理 Wcf-custom または WCF-SAP 送信ポートを定義します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-230">Define a physical WCF-Custom or WCF-SAP send port to send messages to the SAP system.</span></span> <span data-ttu-id="c97b2-231">送信ポートでアクションを指定することも必要があります。</span><span class="sxs-lookup"><span data-stu-id="c97b2-231">You must also specify the action in the send port.</span></span> <span data-ttu-id="c97b2-232">ポートを作成する方法については、次を参照してください。 [SAP アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-232">For information about how to create ports, see [Manually configure a physical port binding to the SAP adapter](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md).</span></span>
  
    > [!NOTE]
    >  <span data-ttu-id="c97b2-233">使用して、スキーマの生成、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。</span><span class="sxs-lookup"><span data-stu-id="c97b2-233">Generating the schema using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] also creates a binding file containing information about the ports and the actions to be set for those ports.</span></span> <span data-ttu-id="c97b2-234">(発信) の送信ポートを作成または (着信) 用のポートを受信する BizTalk Server 管理コンソールから、このバインド ファイルをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="c97b2-234">You can import this binding file from the BizTalk Server Administration console to create send ports (for outbound calls) or receive ports (for inbound calls).</span></span> <span data-ttu-id="c97b2-235">詳細については、次を参照してください。 [sap ポートのバインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md)します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-235">For more information, see [Configure a physical port binding using a port binding file to SAP](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md).</span></span>
  
## <a name="starting-the-application"></a><span data-ttu-id="c97b2-236">アプリケーションの起動</span><span class="sxs-lookup"><span data-stu-id="c97b2-236">Starting the Application</span></span>  
 <span data-ttu-id="c97b2-237">SAP システムでの RFC を呼び出すための BizTalk アプリケーションを起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c97b2-237">You must start the BizTalk application for invoking an RFC in the SAP system.</span></span> <span data-ttu-id="c97b2-238">BizTalk アプリケーションを開始する手順については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)または[アプリケーションを起動する方法](../../core/how-to-start-and-stop-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-238">For instructions on starting a BizTalk application, see [How to Start an Orchestration](../../core/how-to-start-an-orchestration.md) or [how to start an application](../../core/how-to-start-and-stop-a-biztalk-application.md).</span></span>
  
 <span data-ttu-id="c97b2-239">この段階で、ことを確認します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-239">At this stage, make sure:</span></span>  
  
-   <span data-ttu-id="c97b2-240">ファイルは、オーケストレーションが実行中の要求メッセージを受信するポートを受信します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-240">The FILE receive port to receive request messages for the orchestration is running.</span></span>  
  
-   <span data-ttu-id="c97b2-241">オーケストレーションから応答メッセージを受信する FILE 送信ポートが実行されています。</span><span class="sxs-lookup"><span data-stu-id="c97b2-241">The FILE send port to receive the response messages from the orchestration is running.</span></span>  
  
-   <span data-ttu-id="c97b2-242">SAP システムにメッセージを送信する Wcf-custom または WCF SAP の送信ポートが実行されています。</span><span class="sxs-lookup"><span data-stu-id="c97b2-242">The WCF-Custom or WCF-SAP send port to send messages to the SAP system is running.</span></span>  
  
-   <span data-ttu-id="c97b2-243">操作の BizTalk オーケストレーションが実行されています。</span><span class="sxs-lookup"><span data-stu-id="c97b2-243">The BizTalk orchestration for the operation is running.</span></span>  
  
## <a name="executing-the-operation"></a><span data-ttu-id="c97b2-244">操作の実行</span><span class="sxs-lookup"><span data-stu-id="c97b2-244">Executing the Operation</span></span>  
 <span data-ttu-id="c97b2-245">アプリケーションを実行した後に、定義済みの場所で要求メッセージをオーケストレーションを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c97b2-245">After you run the application, you must drop a request message for the orchestration at a predefined location.</span></span> <span data-ttu-id="c97b2-246">参照してください[RFC 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)SAP システムでの RFC を呼び出すための要求メッセージのスキーマについて理解します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-246">See [Message Schemas for RFC Operations](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md) to know about the schema for the request message for invoking an RFC in an SAP system.</span></span> <span data-ttu-id="c97b2-247">たとえば、RFC_CUSTOMER_GET を起動する要求メッセージには。</span><span class="sxs-lookup"><span data-stu-id="c97b2-247">For example, the request message to invoke RFC_CUSTOMER_GET is:</span></span>  
  
```  
<RFC_CUSTOMER_GET xmlns="http://Microsoft.LobServices.Sap/2007/03/Rfc/">  
  <KUNNR>0000001390</KUNNR>  
  <NAME1>*</NAME1>  
  <CUSTOMER_T/>  
</RFC_CUSTOMER_GET>  
```  
  
 <span data-ttu-id="c97b2-248">オーケストレーションはメッセージを使用し、SAP システムに送信します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-248">The orchestration consumes the message and sends it to the SAP system.</span></span> <span data-ttu-id="c97b2-249">SAP システムからの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。</span><span class="sxs-lookup"><span data-stu-id="c97b2-249">The response from the SAP system is saved at other file location defined as part of the orchestration.</span></span> <span data-ttu-id="c97b2-250">たとえば、上記の要求メッセージの SAP システムからの応答には。</span><span class="sxs-lookup"><span data-stu-id="c97b2-250">For example, the response from the SAP system for the above request message is:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<RFC_CUSTOMER_GETResponse xmlns="http://Microsoft.LobServices.Sap/2007/03/Rfc/">  
  <CUSTOMER_T>  
    <RFCCUST xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
      <KUNNR>0000001390</KUNNR>   
      <ANRED>Firma</ANRED>   
      <NAME1>Contoso, Ltd.</NAME1>   
      <PFACH />   
      <STRAS>4567 Main Street</STRAS>   
      <PSTLZ>98052</PSTLZ>   
      <ORT01>USA</ORT01>   
      <TELF1>555-0101</TELF1>   
      <TELFX>555-0102</TELFX>   
    </RFCCUST>  
  </CUSTOMER_T>  
</RFC_CUSTOMER_GETResponse>  
```  
  
## <a name="possible-exceptions"></a><span data-ttu-id="c97b2-251">可能性のある例外</span><span class="sxs-lookup"><span data-stu-id="c97b2-251">Possible Exceptions</span></span>  
 <span data-ttu-id="c97b2-252">BizTalk Server を使用して SAP システムでの RFC の呼び出し中に発生する可能性が、例外については、次を参照してください。[例外とエラーは、SAP アダプターを使用した処理](../../adapters-and-accelerators/adapter-sap/exceptions-and-error-handling-with-the-sap-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-252">For information about the exceptions you might encounter while invoking an RFC in an SAP system using BizTalk Server, see [Exceptions and Error Handling with the SAP adapter](../../adapters-and-accelerators/adapter-sap/exceptions-and-error-handling-with-the-sap-adapter.md).</span></span>  
  
## <a name="best-practices"></a><span data-ttu-id="c97b2-253">ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="c97b2-253">Best Practices</span></span>  
 <span data-ttu-id="c97b2-254">展開し、BizTalk プロジェクトの構成後は、バインド ファイルと呼ばれる XML ファイル構成設定をエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="c97b2-254">After you have deployed and configured the BizTalk project, you can export configuration settings to an XML file called the bindings file.</span></span> <span data-ttu-id="c97b2-255">バインド ファイルを生成した後は、受信ポートなど、同じオーケストレーションの送信ポートを作成する必要はありませんように、ファイルから構成設定をインポートできます。</span><span class="sxs-lookup"><span data-stu-id="c97b2-255">Once you generate a bindings file, you can import the configuration settings from the file so that you do not need to create the send ports, receive ports, etc. for the same orchestration.</span></span> <span data-ttu-id="c97b2-256">バインド ファイルの詳細については、次を参照してください。[再利用の SAP アダプター バインド](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md)します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-256">For more information about binding files, see [Reuse SAP adapter bindings](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c97b2-257">参照</span><span class="sxs-lookup"><span data-stu-id="c97b2-257">See Also</span></span>  
[<span data-ttu-id="c97b2-258">BizTalk アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="c97b2-258">Develop BizTalk applications</span></span>](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)