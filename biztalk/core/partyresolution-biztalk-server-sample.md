---
title: "PartyResolution (BizTalk Server サンプル) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, parties
- orchestrations, examples
- parties, examples
- parties, orchestrations
- examples, routing
- orchestrations, parties
- examples, orchestrations
- examples, messages
- routing, messages
- messages, routing
ms.assetid: 220e6bc5-6f04-4f37-b0d0-f11c2cc14422
caps.latest.revision: "33"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be8d7e33cefd2272490bd2f01243ff03b0e7009a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="partyresolution-biztalk-server-sample"></a><span data-ttu-id="6d676-102">PartyResolution (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="6d676-102">PartyResolution (BizTalk Server Sample)</span></span>
<span data-ttu-id="6d676-103">PartyResolution サンプルは、パーティの解決で BizTalk オーケストレーションを使用して、2 つのうちいずれかの受信側にメッセージをルーティングする方法を示すものです。</span><span class="sxs-lookup"><span data-stu-id="6d676-103">The PartyResolution sample demonstrates how to use BizTalk orchestrations with party resolution to route messages to one of two possible recipients.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="6d676-104">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="6d676-104">What This Sample Does</span></span>  
 <span data-ttu-id="6d676-105">このサンプルでは、次に示す複数のオーケストレーションがそれぞれのロールを実行します。</span><span class="sxs-lookup"><span data-stu-id="6d676-105">This sample runs multiple orchestrations that demonstrate the following different roles:</span></span>  
  
-   <span data-ttu-id="6d676-106">購入側のオーケストレーション : 注文書 (PO) メッセージの処理を開始するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="6d676-106">Buyer orchestration, used to initiate the purchase order (PO) message processing.</span></span>  
  
-   <span data-ttu-id="6d676-107">供給業者側のオーケストレーション : 受信パーティおよび送信パーティの両方の解決を実行します。</span><span class="sxs-lookup"><span data-stu-id="6d676-107">Supplier orchestration, which demonstrates both inbound and outbound party resolution.</span></span>  
  
-   <span data-ttu-id="6d676-108">ShipmentAgency1 および ShipmentAgency2 オーケストレーション : PO の出荷先に基づいて供給業者側のオーケストレーションに応答します。</span><span class="sxs-lookup"><span data-stu-id="6d676-108">ShipmentAgency1 and ShipmentAgency2 orchestrations, which respond to the supplier orchestration based on the shipment destination in the PO.</span></span>  
  
## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="6d676-109">このサンプルのデザイン方法とその理由</span><span class="sxs-lookup"><span data-stu-id="6d676-109">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="6d676-110">パーティの解決とは、メッセージの送信元 (パーティ) を特定するプロセスのことです。</span><span class="sxs-lookup"><span data-stu-id="6d676-110">Party resolution refers to the process of determining who (that is, what party) sends a message.</span></span> <span data-ttu-id="6d676-111">たとえば、既存のパーティのみがメッセージを送信できるようにする場合などに使用します。</span><span class="sxs-lookup"><span data-stu-id="6d676-111">For example, you may want to enable only known parties to send a message.</span></span> <span data-ttu-id="6d676-112">また、送信パーティの解決とは、メッセージの送信先のパーティを特定するプロセスのことです。</span><span class="sxs-lookup"><span data-stu-id="6d676-112">Outbound party resolution is the process by which you determine which parties should be sent a message.</span></span>  
  
 <span data-ttu-id="6d676-113">このサンプルでは、パーティの解決方法の他に、ロールの実装方法と使用方法も示しています。</span><span class="sxs-lookup"><span data-stu-id="6d676-113">In addition to party resolution, this sample demonstrates how to implement and use roles.</span></span> <span data-ttu-id="6d676-114">たとえば、製品の出荷を処理するには、出荷業者に製品の出荷を指示するドキュメントを送信するための送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="6d676-114">For example, to process the shipment of your product, you create a send port to which you send a document instructing a shipper to ship your product.</span></span> <span data-ttu-id="6d676-115">出荷業者が複数ある場合は、出荷業者の URL だけが異なる複数の送信ポートを作成するのではなく、オーケストレーション内に出荷業者のロールを作成でき、</span><span class="sxs-lookup"><span data-stu-id="6d676-115">If you have multiple shippers to choose from, you can create a shipper role in your orchestration rather than create multiple send ports whose only difference is the shipper's URL.</span></span> <span data-ttu-id="6d676-116">製品の出荷を出荷業者ロールに関連するメッセージを送信することができます。</span><span class="sxs-lookup"><span data-stu-id="6d676-116">You can then send messages relating to product shipment to the shipper role.</span></span> <span data-ttu-id="6d676-117">次にパーティを作成し、送信ポートを各パーティとパーティの証明書に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="6d676-117">You create parties and associate a send port to each party and party certificate.</span></span> <span data-ttu-id="6d676-118">最後に、各パーティを出荷業者のロールに参加させて有効にします。</span><span class="sxs-lookup"><span data-stu-id="6d676-118">Finally, you enlist each party to the shipper role to enable it.</span></span> <span data-ttu-id="6d676-119">オーケストレーションではさらに、メッセージの送信先となる出荷業者を動的に指定できます。</span><span class="sxs-lookup"><span data-stu-id="6d676-119">In the orchestration, you can then dynamically specify which shipper you are sending the message to.</span></span>  
  
 <span data-ttu-id="6d676-120">このサンプルでは、関連付けを使用して受信メッセージを正しいオーケストレーション インスタンスと組み合わせる方法も示します。</span><span class="sxs-lookup"><span data-stu-id="6d676-120">This sample also demonstrates how to use correlation to match the incoming message to the right orchestration instance.</span></span>  
  
-   <span data-ttu-id="6d676-121">購入者、供給業者、および出荷業者のビジネス プロセス フローは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6d676-121">The business process flows for the buyer, supplier, and shipping agencies are as follows:</span></span>  
  
-   <span data-ttu-id="6d676-122">購入者のビジネス プロセス フロー</span><span class="sxs-lookup"><span data-stu-id="6d676-122">Buyer business process flow:</span></span>  
  
    1.  <span data-ttu-id="6d676-123">.xml ファイルの PO メッセージを社内の部署から受信します。</span><span class="sxs-lookup"><span data-stu-id="6d676-123">Receive PO message from internal department as an .xml file.</span></span>  
  
    2.  <span data-ttu-id="6d676-124">PO メッセージを供給業者に送信します。</span><span class="sxs-lookup"><span data-stu-id="6d676-124">Send PO message to supplier.</span></span>  
  
-   <span data-ttu-id="6d676-125">供給業者のビジネス プロセス フロー</span><span class="sxs-lookup"><span data-stu-id="6d676-125">Supplier business process flow:</span></span>  
  
    1.  <span data-ttu-id="6d676-126">パーティを解決し (受信パーティの解決)、署名証明書に基づいて送信元のパーティを更新します。</span><span class="sxs-lookup"><span data-stu-id="6d676-126">Resolve the party (inbound party resolution) to update the source party based on signature certificate.</span></span>  
  
    2.  <span data-ttu-id="6d676-127">購入者からアクティベーション メッセージ (PO) を受信します。</span><span class="sxs-lookup"><span data-stu-id="6d676-127">Receive an activation message (PO) from buyer.</span></span>  
  
    3.  <span data-ttu-id="6d676-128">PO の確認メッセージを購入者に送信します。</span><span class="sxs-lookup"><span data-stu-id="6d676-128">Send a PO Acknowledgement message to buyer.</span></span>  
  
    4.  <span data-ttu-id="6d676-129">配送する国/地域を確認します。</span><span class="sxs-lookup"><span data-stu-id="6d676-129">Verify the delivery country/region.</span></span>  
  
    5.  <span data-ttu-id="6d676-130">送信パーティを解決し、使用する出荷業者を決定します。</span><span class="sxs-lookup"><span data-stu-id="6d676-130">Resolve the outbound party to find which shipping agency to use.</span></span> <span data-ttu-id="6d676-131">国/地域が米国の場合、出荷業者は ShipmentAgency2 です。</span><span class="sxs-lookup"><span data-stu-id="6d676-131">If the country/region is U.S., the shipping agency is ShipmentAgency2.</span></span> <span data-ttu-id="6d676-132">国/地域がカナダの場合、出荷業者は ShipmentAgency1 です。</span><span class="sxs-lookup"><span data-stu-id="6d676-132">If the country/region is Canada, the shipping agency is ShipmentAgency1.</span></span>  
  
    6.  <span data-ttu-id="6d676-133">出荷指令の要求メッセージを対象の出荷業者に送信します。</span><span class="sxs-lookup"><span data-stu-id="6d676-133">Send a Shipment Order Request message to the appropriate shipping agency.</span></span>  
  
    7.  <span data-ttu-id="6d676-134">対象の出荷業者から出荷指令の確認メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="6d676-134">Receive the Shipment Order Acknowledgement message from the appropriate shipping agency.</span></span>  
  
    8.  <span data-ttu-id="6d676-135">出荷通知メッセージを対象の出荷業者に送信します。</span><span class="sxs-lookup"><span data-stu-id="6d676-135">Send a Shipment Advice message to the appropriate shipping agency.</span></span>  
  
    9. <span data-ttu-id="6d676-136">対象の出荷業者から出荷通知の確認メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="6d676-136">Receive a Shipment Advice Acknowledgement message from the appropriate shipping agency.</span></span>  
  
    10. <span data-ttu-id="6d676-137">最終の PO 配信確認メッセージを購入者に送信します。</span><span class="sxs-lookup"><span data-stu-id="6d676-137">Send a final PO Delivery Receipt message to the buyer.</span></span>  
  
-   <span data-ttu-id="6d676-138">出荷業者のビジネス プロセス フロー (ShipmentAgency1 および ShipmentAgency2 両方の出荷業者に共通)</span><span class="sxs-lookup"><span data-stu-id="6d676-138">Shipping agency business process flow (same for both shipping agencies):</span></span>  
  
    1.  <span data-ttu-id="6d676-139">供給業者から出荷指令の要求メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="6d676-139">Receive the Shipment Order Request message from the supplier.</span></span>  
  
    2.  <span data-ttu-id="6d676-140">出荷指令の要求メッセージに対する確認メッセージを生成して送信します。</span><span class="sxs-lookup"><span data-stu-id="6d676-140">Generate and send an Acknowledgement message for the Shipment Order Request message.</span></span>  
  
    3.  <span data-ttu-id="6d676-141">供給業者から出荷通知メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="6d676-141">Receive a Shipment Advice message from the supplier.</span></span>  
  
    4.  <span data-ttu-id="6d676-142">出荷通知メッセージに対する確認メッセージを生成して送信します。</span><span class="sxs-lookup"><span data-stu-id="6d676-142">Generate and send an Acknowledgement message for the Shipment Advice message.</span></span>  
  
 <span data-ttu-id="6d676-143">このサンプルの処理は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6d676-143">The following statements explain how this sample is designed:</span></span>  
  
-   <span data-ttu-id="6d676-144">BuyerProcess.odx オーケストレーションで、メッセージを受信した後、カスタム パイプライン MimePartyResSendPipeline を使用してメッセージをエンコードし供給業者に送信します。</span><span class="sxs-lookup"><span data-stu-id="6d676-144">The BuyerProcess.odx orchestration receives a message and uses the custom pipeline MimePartyResSendPipeline to encode the message and send it to the supplier.</span></span> <span data-ttu-id="6d676-145">この処理を行うには、パイプライン デザイナーで、カスタムの送信パイプラインをビルドし展開します。</span><span class="sxs-lookup"><span data-stu-id="6d676-145">This is done by using Pipeline Designer to build and deploy a custom send pipeline.</span></span> <span data-ttu-id="6d676-146">メッセージは供給業者への送信前に購入者の秘密キーでデジタル署名されます。この秘密キーは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールの [BizTalk グループのプロパティ] で指定します。</span><span class="sxs-lookup"><span data-stu-id="6d676-146">Before sending the message to the supplier, the message is digitally signed with buyer's private key, which is specified in BizTalk Group Properties in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
-   <span data-ttu-id="6d676-147">SupplierProcess.odx オーケストレーションで、MIME/SMIME デコーダー コンポーネントを含むカスタム パイプライン MimePartyResReceivePipeline を使用してメッセージをデコードし、受信パーティを解決します。このとき、購入者の公開キーを使用して購入者の ID を解決します。</span><span class="sxs-lookup"><span data-stu-id="6d676-147">The SupplierProcess.odx orchestration uses the custom pipeline MimePartyResReceivePipeline, which includes a MIME/SMIME decoder component, to decode the message and perform inbound party resolution by using the buyer's public key to resolve and validate the buyer's identity.</span></span> <span data-ttu-id="6d676-148">この処理を行うには、カスタム受信パイプラインをビルドし展開します。</span><span class="sxs-lookup"><span data-stu-id="6d676-148">This is done by building and deploying a custom receive pipeline.</span></span>  
  
-   <span data-ttu-id="6d676-149">供給業者側のオーケストレーションで、POCorrelationSets を開始します。POCorrelationSets は昇格されたプロパティ PONo に基づくよう定義されています。</span><span class="sxs-lookup"><span data-stu-id="6d676-149">The supplier orchestration then initiates the POCorrelationSets which is defined to base on a promoted property - PONo.</span></span> <span data-ttu-id="6d676-150">PONo は、後の段階で、このオーケストレーション インスタンスに対する受信メッセージと送信メッセージを照合する際に使用されます。この照合が必要な理由は、オーケストレーション全体で複数の送信アクションと受信アクションが行われるためです。</span><span class="sxs-lookup"><span data-stu-id="6d676-150">The PONo is used to match the inbound and outbound messages to this orchestration instance in the later stage, because there are multiple send and receive actions throughout the entire orchestration.</span></span>  
  
-   <span data-ttu-id="6d676-151">供給業者側のオーケストレーションで、受信パーティおよび送信パーティの解決を行うためのロール リンクを実装します。</span><span class="sxs-lookup"><span data-stu-id="6d676-151">The supplier orchestration implements role links to deal with inbound and outbound party resolution.</span></span> <span data-ttu-id="6d676-152">供給業者のオーケストレーションでは、次の 2 種類のロール リンクを使用します。</span><span class="sxs-lookup"><span data-stu-id="6d676-152">The supplier orchestration uses two role link types:</span></span>  
  
    -   <span data-ttu-id="6d676-153">Buyer_Supplier ロール リンク</span><span class="sxs-lookup"><span data-stu-id="6d676-153">Buyer_Supplier role link type</span></span>  
  
    -   <span data-ttu-id="6d676-154">Supplier_Shipment ロール リンク</span><span class="sxs-lookup"><span data-stu-id="6d676-154">Supplier_Shipment role link type</span></span>  
  
-   <span data-ttu-id="6d676-155">Buyer_supplier**ロール リンク**図形は、供給業者はプロバイダー ロールと、購入者はコンシューマー ロール供給業者は購入者から最初のメッセージを受信するためです。</span><span class="sxs-lookup"><span data-stu-id="6d676-155">In the Buyer_Supplier **Role Link** shape, the supplier is in the Provider role and the buyer is in the Consumer role because the supplier receives the first message from the buyer.</span></span> <span data-ttu-id="6d676-156">供給業者側のオーケストレーションで購入者のロールに確認メッセージを送信するときには、購入者に関連付けられている送信ポートを使用します。これによって、購入者にメッセージが送信されます。</span><span class="sxs-lookup"><span data-stu-id="6d676-156">When the supplier orchestration sends the acknowledgment to the buyer role, there is a send port associated with the buyer, and the message is sent to the buyer through the specified send port.</span></span> <span data-ttu-id="6d676-157">送信ポートを見つけるを右クリックして**BuyerAgency**で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールとクリック**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="6d676-157">To find the send port, right-click **BuyerAgency** in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console and then click **Properties**.</span></span> <span data-ttu-id="6d676-158">送信ポートが表示されます**送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="6d676-158">The send port is displayed under **Send Ports**.</span></span>  
  
-   <span data-ttu-id="6d676-159">オーケストレーションで、次のコードを使用してパートナー情報を返し、CheckPartyName という名前の外部アセンブリを呼び出して、XML ファイルをフォルダーに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="6d676-159">The orchestration then uses the following expression to return the partner information, and writes an XML file to a folder through a call to an external assembly named CheckPartyName.</span></span>  
  
    ```  
    Buyer_Supplier(Microsoft.XLANGs.BaseTypes.SourceParty)  
    ```  
  
-   <span data-ttu-id="6d676-160">Supplier_shipment**ロール リンク**図形、出荷業者のロールには 2 つの操作、業者から、送信先パーティに応じて適切な出荷業者にメッセージを送信に使用される送信ポートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6d676-160">In the Supplier_Shipment **Role Link** shape, the Shipment role contains a send port with two operations that are used to send the message from the supplier to the appropriate shipping agency depending on the destination party.</span></span> <span data-ttu-id="6d676-161">また、供給業者のロールには受信ポートと 2 つの操作が含まれます。これらの操作は、出荷業者から応答を受信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="6d676-161">The Supplier role contains a receive port with two operations that are used to receive the response from the shipping agency.</span></span> <span data-ttu-id="6d676-162">これらのメッセージの送信および受信時には PONo に基づく関連付けが使用されます。</span><span class="sxs-lookup"><span data-stu-id="6d676-162">The correlation is used when sending and receiving these messages, and it is based on the PONo.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6d676-163">供給業者側のオーケストレーションをバインドするとき、バインドする必要があるのは、1 つの送信ポートと 2 つの受信ポートだけです。</span><span class="sxs-lookup"><span data-stu-id="6d676-163">When you bind the supplier orchestration, you will find that only one send port and two receive ports need to be bound.</span></span> <span data-ttu-id="6d676-164">送信先パーティに対する送信ポートは、既にパーティにバインドされています。</span><span class="sxs-lookup"><span data-stu-id="6d676-164">This is because the send ports to the destination parties are already bound with the parties.</span></span> <span data-ttu-id="6d676-165">2 つの受信操作を含むオーケストレーションの受信ポートのいずれかのさらに、3 つが表示された場合でもは**受信**図形、それらの 2 つだけ必要がありますをバインドします。</span><span class="sxs-lookup"><span data-stu-id="6d676-165">Moreover, one of the receive ports in the orchestration contains two receive operations, so even if you see three **Receive** shapes, only two of them need to be bound.</span></span>  
  
-   <span data-ttu-id="6d676-166">供給業者側のオーケストレーションでは、次のコードの 1 行目で QueryShipmentCatalogComponent という名前の外部アセンブリを呼び出し、出荷業者を取得します。</span><span class="sxs-lookup"><span data-stu-id="6d676-166">The supplier orchestration uses the first line in the following code to get the shipment agency by calling an external assembly named QueryShipmentCatalogComponent.</span></span> <span data-ttu-id="6d676-167">2 行目では、出荷業者のロールの送信先パーティを設定します。</span><span class="sxs-lookup"><span data-stu-id="6d676-167">It then uses the second line to set the destination party for the shipment role.</span></span>  
  
    ```  
    strShipmentName= objQueryShipmentCatalog.GetShipmentDetails(POMessage.MessagePart_1.POHeader.Address.Country);  
    Supplier_Shipment(Microsoft.XLANGs.BaseTypes.DestinationParty) = new Microsoft.XLANGs.BaseTypes.Party(strShipmentName,"OrganizationName");  
    ```  
  
-   <span data-ttu-id="6d676-168">Shipper1Process.odx および Shipper2Process.odx は、SupplierProcess.odx から出荷指令と出荷通知を受信し、SupplierProcess.odx に応答を返すようビルドされています。</span><span class="sxs-lookup"><span data-stu-id="6d676-168">Shipper1Process.odx and Shipper2Process.odx are built to receive the shipping order and the shipping advice from SupplierProcess.odx and to send the response back to SupplierProcess.odx.</span></span> <span data-ttu-id="6d676-169">両方の出荷業者側のオーケストレーションで、昇格させたプロパティ PONo に基づく種類の関連付けが使用されます。</span><span class="sxs-lookup"><span data-stu-id="6d676-169">In both of the shipper orchestrations, correlation is used, and the correlation type is based on the promoted property PONo.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="6d676-170">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="6d676-170">Where to Find This Sample</span></span>  
 <span data-ttu-id="6d676-171">*\<パスのサンプル\>*\Orchestrations\PartyResolution\\</span><span class="sxs-lookup"><span data-stu-id="6d676-171">*\<Samples Path\>*\Orchestrations\PartyResolution\\</span></span>  
  
 <span data-ttu-id="6d676-172">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="6d676-172">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="6d676-173">ファイル</span><span class="sxs-lookup"><span data-stu-id="6d676-173">File(s)</span></span>|<span data-ttu-id="6d676-174">Description</span><span class="sxs-lookup"><span data-stu-id="6d676-174">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6d676-175">BuyerBinding.xml、ShippingAgency1Binding.xml、ShippingAgency2Binding.xml、SupplierBinding.xml</span><span class="sxs-lookup"><span data-stu-id="6d676-175">BuyerBinding.xml, ShippingAgency1Binding.xml, ShippingAgency2Binding.xml, SupplierBinding.xml</span></span>|<span data-ttu-id="6d676-176">ポートのバインドなど、自動化されたセットアップに使用されます。</span><span class="sxs-lookup"><span data-stu-id="6d676-176">Used for automated setup such as port binding.</span></span>|  
|<span data-ttu-id="6d676-177">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="6d676-177">Cleanup.bat</span></span>|<span data-ttu-id="6d676-178">アセンブリの展開を解除し、グローバル アセンブリ キャッシュからアセンブリを削除するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="6d676-178">Used to undeploy assemblies and remove them from the global assembly cache.</span></span> <span data-ttu-id="6d676-179">送信ポートと受信ポートが削除されます。</span><span class="sxs-lookup"><span data-stu-id="6d676-179">Removes send and receive ports.</span></span> <span data-ttu-id="6d676-180">必要に応じて、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。</span><span class="sxs-lookup"><span data-stu-id="6d676-180">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="6d676-181">PartyResolution.sln</span><span class="sxs-lookup"><span data-stu-id="6d676-181">PartyResolution.sln</span></span>|<span data-ttu-id="6d676-182">各種サブフォルダー内にあるすべてのプロジェクトが格納されているソリューション ファイルです。</span><span class="sxs-lookup"><span data-stu-id="6d676-182">Solution file that contains all of the projects in the various subfolders.</span></span>|  
|<span data-ttu-id="6d676-183">PurchaseOrder.xml</span><span class="sxs-lookup"><span data-stu-id="6d676-183">PurchaseOrder.xml</span></span>|<span data-ttu-id="6d676-184">サンプルの入力 PO です。</span><span class="sxs-lookup"><span data-stu-id="6d676-184">Sample input PO.</span></span>|  
|<span data-ttu-id="6d676-185">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="6d676-185">Setup.bat</span></span>|<span data-ttu-id="6d676-186">このサンプルの各部分をビルドおよび初期化するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="6d676-186">Used to build and initialize portions of this sample.</span></span>|  
|<span data-ttu-id="6d676-187">\Buyer フォルダーには、次のファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6d676-187">In the \Buyer folder:</span></span><br /><br /> <span data-ttu-id="6d676-188">Buyer.btproj、BuyerProcess.odx</span><span class="sxs-lookup"><span data-stu-id="6d676-188">Buyer.btproj, BuyerProcess.odx</span></span>|<span data-ttu-id="6d676-189">このサンプルの購入者を実装するために使用される、BizTalk プロジェクトおよびオーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="6d676-189">BizTalk project and orchestration used to implement the buyer in this sample.</span></span>|  
|<span data-ttu-id="6d676-190">\Catalog フォルダーには、次のファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6d676-190">In the \Catalog folder:</span></span><br /><br /> <span data-ttu-id="6d676-191">Catalog.xml</span><span class="sxs-lookup"><span data-stu-id="6d676-191">Catalog.xml</span></span>|<span data-ttu-id="6d676-192">PO で指定された出荷先に基づいて出荷業者を決定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="6d676-192">Used to determine shipment agency based on shipping destination specified in the PO.</span></span>|  
|<span data-ttu-id="6d676-193">\CheckPartyName フォルダーには、次のファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6d676-193">In the \CheckPartyName folder:</span></span><br /><br /> <span data-ttu-id="6d676-194">AssemblyInfo.cs、CheckPartyName.csproj、Class1.cs</span><span class="sxs-lookup"><span data-stu-id="6d676-194">AssemblyInfo.cs, CheckPartyName.csproj, Class1.cs</span></span>|<span data-ttu-id="6d676-195">CheckPartyName アプリケーション用の Microsoft Visual C# プロジェクトおよびソース ファイルです。送信元パーティのプロパティにアクセスするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="6d676-195">Microsoft Visual C# project and source files for the CheckPartyName application used to access the properties of the source party.</span></span>|  
|<span data-ttu-id="6d676-196">\FilePolling フォルダーには、次のファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6d676-196">In the \FilePolling folder:</span></span><br /><br /> <span data-ttu-id="6d676-197">App.ico、AssemblyInfo.cs、FilePolling.cs、FilePolling.csproj、FilePolling.resx、FilePolling.sln</span><span class="sxs-lookup"><span data-stu-id="6d676-197">App.ico, AssemblyInfo.cs, FilePolling.cs, FilePolling.csproj, FilePolling.resx, FilePolling.sln,</span></span>|<span data-ttu-id="6d676-198">FilePolling アプリケーション用の Visual C# ソリューション、プロジェクト、ソース、および関連ファイルです。</span><span class="sxs-lookup"><span data-stu-id="6d676-198">Visual C# solution, project, source, and associated files for the FilePolling application.</span></span><br /><br /> <span data-ttu-id="6d676-199">このアプリケーションを使用すると、この自動化されたシナリオの進行状況に関する情報を入手できます。</span><span class="sxs-lookup"><span data-stu-id="6d676-199">Use this application to keep informed about the progressing state of this automated scenario.</span></span>|  
|<span data-ttu-id="6d676-200">\Pipeline\projectschema フォルダーには、次のファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6d676-200">In the \Pipeline\projectschema folder:</span></span><br /><br /> <span data-ttu-id="6d676-201">MimePartyResReceivePipeline.btp、MimePartyResSendPipeline.btp</span><span class="sxs-lookup"><span data-stu-id="6d676-201">MimePartyResReceivePipeline.btp, MimePartyResSendPipeline.btp</span></span>|<span data-ttu-id="6d676-202">このサンプルの各ロールで使用される [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] パイプライン ファイルです。</span><span class="sxs-lookup"><span data-stu-id="6d676-202">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] pipeline files used by the different roles in this sample.</span></span>|  
|<span data-ttu-id="6d676-203">\QueryShipmentCatalogComponent フォルダーには、次のファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6d676-203">In the \QueryShipmentCatalogComponent folder:</span></span><br /><br /> <span data-ttu-id="6d676-204">AssemblyInfo.cs、QueryShipmentCatalog.cs、QueryShipmentCatalogComponent.csproj</span><span class="sxs-lookup"><span data-stu-id="6d676-204">AssemblyInfo.cs, QueryShipmentCatalog.cs, QueryShipmentCatalogComponent.csproj</span></span>|<span data-ttu-id="6d676-205">QueryShipmentCatalog コンポーネント用の Visual C# プロジェクトおよびソース ファイルです。ファイル Catalog.xml で定義されている出荷カタログにアクセスするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="6d676-205">Visual C# project and source files for the QueryShipmentCatalog component used to access the shipment catalog defined in the file Catalog.xml.</span></span><br /><br /> <span data-ttu-id="6d676-206">QueryShipmentCatalog コンポーネントは、供給業者が使用する出荷業者を決定します。</span><span class="sxs-lookup"><span data-stu-id="6d676-206">The QueryShipmentCatalog component determines which shipment agency the supplier will use.</span></span> <span data-ttu-id="6d676-207">地理的に最も近い出荷業者を決定するため、Catalog.xml のデータが使用されます。</span><span class="sxs-lookup"><span data-stu-id="6d676-207">It uses data from Catalog.xml to determine the best shipper based on geography.</span></span>|  
|<span data-ttu-id="6d676-208">\Schemas フォルダーには、次のファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6d676-208">In the \Schemas folder:</span></span><br /><br /> <span data-ttu-id="6d676-209">PODeliveryReceipt.xsd、POPropertySchema.xsd、PurchaseOrder.xsd、PurchaseOrderAcknowledgement.xsd、Schemas.btproj、ShipmentAdvice.xsd、ShipmentAdviceAcknowledgement.xsd、ShipmentOrderAcknowledgement.xsd、ShipmentOrderRequest.xsd</span><span class="sxs-lookup"><span data-stu-id="6d676-209">PODeliveryReceipt.xsd, POPropertySchema.xsd, PurchaseOrder.xsd, PurchaseOrderAcknowledgement.xsd, Schemas.btproj, ShipmentAdvice.xsd, ShipmentAdviceAcknowledgement.xsd, ShipmentOrderAcknowledgement.xsd, ShipmentOrderRequest.xsd</span></span>|<span data-ttu-id="6d676-210">このサンプルの各ロールで使用されるスキーマです。</span><span class="sxs-lookup"><span data-stu-id="6d676-210">Schemas used by the various roles in this sample.</span></span>|  
|<span data-ttu-id="6d676-211">\ShipmentAgency1 フォルダーには、次のファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6d676-211">In the \ShipmentAgency1 folder:</span></span><br /><br /> <span data-ttu-id="6d676-212">ShipmentAdviceAck.btm、ShipmentAgency1.btproj、ShipmentOrderAck.btm、Shipper1Process.odx</span><span class="sxs-lookup"><span data-stu-id="6d676-212">ShipmentAdviceAck.btm, ShipmentAgency1.btproj, ShipmentOrderAck.btm, Shipper1Process.odx</span></span>|<span data-ttu-id="6d676-213">このサンプルの ShipmentAgency1 を実装するために使用される、BizTalk プロジェクト、オーケストレーション、およびマップです。</span><span class="sxs-lookup"><span data-stu-id="6d676-213">BizTalk project, orchestration, and maps used to implement ShipmentAgency1 in this sample.</span></span>|  
|<span data-ttu-id="6d676-214">\ShipmentAgency2 フォルダーには、次のファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6d676-214">In the \ShipmentAgency2 folder:</span></span><br /><br /> <span data-ttu-id="6d676-215">ShipmentAdviceAck.btm、ShipmentAgency2.btproj、ShipmentOrderAck.btm、Shipper2Process.odx</span><span class="sxs-lookup"><span data-stu-id="6d676-215">ShipmentAdviceAck.btm, ShipmentAgency2.btproj, ShipmentOrderAck.btm, Shipper2Process.odx</span></span>|<span data-ttu-id="6d676-216">このサンプルの ShipmentAgency2 を実装するために使用される、BizTalk プロジェクト、オーケストレーション、およびマップです。</span><span class="sxs-lookup"><span data-stu-id="6d676-216">BizTalk project, orchestration, and maps used to implement ShipmentAgency2 in this sample.</span></span>|  
|<span data-ttu-id="6d676-217">\Supplier フォルダーには、次のファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6d676-217">In the \Supplier folder:</span></span><br /><br /> <span data-ttu-id="6d676-218">PO_POAck.btm、PO_ShipmentOrderRequest.btm、ShipmentAdviceAck_PODeliveryReceipt.btm、ShipmentOrder_ShipmentAdvice.btm、Supplier.btproj、SupplierProcess.odx</span><span class="sxs-lookup"><span data-stu-id="6d676-218">PO_POAck.btm, PO_ShipmentOrderRequest.btm, ShipmentAdviceAck_PODeliveryReceipt.btm, ShipmentOrder_ShipmentAdvice.btm, Supplier.btproj, SupplierProcess.odx</span></span>|<span data-ttu-id="6d676-219">このサンプルの供給業者を実装するために使用される、BizTalk プロジェクト、オーケストレーション、およびマップです。</span><span class="sxs-lookup"><span data-stu-id="6d676-219">BizTalk project, orchestration, and maps used to implement the supplier in this sample.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="6d676-220">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="6d676-220">Building and Initializing This Sample</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6d676-221">このサンプルをビルドおよび初期化する前に、既定の BizTalk インプロセス ホストが、信頼されている認証として構成されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d676-221">Before you build and initialize this sample, you need to make sure that the default BizTalk In-Process Host is configured as Authentication Trusted.</span></span> <span data-ttu-id="6d676-222">詳細については、次を参照してください。 [BizTalk Server ランタイムのセキュリティに関する推奨事項](../core/biztalk-server-runtime-security-recommendations.md)です。</span><span class="sxs-lookup"><span data-stu-id="6d676-222">For more information, see [BizTalk Server Runtime Security Recommendations](../core/biztalk-server-runtime-security-recommendations.md).</span></span>  
  
 <span data-ttu-id="6d676-223">MIME パイプライン コンポーネントは 64 ビット ホスト インスタンスではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6d676-223">The MIME pipeline component is not supported in a 64-bit host instance.</span></span> <span data-ttu-id="6d676-224">ファイル アダプターの送信および受信ハンドラーと関連付けられているホストを、32 ビット専用ホストとして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d676-224">The host associated with the send and receive handler for the file adapter must be configured as a 32-bit only host.</span></span> <span data-ttu-id="6d676-225">この参照の詳細については[ホストのプロパティを変更する方法](../core/how-to-modify-host-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="6d676-225">For more information on this see [How to Modify Host Properties](../core/how-to-modify-host-properties.md).</span></span> <span data-ttu-id="6d676-226">既にしている場合、システムで構成されている 32 ビット専用ホストを参照してください、それを使用する[ファイル アダプタを構成する](../core/configure-the-file-adapter.md)送信および受信ハンドラーについては、ファイル アダプターに関連付けられているホストの構成。</span><span class="sxs-lookup"><span data-stu-id="6d676-226">If you already have a 32-bit only host configured on the system, and want to use it, see [Configuring the File Adapter](../core/configure-the-file-adapter.md) for instructions on configuring the host(s) associated to the file adapter’s send and receive handler.</span></span>  
  
 <span data-ttu-id="6d676-227">このセクションで説明されている証明書を、メッセージに署名する既定の BizTalk インプロセス ホスト インスタンス用に構成されているログオン アカウントの個人用ストアに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d676-227">The certificate mentioned in this section must to be added to the Personal store of the Logon account configured for the default BizTalk In-Process host instance which will be signing messages.</span></span>  
  
 <span data-ttu-id="6d676-228">既定では、以下で説明する setup.bat ファイルによって、パーティの解決サンプルが既定の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーションにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="6d676-228">By default the setup.bat file mentioned below will install the Party Resolution sample into the default [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application.</span></span> <span data-ttu-id="6d676-229">setup.bat ファイルを開き、ステートメント `@ECHO Deploy Assemblies...` の後に続くセクションを以下に置き換えることで、サンプルを新しい [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーションに展開できます。</span><span class="sxs-lookup"><span data-stu-id="6d676-229">You can modify the setup.bat file to deploy the sample into a new [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application by opening the setup.bat file and replacing the section preceded by the statement `@ECHO Deploy Assemblies...` with the following:</span></span>  
  
```  
@ECHO Deploy Assemblies...  
  
btstask AddApp -ApplicationName:PartyResolutionSample -Description:"Party Resolution Orchestration sample from the SDK"  
btstask AddResource -ApplicationName:PartyResolutionSample -Type:System.BizTalk:BizTalkAssembly  -Source:Schemas\bin\Release\Schemas.dll -Options:GacOnAdd  
btstask AddResource -ApplicationName:PartyResolutionSample -Type:System.BizTalk:BizTalkAssembly  -Source:Pipeline\projectschema\bin\Release\ProjectSchema.dll -Options:GacOnAdd   
btstask AddResource -ApplicationName:PartyResolutionSample -Type:System.BizTalk:BizTalkAssembly  -Source:Buyer\bin\Release\Buyer.dll -Options:GacOnAdd  
btstask ImportBindings -ApplicationName:PartyResolutionSample -Source:%BuyerBindingFileName%  
btstask AddResource -ApplicationName:PartyResolutionSample -Type:System.BizTalk:BizTalkAssembly  -Source:ShipmentAgency1\bin\Release\ShipmentAgency1.dll -Options:GacOnAdd  
btstask ImportBindings -ApplicationName:PartyResolutionSample -Source:%ShipmentAgency1BindingFileName%  
btstask AddResource -ApplicationName:PartyResolutionSample -Type:System.BizTalk:BizTalkAssembly  -Source:ShipmentAgency2\bin\Release\ShipmentAgency2.dll -Options:GacOnAdd  
btstask ImportBindings -ApplicationName:PartyResolutionSample -Source:%ShipmentAgency2BindingFileName%  
btstask AddResource -ApplicationName:PartyResolutionSample -Type:System.BizTalk:BizTalkAssembly  -Source:Supplier\bin\Release\Supplier.dll -Options:GacOnAdd  
btstask ImportBindings -ApplicationName:PartyResolutionSample -Source:%SupplierBindingFileName%  
```  
  
#### <a name="to-build-and-initialize-the-partyresolution-sample"></a><span data-ttu-id="6d676-230">PartyResolution サンプルをビルドおよび初期化するには</span><span class="sxs-lookup"><span data-stu-id="6d676-230">To build and initialize the PartyResolution sample</span></span>  
  
1.  <span data-ttu-id="6d676-231">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="6d676-231">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="6d676-232">\<*パスのサンプル*> \Orchestrations\PartyResolution</span><span class="sxs-lookup"><span data-stu-id="6d676-232">\<*Samples Path*>\Orchestrations\PartyResolution</span></span>  
  
2.  <span data-ttu-id="6d676-233">次の操作を実行する Setup.bat ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="6d676-233">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="6d676-234">このサンプル用に [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] プロジェクトをコンパイルし、生成されたアセンブリを展開します。</span><span class="sxs-lookup"><span data-stu-id="6d676-234">Compiles the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] projects for this sample, and deploys the resulting assemblies.</span></span>  
  
    -   <span data-ttu-id="6d676-235">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の送信ポートおよび受信ポートを作成し、バインドします。</span><span class="sxs-lookup"><span data-stu-id="6d676-235">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] send and receive ports.</span></span>  
  
         <span data-ttu-id="6d676-236">セットアップ プロセス中、次のような警告が表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="6d676-236">You may receive the following or similar warnings during the setup process.</span></span> <span data-ttu-id="6d676-237">これらの警告は、無視してもかまいません。</span><span class="sxs-lookup"><span data-stu-id="6d676-237">You can safely ignore them.</span></span>  
  
        ```  
        "C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\Orchestrations\PartyResolution\PartyResolution.sln" (Buildtarget) (1) ->  
        "C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\Orchestrations\PartyResolution\Supplier\Supplier.btproj" (default target) (5) ->  
        "C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\Orchestrations\PartyResolution\Supplier\Supplier.btproj" (default target) (5:2) ->  
        (CompileODX target) ->  
          C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\Orchestrations\PartyResolution\Supplier\SupplierProcess.odx(831,13): warning X4014: convoy processing will not occur -- check your protocol if you were expecting it [C:\ProgramFiles\Microsoft BizTalk Server <version>\SDK\Samples\Orchestrations\PartyResolution\Supplier\Supplier.btproj]  
          C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\Orchestrations\PartyResolution\Supplier\SupplierProcess.odx(841,13): warning X4014: convoy processing will not occur -- check your protocol if you were expecting it [C:\ProgramFiles\Microsoft BizTalk Server <version>\SDK\Samples\Orchestrations\PartyResolution\Supplier\Supplier.btproj]  
  
        ```  
  
3.  <span data-ttu-id="6d676-238">開始**Visual Studio コマンド プロンプト**です。</span><span class="sxs-lookup"><span data-stu-id="6d676-238">Start **Visual Studio Command Prompt**.</span></span>  
  
4.  <span data-ttu-id="6d676-239">次のコマンドを入力して、アセンブリをグローバル アセンブリ キャッシュにインストールします。</span><span class="sxs-lookup"><span data-stu-id="6d676-239">Type the following commands to install the assemblies to the global assembly cache:</span></span>  
  
    -   <span data-ttu-id="6d676-240">gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\Schemas\bin\Release\schemas.dll</span><span class="sxs-lookup"><span data-stu-id="6d676-240">gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\Schemas\bin\Release\schemas.dll</span></span>  
  
    -   <span data-ttu-id="6d676-241">gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\Pipeline\projectschema\bin\Release\ProjectSchema.dll</span><span class="sxs-lookup"><span data-stu-id="6d676-241">gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\Pipeline\projectschema\bin\Release\ProjectSchema.dll</span></span>  
  
    -   <span data-ttu-id="6d676-242">gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\Buyer\bin\Release\Buyer.dll</span><span class="sxs-lookup"><span data-stu-id="6d676-242">gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\Buyer\bin\Release\Buyer.dll</span></span>  
  
    -   <span data-ttu-id="6d676-243">gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\ShipmentAgency1\bin\Release\ShipmentAgency1.dll</span><span class="sxs-lookup"><span data-stu-id="6d676-243">gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\ShipmentAgency1\bin\Release\ShipmentAgency1.dll</span></span>  
  
    -   <span data-ttu-id="6d676-244">gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\ShipmentAgency2\bin\Release\ShipmentAgency2.dll</span><span class="sxs-lookup"><span data-stu-id="6d676-244">gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\ShipmentAgency2\bin\Release\ShipmentAgency2.dll</span></span>  
  
    -   <span data-ttu-id="6d676-245">gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\Supplier\bin\Release\Supplier.dll</span><span class="sxs-lookup"><span data-stu-id="6d676-245">gacutil -i [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Orchestrations\PartyResolution\Supplier\bin\Release\Supplier.dll</span></span>  
  
5.  <span data-ttu-id="6d676-246">証明機関 (CA) から、安全な電子メールの証明書を入手します。</span><span class="sxs-lookup"><span data-stu-id="6d676-246">Obtain a secured e-mail certificate from a certificate authority (CA).</span></span> <span data-ttu-id="6d676-247">CA は、第三者機関である場合と組織内の機関である場合があります。</span><span class="sxs-lookup"><span data-stu-id="6d676-247">The CA could be a third-party authority or the authority within your organization.</span></span> <span data-ttu-id="6d676-248">証明書を取得した後は、公開キーと秘密キーをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="6d676-248">After you obtain the certificate, export the public key and private key.</span></span>  
  
6.  <span data-ttu-id="6d676-249">秘密キーをホスト インスタンス ログオン アカウントの個人用ストアにインポートしたり、公開キーをローカル コンピューターの "他の人" ストアにインポートするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6d676-249">To import the private key to the Personal store of the Host instance logon account and the public key to the Local Computer Other People store, do the following:</span></span>  
  
    1.  <span data-ttu-id="6d676-250">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、BizTalk グループを展開し、展開**プラットフォームの設定**です。</span><span class="sxs-lookup"><span data-stu-id="6d676-250">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand the BizTalk Group, and then expand **Platform Settings**.</span></span>  
  
    2.  <span data-ttu-id="6d676-251">をクリックして**ホスト インスタンス**既定のインプロセス ホスト インスタンスに対して表示されるログオン アカウントを見つけるとします。</span><span class="sxs-lookup"><span data-stu-id="6d676-251">Click on **Host Instances** and find the Logon account shown for the default In-Process host instance.</span></span> <span data-ttu-id="6d676-252">既定のインストールでは、既定のインプロセス ホストの名前は BizTalkServerApplication です。</span><span class="sxs-lookup"><span data-stu-id="6d676-252">In a default installation the default In-Process host should be named BizTalkServerApplication.</span></span>  
  
    3.  <span data-ttu-id="6d676-253">**[スタート]**ボタンをクリックし、 **[ファイル名を指定して実行]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d676-253">Click **Start**, and then click **Run**.</span></span> <span data-ttu-id="6d676-254">**実行**ボックスに、入力**mmc.exe**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="6d676-254">In the **Run** box, type **mmc.exe**, and then click **OK**.</span></span> <span data-ttu-id="6d676-255">ホスト インスタンス ログオン アカウントの正しいパスワードを入力し、そのアカウントで Microsoft 管理コンソール (MMC) を開きます。</span><span class="sxs-lookup"><span data-stu-id="6d676-255">Enter the correct password for the host instance logon account to open the Microsoft Management Console (MMC) under that account.</span></span>  
  
    4.  <span data-ttu-id="6d676-256">**[ファイル]** メニューの **[スナップインの追加と削除]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d676-256">On the **File** menu, click **Add/Remove Snap-in**.</span></span>  
  
    5.  <span data-ttu-id="6d676-257">**を追加または削除スナップイン**ダイアログ ボックスで、**証明書**、順にクリック**追加**です。</span><span class="sxs-lookup"><span data-stu-id="6d676-257">In the **Add or Remove Snap-ins** dialog box, select **Certificates**, and then click **Add**.</span></span>  
  
    6.  <span data-ttu-id="6d676-258">**証明書スナップイン**ダイアログ ボックスで、 **ユーザー アカウント**、クリックして**完了**です。</span><span class="sxs-lookup"><span data-stu-id="6d676-258">In the **Certificates snap-in** dialog box, select **My user account**, and then click **Finish**.</span></span>  
  
    7.  <span data-ttu-id="6d676-259">**を追加または削除スナップイン**ダイアログ ボックスで、**証明書**、順にクリック**追加**です。</span><span class="sxs-lookup"><span data-stu-id="6d676-259">In the **Add or Remove Snap-ins** dialog box, select **Certificates**, and then click **Add**.</span></span>  
  
    8.  <span data-ttu-id="6d676-260">**証明書スナップイン**ダイアログ ボックスで、**コンピューター アカウント**、順にクリック**次**です。</span><span class="sxs-lookup"><span data-stu-id="6d676-260">In the **Certificates snap-in** dialog box, select **Computer account**, and then click **Next**.</span></span>  
  
    9. <span data-ttu-id="6d676-261">**コンピューターの選択**ダイアログ ボックスで、**ローカル コンピューター**、クリックして**完了**です。</span><span class="sxs-lookup"><span data-stu-id="6d676-261">In the **Select Computer** dialog box, select **Local computer**, and then click **Finish**.</span></span>  
  
    10. <span data-ttu-id="6d676-262">**を追加または削除スナップイン**ダイアログ ボックスで、をクリックして**[ok]**です。</span><span class="sxs-lookup"><span data-stu-id="6d676-262">In the **Add or Remove Snap-ins** dialog box, click **OK**.</span></span>  
  
    11. <span data-ttu-id="6d676-263">展開、**証明書 - 現在のユーザー**ノードを展開し、**個人**です。</span><span class="sxs-lookup"><span data-stu-id="6d676-263">Expand the **Certificates - Current User** node and then expand **Personal**.</span></span> <span data-ttu-id="6d676-264">右クリック**証明書**をクリックして**すべてのタスク**、順にクリック**インポート**です。</span><span class="sxs-lookup"><span data-stu-id="6d676-264">Right-click **Certificates**, click **All Tasks**, and then click **Import**.</span></span>  
  
    12. <span data-ttu-id="6d676-265">ウィザードで秘密キーをインポートし、パスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="6d676-265">Import the private key and provide a password in the wizard.</span></span>  
  
    13. <span data-ttu-id="6d676-266">展開、**証明書 (ローカル コンピューター)**ノードを展開し、**ほかの人**です。</span><span class="sxs-lookup"><span data-stu-id="6d676-266">Expand the **Certificates (Local Computer)** node and then expand **Other People**.</span></span> <span data-ttu-id="6d676-267">右クリック**証明書**をクリックして**すべてのタスク**、順にクリック**インポート**です。</span><span class="sxs-lookup"><span data-stu-id="6d676-267">Right-click **Certificates**, click **All Tasks**, and then click **Import**.</span></span>  
  
    14. <span data-ttu-id="6d676-268">公開キーをインポートします。</span><span class="sxs-lookup"><span data-stu-id="6d676-268">Import the public key.</span></span>  
  
7.  <span data-ttu-id="6d676-269">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックし、 **BizTalk グループ**ノードをクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="6d676-269">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click the **BizTalk Group** node and then click **Properties**.</span></span> <span data-ttu-id="6d676-270">**BizTalk グループ - グループのプロパティ**ダイアログ ボックスで、**証明書**です。</span><span class="sxs-lookup"><span data-stu-id="6d676-270">In the **BizTalk Group - Group Properties** dialog box, select **Certificate**.</span></span>  
  
8.  <span data-ttu-id="6d676-271">**証明書**ダイアログ ボックスで、をクリックして**参照**をインポートした秘密キーを選択します。</span><span class="sxs-lookup"><span data-stu-id="6d676-271">In the **Certificate** dialog box, click **Browse** and select the private key you just imported.</span></span> <span data-ttu-id="6d676-272">ここで指定した証明書は、送信メッセージの署名に使用されます。</span><span class="sxs-lookup"><span data-stu-id="6d676-272">The certificate specified here is used to sign the outbound message.</span></span> <span data-ttu-id="6d676-273">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d676-273">Click **OK**.</span></span>  
  
9. <span data-ttu-id="6d676-274">このサンプルの BuyerAgency パーティを更新するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6d676-274">To update the BuyerAgency party in this sample do the following:</span></span>  
  
    1.  <span data-ttu-id="6d676-275">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、**パーティ**です。</span><span class="sxs-lookup"><span data-stu-id="6d676-275">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, select **Parties**.</span></span>  
  
    2.  <span data-ttu-id="6d676-276">右クリック**BuyerAgency**  をクリックし、**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="6d676-276">Right-click **BuyerAgency** and then click **Properties**.</span></span> <span data-ttu-id="6d676-277">**BuyerAgency - パーティのプロパティ**ダイアログ ボックスで、**全般**です。</span><span class="sxs-lookup"><span data-stu-id="6d676-277">In the **BuyerAgency - Party Properties** dialog box, select **General**.</span></span>  
  
    3.  <span data-ttu-id="6d676-278">下にある、**エイリアス**セクションで、ダイアログ ボックスの設定の修飾子と名前で新しいエイリアスを追加**WindowsUser**です。</span><span class="sxs-lookup"><span data-stu-id="6d676-278">Under the **Aliases** section of the dialog, add a new alias with the name and qualifier set to **WindowsUser**.</span></span> <span data-ttu-id="6d676-279">値の形式でユーザー名を設定\<ドメイン \ ユーザー名 > (somedomain \someuser など)。</span><span class="sxs-lookup"><span data-stu-id="6d676-279">Set the Value to a user name in format of \<domain\user name> (e.g. SOMEDOMAIN\someuser).</span></span>  
  
    4.  <span data-ttu-id="6d676-280">選択**証明書** をクリックし、**参照**をインポートした公開キーを選択します。</span><span class="sxs-lookup"><span data-stu-id="6d676-280">Select **Certificate** and then click **Browse** and select the public key you just imported.</span></span> <span data-ttu-id="6d676-281">ここで指定した証明書は、受信メッセージの送信者 ID の検証に使用されます。</span><span class="sxs-lookup"><span data-stu-id="6d676-281">The certificate specified here is used to validate the sender identity of the inbound message.</span></span> <span data-ttu-id="6d676-282">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d676-282">Click **OK**.</span></span>  
  
10. <span data-ttu-id="6d676-283">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、**プラットフォームの設定**、し、**ホスト**です。</span><span class="sxs-lookup"><span data-stu-id="6d676-283">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **Platform Settings**, and then select **Hosts**.</span></span>  
  
11. <span data-ttu-id="6d676-284">右クリック**BizTalkServerApplication**  をクリックし、**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="6d676-284">Right-click **BizTalkServerApplication** and then click **Properties**.</span></span> <span data-ttu-id="6d676-285">**BizTalkServerApplication - ホストのプロパティ**ダイアログ ボックスで、**証明書**です。</span><span class="sxs-lookup"><span data-stu-id="6d676-285">In the **BizTalkServerApplication - Host Properties** dialog box, select **Certificates**.</span></span>  
  
12. <span data-ttu-id="6d676-286">をクリックして**参照**をインポートした秘密キーを選択します。</span><span class="sxs-lookup"><span data-stu-id="6d676-286">Click **Browse** and select the private key you just imported.</span></span> <span data-ttu-id="6d676-287">ここで指定した証明書は、受信メッセージの解読に使用されます。</span><span class="sxs-lookup"><span data-stu-id="6d676-287">The certificate specified here is used to decrypt the inbound messages.</span></span> <span data-ttu-id="6d676-288">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d676-288">Click **OK**.</span></span>  
  
13. <span data-ttu-id="6d676-289">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、**プラットフォームの設定**、し、**ホスト インスタンス**です。</span><span class="sxs-lookup"><span data-stu-id="6d676-289">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **Platform Settings**, and then select **Host Instances**.</span></span>  
  
14. <span data-ttu-id="6d676-290">右クリック**BizTalkServerApplication**  をクリックし、**再起動**です。</span><span class="sxs-lookup"><span data-stu-id="6d676-290">Right-click **BizTalkServerApplication** and then click **Restart**.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="6d676-291">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="6d676-291">Running This Sample</span></span>  
  
#### <a name="to-run-the-partyresolution-sample"></a><span data-ttu-id="6d676-292">PartyResolution サンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="6d676-292">To run the PartyResolution sample</span></span>  
  
1.  <span data-ttu-id="6d676-293">次のフォルダーから FilePolling.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="6d676-293">Run FilePolling.exe from the following folder:</span></span>  
  
     <span data-ttu-id="6d676-294">*\<サンプル パス >*\Orchestrations\PartyResolution\FilePolling\bin\Debug</span><span class="sxs-lookup"><span data-stu-id="6d676-294">*\<Samples Path>*\Orchestrations\PartyResolution\FilePolling\bin\Debug</span></span>  
  
2.  <span data-ttu-id="6d676-295">をクリックして**ポーリングの開始**です。</span><span class="sxs-lookup"><span data-stu-id="6d676-295">Click **Start polling**.</span></span>  
  
3.  <span data-ttu-id="6d676-296">用意されている PO インスタンス ファイル PurchaseOrder.xml を、次のフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="6d676-296">Paste a copy of the provided PO instance file, PurchaseOrder.xml, in the following folder:</span></span>  
  
     <span data-ttu-id="6d676-297">*\<サンプル パス >*\Orchestrations\PartyResolution\FileDrop\PurchaseOrder</span><span class="sxs-lookup"><span data-stu-id="6d676-297">*\<Samples Path>*\Orchestrations\PartyResolution\FileDrop\PurchaseOrder</span></span>  
  
4.  <span data-ttu-id="6d676-298">次の各時点でサンプルの進行状況を知らせるメッセージがメッセージ ボックスの形式で表示されるので、それを確認します。</span><span class="sxs-lookup"><span data-stu-id="6d676-298">Observe the sequence of messages that are provided in the form of message boxes that keep you informed about the progress of the sample:</span></span>  
  
    1.  <span data-ttu-id="6d676-299">供給業者が購入者から PO を受信したとき。</span><span class="sxs-lookup"><span data-stu-id="6d676-299">When the supplier receives the PO from the buyer.</span></span>  
  
    2.  <span data-ttu-id="6d676-300">出荷業者 1 または 2 から出荷指令の要求を受信したとき。</span><span class="sxs-lookup"><span data-stu-id="6d676-300">When a shipment order request is received from shipment agency 1 or 2.</span></span>  
  
    3.  <span data-ttu-id="6d676-301">出荷業者 1 または 2 から出荷通知を受信したとき。</span><span class="sxs-lookup"><span data-stu-id="6d676-301">When a shipment advice is received by shipment agency 1 or 2.</span></span>  
  
    4.  <span data-ttu-id="6d676-302">供給業者が購入者に PO の配信確認を送信したとき。</span><span class="sxs-lookup"><span data-stu-id="6d676-302">When the supplier sends the PO delivery receipt to the buyer.</span></span>  
  
5.  <span data-ttu-id="6d676-303">をクリックして**終了**ファイル ポーリング プログラムを終了します。</span><span class="sxs-lookup"><span data-stu-id="6d676-303">Click **Exit** to close the File Polling program.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6d676-304">PurchaseOrder.xml 内の "Country" タグを "US" に編集し、手順 2. と 3. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="6d676-304">You can edit the Country tag in PurchaseOrder.xml to "US" and then repeat step 2 and step 3.</span></span> <span data-ttu-id="6d676-305">出荷指令が ShipmentAgency2 に送信されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6d676-305">Observe that the shipment order is now sent to shipment agency 2.</span></span>  
  
## <a name="uninstalling-this-sample"></a><span data-ttu-id="6d676-306">このサンプルのアンインストール</span><span class="sxs-lookup"><span data-stu-id="6d676-306">Uninstalling This Sample</span></span>  
  
#### <a name="to-uninstall-the-partyresolution-sample"></a><span data-ttu-id="6d676-307">PartyResolution サンプルをアンインストールするには</span><span class="sxs-lookup"><span data-stu-id="6d676-307">To uninstall the PartyResolution sample</span></span>  
  
1.  <span data-ttu-id="6d676-308">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]コマンド プロンプトでディレクトリ変更コマンド (**cd**) に\<*サンプル パス*> \Orchestrations\ PartyResolution\\です。</span><span class="sxs-lookup"><span data-stu-id="6d676-308">At a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] command prompt, change directory (**cd**) to \<*Samples Path*>\Orchestrations\ PartyResolution\\.</span></span>  
  
2.  <span data-ttu-id="6d676-309">Cleanup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="6d676-309">Run Cleanup.bat.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d676-310">参照</span><span class="sxs-lookup"><span data-stu-id="6d676-310">See Also</span></span>  
 <span data-ttu-id="6d676-311">[パーティの解決パイプライン コンポーネント](../core/party-resolution-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="6d676-311">[Party Resolution Pipeline Component](../core/party-resolution-pipeline-component.md) </span></span>  
 <span data-ttu-id="6d676-312">[MIME/SMIME エンコーダー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="6d676-312">[How to Configure the MIME-SMIME Encoder Pipeline Component](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md) </span></span>  
 <span data-ttu-id="6d676-313">[MIME/SMIME デコーダー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="6d676-313">[How to Configure the MIME-SMIME Decoder Pipeline Component](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md) </span></span>  
 [<span data-ttu-id="6d676-314">オーケストレーション (BizTalk Server サンプル フォルダー)</span><span class="sxs-lookup"><span data-stu-id="6d676-314">Orchestrations (BizTalk Server Samples Folder)</span></span>](../core/orchestrations-biztalk-server-samples-folder.md)