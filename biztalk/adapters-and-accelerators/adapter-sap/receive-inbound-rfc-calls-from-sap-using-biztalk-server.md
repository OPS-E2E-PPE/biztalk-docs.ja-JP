---
title: "RFC 呼び出しの受信を BizTalk Server を使用して SAP から受信 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: RFC calls, receiving using BizTalk Server
ms.assetid: 822fd9fb-772f-4910-a11e-25c1d5dca6e1
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b949ae0d6d5938493c78ed542a67d3c8bd09b48
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="receive-inbound-rfc-calls-from-sap-using-biztalk-server"></a><span data-ttu-id="910cb-102">BizTalk Server を使用して SAP から受信 RFC 呼び出しの受信します。</span><span class="sxs-lookup"><span data-stu-id="910cb-102">Receive Inbound RFC Calls from SAP using BizTalk Server</span></span>
<span data-ttu-id="910cb-103">RFC サーバーのシナリオでは、3 つのエンティティがあります。</span><span class="sxs-lookup"><span data-stu-id="910cb-103">In an RFC server scenario, there are three entities:</span></span>  
  
-   <span data-ttu-id="910cb-104">SAP RFC を呼び出すために、要求を送信する SAP クライアント。</span><span class="sxs-lookup"><span data-stu-id="910cb-104">An SAP client that sends a request to SAP to invoke an RFC.</span></span> <span data-ttu-id="910cb-105">SAP GUI を使用して、または、RFC クライアントを通じて呼び出しをすることでこの呼び出すが、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="910cb-105">This could be invoked either by using the SAP GUI or by making an RFC client call through the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
-   <span data-ttu-id="910cb-106">SAP クライアントが呼び出す RFC 関数定義を含む SAP システムです。</span><span class="sxs-lookup"><span data-stu-id="910cb-106">The SAP system that contains an RFC function definition that the SAP client invokes.</span></span> <span data-ttu-id="910cb-107">要求で、SAP システムでは、RFC サーバー (アダプター) を渡します。</span><span class="sxs-lookup"><span data-stu-id="910cb-107">The SAP system passes on the request to the RFC server (the adapter).</span></span> <span data-ttu-id="910cb-108">これは、操作は、SAP サーバーは、アダプターに、RFC 呼び出しのメタデータを取得するアダプターによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="910cb-108">This is used by the adapter to get the metadata of the RFC call that the SAP server makes into the adapter.</span></span>  
  
-   <span data-ttu-id="910cb-109">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]は RFC サーバーとして機能し、実際の RFC をホストします。</span><span class="sxs-lookup"><span data-stu-id="910cb-109">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] that acts as the RFC server and hosts the actual RFC.</span></span>  
  
 <span data-ttu-id="910cb-110">最初のエンティティでは、SAP クライアントは、このトピックでは説明しません。</span><span class="sxs-lookup"><span data-stu-id="910cb-110">The first entity, the SAP client, is not discussed in this topic.</span></span> <span data-ttu-id="910cb-111">RFC を呼び出すため、SAP GUI を使用している場合は、SAP のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="910cb-111">If you are using the SAP GUI to invoke an RFC, refer to SAP documentation.</span></span> <span data-ttu-id="910cb-112">使用している場合、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] RFC を呼び出すを参照してください。[呼び出しを使用して BizTalk Server での SAP Rfc](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="910cb-112">If you are using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] to invoke an RFC, see [Invoke RFCs in SAP by Using BizTalk Server](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-biztalk-server.md).</span></span>  
  
 <span data-ttu-id="910cb-113">このセクションでは、RFC が SAP クライアントによって呼び出されると、RFC サーバー呼び出しを受信するアダプターを使用する方法の指示を提供します。</span><span class="sxs-lookup"><span data-stu-id="910cb-113">This section provides instructions on how to use the adapter to receive an RFC server call, once the RFC is invoked by an SAP client.</span></span> <span data-ttu-id="910cb-114">アダプターが受信側の RFC をサポートする方法の詳細についてサーバーの呼び出しを使用して、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を参照してください[SAP Rfc に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-rfcs-in-sap.md)です。</span><span class="sxs-lookup"><span data-stu-id="910cb-114">For more information on how the adapter supports receiving RFC server calls using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], see [Operations on RFCs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-rfcs-in-sap.md).</span></span>  
  
## <a name="how-to-receive-an-inbound-rfc-call-from-the-sap-system"></a><span data-ttu-id="910cb-115">SAP システムから受信 RFC 呼び出しを受信する方法は?</span><span class="sxs-lookup"><span data-stu-id="910cb-115">How to Receive an Inbound RFC Call from the SAP System?</span></span>  
 <span data-ttu-id="910cb-116">SAP システムを使用して、操作を実行[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明した手順のタスクでは、 [SAP アプリケーションを作成するビルド ブロック](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)です。</span><span class="sxs-lookup"><span data-stu-id="910cb-116">Performing an operation on an SAP system using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] involves procedural tasks described in [Building blocks to create SAP applications](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md).</span></span> <span data-ttu-id="910cb-117">これらのタスクは、SAP システムから、RFC 呼び出しを受信するには。</span><span class="sxs-lookup"><span data-stu-id="910cb-117">To receive an RFC call from the SAP system, these tasks are:</span></span>  
  
1.  <span data-ttu-id="910cb-118">RFC をここでは、外部アプリケーションに送信する SAP システムを構成、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="910cb-118">Configure your SAP system to send RFC to an external application, in this case the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
2.  <span data-ttu-id="910cb-119">BizTalk プロジェクトを作成し、RFC のスキーマを生成する、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムから受信します。</span><span class="sxs-lookup"><span data-stu-id="910cb-119">Create a BizTalk project and generate schema for the RFC that the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] will be receiving from the SAP system.</span></span>  
  
3.  <span data-ttu-id="910cb-120">SAP システムからメッセージを受信して応答を送信する BizTalk プロジェクトでメッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="910cb-120">Create messages in the BizTalk project for receiving messages from the SAP system and sending responses.</span></span>  
  
4.  <span data-ttu-id="910cb-121">SAP システムから RFC を受信、処理、および SAP システムへの応答を送信するためのオーケストレーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="910cb-121">Create an orchestration to receive an RFC from the SAP system, process it, and send the response to the SAP system.</span></span>  
  
5.  <span data-ttu-id="910cb-122">構築し、BizTalk プロジェクトを展開します。</span><span class="sxs-lookup"><span data-stu-id="910cb-122">Build and deploy the BizTalk project.</span></span>  
  
6.  <span data-ttu-id="910cb-123">BizTalk アプリケーションを作成する物理送信ポートと受信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="910cb-123">Configure the BizTalk application by creating physical send and receive ports.</span></span>  
  
7.  <span data-ttu-id="910cb-124">BizTalk アプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="910cb-124">Start the BizTalk application.</span></span>  
  
 <span data-ttu-id="910cb-125">このトピックでは、これらのタスクを実行する手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="910cb-125">This topic provides instructions to perform these tasks.</span></span>  
  
## <a name="activities-on-the-sap-system"></a><span data-ttu-id="910cb-126">SAP システムでのアクティビティ</span><span class="sxs-lookup"><span data-stu-id="910cb-126">Activities on the SAP System</span></span>  
 <span data-ttu-id="910cb-127">使用する前に、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムから受信 RFC 呼び出しを受信するには、SAP システムで、次のタスクを完了するを確認してください。</span><span class="sxs-lookup"><span data-stu-id="910cb-127">Before using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] to receive inbound RFC calls from the SAP system, make sure you complete the following tasks on the SAP system.</span></span>  
  
-   <span data-ttu-id="910cb-128">SAP アダプターの RFC 変換先が存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="910cb-128">An RFC destination for the SAP adapter must exist.</span></span> <span data-ttu-id="910cb-129">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムで定義されている、RFC 変換先を使用して SAP システムからの Rfc を受信します。</span><span class="sxs-lookup"><span data-stu-id="910cb-129">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] receives RFCs from the SAP system through an RFC destination defined on the SAP system.</span></span> <span data-ttu-id="910cb-130">RFC 転送先には、SAP ゲートウェイ ホスト、SAP ゲートウェイ サービスと、SAP プログラム ID をコードで接続 URI で指定する必要がありますが含まれています。</span><span class="sxs-lookup"><span data-stu-id="910cb-130">The RFC destination contains the SAP Gateway Host, the SAP Gateway Service, and the SAP Program ID that you must specify in the connection URI in your code.</span></span> <span data-ttu-id="910cb-131">SAP に、RFC 変換先をセットアップする方法については、次を参照してください。 [Create RFC、RFC 変換先、および送信の SAP システムから RFC](creating-an-rfc-in-an-sap-system.md)です。</span><span class="sxs-lookup"><span data-stu-id="910cb-131">For information about how to setup an RFC destination on SAP, see [Create an RFC, RFC destination, and send an RFC from SAP system](creating-an-rfc-in-an-sap-system.md).</span></span>  
  
-   <span data-ttu-id="910cb-132">SAP システムで、RFC を定義する関数モジュールを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="910cb-132">You must create a function module that defines the RFC on the SAP system.</span></span> <span data-ttu-id="910cb-133">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムで、RFC 定義を使用して、RFC (デザイン時および実行時に両方) に関するメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="910cb-133">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] uses the RFC definition on the SAP system to retrieve metadata about the RFC (both at design-time and at runtime).</span></span> <span data-ttu-id="910cb-134">詳細については、次を参照してください。 [SAP システムで RFC を作成する](../../adapters-and-accelerators/adapter-sap/creating-an-rfc-in-an-sap-system.md)です。</span><span class="sxs-lookup"><span data-stu-id="910cb-134">For more information see [Creating an RFC in an SAP System](../../adapters-and-accelerators/adapter-sap/creating-an-rfc-in-an-sap-system.md).</span></span>  
  
     <span data-ttu-id="910cb-135">RFC を 2 つの整数を追加し、その結果を返しますの SAP システム上のソース コードの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="910cb-135">The following is an example of the source code on the SAP system for an RFC that adds two integers and returns their result.</span></span> <span data-ttu-id="910cb-136">コードでは、指定した宛先を介して、RFC だけ呼び出します。</span><span class="sxs-lookup"><span data-stu-id="910cb-136">The code merely calls the RFC through a specified destination.</span></span> <span data-ttu-id="910cb-137">関数の実装は、SAP アダプターのクライアント コードで行われます。</span><span class="sxs-lookup"><span data-stu-id="910cb-137">The implementation of the function is done by the SAP adapter client code.</span></span>  
  
    ```  
    FUNCTION Z_RFC_ADD.  
    *"------------------------------------------------------------------  
    *"  
    *"Local interface:  
    *"  IMPORTING  
    *"     VALUE(X) TYPE  INT4  
    *"     VALUE(Y) TYPE  INT4  
    *"     VALUE(DEST) TYPE  CHAR20 DEFAULT 'SAPADAPTER'  
    *"  EXPORTING  
    *"     VALUE(RESULT) TYPE  INT4  
    *"------------------------------------------------------------------  
    CALL FUNCTION 'Z_RFC_ADD' DESTINATION DEST  
      EXPORTING X = X  
                Y = Y  
      IMPORTING RESULT = RESULT.  
  
    ENDFUNCTION.  
    ```  
  
## <a name="sample-based-on-this-topic"></a><span data-ttu-id="910cb-138">このトピックの内容に基づくサンプル</span><span class="sxs-lookup"><span data-stu-id="910cb-138">Sample Based On This Topic</span></span>  
 <span data-ttu-id="910cb-139">サンプルは、RFCServer、このトピックの内容に基づいてが付属しても、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="910cb-139">A sample, RFCServer, based on this topic is also provided with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="910cb-140">詳細については、次を参照してください。 [SAP アダプターのサンプル](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="910cb-140">For more information, see [Samples for the SAP adapter](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md).</span></span>  
  
## <a name="generating-the-schema"></a><span data-ttu-id="910cb-141">スキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="910cb-141">Generating the Schema</span></span>  
 <span data-ttu-id="910cb-142">このトピックでは、SAP システムから受信 RFC 呼び出しを受信する方法を示すおスキーマを生成*Z_RFC_ADD* RFC です。</span><span class="sxs-lookup"><span data-stu-id="910cb-142">In this topic, to demonstrate how to receive an inbound RFC call from the SAP system, we generate the schema for *Z_RFC_ADD* RFC.</span></span> <span data-ttu-id="910cb-143">前の手順では、この RFC を作成します。</span><span class="sxs-lookup"><span data-stu-id="910cb-143">You created this RFC in the previous step.</span></span> <span data-ttu-id="910cb-144">この RFC では、入力パラメーターとして 2 つの整数値を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="910cb-144">This RFC takes two integer values as input parameters.</span></span>  
  
 <span data-ttu-id="910cb-145">参照してください[参照、検索、および get メタデータの SAP RFC 操作](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md)手順については、特定の RFC のスキーマを生成する方法です。</span><span class="sxs-lookup"><span data-stu-id="910cb-145">See [Browse, search, and get Metadata for RFC Operations in SAP](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md) for instructions on how to generate schema for a particular RFC.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="910cb-146">受信 RFC 呼び出しのスキーマを生成するために選択を確認してください**サービス (入力方向の操作)**から、**選択コントラクト型**ドロップダウン リストで、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="910cb-146">Because you are generating the schema for an inbound RFC call, make sure you select **Service (Inbound operation)** from the **Select contract type** drop-down list in the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)].</span></span>  
  
## <a name="defining-messages-and-message-types"></a><span data-ttu-id="910cb-147">メッセージとメッセージの種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="910cb-147">Defining Messages and Message Types</span></span>  
 <span data-ttu-id="910cb-148">以前に生成したスキーマには、オーケストレーション内のメッセージに対して必要な「種類」がについて説明します。</span><span class="sxs-lookup"><span data-stu-id="910cb-148">The schema that you generated earlier describes the "types" required for the messages in the orchestration.</span></span> <span data-ttu-id="910cb-149">メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。</span><span class="sxs-lookup"><span data-stu-id="910cb-149">A message is typically a variable, the type for which is defined by the corresponding schema.</span></span> <span data-ttu-id="910cb-150">BizTalk プロジェクトのオーケストレーションの種類からのメッセージに最初の手順で生成したスキーマをリンクする必要があります。</span><span class="sxs-lookup"><span data-stu-id="910cb-150">You must link the schema you generated in the first step to the messages from the Orchestration view of the BizTalk project.</span></span>  
  
 <span data-ttu-id="910cb-151">このトピックでは、2 つのメッセージを作成する必要があります: SAP システムとは、SAP システムへの応答を送信するメッセージを受信する 1 つです。</span><span class="sxs-lookup"><span data-stu-id="910cb-151">For this topic, you must create two messages—one to receive messages from the SAP system and the other to send a response to the SAP system.</span></span>  
  
 <span data-ttu-id="910cb-152">メッセージを作成し、スキーマにそれらをリンクするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="910cb-152">Perform the following steps to create messages and link them to the schema:</span></span>  
  
#### <a name="to-create-messages-and-link-to-schema"></a><span data-ttu-id="910cb-153">メッセージを作成し、スキーマにリンクするには</span><span class="sxs-lookup"><span data-stu-id="910cb-153">To create messages and link to schema</span></span>  
  
1.  <span data-ttu-id="910cb-154">新しいオーケストレーションを BizTalk プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="910cb-154">Add a new orchestration to the BizTalk project.</span></span>  
  
2.  <span data-ttu-id="910cb-155">オーケストレーションの種類、BizTalk プロジェクトを開くまだ開いていない場合。</span><span class="sxs-lookup"><span data-stu-id="910cb-155">Open the orchestration view the BizTalk project, if not already open.</span></span> <span data-ttu-id="910cb-156">をクリックして**ビュー**、 をポイント**その他のウィンドウ**、 をクリック**オーケストレーション**です。</span><span class="sxs-lookup"><span data-stu-id="910cb-156">Click **View**, point to **Other Windows**, and click **Orchestration View**.</span></span>  
  
3.  <span data-ttu-id="910cb-157">**オーケストレーション ビュー**を右クリックして**メッセージ**、クリックして**新しいメッセージ**です。</span><span class="sxs-lookup"><span data-stu-id="910cb-157">In the **Orchestration View**, right-click **Messages**, and then click **New Message**.</span></span>  
  
4.  <span data-ttu-id="910cb-158">右クリックし、新規メッセージを作成および選択**プロパティ ウィンドウ**します。</span><span class="sxs-lookup"><span data-stu-id="910cb-158">Right-click the newly create message and select **Properties Window**.</span></span>  
  
5.  <span data-ttu-id="910cb-159">**プロパティ**のウィンドウ**Message_1**次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="910cb-159">In the **Properties** pane for **Message_1**, do the following.</span></span>  
  
    |<span data-ttu-id="910cb-160">プロパティ</span><span class="sxs-lookup"><span data-stu-id="910cb-160">Use this</span></span>|<span data-ttu-id="910cb-161">目的</span><span class="sxs-lookup"><span data-stu-id="910cb-161">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="910cb-162">[Identifier]</span><span class="sxs-lookup"><span data-stu-id="910cb-162">Identifier</span></span>|<span data-ttu-id="910cb-163">型**要求**です。</span><span class="sxs-lookup"><span data-stu-id="910cb-163">Type **Request**.</span></span>|  
    |<span data-ttu-id="910cb-164">メッセージの種類</span><span class="sxs-lookup"><span data-stu-id="910cb-164">Message Type</span></span>|<span data-ttu-id="910cb-165">ドロップダウン リストから、展開**スキーマ**を選択して*RFCServer.SAPBindingSchema.Z_RFC_ADD*ここで、 *RFCServer* BizTalk プロジェクトの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="910cb-165">From the drop-down list, expand **Schemas**, and select *RFCServer.SAPBindingSchema.Z_RFC_ADD*, where *RFCServer* is the name of your BizTalk project.</span></span> <span data-ttu-id="910cb-166">*SAPBindingSchema* RFC に対して生成されたスキーマは、 *Z_RFC_ADD*です。</span><span class="sxs-lookup"><span data-stu-id="910cb-166">*SAPBindingSchema* is the schema generated for the RFC *Z_RFC_ADD*.</span></span>|  
  
6.  <span data-ttu-id="910cb-167">新しいメッセージを作成する 2 の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="910cb-167">Repeat step 2 to create a new message.</span></span> <span data-ttu-id="910cb-168">**プロパティ**新しいメッセージ用のウィンドウは、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="910cb-168">In the **Properties** pane for the new message, do the following.</span></span>  
  
    |<span data-ttu-id="910cb-169">プロパティ</span><span class="sxs-lookup"><span data-stu-id="910cb-169">Use this</span></span>|<span data-ttu-id="910cb-170">目的</span><span class="sxs-lookup"><span data-stu-id="910cb-170">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="910cb-171">[Identifier]</span><span class="sxs-lookup"><span data-stu-id="910cb-171">Identifier</span></span>|<span data-ttu-id="910cb-172">型**応答**です。</span><span class="sxs-lookup"><span data-stu-id="910cb-172">Type **Response**.</span></span>|  
    |<span data-ttu-id="910cb-173">メッセージの種類</span><span class="sxs-lookup"><span data-stu-id="910cb-173">Message Type</span></span>|<span data-ttu-id="910cb-174">ドロップダウン リストから、展開**スキーマ**を選択して*RFCServer.SAPBindingSchema.Z_RFC_ADDResponse*です。</span><span class="sxs-lookup"><span data-stu-id="910cb-174">From the drop-down list, expand **Schemas**, and select *RFCServer.SAPBindingSchema.Z_RFC_ADDResponse*.</span></span>|  
  
## <a name="setting-up-the-orchestration"></a><span data-ttu-id="910cb-175">オーケストレーションを設定します。</span><span class="sxs-lookup"><span data-stu-id="910cb-175">Setting up the Orchestration</span></span>  
 <span data-ttu-id="910cb-176">使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]SAP システムから RFC サーバー呼び出しを受信するためです。</span><span class="sxs-lookup"><span data-stu-id="910cb-176">You must create a BizTalk orchestration to use [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] for receiving RFC server calls from the SAP system.</span></span> <span data-ttu-id="910cb-177">この例では、RFC クライアントが 2 つの整数を追加する SAP システムに要求を送信するシナリオを検討してください。</span><span class="sxs-lookup"><span data-stu-id="910cb-177">For this example, consider a scenario where an RFC client sends a request to the SAP system to add two integers.</span></span> <span data-ttu-id="910cb-178">SAP システムが、入力パラメーターを使用して、要求を受け取り、によってホストされている外部の RFC サーバーに渡します、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="910cb-178">The SAP system takes the request, with the input parameters, and passes it on to the external RFC server hosted by the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="910cb-179">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]プロセス 2 つの整数を追加する要求を SAP システムから要求を受信し、応答を生成します。</span><span class="sxs-lookup"><span data-stu-id="910cb-179">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] receives the request from the SAP system, process the request to add two integers, and generates a response.</span></span> <span data-ttu-id="910cb-180">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] 、順番に渡される RFC クライアント SAP システムへの応答を渡します。</span><span class="sxs-lookup"><span data-stu-id="910cb-180">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] passes the response to the SAP system, which in turn, is passed on to the RFC client.</span></span>  
  
 <span data-ttu-id="910cb-181">これを実現するオーケストレーションの一部として、オーケストレーションを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="910cb-181">To achieve this as part of an orchestration, the orchestration must contain:</span></span>  
  
-   <span data-ttu-id="910cb-182">双方向の受信ポートを SAP システムから、RFC サーバーによって要求を受信し、応答を送信します。</span><span class="sxs-lookup"><span data-stu-id="910cb-182">A two-way receive port to receive the RFC server request from the SAP system and send the response.</span></span>  
  
-   <span data-ttu-id="910cb-183">送信図形と受信図形。</span><span class="sxs-lookup"><span data-stu-id="910cb-183">Send and Receive shapes.</span></span>  
  
-   <span data-ttu-id="910cb-184">メッセージの構築図形、RFC サーバー要求を処理する、メッセージの割り当て図形が SAP システムから送信されるとします。</span><span class="sxs-lookup"><span data-stu-id="910cb-184">Construct Message shape, and within that a Message Assignment shape, to process the RFC server request coming from the SAP system.</span></span>  
  
 <span data-ttu-id="910cb-185">RFC サーバー呼び出しのサンプルのオーケストレーションには、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="910cb-185">A sample orchestration for an RFC server call resembles the following.</span></span>  
  
 <span data-ttu-id="910cb-186">![RFC サーバー呼び出しを行うオーケストレーション](../../adapters-and-accelerators/adapter-sap/media/f5da2947-56d6-41f0-b411-c8e6eacf68cd.gif "f5da2947-56d6-41f0-b411-c8e6eacf68cd")</span><span class="sxs-lookup"><span data-stu-id="910cb-186">![Orchestration to make RFC server call](../../adapters-and-accelerators/adapter-sap/media/f5da2947-56d6-41f0-b411-c8e6eacf68cd.gif "f5da2947-56d6-41f0-b411-c8e6eacf68cd")</span></span>  
  
### <a name="adding-message-shapes"></a><span data-ttu-id="910cb-187">メッセージの構築図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="910cb-187">Adding Message Shapes</span></span>  
 <span data-ttu-id="910cb-188">メッセージの構築図形のごとに、次のプロパティを指定することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="910cb-188">Make sure you specify the following properties for each of the message shapes.</span></span> <span data-ttu-id="910cb-189">示されている名前、*図形*列が上記のオーケストレーションで表示される、メッセージの構築図形の名前を示します。</span><span class="sxs-lookup"><span data-stu-id="910cb-189">The names listed in the *Shape* column are the names of the message shapes as displayed in the preceding orchestration.</span></span>  
  
|<span data-ttu-id="910cb-190">図形</span><span class="sxs-lookup"><span data-stu-id="910cb-190">Shape</span></span>|<span data-ttu-id="910cb-191">図形の種類</span><span class="sxs-lookup"><span data-stu-id="910cb-191">Shape Type</span></span>|<span data-ttu-id="910cb-192">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="910cb-192">Properties</span></span>|  
|-----------|----------------|----------------|  
|<span data-ttu-id="910cb-193">ListenToSAP</span><span class="sxs-lookup"><span data-stu-id="910cb-193">ListenToSAP</span></span>|<span data-ttu-id="910cb-194">Receive</span><span class="sxs-lookup"><span data-stu-id="910cb-194">Receive</span></span>|<span data-ttu-id="910cb-195">-設定**名前**に*ListenToSAP*</span><span class="sxs-lookup"><span data-stu-id="910cb-195">-   Set **Name** to *ListenToSAP*</span></span><br /><span data-ttu-id="910cb-196">-設定**アクティブ**に*は True。*</span><span class="sxs-lookup"><span data-stu-id="910cb-196">-   Set **Activate** to *True*</span></span>|  
|<span data-ttu-id="910cb-197">SendResponse</span><span class="sxs-lookup"><span data-stu-id="910cb-197">SendResponse</span></span>|<span data-ttu-id="910cb-198">Send</span><span class="sxs-lookup"><span data-stu-id="910cb-198">Send</span></span>|<span data-ttu-id="910cb-199">-設定**名前**に*SendResponse*</span><span class="sxs-lookup"><span data-stu-id="910cb-199">-   Set **Name** to *SendResponse*</span></span>|  
  
### <a name="adding-construct-message-shape"></a><span data-ttu-id="910cb-200">メッセージの構築図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="910cb-200">Adding Construct Message Shape</span></span>  
 <span data-ttu-id="910cb-201">2 つの整数値を追加する受信の RFC 呼び出しを処理するには、メッセージの構築図形を追加する必要があり、そのを 2 つの間、オーケストレーションにメッセージの割り当て図形が図形を送信します。</span><span class="sxs-lookup"><span data-stu-id="910cb-201">To process the incoming RFC call to add two integer values, you must add a Construct Message shape and within that a Message Assignment shape to your orchestration, between the two send shapes.</span></span> <span data-ttu-id="910cb-202">この例では、2 つの整数を追加するメッセージの割り当て図形を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="910cb-202">For this example, the Message Assignment shape invokes to add two integers.</span></span> <span data-ttu-id="910cb-203">メッセージの割り当て図形では、SAP システムに送信される応答のアクションも設定します。</span><span class="sxs-lookup"><span data-stu-id="910cb-203">The Message Assignment shape also sets the action for the response to be sent to the SAP system.</span></span>  
  
 <span data-ttu-id="910cb-204">メッセージの構築図形、設定、**メッセージ構築**プロパティを**応答**です。</span><span class="sxs-lookup"><span data-stu-id="910cb-204">For the Construct Message shape, set the **Message Constructed** property to **Response**.</span></span>  
  
 <span data-ttu-id="910cb-205">RFC の要求を処理するコードは、BizTalk プロジェクトと同じ Visual Studio ソリューションの一部になります。</span><span class="sxs-lookup"><span data-stu-id="910cb-205">The code to process the RFC request could be part of the same Visual Studio solution as your BizTalk project.</span></span> <span data-ttu-id="910cb-206">2 つの整数を追加するためのサンプル コードは、次のように検索します。</span><span class="sxs-lookup"><span data-stu-id="910cb-206">A sample code for adding two integers looks like this.</span></span>  
  
```  
namespace RFCServerResponseCreator  
{  
    public class RFCServerResponseCreator  
    {  
        private static XmlDocument messageIn;  
        private static XmlDocument messageOut;  
        public static XmlDocument CreateRequest(int a, int b, string destination)  
        {  
            messageIn = new XmlDocument();  
            messageIn.LoadXml(  "<Z_RFC_ADD xmlns=\"http://Microsoft.LobServices.Sap/2007/03/Rfc/\">" +  
                                "<DEST>" + destination + "</DEST>" +  
                                "<X>" + a + "</X>" +  
                                "<Y>" + b + "</Y>" +   
                                "</Z_RFC_ADD>"  
                             );  
            return messageIn;  
        }  
        public static XmlDocument CreateResponse(int a, int b)  
        {  
            int c = a + b;  
            messageOut = new XmlDocument();  
            messageOut.LoadXml( "<Z_RFC_ADDResponse xmlns=\"http://Microsoft.LobServices.Sap/2007/03/Rfc/\">" +  
                                "<RESULT>" + c + "</RESULT>" +   
                                "</Z_RFC_ADDResponse>"  
                              );  
            return messageOut;  
        }  
    }  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="910cb-207">プロジェクトをビルドした後、RFCServerResponseCreator.dll はプロジェクト ディレクトリに作成されます。</span><span class="sxs-lookup"><span data-stu-id="910cb-207">After you build the project, RFCServerResponseCreator.dll will be created in the project directory.</span></span> <span data-ttu-id="910cb-208">グローバル アセンブリ キャッシュ (GAC) には、この DLL を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="910cb-208">You must add this DLL to the global assembly cache (GAC).</span></span>  
  
 <span data-ttu-id="910cb-209">メッセージの割り当て図形から次のコードを呼び出すと、SAP システムに送信される応答のアクションを設定する次の式を追加します。</span><span class="sxs-lookup"><span data-stu-id="910cb-209">Add the following expression to invoke this code from the Message Assignment shape and to set the action for the response sent to the SAP system.</span></span> <span data-ttu-id="910cb-210">式を追加するには、式エディターを開く、メッセージの割り当て図形をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="910cb-210">To add an expression, double-click the Message Assignment shape to open the Expression Editor.</span></span>  
  
```  
Response = RFCServerResponseCreator.RFCServerResponseCreator.CreateResponse(Request.X, Request.Y);  
Response(WCF.Action) = "http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_ADD/response";  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="910cb-211">応答メッセージのアクションを明示的に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="910cb-211">You must explicitly set the action on the response message.</span></span> <span data-ttu-id="910cb-212">アクションを設定しないと、Wcf-custom アダプターは要求された操作を"Response"を追加することによって、アクション メッセージでに到着します。</span><span class="sxs-lookup"><span data-stu-id="910cb-212">If you do not set the action, WCF-Custom adapter arrives at the action message by appending “Response” to the request action.</span></span> <span data-ttu-id="910cb-213">そのため、応答メッセージのアクションを`http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_ADDResponse`です。</span><span class="sxs-lookup"><span data-stu-id="910cb-213">So, the action for the response message becomes `http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_ADDResponse`.</span></span> <span data-ttu-id="910cb-214">ただし、sapBinding が必要ですが、応答アクションを追加して"/応答"例については、要求された操作に`http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_ADD/response`です。</span><span class="sxs-lookup"><span data-stu-id="910cb-214">However, the sapBinding expects the response action by appending “/response” to the request action, for example `http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_ADD/response`.</span></span>  
  
### <a name="adding-ports"></a><span data-ttu-id="910cb-215">ポートの追加</span><span class="sxs-lookup"><span data-stu-id="910cb-215">Adding Ports</span></span>  
 <span data-ttu-id="910cb-216">次のプロパティ、論理ポートを指定することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="910cb-216">Make sure you specify the following properties for the logical port.</span></span> <span data-ttu-id="910cb-217">表示される名前、*ポート*列は、ポートの名前、オーケストレーションで表示されます。</span><span class="sxs-lookup"><span data-stu-id="910cb-217">The name listed in the *Port* column is the name of the port as displayed in the orchestration.</span></span>  
  
|<span data-ttu-id="910cb-218">ポート</span><span class="sxs-lookup"><span data-stu-id="910cb-218">Port</span></span>|<span data-ttu-id="910cb-219">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="910cb-219">Properties</span></span>|  
|----------|----------------|  
|<span data-ttu-id="910cb-220">RFCServerPort</span><span class="sxs-lookup"><span data-stu-id="910cb-220">RFCServerPort</span></span>|<span data-ttu-id="910cb-221">-設定**識別子**に*RFCServerPort*</span><span class="sxs-lookup"><span data-stu-id="910cb-221">-   Set **Identifier** to *RFCServerPort*</span></span><br /><span data-ttu-id="910cb-222">-設定**型**に*RFCServerPortType*</span><span class="sxs-lookup"><span data-stu-id="910cb-222">-   Set **Type** to *RFCServerPortType*</span></span><br /><span data-ttu-id="910cb-223">-設定**通信パターン**に*要求-応答*</span><span class="sxs-lookup"><span data-stu-id="910cb-223">-   Set **Communication Pattern** to *Request-Response*</span></span><br /><span data-ttu-id="910cb-224">-設定**通信方向**に*受信送信*</span><span class="sxs-lookup"><span data-stu-id="910cb-224">-   Set **Communication Direction** to *Receive-Send*</span></span>|  
  
## <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a><span data-ttu-id="910cb-225">アクション図形のメッセージを指定し、ポートに接続</span><span class="sxs-lookup"><span data-stu-id="910cb-225">Specify Messages for Action Shapes and Connect to Ports</span></span>  
 <span data-ttu-id="910cb-226">次の表は、プロパティと、メッセージのアクション図形およびポートにリンクすることを指定するために設定するには、その値を指定します。</span><span class="sxs-lookup"><span data-stu-id="910cb-226">The following table specifies the properties and their values to be set to specify messages for action shapes and linking them to the ports.</span></span> <span data-ttu-id="910cb-227">示されている名前、*図形*列が上記のオーケストレーションで表示される、メッセージの構築図形の名前を示します。</span><span class="sxs-lookup"><span data-stu-id="910cb-227">The names listed in the *Shape* column are the names of the message shapes as displayed in the preceding orchestration.</span></span>  
  
|<span data-ttu-id="910cb-228">図形</span><span class="sxs-lookup"><span data-stu-id="910cb-228">Shape</span></span>|<span data-ttu-id="910cb-229">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="910cb-229">Properties</span></span>|  
|-----------|----------------|  
|<span data-ttu-id="910cb-230">ListenToSAP</span><span class="sxs-lookup"><span data-stu-id="910cb-230">ListenToSAP</span></span>|<span data-ttu-id="910cb-231">-設定**メッセージ**に*要求*</span><span class="sxs-lookup"><span data-stu-id="910cb-231">-   Set **Message** to *Request*</span></span><br /><span data-ttu-id="910cb-232">-設定**操作**に*RFCServerPort.Add.Request*</span><span class="sxs-lookup"><span data-stu-id="910cb-232">-   Set **Operation** to *RFCServerPort.Add.Request*</span></span>|  
|<span data-ttu-id="910cb-233">SendResponse</span><span class="sxs-lookup"><span data-stu-id="910cb-233">SendResponse</span></span>|<span data-ttu-id="910cb-234">-設定**メッセージ**に*FuncResponse*</span><span class="sxs-lookup"><span data-stu-id="910cb-234">-   Set **Message** to *FuncResponse*</span></span><br /><span data-ttu-id="910cb-235">-設定**操作**に*RFCServerPort.Add.Response*</span><span class="sxs-lookup"><span data-stu-id="910cb-235">-   Set **Operation** to *RFCServerPort.Add.Response*</span></span>|  
  
 <span data-ttu-id="910cb-236">これらのプロパティを指定した後、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。</span><span class="sxs-lookup"><span data-stu-id="910cb-236">After you have specified these properties, the message shapes and ports are connected and your orchestration is complete.</span></span>  
  
 <span data-ttu-id="910cb-237">これで、BizTalk ソリューションをビルドしして、BizTalk Server に展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="910cb-237">You must now build the BizTalk solution and then deploy it to a BizTalk Server.</span></span> <span data-ttu-id="910cb-238">詳細については、次を参照してください。[のビルドおよび実行されているオーケストレーション](../../core/building-and-running-orchestrations.md)です。</span><span class="sxs-lookup"><span data-stu-id="910cb-238">For more information, see [Building and Running Orchestrations](../../core/building-and-running-orchestrations.md).</span></span>
  
## <a name="configuring-the-biztalk-application"></a><span data-ttu-id="910cb-239">BizTalk アプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="910cb-239">Configuring the BizTalk Application</span></span>  
 <span data-ttu-id="910cb-240">以前に作成したオーケストレーションが下に表示、BizTalk プロジェクトを配置した後、**オーケストレーション**BizTalk Server 管理コンソール ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="910cb-240">After you have deployed the BizTalk project, the orchestration you created earlier is listed under the **Orchestrations** pane in the BizTalk Server Administration console.</span></span> <span data-ttu-id="910cb-241">BizTalk Server 管理コンソールを使用して、アプリケーションを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="910cb-241">You must use the BizTalk Server Administration console to configure the application.</span></span> <span data-ttu-id="910cb-242">アプリケーションの構成の詳細については、次を参照してください。[アプリケーションを構成する方法](../../core/how-to-configure-an-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="910cb-242">For more information about configuring an application, see [How to Configure an Application](../../core/how-to-configure-an-application.md).</span></span>
  
 <span data-ttu-id="910cb-243">アプリケーションの構成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="910cb-243">Configuring an application involves:</span></span>  
  
-   <span data-ttu-id="910cb-244">アプリケーションのホストを選択します。</span><span class="sxs-lookup"><span data-stu-id="910cb-244">Selecting a host for the application.</span></span>  
  
-   <span data-ttu-id="910cb-245">BizTalk Server 管理コンソールで物理ポートにオーケストレーションで作成したポートをマッピングします。</span><span class="sxs-lookup"><span data-stu-id="910cb-245">Mapping the ports that you created in your orchestration to physical ports in the BizTalk Server Administration console.</span></span> <span data-ttu-id="910cb-246">このオーケストレーションの次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="910cb-246">For this orchestration you must:</span></span>  
  
    -   <span data-ttu-id="910cb-247">WCF カスタム定義または WCF SAP 受信ポートにします。</span><span class="sxs-lookup"><span data-stu-id="910cb-247">Define a WCF-Custom or WCF-SAP receive port.</span></span> <span data-ttu-id="910cb-248">このポートは、SAP システムから受信 RFC 呼び出しを受信および SAP システムへの応答を送信します。</span><span class="sxs-lookup"><span data-stu-id="910cb-248">This port will receive inbound RFC calls from the SAP system and will send the response back to the SAP system.</span></span> <span data-ttu-id="910cb-249">ポートを作成する方法については、次を参照してください。 [SAP アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="910cb-249">For information about how to create ports, see [Manually configure a physical port binding to the SAP adapter](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md).</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="910cb-250">使用してスキーマを生成する、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。</span><span class="sxs-lookup"><span data-stu-id="910cb-250">Generating the schema using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] also creates a binding file containing information about the ports and the actions to be set for those ports.</span></span> <span data-ttu-id="910cb-251">(発信) の送信ポートを作成または受信ポート (着信)、BizTalk 管理コンソールからこのバインド ファイルをインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="910cb-251">You can import this binding file from the BizTalk Administration Console to create send ports (for outbound calls) or receive ports (for inbound calls).</span></span> <span data-ttu-id="910cb-252">詳細については、次を参照してください。 [sap ポートのバインド ファイルを使用して物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md)です。</span><span class="sxs-lookup"><span data-stu-id="910cb-252">For more information, see [Configure a physical port binding using a port binding file to SAP](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md).</span></span>
  
 <span data-ttu-id="910cb-253">RFCServerResponseCreator プロジェクトのアセンブリを BizTalk アプリケーションに追加することも必要があります。</span><span class="sxs-lookup"><span data-stu-id="910cb-253">You must also add the assembly for the RFCServerResponseCreator project to your BizTalk application.</span></span> <span data-ttu-id="910cb-254">SAP システムから受信した RFC 呼び出しを処理するには、このプロジェクトを作成したとします。</span><span class="sxs-lookup"><span data-stu-id="910cb-254">You created this project to process the RFC call received from the SAP system.</span></span> <span data-ttu-id="910cb-255">そのためには次を行います。</span><span class="sxs-lookup"><span data-stu-id="910cb-255">To do so:</span></span>  
  
1.  <span data-ttu-id="910cb-256">右クリックし、バインドをインポートする BizTalk アプリケーションの下で、BizTalk Server 管理コンソールの左側にあるコンソール ツリーで**リソース**、 をポイント**追加**をクリックし、**BizTalk アセンブリ**です。</span><span class="sxs-lookup"><span data-stu-id="910cb-256">In the console tree on the left side of the BizTalk Server Administration console, under the BizTalk application where you imported the bindings, right-click **Resources**, point to **Add**, and then click **BizTalk Assemblies**.</span></span>  
  
2.  <span data-ttu-id="910cb-257">**リソースの追加**] ダイアログ ボックス、[**追加**、し RFCServerResponseCreator.dll を含むフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="910cb-257">In the **Add Resources** dialog box, Click **Add**, and then navigate to the folder containing RFCServerResponseCreator.dll.</span></span> <span data-ttu-id="910cb-258">ファイルを選択し、をクリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="910cb-258">Select the file and then click **Open**.</span></span>  
  
3.  <span data-ttu-id="910cb-259">**リソースの追加**ダイアログ ボックスで、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="910cb-259">In the **Add Resources** dialog box, click **OK**.</span></span>  
  
## <a name="starting-the-application"></a><span data-ttu-id="910cb-260">アプリケーションの起動</span><span class="sxs-lookup"><span data-stu-id="910cb-260">Starting the Application</span></span>  
 <span data-ttu-id="910cb-261">SAP システムから受信 RFC 呼び出しを受信するための BizTalk アプリケーションを起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="910cb-261">You must start the BizTalk application for receiving inbound RFC calls from an SAP system.</span></span> <span data-ttu-id="910cb-262">BizTalk アプリケーションの起動方法の詳細については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)、および[アプリケーションを起動する方法](../../core/how-to-start-and-stop-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="910cb-262">For instructions on starting a BizTalk application, see [How to Start an Orchestration](../../core/how-to-start-an-orchestration.md), and [How to start an application](../../core/how-to-start-and-stop-a-biztalk-application.md).</span></span>
  
 <span data-ttu-id="910cb-263">この段階で確認します。</span><span class="sxs-lookup"><span data-stu-id="910cb-263">At this stage, make sure:</span></span>  
  
-   <span data-ttu-id="910cb-264">Wcf-custom または WCF SAP RFC 呼び出しを受信するポートが表示される SAP システムを実行しています。</span><span class="sxs-lookup"><span data-stu-id="910cb-264">The WCF-Custom or WCF-SAP receive port to receive RFC calls from the SAP system is running.</span></span>  
  
-   <span data-ttu-id="910cb-265">操作の BizTalk オーケストレーションが実行されています。</span><span class="sxs-lookup"><span data-stu-id="910cb-265">The BizTalk orchestration for the operation is running.</span></span>  
  
## <a name="executing-the-operation"></a><span data-ttu-id="910cb-266">操作の実行</span><span class="sxs-lookup"><span data-stu-id="910cb-266">Executing the Operation</span></span>  
 <span data-ttu-id="910cb-267">アプリケーションを実行した後は、するには、RFC を送信する必要があります、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="910cb-267">After you run the application, you must send an RFC to the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="910cb-268">SAP システムでトランザクション SE37 を実行することによって行うことができます。</span><span class="sxs-lookup"><span data-stu-id="910cb-268">You can do so by executing the transaction SE37 on the SAP system.</span></span> <span data-ttu-id="910cb-269">RFC 呼び出しの入力パラメーターも指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="910cb-269">You must also specify the input parameters for the RFC call.</span></span> <span data-ttu-id="910cb-270">アダプターは、パラメータと共に呼び出しを受信、処理、および SAP システムへの応答を送信します。</span><span class="sxs-lookup"><span data-stu-id="910cb-270">The adapter receives the call along with the parameters, processes it, and sends the response back to the SAP system.</span></span> <span data-ttu-id="910cb-271">RFC を送信してから、同じトランザクションの応答を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="910cb-271">You will be able to see the response on the same transaction from where you sent the RFC.</span></span>  
  
## <a name="possible-exceptions"></a><span data-ttu-id="910cb-272">可能性のある例外</span><span class="sxs-lookup"><span data-stu-id="910cb-272">Possible Exceptions</span></span>  
 <span data-ttu-id="910cb-273">例外については、BizTalk Server を使用して SAP システムから RFC サーバー呼び出しを受信中に発生する可能性が、次を参照してください。[例外とエラー処理、SAP アダプター](../../adapters-and-accelerators/adapter-sap/exceptions-and-error-handling-with-the-sap-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="910cb-273">For information about the exceptions you might encounter while receiving an RFC server call from an SAP system using BizTalk Server, see [Exceptions and Error Handling with the SAP adapter](../../adapters-and-accelerators/adapter-sap/exceptions-and-error-handling-with-the-sap-adapter.md).</span></span>  
  
## <a name="best-practices"></a><span data-ttu-id="910cb-274">ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="910cb-274">Best Practices</span></span>  
 <span data-ttu-id="910cb-275">展開して、BizTalk プロジェクトを構成することが後、は、バインド ファイルと呼ばれる XML ファイルに構成設定をエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="910cb-275">After you have deployed and configured the BizTalk project, you can export configuration settings to an XML file called the bindings file.</span></span> <span data-ttu-id="910cb-276">バインド ファイルを生成したできるように、受信ポートなど、同じオーケストレーションの送信ポートを作成する必要はありません、ファイルから構成設定をインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="910cb-276">Once you generate a bindings file, you can import the configuration settings from the file so that you do not need to create the send ports, receive ports, etc. for the same orchestration.</span></span> <span data-ttu-id="910cb-277">バインド ファイルの詳細については、次を参照してください。[を再利用の SAP アダプターのバインド](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md)です。</span><span class="sxs-lookup"><span data-stu-id="910cb-277">For more information about binding files, see [Reuse SAP adapter bindings](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="910cb-278">参照</span><span class="sxs-lookup"><span data-stu-id="910cb-278">See Also</span></span>  
[<span data-ttu-id="910cb-279">BizTalk アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="910cb-279">Develop BizTalk applications</span></span>](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)