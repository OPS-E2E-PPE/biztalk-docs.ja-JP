---
title: メッセージ プロセッサ (BizTalk Server サンプル) で構成されます |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, examples
- messages, processing
- messages, aggregated
- examples, pipelines
ms.assetid: a0f87f98-6f5f-4edb-8f65-49d22df5de97
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6a072a889403abd474a31625eba86f9e28a2da6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356653"
---
# <a name="composed-message-processor-biztalk-server-sample"></a><span data-ttu-id="b33e6-102">構成済みメッセージ プロセッサ (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="b33e6-102">Composed Message Processor (BizTalk Server Sample)</span></span>
<span data-ttu-id="b33e6-103">このサンプルの目的は、個別のアイテムを集計したメッセージを処理する構成済みメッセージ プロセッサ アプリケーションを構築します。</span><span class="sxs-lookup"><span data-stu-id="b33e6-103">The purpose of this sample is to build a composed message processor application that processes individual line items from aggregated messages.</span></span>  
  
 <span data-ttu-id="b33e6-104">具体的にはようはオーケストレーション スケジュールを作成します。</span><span class="sxs-lookup"><span data-stu-id="b33e6-104">Specifically we will build an orchestration schedule that:</span></span>  
  
1. <span data-ttu-id="b33e6-105">複数の購買発注で構成されるバッチ インターチェンジ メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="b33e6-105">Receives a batched interchange message consisting of multiple purchase orders.</span></span>  
  
2. <span data-ttu-id="b33e6-106">個々 の注文書インターチェンジ メッセージを逆アセンブルします。</span><span class="sxs-lookup"><span data-stu-id="b33e6-106">Disassembles the interchange message into individual purchase order documents.</span></span>  
  
3. <span data-ttu-id="b33e6-107">各ドキュメントの処理: 各購買発注、請求書メッセージに変換します。</span><span class="sxs-lookup"><span data-stu-id="b33e6-107">Processes each document – converts each purchase order into an invoice message.</span></span>  
  
4. <span data-ttu-id="b33e6-108">すべての請求書メッセージをバッチ インターチェンジにアセンブルします。</span><span class="sxs-lookup"><span data-stu-id="b33e6-108">Assembles all the invoice messages into a batched interchange.</span></span>  
  
   <span data-ttu-id="b33e6-109">手順 3. サンプルの目的で簡単になります。</span><span class="sxs-lookup"><span data-stu-id="b33e6-109">Step #3 is simplified for the sample purposes.</span></span> <span data-ttu-id="b33e6-110">やなどのより複雑なアプリケーションは、オーケストレーション可能性がありますを異なるバックエンド在庫システムに発注書を逆アセンブルを送信し、すべての応答を収集した後に集計する 1 つのバッチ化された請求書メッセージ。</span><span class="sxs-lookup"><span data-stu-id="b33e6-110">For example, in more complex applications, an orchestration may send disassembled purchase orders to different back-end inventory systems and then after collecting all the responses, aggregate them into one batched invoice message.</span></span>  
  
   <span data-ttu-id="b33e6-111">構成済みメッセージ プロセッサ パターンの詳細については、[1] を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b33e6-111">For more information on the composed message processor pattern refer to [1].</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="b33e6-112">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="b33e6-112">What This Sample Does</span></span>  
 <span data-ttu-id="b33e6-113">いずれは、次のセクションで詳しく説明、サンプル ソリューション内の 2 つのプロジェクトがあります。</span><span class="sxs-lookup"><span data-stu-id="b33e6-113">There are two projects within the sample solution, both of which are described in detail in the following sections.</span></span>  
  
### <a name="pipelines-and-schemas"></a><span data-ttu-id="b33e6-114">パイプラインとスキーマ</span><span class="sxs-lookup"><span data-stu-id="b33e6-114">Pipelines and Schemas</span></span>  
 <span data-ttu-id="b33e6-115">パイプラインとスキーマのプロジェクトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b33e6-115">Pipelines and schemas project contains:</span></span>  
  
-   <span data-ttu-id="b33e6-116">入力注文書インターチェンジと出力請求書インターチェンジのフラット ファイル スキーマです。</span><span class="sxs-lookup"><span data-stu-id="b33e6-116">Flat file schemas for input purchase order interchange and for output invoice interchange.</span></span>  
  
-   <span data-ttu-id="b33e6-117">請求書ドキュメントに注文書ドキュメントを変換するマップです。</span><span class="sxs-lookup"><span data-stu-id="b33e6-117">Map to transform purchase order document into an invoice document.</span></span>  
  
-   <span data-ttu-id="b33e6-118">受信および送信パイプラインです。</span><span class="sxs-lookup"><span data-stu-id="b33e6-118">Receive and send pipelines.</span></span>  
  
#### <a name="flat-file-schemas-for-input-and-output-interchanges"></a><span data-ttu-id="b33e6-119">入力と出力インターチェンジのフラット ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="b33e6-119">Flat File Schemas For Input and Output Interchanges</span></span>  
 <span data-ttu-id="b33e6-120">サンプル アプリケーションについては、フラット ファイル形式でインターチェンジを作成します。</span><span class="sxs-lookup"><span data-stu-id="b33e6-120">Our sample application will be working with the interchanges in the flat file format.</span></span> <span data-ttu-id="b33e6-121">次には、注文書インターチェンジと請求書インターチェンジの例を示します。</span><span class="sxs-lookup"><span data-stu-id="b33e6-121">Below are the examples of the purchase order interchange and invoice interchange:</span></span>  
  
 <span data-ttu-id="b33e6-122">注文書インターチェンジ (CMPInput.txt):</span><span class="sxs-lookup"><span data-stu-id="b33e6-122">Purchase order interchange (CMPInput.txt):</span></span>  
  
```  
Northwind Shipping  
Batch type:Purchase Orders  
PO1999-10-20  
US    Alice Smith    123 Maple Street    Mill Valley    CA 90952  
US    Robert Smith   8 Oak Avenue        Old Town       PA 95819  
Hurry, my lawn is going wild!  
ITEMS,ITEM872-AA|Lawnmower|1|148.95|Confirm this is electric,ITEM926-AA|Baby Monitor|1|39.98|Confirm this is electric|1999-10-21  
PO1999-10-21  
US    John Dow       123 Elm Street      Mill Valley    CA 90952  
US    July Dow       8 Pine Avenue       Old Town       PA 95819  
Please ship it urgent!  
ITEMS,ITEM398-BB|Tire|4|324.99|Wrap them up nicely,ITEM201-BB|Engine Oil|1|12.99|SAE10W30|1999-05-22  
PO1999-10-23  
US    John Connor    123 Cedar Street    Mill Valley    CA 90952  
US    Sarah Connor   8 Grass Avenue      Old Town       PA 95819  
Use cheapest shipping method.  
ITEMS,ITEM101-TT|Plastic flowers|10|4.99|Fragile handle with care,ITEM202-RR|Fertilizer|1|10.99|Lawn fertilizer,ITEM453-XS|Weed killer|1|5.99|Lawn weed killer|1999-05-25  
```  
  
 <span data-ttu-id="b33e6-123">インターチェンジ、または購買発注書ドキュメントでは、含まれているドキュメントの種類を識別するヘッダーがあります。</span><span class="sxs-lookup"><span data-stu-id="b33e6-123">The interchange, or purchase order document, has a header that identifies what type of the documents it contains:</span></span>  
  
```  
Northwind Shipping  
Batch type:Purchase Orders  
```  
  
 <span data-ttu-id="b33e6-124">このインターチェンジは、次の 3 つの注文書で構成されます。</span><span class="sxs-lookup"><span data-stu-id="b33e6-124">This interchange consist of three purchase order documents.</span></span> <span data-ttu-id="b33e6-125">1 つのインスタンスは、下に表示される情報で構成されます。</span><span class="sxs-lookup"><span data-stu-id="b33e6-125">One instance consists of the information shown below.</span></span> <span data-ttu-id="b33e6-126">ご覧のとおり、課金、および配布および注文したアイテムの一覧のアドレスなどの情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b33e6-126">As you can see, it contains such information as address for billing and shipping as well as the list of items that were ordered.</span></span>  
  
```  
PO1999-10-20  
US    Alice Smith    123 Maple Street    Mill Valley    CA 90952  
US    Robert Smith   8 Oak Avenue        Old Town       PA 95819  
Hurry, my lawn is going wild!  
ITEMS,ITEM872-AA|Lawnmower|1|148.95|Confirm this is electric,ITEM926-AA|Baby Monitor|1|39.98|Confirm this is electric|1999-10-21  
```  
  
 <span data-ttu-id="b33e6-127">これを生成する請求書インターチェンジは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="b33e6-127">The invoice interchange we want to generate for this should look like the following:</span></span>  
  
```  
Northwest Shipping  
DocumentTypes:Invoices  
INVOICE1999-10-20  
BILLTO,US,Alice Smith,123 Maple Street,Mill Valley,CA,90952  
872-AA    Lawnmower         1    148.95    Confirm this is electric  
926-AA    Baby Monitor      1    39.98     Confirm this is electric  
INVOICE1999-10-21  
BILLTO,US,John Dow,123 Elm Street,Mill Valley,CA,90952  
398-BB    Tire              4    324.99    Wrap them up nicely  
201-BB    Engine Oil        1    12.99     SAE10W30  
INVOICE1999-10-20  
BILLTO,US,John Connor,123 Cedar Street,Mill Valley,CA,90952  
101-TT    Plastic flowers   10   4.99      Fragile handle with care  
202-RR    Fertilizer        1    10.99     Lawn fertilizer  
453-XS    Weed killer       1    5.99      Lawn weed killer  
```  
  
 <span data-ttu-id="b33e6-128">このインターチェンジには、インターチェンジを購入しても、インターチェンジの形式とヘッダーの形式が異なるが含まれる情報のサブセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b33e6-128">This interchange contains a subset of information that was in purchase order interchange and also the format of the interchange as well as format of the header are different.</span></span>  
  
 <span data-ttu-id="b33e6-129">ヘッダーは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b33e6-129">The header is as follows:</span></span>  
  
```  
Northwest Shipping  
DocumentTypes:Invoices  
```  
  
 <span data-ttu-id="b33e6-130">ドキュメント インスタンスが、次が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b33e6-130">And the document instance includes the following:</span></span>  
  
```  
INVOICE1999-10-20  
BILLTO,US,Alice Smith,123 Maple Street,Mill Valley,CA,90952  
872-AA    Lawnmower         1    148.95    Confirm this is electric  
926-AA    Baby Monitor      1    39.98     Confirm this is electric  
```  
  
 <span data-ttu-id="b33e6-131">最初のフラット ファイル スキーマを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b33e6-131">First thing we need to create flat file schemas for:</span></span>  
  
- <span data-ttu-id="b33e6-132">購買発注書ドキュメント (PO.xsd)</span><span class="sxs-lookup"><span data-stu-id="b33e6-132">Purchase order document (PO.xsd)</span></span>  
  
- <span data-ttu-id="b33e6-133">請求書ドキュメント (Invoice.xsd)</span><span class="sxs-lookup"><span data-stu-id="b33e6-133">Invoice document (Invoice.xsd)</span></span>  
  
- <span data-ttu-id="b33e6-134">発注書ヘッダー (POHeader.xsd)</span><span class="sxs-lookup"><span data-stu-id="b33e6-134">Purchase order header (POHeader.xsd)</span></span>  
  
- <span data-ttu-id="b33e6-135">請求書ヘッダー (InvoiceHeader.xsd)</span><span class="sxs-lookup"><span data-stu-id="b33e6-135">Invoice header (InvoiceHeader.xsd)</span></span>  
  
  <span data-ttu-id="b33e6-136">このサンプルでは、フラット ファイル スキーマを作成するプロセスを説明することはしません。</span><span class="sxs-lookup"><span data-stu-id="b33e6-136">For this sample, we are not going to explain the process of creating flat file schemas.</span></span> <span data-ttu-id="b33e6-137">ドキュメント インスタンスからフラット ファイル スキーマを作成する方法については、「ドキュメント インスタンスからフラット ファイル スキーマを作成する」ドキュメントのセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b33e6-137">To learn how to create flat file schemas from document instances, refer to the "Creating flat file schemas from document instance" documentation section.</span></span>  
  
#### <a name="map-to-transform-purchase-order-document-into-invoice-document"></a><span data-ttu-id="b33e6-138">請求書ドキュメントに注文書ドキュメントを変換するマップ</span><span class="sxs-lookup"><span data-stu-id="b33e6-138">Map to Transform Purchase Order Document Into Invoice Document</span></span>  
 <span data-ttu-id="b33e6-139">マップ (PO2Invoice.btm) は、注文書のインスタンスを請求書ドキュメントに変換します。</span><span class="sxs-lookup"><span data-stu-id="b33e6-139">The map (PO2Invoice.btm) transforms an instance of the purchase order into an invoice document.</span></span>  
  
#### <a name="receive-and-send-pipelines"></a><span data-ttu-id="b33e6-140">受信パイプラインと送信</span><span class="sxs-lookup"><span data-stu-id="b33e6-140">Receive and Send Pipelines</span></span>  
 <span data-ttu-id="b33e6-141">受信パイプライン (FFReceivePipeline.btp) には、注文書インターチェンジを処理するために使用するフラット ファイル逆アセンブラー コンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b33e6-141">The receive pipeline (FFReceivePipeline.btp) contains a flat file disassembler component that is used to process a purchase order interchange.</span></span> <span data-ttu-id="b33e6-142">具体的には、特に CMPInput.txt ファイルで、インターチェンジのインターチェンジ ヘッダーを削除し、3 つの発注書に対応する 3 つの XML ドキュメントを生成します。</span><span class="sxs-lookup"><span data-stu-id="b33e6-142">In particular, for the interchange in file CMPInput.txt, it removes the interchange header and produces three XML documents corresponding to three purchase orders.</span></span>  
  
 <span data-ttu-id="b33e6-143">受信パイプラインのフラット ファイル逆アセンブラーが示すように構成されています。</span><span class="sxs-lookup"><span data-stu-id="b33e6-143">The flat file disassembler in the receive pipeline is configured as shown:</span></span>  
  
- <span data-ttu-id="b33e6-144">**ドキュメント スキーマ:** PipelinesAndSchemas.PO</span><span class="sxs-lookup"><span data-stu-id="b33e6-144">**Document schema:** PipelinesAndSchemas.PO</span></span>  
  
- <span data-ttu-id="b33e6-145">**ヘッダー スキーマ:** PipelinesAndSchemas.POHeader</span><span class="sxs-lookup"><span data-stu-id="b33e6-145">**Header schema:** PipelinesAndSchemas.POHeader</span></span>  
  
- <span data-ttu-id="b33e6-146">**ヘッダーを保存します。** False</span><span class="sxs-lookup"><span data-stu-id="b33e6-146">**Preserve header:** False</span></span>  
  
- <span data-ttu-id="b33e6-147">**回復可能なインターチェンジ:** False</span><span class="sxs-lookup"><span data-stu-id="b33e6-147">**Recoverable interchange:** False</span></span>  
  
- <span data-ttu-id="b33e6-148">**トレーラー スキーマ:**(なし)</span><span class="sxs-lookup"><span data-stu-id="b33e6-148">**Trailer schema:** (None)</span></span>  
  
- <span data-ttu-id="b33e6-149">**ドキュメント構造を検証します。** False</span><span class="sxs-lookup"><span data-stu-id="b33e6-149">**Validate document structure:** False</span></span>  
  
  <span data-ttu-id="b33e6-150">送信パイプライン (FFSendPipeline.btp) には、集計請求書インターチェンジを作成するために使用するフラット ファイル アセンブラー コンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b33e6-150">The send pipeline (FFSendPipeline.btp) contains a flat file assembler component that is used to create aggregated invoice interchange.</span></span>  
  
  <span data-ttu-id="b33e6-151">送信パイプラインのフラット ファイル アセンブラーが示すように構成されています。</span><span class="sxs-lookup"><span data-stu-id="b33e6-151">The flat file assembler in send pipeline is configured as shown:</span></span>  
  
- <span data-ttu-id="b33e6-152">**ドキュメント スキーマ:** PipelinesandSchemas.Invoice</span><span class="sxs-lookup"><span data-stu-id="b33e6-152">**Document schema:** PipelinesandSchemas.Invoice</span></span>  
  
- <span data-ttu-id="b33e6-153">**ヘッダー スキーマ:** PipelinesAndSchemas.InvoiceHeader</span><span class="sxs-lookup"><span data-stu-id="b33e6-153">**Header schema:** PipelinesAndSchemas.InvoiceHeader</span></span>  
  
- <span data-ttu-id="b33e6-154">**バイト オーダー マークを保存します。** False</span><span class="sxs-lookup"><span data-stu-id="b33e6-154">**Preserve byte order mark:** False</span></span>  
  
- <span data-ttu-id="b33e6-155">**ターゲット文字セット:**(なし)</span><span class="sxs-lookup"><span data-stu-id="b33e6-155">**Target charset:** (None)</span></span>  
  
- <span data-ttu-id="b33e6-156">**トレーラー スキーマ:**(なし)</span><span class="sxs-lookup"><span data-stu-id="b33e6-156">**Trailer schema:** (None)</span></span>  
  
### <a name="orchestration-schedule"></a><span data-ttu-id="b33e6-157">オーケストレーション スケジュール</span><span class="sxs-lookup"><span data-stu-id="b33e6-157">Orchestration Schedule</span></span>  
 <span data-ttu-id="b33e6-158">オーケストレーション スケジュール (CMP.odx) は、すべての主な処理が行われる場所です。</span><span class="sxs-lookup"><span data-stu-id="b33e6-158">Orchestration schedule (CMP.odx) is where all the main processing happens.</span></span> <span data-ttu-id="b33e6-159">具体的には、次の操作が実行されます。</span><span class="sxs-lookup"><span data-stu-id="b33e6-159">Specifically the following actions are performed:</span></span>  
  
-   <span data-ttu-id="b33e6-160">受信パイプラインを実行すると、注文書インターチェンジを逆アセンブル</span><span class="sxs-lookup"><span data-stu-id="b33e6-160">Receive pipeline is executed to disassemble purchase order interchange</span></span>  
  
-   <span data-ttu-id="b33e6-161">受信パイプラインのすべての出力メッセージを変換します。</span><span class="sxs-lookup"><span data-stu-id="b33e6-161">Every output message of receive pipeline is transformed</span></span>  
  
-   <span data-ttu-id="b33e6-162">送信パイプラインを実行して、請求書インターチェンジをアセンブルするには</span><span class="sxs-lookup"><span data-stu-id="b33e6-162">Send pipeline is executed to assemble an invoice interchange</span></span>  
  
#### <a name="creating-orchestration-schedule-and-defining-global-variables"></a><span data-ttu-id="b33e6-163">オーケストレーション スケジュールを作成して、グローバル変数を定義します。</span><span class="sxs-lookup"><span data-stu-id="b33e6-163">Creating Orchestration Schedule and Defining Global Variables</span></span>  
 <span data-ttu-id="b33e6-164">オーケストレーションでは、入力としてのフラット ファイル インターチェンジを受信して、出力として、フラット ファイル インターチェンジを送信します。</span><span class="sxs-lookup"><span data-stu-id="b33e6-164">Our orchestration will receive a flat file interchange as an input and will send a flat file interchange as an output.</span></span> <span data-ttu-id="b33e6-165">そのため、型として (それぞれという InputInterchange および OutputInterchange) 入力と出力メッセージを定義する必要があります (つまり System.Xml.XmlDocument 型を持つ) に依存しません。</span><span class="sxs-lookup"><span data-stu-id="b33e6-165">Because of that, we need to define input and output messages (called InputInterchange and OutputInterchange respectively) as type agnostic (i.e. having type of System.Xml.XmlDocument).</span></span>  
  
 <span data-ttu-id="b33e6-166">また、メッセージを処理しますが、アトミックのスコープを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b33e6-166">Also, we need to define an atomic scope where we will process messages.</span></span> <span data-ttu-id="b33e6-167">受信パイプラインはアトミックのスコープ内で実行できるために必要です。</span><span class="sxs-lookup"><span data-stu-id="b33e6-167">This is required because the receive pipeline can be executed within atomic scope.</span></span>  
  
#### <a name="executing-receive-pipeline"></a><span data-ttu-id="b33e6-168">受信パイプラインの実行</span><span class="sxs-lookup"><span data-stu-id="b33e6-168">Executing Receive Pipeline</span></span>  
 <span data-ttu-id="b33e6-169">次の手順としては、オーケストレーションで受信したメッセージの受信パイプラインを実行するロジックを追加します。</span><span class="sxs-lookup"><span data-stu-id="b33e6-169">As a next step, we will add logic to execute a receive pipeline for the message that was received in orchestration.</span></span> <span data-ttu-id="b33e6-170">これを行うには、最初に宣言のスコープ内で Microsoft.XLANGs.Pipeline.ReceivePipelineOutputMessages の種類の変数 (rcvpipeoutput)。</span><span class="sxs-lookup"><span data-stu-id="b33e6-170">To do this, first we declare a variable (called RcvPipeOutput) of type Microsoft.XLANGs.Pipeline.ReceivePipelineOutputMessages within the scope.</span></span> <span data-ttu-id="b33e6-171">この変数は、順番にパイプライン出力メッセージを受信できるようにする列挙子です。</span><span class="sxs-lookup"><span data-stu-id="b33e6-171">This variable is an enumerator that allows us to cycle through the receive pipeline output messages.</span></span> <span data-ttu-id="b33e6-172">オーケストレーションからパイプラインの実行の他のすべての種類と、この型にアクセスするために必要です、次のアセンブリへの参照を追加することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b33e6-172">Note that in order to access this type, as well as all the other types for execution of pipelines from orchestration, you need to add references to the following assemblies:</span></span>  
  
- <span data-ttu-id="b33e6-173">Microsoft.XLANGs.Pipeline.dll</span><span class="sxs-lookup"><span data-stu-id="b33e6-173">Microsoft.XLANGs.Pipeline.dll</span></span>  
  
- <span data-ttu-id="b33e6-174">Microsoft.biztalk.pipeline.dll 内</span><span class="sxs-lookup"><span data-stu-id="b33e6-174">Microsoft.BizTalk.Pipeline.dll</span></span>  
  
  <span data-ttu-id="b33e6-175">常に、受信パイプラインは正常に実行される保証はありません。</span><span class="sxs-lookup"><span data-stu-id="b33e6-175">There is no guarantee that the receive pipeline will always execute successfully.</span></span> <span data-ttu-id="b33e6-176">メッセージあります不適切な形式では、パイプライン処理の失敗が発生します。</span><span class="sxs-lookup"><span data-stu-id="b33e6-176">Sometimes messages may be malformed, which would cause the pipeline processing to fail.</span></span> <span data-ttu-id="b33e6-177">パイプラインには、オーケストレーションでの実行が失敗するとスローされる例外をキャッチできますが、エラー処理ロジックを実行できます。</span><span class="sxs-lookup"><span data-stu-id="b33e6-177">When a pipeline fails execution in the orchestration, there is an exception thrown that can be caught and the error handling logic can be performed.</span></span> <span data-ttu-id="b33e6-178">パイプラインによってスローされる例外をキャッチするためには、例外処理を使用する非アトミックのスコープ内のパイプラインを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b33e6-178">In order for us to catch the exception thrown by pipeline, we need to execute the pipeline within a non-atomic scope with an exception handling.</span></span> <span data-ttu-id="b33e6-179">パイプラインを実行する実際のコードは、そのスコープ内で式図形から呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="b33e6-179">The actual code to execute pipeline is invoked from an expression shape within that scope.</span></span>  
  
  <span data-ttu-id="b33e6-180">ExecuteRcvPipe 式図形で、受信パイプラインを実行するコードの次の行に記述します。</span><span class="sxs-lookup"><span data-stu-id="b33e6-180">In the ExecuteRcvPipe expression shape, write the following line of code to execute the receive pipeline:</span></span>  
  
```  
RcvPipeOutput = Microsoft.XLANGs.Pipeline.XLANGPipelineManager.ExecuteReceivePipeline(typeof(PipelinesAndSchemas.FFReceivePipeline), InputInterchange);  
```  
  
 <span data-ttu-id="b33e6-181">この行のコードの詳細を分析してみましょう。</span><span class="sxs-lookup"><span data-stu-id="b33e6-181">Let's analyze this line of code in more detail.</span></span> <span data-ttu-id="b33e6-182">ご覧のように、静的メソッド ExecuteReceivePipeline をパラメーターとして受信パイプラインを実行して、入力メッセージの種類を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="b33e6-182">As you can see, we call a static method ExecuteReceivePipeline that takes as a parameter a type of receive pipeline to execute and an input message.</span></span> <span data-ttu-id="b33e6-183">その結果、出力メッセージのセットを持つ列挙子オブジェクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="b33e6-183">As a result, it produces an enumerator object with the set of output messages.</span></span> <span data-ttu-id="b33e6-184">結果は、前にこのスコープで定義した ReceivePipelineOutputMessages 型の変数に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="b33e6-184">The result is assigned to a variable of type ReceivePipelineOutputMessages that was defined in this scope before.</span></span>  
  
 <span data-ttu-id="b33e6-185">例外処理パイプラインの実行スコープのブロックも含めました。</span><span class="sxs-lookup"><span data-stu-id="b33e6-185">We have also included an exception handling block for the pipeline execution scope.</span></span> <span data-ttu-id="b33e6-186">このブロックは、XLANGPipelineManagerException 型の例外をキャッチし、簡単にするためにカスタマイズされたエラー メッセージがオーケストレーション インスタンスを終了します。</span><span class="sxs-lookup"><span data-stu-id="b33e6-186">This block catches the exception of type XLANGPipelineManagerException and then for simplicity reasons just terminates an orchestration instance with customized error message.</span></span>  
  
 <span data-ttu-id="b33e6-187">複雑なシナリオは、追加のエラー処理を実行できますここでは、生成など、エラー通知メッセージと、ビジネス ユーザーや電子メールを使用して管理者に送信します。</span><span class="sxs-lookup"><span data-stu-id="b33e6-187">In more complex scenarios, additional error handling can be performed here, such as generation or the error notification message and sending it to a business user or administrator using email.</span></span>  
  
#### <a name="transforming-pipeline-output-messages"></a><span data-ttu-id="b33e6-188">変換のパイプライン出力メッセージ</span><span class="sxs-lookup"><span data-stu-id="b33e6-188">Transforming Pipeline Output Messages</span></span>  
 <span data-ttu-id="b33e6-189">パイプラインが実行されているし、逆アセンブルされたメッセージのセットが生成されて、各出力メッセージを別の形式に変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b33e6-189">After the pipeline has been executed and the set of disassembled messages has been produced, we need to transform each output message into a different format.</span></span>  
  
 <span data-ttu-id="b33e6-190">オーケストレーションで変換を使用するには、変換入力し、出力-2 つのメッセージを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b33e6-190">To use transformation in orchestration we need to define two messages – transformation input and output.</span></span> <span data-ttu-id="b33e6-191">アトミックのスコープ内でのメッセージを定義します。</span><span class="sxs-lookup"><span data-stu-id="b33e6-191">We will define those messages within the atomic scope.</span></span> <span data-ttu-id="b33e6-192">TmpMessageIn という変換入力メッセージは、PipelinesAndSchemas.PO 型になります。</span><span class="sxs-lookup"><span data-stu-id="b33e6-192">The transformation input message called TmpMessageIn will be of type PipelinesAndSchemas.PO.</span></span> <span data-ttu-id="b33e6-193">TmpMessageOut という変換出力メッセージは、PipeliensAndSchemas.Invoice 型になります。</span><span class="sxs-lookup"><span data-stu-id="b33e6-193">The transformation output message called TmpMessageOut will be of type PipeliensAndSchemas.Invoice.</span></span> <span data-ttu-id="b33e6-194">マップ、PO2Invoice.btm PipelinesAndSchemas プロジェクトで定義されているが適用されます。</span><span class="sxs-lookup"><span data-stu-id="b33e6-194">We will apply the map PO2Invoice.btm that is defined in project PipelinesAndSchemas.</span></span>  
  
 <span data-ttu-id="b33e6-195">各パイプライン出力メッセージにマップするため、ループ内で変換を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b33e6-195">As we want to map each pipeline output message we need to perform transformation in the loop.</span></span> <span data-ttu-id="b33e6-196">ここでは、ループ図形を以下の終了条件を使います。</span><span class="sxs-lookup"><span data-stu-id="b33e6-196">We will use a loop shape with the condition for exiting as below:</span></span>  
  
```  
RcvPipeOutput.MoveNext()  
```  
  
 <span data-ttu-id="b33e6-197">MoveNext() メソッドは、パイプライン出力メッセージのコレクション内で移動できる IEnumerator .NET インターフェイスの標準的な方法です。</span><span class="sxs-lookup"><span data-stu-id="b33e6-197">MoveNext() method is a standard method of IEnumerator .NET interface that allows to move within the collection of pipeline output messages.</span></span> <span data-ttu-id="b33e6-198">コレクションの末尾に達すると false を返します。</span><span class="sxs-lookup"><span data-stu-id="b33e6-198">When it reaches the end of collection it returns false.</span></span>  
  
 <span data-ttu-id="b33e6-199">最初の構築図形は、パイプライン出力メッセージから、オーケストレーション メッセージ TmpMessageIn を構築に使用されます。</span><span class="sxs-lookup"><span data-stu-id="b33e6-199">The first construct shape is used to construct an orchestration message TmpMessageIn out of the pipeline output message.</span></span>  
  
 <span data-ttu-id="b33e6-200">構築図形内のコード:</span><span class="sxs-lookup"><span data-stu-id="b33e6-200">The code in the construct shape:</span></span>  
  
```  
TmpMessageIn = null;  
RcvPipeOutput.GetCurrent(TmpMessageIn);  
```  
  
 <span data-ttu-id="b33e6-201">このコードではオーケストレーションのメッセージを null に設定し、パイプライン出力メッセージ コレクションから現在のメッセージに設定を最初に初期化します。</span><span class="sxs-lookup"><span data-stu-id="b33e6-201">In this code we first initialize orchestration message to null and then set it to the current message from the pipeline output messages collection.</span></span>  
  
 <span data-ttu-id="b33e6-202">2 番目の構築図形、TmpMessageIn の実際の変換が行われると型の TmpMessageOut PipelinesAndSchemas.Invoice が構築されます。</span><span class="sxs-lookup"><span data-stu-id="b33e6-202">In second construct shape the actual transformation of the TmpMessageIn is performed and the TmpMessageOut of type PipelinesAndSchemas.Invoice is constructed.</span></span>  
  
#### <a name="executing-send-pipeline"></a><span data-ttu-id="b33e6-203">送信パイプラインの実行</span><span class="sxs-lookup"><span data-stu-id="b33e6-203">Executing Send Pipeline</span></span>  
 <span data-ttu-id="b33e6-204">オーケストレーションの最後の処理手順では、すべての変換後の xml メッセージを 1 つのフラット ファイル インターチェンジにアセンブルするフラット ファイル送信パイプラインを実行します。</span><span class="sxs-lookup"><span data-stu-id="b33e6-204">Last processing step in orchestration is to execute flat file send pipeline to assemble all the transformed xml messages into one flat file interchange.</span></span>  
  
 <span data-ttu-id="b33e6-205">送信を実行するためには、パイプライン Microsoft.XLANGs.Pipeline.SendPipelineInputMessages 型の変数を使用する必要がありますには、送信パイプラインで処理する必要があるオーケストレーション メッセージのコレクションを保持しなければが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="b33e6-205">In order to execute a send pipeline we need to use a variable of type Microsoft.XLANGs.Pipeline.SendPipelineInputMessages called SendPipeInput that will hold a collection of orchestration messages that need to be processed in a send pipeline.</span></span>  
  
 <span data-ttu-id="b33e6-206">変換を実行したループの最後の式では、送信パイプラインのメッセージのコレクションに変換された各メッセージを追加するコードを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="b33e6-206">In the last expression of the loop where we performed transformation we will write a code that will add each transformed message to a message collection for send pipeline:</span></span>  
  
```  
SendPipeInput.Add(TmpMessageOut);  
```  
  
 <span data-ttu-id="b33e6-207">実行する部分と同様には、送信パイプラインの実行のコードが例外処理ブロックと共に非アトミックのスコープ内に配置パイプラインが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b33e6-207">Similar to the part where we execute receive pipeline the code for execution of send pipeline is placed within a non-atomic scope with exception handling block.</span></span> <span data-ttu-id="b33e6-208">送信パイプラインの実行コードは、構築ブロックのメッセージの割り当て図形にあります。</span><span class="sxs-lookup"><span data-stu-id="b33e6-208">The send pipeline execution code is located in the message assignment shape of the construct block.</span></span>  
  
```  
OutputInterchange = null;  
Microsoft.XLANGs.Pipeline.XLANGPipelineManager.ExecuteSendPipeline(typeof(PipelinesAndSchemas.FFSendPipeline), SendPipeInput, OutputInterchange);  
```  
  
 <span data-ttu-id="b33e6-209">型を構築するコンス トラクター ブロックが使用される依存しない (System.Xml.XmlDocument など) パイプライン出力メッセージ outputinterchange を構築します。</span><span class="sxs-lookup"><span data-stu-id="b33e6-209">The construct block is used to construct type agnostic (i.e. System.Xml.XmlDocument) pipeline output message OutputInterchange.</span></span> <span data-ttu-id="b33e6-210">メッセージの割り当て図形では、新しく構築されたメッセージは null に初期化されます。</span><span class="sxs-lookup"><span data-stu-id="b33e6-210">Then in the message assignment shape the newly constructed message is initialized to null.</span></span> <span data-ttu-id="b33e6-211">その後、送信パイプラインを実行する静的メソッドの ExecuteSendPipeline が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="b33e6-211">After that the static method ExecuteSendPipeline is invoked to execute a send pipeline.</span></span> <span data-ttu-id="b33e6-212">このメソッドは、入力メッセージ、およびパイプラインの出力を格納する出力メッセージへの参照を実行する送信パイプラインの種類をパラメーターとして受け取ります。</span><span class="sxs-lookup"><span data-stu-id="b33e6-212">This method takes as a parameter a type of the send pipeline to execute, the input message and the reference to output message where the pipeline output will be stored.</span></span>  
  
 <span data-ttu-id="b33e6-213">同様に、受信パイプラインの実行、ここでもある例外処理パイプラインの実行スコープのブロック。</span><span class="sxs-lookup"><span data-stu-id="b33e6-213">As with the execution of the receive pipeline, here we also have an exception handling block for the pipeline execution scope.</span></span> <span data-ttu-id="b33e6-214">このブロックは、XLANGPipelineManagerException 型の例外をキャッチし、簡単にするためにカスタマイズされたエラー メッセージがオーケストレーション インスタンスを終了します。</span><span class="sxs-lookup"><span data-stu-id="b33e6-214">This block catches the exception of type XLANGPipelineManagerException and then for simplicity reasons just terminates an orchestration instance with customized error message.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="b33e6-215">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="b33e6-215">Where to Find This Sample</span></span>  
 <span data-ttu-id="b33e6-216">次の表では、このサンプルのファイルを示します。</span><span class="sxs-lookup"><span data-stu-id="b33e6-216">The following table lists the files for this sample.</span></span>  
  
|<span data-ttu-id="b33e6-217">ファイル</span><span class="sxs-lookup"><span data-stu-id="b33e6-217">File(s)</span></span>|<span data-ttu-id="b33e6-218">説明</span><span class="sxs-lookup"><span data-stu-id="b33e6-218">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b33e6-219">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="b33e6-219">Cleanup.bat</span></span>|<span data-ttu-id="b33e6-220">アセンブリを展開解除し、グローバル アセンブリ キャッシュ (GAC) から削除するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="b33e6-220">Used to undeploy assemblies and remove them from the global assembly cache (GAC).</span></span><br /><br /> <span data-ttu-id="b33e6-221">送信ポートと受信ポートが削除されます。</span><span class="sxs-lookup"><span data-stu-id="b33e6-221">Removes send and receive ports.</span></span><br /><br /> <span data-ttu-id="b33e6-222">必要に応じて、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。</span><span class="sxs-lookup"><span data-stu-id="b33e6-222">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="b33e6-223">ComposedMessageProcessor.sln</span><span class="sxs-lookup"><span data-stu-id="b33e6-223">ComposedMessageProcessor.sln</span></span>|<span data-ttu-id="b33e6-224">サンプルの Visual Studio ソリューション ファイルです。</span><span class="sxs-lookup"><span data-stu-id="b33e6-224">Visual Studio solution file for the sample.</span></span>|  
|<span data-ttu-id="b33e6-225">ComposedMessageProcessorBinding.xml</span><span class="sxs-lookup"><span data-stu-id="b33e6-225">ComposedMessageProcessorBinding.xml</span></span>|<span data-ttu-id="b33e6-226">サンプルのバインド ファイルです。</span><span class="sxs-lookup"><span data-stu-id="b33e6-226">Binding file for the sample.</span></span>|  
|<span data-ttu-id="b33e6-227">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="b33e6-227">Setup.bat</span></span>|<span data-ttu-id="b33e6-228">このサンプルをビルドおよび初期化するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="b33e6-228">Used to build and initialize this sample.</span></span>|  
|<span data-ttu-id="b33e6-229">Orchestration フォルダー。</span><span class="sxs-lookup"><span data-stu-id="b33e6-229">In Orchestration folder:</span></span><br /><br /> <span data-ttu-id="b33e6-230">CMP.odx</span><span class="sxs-lookup"><span data-stu-id="b33e6-230">CMP.odx</span></span>|<span data-ttu-id="b33e6-231">逆アセンブラーのメッセージを受信パイプラインを実行しているオーケストレーションが逆アセンブルされた各メッセージを変換し、し、送信メッセージをインターチェンジにアセンブルするパイプラインを実行します。</span><span class="sxs-lookup"><span data-stu-id="b33e6-231">Orchestration that runs the receive pipeline to disassembler message, transforms each disassembled message and then runs send pipeline to assemble messages into an interchange.</span></span>|  
|<span data-ttu-id="b33e6-232">Orchestration フォルダー。</span><span class="sxs-lookup"><span data-stu-id="b33e6-232">In Orchestration folder:</span></span><br /><br /> <span data-ttu-id="b33e6-233">Orchestration.btproj</span><span class="sxs-lookup"><span data-stu-id="b33e6-233">Orchestration.btproj</span></span>|<span data-ttu-id="b33e6-234">オーケストレーションの BizTalk プロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="b33e6-234">BizTalk project for orchestration.</span></span>|  
|<span data-ttu-id="b33e6-235">Orchestration フォルダー。</span><span class="sxs-lookup"><span data-stu-id="b33e6-235">In Orchestration folder:</span></span><br /><br /> <span data-ttu-id="b33e6-236">SuspendMessage.odx</span><span class="sxs-lookup"><span data-stu-id="b33e6-236">SuspendMessage.odx</span></span>|<span data-ttu-id="b33e6-237">パイプライン処理に失敗したメッセージを中断するためのオーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="b33e6-237">Orchestration used for suspending messages that fail pipeline processing.</span></span>|  
|<span data-ttu-id="b33e6-238">PipelinesAndSchemas フォルダー内: </span><span class="sxs-lookup"><span data-stu-id="b33e6-238">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="b33e6-239">CMPInput.xml、CMPOutput.xml</span><span class="sxs-lookup"><span data-stu-id="b33e6-239">CMPInput.xml, CMPOutput.xml</span></span>|<span data-ttu-id="b33e6-240">入力と出力はドキュメント、サンプルのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="b33e6-240">Input and output document instances for the sample.</span></span>|  
|<span data-ttu-id="b33e6-241">PipelinesAndSchemas フォルダー内: </span><span class="sxs-lookup"><span data-stu-id="b33e6-241">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="b33e6-242">FFReceivePipeline.btp、FFSendPipeline.btp</span><span class="sxs-lookup"><span data-stu-id="b33e6-242">FFReceivePipeline.btp, FFSendPipeline.btp</span></span>|<span data-ttu-id="b33e6-243">受信し、送信パイプラインとフラット ファイル コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="b33e6-243">Receive and send pipelines with flat file components.</span></span> <span data-ttu-id="b33e6-244">これらのパイプラインは、オーケストレーション内で実行されます。</span><span class="sxs-lookup"><span data-stu-id="b33e6-244">These pipelines are run within orchestration.</span></span>|  
|<span data-ttu-id="b33e6-245">PipelinesAndSchemas フォルダー内: </span><span class="sxs-lookup"><span data-stu-id="b33e6-245">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="b33e6-246">Invoice.xsd、InvoiceHeader.xsd</span><span class="sxs-lookup"><span data-stu-id="b33e6-246">Invoice.xsd, InvoiceHeader.xsd</span></span>|<span data-ttu-id="b33e6-247">出力ドキュメント、およびヘッダーのフラット ファイル スキーマです。</span><span class="sxs-lookup"><span data-stu-id="b33e6-247">Flat file schemas for the output document and header.</span></span>|  
|<span data-ttu-id="b33e6-248">PipelinesAndSchemas フォルダー内: </span><span class="sxs-lookup"><span data-stu-id="b33e6-248">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="b33e6-249">PO.xsd、POHeader.xsd</span><span class="sxs-lookup"><span data-stu-id="b33e6-249">PO.xsd, POHeader.xsd</span></span>|<span data-ttu-id="b33e6-250">入力ドキュメントとヘッダーのフラット ファイル スキーマです。</span><span class="sxs-lookup"><span data-stu-id="b33e6-250">Flat file schemas for the input document and header.</span></span>|  
|<span data-ttu-id="b33e6-251">PipelinesAndSchemas フォルダー内: </span><span class="sxs-lookup"><span data-stu-id="b33e6-251">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="b33e6-252">PropertySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="b33e6-252">PropertySchema.xsd</span></span>|<span data-ttu-id="b33e6-253">サンプルのプロパティ スキーマです。</span><span class="sxs-lookup"><span data-stu-id="b33e6-253">Property schema for the sample.</span></span>|  
  
## <a name="building-and-initializing-the-sample"></a><span data-ttu-id="b33e6-254">サンプルのビルドおよび初期化</span><span class="sxs-lookup"><span data-stu-id="b33e6-254">Building and Initializing the Sample</span></span>  
 <span data-ttu-id="b33e6-255">次の手順を使用して、ビルドして、Compose サンプルを初期化します。</span><span class="sxs-lookup"><span data-stu-id="b33e6-255">Use the following procedure to build and initialize the Compose sample.</span></span>  
  
#### <a name="to-build-and-initialize-the-compose-sample"></a><span data-ttu-id="b33e6-256">Compose サンプルをビルドして初期化するには</span><span class="sxs-lookup"><span data-stu-id="b33e6-256">To build and initialize the Compose sample</span></span>  
  
1.  <span data-ttu-id="b33e6-257">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="b33e6-257">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="b33e6-258">\<パスのサンプル\>\Pipelines\ComposedMessageProcessor</span><span class="sxs-lookup"><span data-stu-id="b33e6-258">\<Samples Path\>\Pipelines\ComposedMessageProcessor</span></span>  
  
2.  <span data-ttu-id="b33e6-259">ファイルは、次の操作を実行します。 Setup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="b33e6-259">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="b33e6-260">入力 (In) フォルダと出力 (Out) フォルダーに、このサンプル用のフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="b33e6-260">Creates the input (In) and output (Out) folders for this sample in the folder:</span></span>  
  
         <span data-ttu-id="b33e6-261">\<パスのサンプル\>\Pipelines\ComposedMessageProcessor</span><span class="sxs-lookup"><span data-stu-id="b33e6-261">\<Samples Path\>\Pipelines\ComposedMessageProcessor</span></span>  
  
    -   <span data-ttu-id="b33e6-262">このサンプルの Visual Studio プロジェクトをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="b33e6-262">Compiles the Visual Studio projects for this sample.</span></span>  
  
    -   <span data-ttu-id="b33e6-263">"CMP Sample"と呼ばれる新しいアプリケーションを作成し、そこにサンプル アセンブリを展開します。</span><span class="sxs-lookup"><span data-stu-id="b33e6-263">Creates a new application called "CMP Sample" and deploys the sample assemblies into it.</span></span>  
  
    -   <span data-ttu-id="b33e6-264">作成し、バインド、BizTalk Server 受信場所と送信ポートと受信ポート。</span><span class="sxs-lookup"><span data-stu-id="b33e6-264">Creates and binds the BizTalk Server receive location, and the send and receive ports.</span></span>  
  
    -   <span data-ttu-id="b33e6-265">参加しオーケストレーションを開始、により、受信場所および送信ポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="b33e6-265">Enlists and starts orchestration, enables the receive location, and starts the send port.</span></span>  
  
         <span data-ttu-id="b33e6-266">開き、Setup.bat ファイルを実行することがなくこのサンプルでは、プロジェクトをビルドする場合は、まず、.NET Framework の厳密名ユーティリティ (sn.exe) を使用して厳密な名前キーのペアを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b33e6-266">If you choose to open and build the projects in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name utility (sn.exe).</span></span> <span data-ttu-id="b33e6-267">このキー ペアが結果として得られるアセンブリの署名に使用されるを使用します。</span><span class="sxs-lookup"><span data-stu-id="b33e6-267">Use this key pair is used to sign the resulting assemblies.</span></span>  
  
3.  <span data-ttu-id="b33e6-268">このサンプルを実行する前に、BizTalk Server がビルドおよび初期化プロセス中にエラーを報告しないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="b33e6-268">Before attempting to run this sample, confirm that BizTalk Server did not report any errors during the build and initialization process.</span></span>  
  
     <span data-ttu-id="b33e6-269">Setup.bat による変更を元に戻すには、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="b33e6-269">To undo changes made by Setup.bat, you must do the following:</span></span>  
  
    1.  <span data-ttu-id="b33e6-270">停止して、BizTalk Server 管理コンソールからのホスト インスタンスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="b33e6-270">Stop and restart the host instance from the BizTalk Server Administration console.</span></span>  
  
    2.  <span data-ttu-id="b33e6-271">Cleanup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="b33e6-271">Run Cleanup.bat.</span></span> <span data-ttu-id="b33e6-272">Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。</span><span class="sxs-lookup"><span data-stu-id="b33e6-272">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  
  
## <a name="running-the-sample"></a><span data-ttu-id="b33e6-273">サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="b33e6-273">Running the sample</span></span>  
 <span data-ttu-id="b33e6-274">ComposedMessageProcessor サンプルを実行するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="b33e6-274">Use the following procedure to run the ComposedMessageProcessor sample.</span></span>  
  
#### <a name="to-run-the-composedmessageprocessor-sample"></a><span data-ttu-id="b33e6-275">ComposedMessageProcessor サンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="b33e6-275">To run the ComposedMessageProcessor sample</span></span>  
  
1.  <span data-ttu-id="b33e6-276">PipelinesAndSchemas フォルダー内にある CMPInput.txt テキスト ファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="b33e6-276">Copy the text file CMPInput.txt located in the PipelinesAndSchemas folder.</span></span> <span data-ttu-id="b33e6-277">このファイルをフォルダーに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="b33e6-277">Paste the file into the folder In.</span></span>  
  
2.  <span data-ttu-id="b33e6-278">テキスト ファイルが Out フォルダに作成されたことを確認します。このファイルには、CMPInput.txt と同じレコードが含まれていますが、ファイル内のデータの形式が異なります。</span><span class="sxs-lookup"><span data-stu-id="b33e6-278">Observe the text file created in the folder Out. This file contains the same records as the CMPInput.txt, but the format of data in the file is different.</span></span>  
  
     <span data-ttu-id="b33e6-279">メッセージは、BizTalk Server を通過して、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="b33e6-279">As the message passes through the BizTalk Server, the following happens:</span></span>  
  
    1.  <span data-ttu-id="b33e6-280">メッセージは、逆アセンブルされ、XML メッセージに変換を取得します。</span><span class="sxs-lookup"><span data-stu-id="b33e6-280">The message gets disassembled and converted into XML messages.</span></span> <span data-ttu-id="b33e6-281">各メッセージは、別の形式にマップされます。</span><span class="sxs-lookup"><span data-stu-id="b33e6-281">Each message is mapped to a different format.</span></span>  
  
    2.  <span data-ttu-id="b33e6-282">マップされたすべてのメッセージは一緒にアセンブルし、フラット ファイル形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="b33e6-282">All mapped messages are assembled together and converted into the flat file format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b33e6-283">参照</span><span class="sxs-lookup"><span data-stu-id="b33e6-283">See Also</span></span>  
 [<span data-ttu-id="b33e6-284">パイプライン (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="b33e6-284">Pipelines (BizTalk Server Samples Folder)</span></span>](../core/pipelines-biztalk-server-samples-folder.md)