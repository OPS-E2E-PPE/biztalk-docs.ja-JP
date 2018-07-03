---
title: SAP で Rfc に対する操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, operations on RFCs
- adapters, operations on IDOCs
- RFC, receiving inbound RFC calls from an SAP system
- RFCs, invoking RFCs on an SAP system
- adapters, operations on BAPIs
- RFC client
- adapters, operations on tRFCs
- RFC server
ms.assetid: ca1b7b00-a9cf-41bc-b87c-2e7ce8cff65c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8219a063fed2c940cfcd2658937fde0686542d1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015361"
---
# <a name="operations-on-rfcs-in-sap"></a><span data-ttu-id="be2dc-102">SAP で Rfc に対する操作</span><span class="sxs-lookup"><span data-stu-id="be2dc-102">Operations on RFCs in SAP</span></span>
<span data-ttu-id="be2dc-103">使用することができます、[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]クライアントが RFC と RFC サーバーの両方。</span><span class="sxs-lookup"><span data-stu-id="be2dc-103">You can use the[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] both as an RFC client and as an RFC server.</span></span> <span data-ttu-id="be2dc-104">RFC クライアントのシナリオで、アプリケーションが呼び出す Rfc SAP システムでの RFC 操作を呼び出すことによって、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="be2dc-104">In RFC client scenarios, your application invokes RFCs on the SAP system by invoking RFC operations on the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="be2dc-105">システム、SAP の RFC サーバー シナリオでの Rfc を呼び出される、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]をさらに、アプリケーションに対する操作として、RFC を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="be2dc-105">In RFC server scenarios the SAP system invokes RFCs on the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], which, in turn, invokes the RFC as an operation on your application.</span></span>  
  
## <a name="rfc-operations"></a><span data-ttu-id="be2dc-106">RFC 操作</span><span class="sxs-lookup"><span data-stu-id="be2dc-106">RFC Operations</span></span>  
 <span data-ttu-id="be2dc-107">Rfc は、名前で、RFC のメタデータ カテゴリ ノードの下での操作として表示されます、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="be2dc-107">RFCs are surfaced by name as operations under the RFC metadata category node by the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="be2dc-108">(参照したり、Rfc の検索、 **RFC**ノードを使用する場合、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="be2dc-108">(You can browse or search for RFCs under the **RFC** node when you use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].)</span></span>  
  
 <span data-ttu-id="be2dc-109">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を SAP システムからメタデータを取得できる Rfc のみを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="be2dc-109">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] can surface only those RFCs for which it can retrieve metadata from the SAP system.</span></span> <span data-ttu-id="be2dc-110">アダプターでは、RFC SDK を使用して、RFC SDK でサポートされていないデータ型を持つパラメーターを含む Rfc を surface ことはできませんので、このメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="be2dc-110">The adapter uses the RFC SDK to retrieve this metadata, so it cannot surface RFCs that contain parameters with data types that are not supported by the RFC SDK.</span></span> <span data-ttu-id="be2dc-111">たとえば、アダプターでは、Rfc ITAB II 型の構造体またはテーブルが含まれているを画面ことはできません。</span><span class="sxs-lookup"><span data-stu-id="be2dc-111">For example, the adapter cannot surface RFCs that contain ITAB II type structures or tables.</span></span>  
  
 <span data-ttu-id="be2dc-112">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Rfc に対する次のサポートします。</span><span class="sxs-lookup"><span data-stu-id="be2dc-112">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports the following on RFCs:</span></span>  
  
- <span data-ttu-id="be2dc-113">インポート パラメーター</span><span class="sxs-lookup"><span data-stu-id="be2dc-113">IMPORT parameters</span></span>  
  
- <span data-ttu-id="be2dc-114">パラメーターをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="be2dc-114">EXPORT parameters</span></span>  
  
- <span data-ttu-id="be2dc-115">変化するパラメーター</span><span class="sxs-lookup"><span data-stu-id="be2dc-115">CHANGING parameters</span></span>  
  
  <span data-ttu-id="be2dc-116">メッセージの構造と、アダプターによって Rfc に使用される SOAP アクションの詳細については、次を参照してください。 [RFC 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)します。</span><span class="sxs-lookup"><span data-stu-id="be2dc-116">For more information about the message structures and SOAP actions used for RFCs by the adapter, see [Message Schemas for RFC Operations](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md).</span></span>  
  
## <a name="invoking-rfcs-on-an-sap-system"></a><span data-ttu-id="be2dc-117">SAP システムでの Rfc を呼び出す</span><span class="sxs-lookup"><span data-stu-id="be2dc-117">Invoking RFCs on an SAP System</span></span>  
 <span data-ttu-id="be2dc-118">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムで、RFC の名前を取得する個々 の操作として Rfc 明らかになります。</span><span class="sxs-lookup"><span data-stu-id="be2dc-118">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces RFCs as individual operations that take the name of the RFC on the SAP system.</span></span> <span data-ttu-id="be2dc-119">SAP システムの RFC を呼び出すには、するには、アダプターで適切に名前付きの RFC 操作を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="be2dc-119">To invoke an RFC on the SAP system, you invoke the appropriately named RFC operation on the adapter.</span></span>  
  
 <span data-ttu-id="be2dc-120">詳細については。</span><span class="sxs-lookup"><span data-stu-id="be2dc-120">For more information about:</span></span>  
  
-   <span data-ttu-id="be2dc-121">BizTalk Server を使用して、RFC の呼び出しを参照してください[を使用して BizTalk Server が呼び出す Rfc](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="be2dc-121">Invoking an RFC using BizTalk Server, see [Invoke RFCs by Using BizTalk Server](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="be2dc-122">WCF サービス モデルを使用して、RFC の呼び出しを参照してください[WCF サービス モデルを使用して SAP で Rfc を呼び出す](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-the-wcf-service-model.md)します。</span><span class="sxs-lookup"><span data-stu-id="be2dc-122">Invoking an RFC using the WCF service model, see [Invoke RFCs in SAP using the WCF Service Model](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-the-wcf-service-model.md).</span></span>  
  
-   <span data-ttu-id="be2dc-123">WCF チャネル モデルを使用して、RFC の呼び出しを参照してください[WCF チャネル モデルを使用して、SAP システムに対する操作を呼び出す](../../adapters-and-accelerators/adapter-sap/invoke-operations-on-the-sap-system-using-the-wcf-channel-model.md)します。</span><span class="sxs-lookup"><span data-stu-id="be2dc-123">Invoking an RFC using the WCF channel model, see [Invoke Operations on the SAP System by Using the WCF Channel Model](../../adapters-and-accelerators/adapter-sap/invoke-operations-on-the-sap-system-using-the-wcf-channel-model.md).</span></span>  
  
## <a name="receiving-inbound-rfc-calls-from-an-sap-system"></a><span data-ttu-id="be2dc-124">SAP システムからの受信側の受信 RFC 呼び出し</span><span class="sxs-lookup"><span data-stu-id="be2dc-124">Receiving Inbound RFC Calls from an SAP System</span></span>  
 <span data-ttu-id="be2dc-125">For SAP をクライアントとして動作させ、外部の RFC サーバー上のモジュールの関数を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="be2dc-125">It is possible for SAP to act as a client and invoke function modules on an external RFC server.</span></span> <span data-ttu-id="be2dc-126">この機能が有効にします。</span><span class="sxs-lookup"><span data-stu-id="be2dc-126">This functionality enables:</span></span>  
  
- <span data-ttu-id="be2dc-127">外部のシステム通知の Rfc を呼び出すことで SAP を継続的にポーリングする必要はなく、外部システムにプッシュ通知を SAP します。</span><span class="sxs-lookup"><span data-stu-id="be2dc-127">SAP to push notifications to external systems without the external systems having to continuously poll SAP for notifications by calling RFCs.</span></span>  
  
- <span data-ttu-id="be2dc-128">SAP システムの外部のビジネス ロジックの実装です。</span><span class="sxs-lookup"><span data-stu-id="be2dc-128">The implementation of business logic outside the SAP system.</span></span> <span data-ttu-id="be2dc-129">SAP システムは、RFC サーバーで、外部プログラムを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="be2dc-129">The SAP system can then call the external program on the RFC server.</span></span>  
  
  <span data-ttu-id="be2dc-130">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムからこのような受信 RFC 呼び出しを受信する RFC サーバーとして機能できます。</span><span class="sxs-lookup"><span data-stu-id="be2dc-130">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] can act as an RFC server to receive such inbound RFC calls from the SAP system.</span></span> <span data-ttu-id="be2dc-131">Sap で RFC 呼び出しを受信すると、アプリケーションでは、その RFC 操作を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="be2dc-131">When the adapter receives an RFC call from SAP, it invokes that RFC operation on your application.</span></span>  
  
  <span data-ttu-id="be2dc-132">アダプターが RFC サーバーとして実行するには。</span><span class="sxs-lookup"><span data-stu-id="be2dc-132">For the adapter to perform as an RFC server:</span></span>  
  
- <span data-ttu-id="be2dc-133">SAP システムでは、RFC を宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="be2dc-133">The RFC must be declared on the SAP system.</span></span> <span data-ttu-id="be2dc-134">これはので、アダプターは、SAP システムから RFC を記述するメタデータを取得できます。</span><span class="sxs-lookup"><span data-stu-id="be2dc-134">This is so the adapter can retrieve metadata that describes the RFC from the SAP system.</span></span> <span data-ttu-id="be2dc-135">RFC は、アプリケーションで実際に実装されます。</span><span class="sxs-lookup"><span data-stu-id="be2dc-135">The RFC is actually implemented in your application.</span></span>  
  
- <span data-ttu-id="be2dc-136">アダプターは、SAP ゲートウェイ RFC 転送先に登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="be2dc-136">The adapter must register with an RFC destination on an SAP gateway.</span></span> <span data-ttu-id="be2dc-137">登録は、プログラム ID と呼ばれる論理名をに基づいてください。</span><span class="sxs-lookup"><span data-stu-id="be2dc-137">The registration is based on a logical name called a program ID.</span></span> <span data-ttu-id="be2dc-138">接続を SAP ゲートウェイ、プログラム ID を指定し、この登録用のサーバー、SAP の URI でパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="be2dc-138">You supply parameters in the connection URI to specify the PROGRAM ID, SAP gateway, and SAP server for this registration.</span></span>  
  
  <span data-ttu-id="be2dc-139">次の例では、プログラム ID、MYDEST を通じて RFC の呼び出しに必要な ABAP コードを示します。</span><span class="sxs-lookup"><span data-stu-id="be2dc-139">The following example shows the ABAP code required to invoke an RFC through the PROGRAM ID, MYDEST.</span></span>  
  
```  
CALL FUNCTION ‘ABC’ DESTINATION ‘MYDEST’  
```  
  
 <span data-ttu-id="be2dc-140">詳細については。</span><span class="sxs-lookup"><span data-stu-id="be2dc-140">For more information about:</span></span>  
  
-   <span data-ttu-id="be2dc-141">BizTalk Server を使用して RFC サーバー呼び出しの受信を参照してください[受信 RFC の呼び出しを使用して BizTalk Server で受信](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-from-sap-using-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="be2dc-141">Receiving an RFC server call using BizTalk Server, see [Receive Inbound RFC Calls by Using BizTalk Server](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-from-sap-using-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="be2dc-142">WCF サービス モデルを使用して RFC サーバー呼び出しの受信を参照してください[WCF サービス モデルを使用して SAP で受信 RFC 呼び出しの受信](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-in-sap-using-the-wcf-service-model.md)します。</span><span class="sxs-lookup"><span data-stu-id="be2dc-142">Receiving an RFC server call using the WCF service model, see [Receive  Inbound RFC Calls in SAP using the WCF Service Model](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-in-sap-using-the-wcf-service-model.md).</span></span>  
  
-   <span data-ttu-id="be2dc-143">WCF チャネル モデルを使用して RFC サーバー呼び出しの受信を参照してください[WCF チャネル モデルを使用して、SAP システムからの受信操作の受信](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md)します。</span><span class="sxs-lookup"><span data-stu-id="be2dc-143">Receiving an RFC server call using the WCF channel model, see [Receive Inbound Operations from the SAP System by Using the WCF Channel Model](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md).</span></span>  
  
## <a name="special-rfc-operations"></a><span data-ttu-id="be2dc-144">RFC の特別な操作</span><span class="sxs-lookup"><span data-stu-id="be2dc-144">Special RFC Operations</span></span>  
 <span data-ttu-id="be2dc-145">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムで特定の特別な RFC 操作も実行できます。</span><span class="sxs-lookup"><span data-stu-id="be2dc-145">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] can also perform certain special RFC operations on the SAP system.</span></span> <span data-ttu-id="be2dc-146">このような 1 つの操作では、RfcGetAttributes です。</span><span class="sxs-lookup"><span data-stu-id="be2dc-146">One such operation is RfcGetAttributes.</span></span>  
  
- <span data-ttu-id="be2dc-147">**RfcGetAttributes**します。</span><span class="sxs-lookup"><span data-stu-id="be2dc-147">**RfcGetAttributes**.</span></span> <span data-ttu-id="be2dc-148">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]この操作を使用して、システム ID、パートナーのコード ページ、および言語などの RFC 接続パラメーターに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="be2dc-148">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] uses this operation to get information about the RFC connection parameters such as system ID, partner code page, and language.</span></span> <span data-ttu-id="be2dc-149">この操作で使用可能な**RFC**ノードを使用する場合、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]と[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="be2dc-149">This operation is available under the **RFC** node when using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span>  
  
  <span data-ttu-id="be2dc-150">メッセージの構造と SAP システムで RfcGetAttributes 操作を呼び出すための SOAP アクションの詳細については、次を参照してください。 [RFC 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)します。</span><span class="sxs-lookup"><span data-stu-id="be2dc-150">For more information about message structure and SOAP action for invoking an RfcGetAttributes operation on the SAP system, see [Message Schemas for RFC Operations](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be2dc-151">参照</span><span class="sxs-lookup"><span data-stu-id="be2dc-151">See Also</span></span>  
 <span data-ttu-id="be2dc-152">[どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="be2dc-152">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>