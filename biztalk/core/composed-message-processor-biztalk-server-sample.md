---
title: "メッセージ プロセッサ (BizTalk Server サンプル) で構成される |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipelines, examples
- messages, processing
- messages, aggregated
- examples, pipelines
ms.assetid: a0f87f98-6f5f-4edb-8f65-49d22df5de97
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3853a5b903215b6f716a13c33727e60c67107b2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="composed-message-processor-biztalk-server-sample"></a><span data-ttu-id="99dcd-102">構成済みメッセージ プロセッサ (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="99dcd-102">Composed Message Processor (BizTalk Server Sample)</span></span>
<span data-ttu-id="99dcd-103">このサンプルの目的は、集計メッセージの個別の品目を処理する構成済みメッセージ プロセッサ アプリケーションをビルドすることです。</span><span class="sxs-lookup"><span data-stu-id="99dcd-103">The purpose of this sample is to build a composed message processor application that processes individual line items from aggregated messages.</span></span>  
  
 <span data-ttu-id="99dcd-104">具体的には、以下の処理を行うオーケストレーション スケジュールをビルドします。</span><span class="sxs-lookup"><span data-stu-id="99dcd-104">Specifically we will build an orchestration schedule that:</span></span>  
  
1.  <span data-ttu-id="99dcd-105">複数の注文書で構成されるバッチ インターチェンジ メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="99dcd-105">Receives a batched interchange message consisting of multiple purchase orders.</span></span>  
  
2.  <span data-ttu-id="99dcd-106">インターチェンジ メッセージを個別の注文書ドキュメントに逆アセンブルします。</span><span class="sxs-lookup"><span data-stu-id="99dcd-106">Disassembles the interchange message into individual purchase order documents.</span></span>  
  
3.  <span data-ttu-id="99dcd-107">各ドキュメントを処理し、各注文書を請求書メッセージに変換します。</span><span class="sxs-lookup"><span data-stu-id="99dcd-107">Processes each document – converts each purchase order into an invoice message.</span></span>  
  
4.  <span data-ttu-id="99dcd-108">すべての請求書メッセージをバッチ インターチェンジにアセンブルします。</span><span class="sxs-lookup"><span data-stu-id="99dcd-108">Assembles all the invoice messages into a batched interchange.</span></span>  
  
 <span data-ttu-id="99dcd-109">ステップ 3 はサンプル用であるため、簡略化されています。</span><span class="sxs-lookup"><span data-stu-id="99dcd-109">Step #3 is simplified for the sample purposes.</span></span> <span data-ttu-id="99dcd-110">たとえば、より複雑なアプリケーションの場合、オーケストレーションが逆アセンブルした注文書を異なるバックエンド在庫システムに送信し、すべての応答を収集した後で、応答をバッチ化された 1 つの請求書メッセージに集計することがあります。</span><span class="sxs-lookup"><span data-stu-id="99dcd-110">For example, in more complex applications, an orchestration may send disassembled purchase orders to different back-end inventory systems and then after collecting all the responses, aggregate them into one batched invoice message.</span></span>  
  
 <span data-ttu-id="99dcd-111">構成済みメッセージ プロセッサのパターンの詳細については、[1] を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99dcd-111">For more information on the composed message processor pattern refer to [1].</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="99dcd-112">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="99dcd-112">What This Sample Does</span></span>  
 <span data-ttu-id="99dcd-113">サンプル ソリューションには 2 つのプロジェクトがあります。次のセクションで、両方のプロジェクトについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="99dcd-113">There are two projects within the sample solution, both of which are described in detail in the following sections.</span></span>  
  
### <a name="pipelines-and-schemas"></a><span data-ttu-id="99dcd-114">パイプラインとスキーマ</span><span class="sxs-lookup"><span data-stu-id="99dcd-114">Pipelines and Schemas</span></span>  
 <span data-ttu-id="99dcd-115">パイプライン、およびスキーマ プロジェクトには以下が含まれています。</span><span class="sxs-lookup"><span data-stu-id="99dcd-115">Pipelines and schemas project contains:</span></span>  
  
-   <span data-ttu-id="99dcd-116">入力注文書インターチェンジと出力請求書インターチェンジのフラット ファイル スキーム</span><span class="sxs-lookup"><span data-stu-id="99dcd-116">Flat file schemas for input purchase order interchange and for output invoice interchange.</span></span>  
  
-   <span data-ttu-id="99dcd-117">注文書ドキュメントを請求書ドキュメントに変換するマップ</span><span class="sxs-lookup"><span data-stu-id="99dcd-117">Map to transform purchase order document into an invoice document.</span></span>  
  
-   <span data-ttu-id="99dcd-118">受信および送信パイプラインです。</span><span class="sxs-lookup"><span data-stu-id="99dcd-118">Receive and send pipelines.</span></span>  
  
#### <a name="flat-file-schemas-for-input-and-output-interchanges"></a><span data-ttu-id="99dcd-119">入力インターチェンジと出力インターチェンジのフラット ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="99dcd-119">Flat File Schemas For Input and Output Interchanges</span></span>  
 <span data-ttu-id="99dcd-120">サンプル アプリケーションでは、フラット ファイル形式のインターチェンジを使用します。</span><span class="sxs-lookup"><span data-stu-id="99dcd-120">Our sample application will be working with the interchanges in the flat file format.</span></span> <span data-ttu-id="99dcd-121">注文書インターチェンジと請求書インターチェンジの例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="99dcd-121">Below are the examples of the purchase order interchange and invoice interchange:</span></span>  
  
 <span data-ttu-id="99dcd-122">注文書インターチェンジ (CMPInput.txt):</span><span class="sxs-lookup"><span data-stu-id="99dcd-122">Purchase order interchange (CMPInput.txt):</span></span>  
  
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
  
 <span data-ttu-id="99dcd-123">インターチェンジ、または注文書ドキュメントには、そこに含まれるドキュメントの種類を識別するヘッダーがあります。</span><span class="sxs-lookup"><span data-stu-id="99dcd-123">The interchange, or purchase order document, has a header that identifies what type of the documents it contains:</span></span>  
  
```  
Northwind Shipping  
Batch type:Purchase Orders  
```  
  
 <span data-ttu-id="99dcd-124">このインターチェンジは、3 つの注文書ドキュメントで構成されています。</span><span class="sxs-lookup"><span data-stu-id="99dcd-124">This interchange consist of three purchase order documents.</span></span> <span data-ttu-id="99dcd-125">1 つのインスタンスを構成する情報は、以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="99dcd-125">One instance consists of the information shown below.</span></span> <span data-ttu-id="99dcd-126">請求先住所や配送先住所、および注文したアイテムの一覧などの情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="99dcd-126">As you can see, it contains such information as address for billing and shipping as well as the list of items that were ordered.</span></span>  
  
```  
PO1999-10-20  
US    Alice Smith    123 Maple Street    Mill Valley    CA 90952  
US    Robert Smith   8 Oak Avenue        Old Town       PA 95819  
Hurry, my lawn is going wild!  
ITEMS,ITEM872-AA|Lawnmower|1|148.95|Confirm this is electric,ITEM926-AA|Baby Monitor|1|39.98|Confirm this is electric|1999-10-21  
```  
  
 <span data-ttu-id="99dcd-127">ここで生成する請求書インターチェンジは、以下のようになります。</span><span class="sxs-lookup"><span data-stu-id="99dcd-127">The invoice interchange we want to generate for this should look like the following:</span></span>  
  
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
  
 <span data-ttu-id="99dcd-128">このインターチェンジには注文書インターチェンジ内の情報のサブセットが含まれ、さらに、インターチェンジの形式だけでなく、ヘッダーの形式も異なっています。</span><span class="sxs-lookup"><span data-stu-id="99dcd-128">This interchange contains a subset of information that was in purchase order interchange and also the format of the interchange as well as format of the header are different.</span></span>  
  
 <span data-ttu-id="99dcd-129">ヘッダーは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="99dcd-129">The header is as follows:</span></span>  
  
```  
Northwest Shipping  
DocumentTypes:Invoices  
```  
  
 <span data-ttu-id="99dcd-130">また、ドキュメント インスタンスには次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="99dcd-130">And the document instance includes the following:</span></span>  
  
```  
INVOICE1999-10-20  
BILLTO,US,Alice Smith,123 Maple Street,Mill Valley,CA,90952  
872-AA    Lawnmower         1    148.95    Confirm this is electric  
926-AA    Baby Monitor      1    39.98     Confirm this is electric  
```  
  
 <span data-ttu-id="99dcd-131">まず、以下のフラット ファイル スキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="99dcd-131">First thing we need to create flat file schemas for:</span></span>  
  
-   <span data-ttu-id="99dcd-132">注文書ドキュメント (PO.xsd)</span><span class="sxs-lookup"><span data-stu-id="99dcd-132">Purchase order document (PO.xsd)</span></span>  
  
-   <span data-ttu-id="99dcd-133">請求書ドキュメント (Invoice.xsd)</span><span class="sxs-lookup"><span data-stu-id="99dcd-133">Invoice document (Invoice.xsd)</span></span>  
  
-   <span data-ttu-id="99dcd-134">注文書ヘッダー (POHeader.xsd)</span><span class="sxs-lookup"><span data-stu-id="99dcd-134">Purchase order header (POHeader.xsd)</span></span>  
  
-   <span data-ttu-id="99dcd-135">請求書ヘッダー (InvoiceHeader.xsd)</span><span class="sxs-lookup"><span data-stu-id="99dcd-135">Invoice header (InvoiceHeader.xsd)</span></span>  
  
 <span data-ttu-id="99dcd-136">このサンプルでは、フラット ファイル スキーマの作成プロセスについては説明しません。</span><span class="sxs-lookup"><span data-stu-id="99dcd-136">For this sample, we are not going to explain the process of creating flat file schemas.</span></span> <span data-ttu-id="99dcd-137">ドキュメント インスタンスからフラット ファイル スキーマを作成する方法については、「ドキュメント インスタンスからのフラット ファイル スキーマの作成」ドキュメント セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="99dcd-137">To learn how to create flat file schemas from document instances, refer to the "Creating flat file schemas from document instance" documentation section.</span></span>  
  
#### <a name="map-to-transform-purchase-order-document-into-invoice-document"></a><span data-ttu-id="99dcd-138">請求書ドキュメントに注文書ドキュメントを変換するマップ</span><span class="sxs-lookup"><span data-stu-id="99dcd-138">Map to Transform Purchase Order Document Into Invoice Document</span></span>  
 <span data-ttu-id="99dcd-139">マップ (PO2Invoice.btm) は、注文書のインスタンスを請求書ドキュメントに変換します。</span><span class="sxs-lookup"><span data-stu-id="99dcd-139">The map (PO2Invoice.btm) transforms an instance of the purchase order into an invoice document.</span></span>  
  
#### <a name="receive-and-send-pipelines"></a><span data-ttu-id="99dcd-140">受信パイプラインと送信パイプライン</span><span class="sxs-lookup"><span data-stu-id="99dcd-140">Receive and Send Pipelines</span></span>  
 <span data-ttu-id="99dcd-141">受信パイプライン (FFReceivePipeline.btp) には、注文書インターチェンジの処理に使用するフラット ファイル逆アセンブラ コンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="99dcd-141">The receive pipeline (FFReceivePipeline.btp) contains a flat file disassembler component that is used to process a purchase order interchange.</span></span> <span data-ttu-id="99dcd-142">特に CMPInput.txt ファイルのインターチェンジでは、インターチェンジ ヘッダーを削除し、3 つの注文書に対応する 3 つの XML ドキュメントを生成します。</span><span class="sxs-lookup"><span data-stu-id="99dcd-142">In particular, for the interchange in file CMPInput.txt, it removes the interchange header and produces three XML documents corresponding to three purchase orders.</span></span>  
  
 <span data-ttu-id="99dcd-143">受信パイプラインのフラット ファイル逆アセンブラは、以下のように構成されます。</span><span class="sxs-lookup"><span data-stu-id="99dcd-143">The flat file disassembler in the receive pipeline is configured as shown:</span></span>  
  
-   <span data-ttu-id="99dcd-144">**ドキュメント スキーマ:** PipelinesAndSchemas.PO</span><span class="sxs-lookup"><span data-stu-id="99dcd-144">**Document schema:** PipelinesAndSchemas.PO</span></span>  
  
-   <span data-ttu-id="99dcd-145">**ヘッダー スキーマ:** PipelinesAndSchemas.POHeader</span><span class="sxs-lookup"><span data-stu-id="99dcd-145">**Header schema:** PipelinesAndSchemas.POHeader</span></span>  
  
-   <span data-ttu-id="99dcd-146">**ヘッダーの保存:** False</span><span class="sxs-lookup"><span data-stu-id="99dcd-146">**Preserve header:** False</span></span>  
  
-   <span data-ttu-id="99dcd-147">**回復可能なインターチェンジ:** False</span><span class="sxs-lookup"><span data-stu-id="99dcd-147">**Recoverable interchange:** False</span></span>  
  
-   <span data-ttu-id="99dcd-148">**トレーラー スキーマ:** (なし)</span><span class="sxs-lookup"><span data-stu-id="99dcd-148">**Trailer schema:** (None)</span></span>  
  
-   <span data-ttu-id="99dcd-149">**ドキュメント構造の検証:** False</span><span class="sxs-lookup"><span data-stu-id="99dcd-149">**Validate document structure:** False</span></span>  
  
 <span data-ttu-id="99dcd-150">送信パイプライン (FFSendPipeline.btp) には、集計請求書インターチェンジの作成に使用するフラット ファイル アセンブラ コンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="99dcd-150">The send pipeline (FFSendPipeline.btp) contains a flat file assembler component that is used to create aggregated invoice interchange.</span></span>  
  
 <span data-ttu-id="99dcd-151">送信パイプラインのフラット ファイルアセンブラは、以下のように構成されます。</span><span class="sxs-lookup"><span data-stu-id="99dcd-151">The flat file assembler in send pipeline is configured as shown:</span></span>  
  
-   <span data-ttu-id="99dcd-152">**ドキュメント スキーマ:** PipelinesandSchemas.Invoice</span><span class="sxs-lookup"><span data-stu-id="99dcd-152">**Document schema:** PipelinesandSchemas.Invoice</span></span>  
  
-   <span data-ttu-id="99dcd-153">**ヘッダー スキーマ:** PipelinesAndSchemas.InvoiceHeader</span><span class="sxs-lookup"><span data-stu-id="99dcd-153">**Header schema:** PipelinesAndSchemas.InvoiceHeader</span></span>  
  
-   <span data-ttu-id="99dcd-154">**バイト オーダー マークの保存:** False</span><span class="sxs-lookup"><span data-stu-id="99dcd-154">**Preserve byte order mark:** False</span></span>  
  
-   <span data-ttu-id="99dcd-155">**文字セットをターゲット:** (なし)</span><span class="sxs-lookup"><span data-stu-id="99dcd-155">**Target charset:** (None)</span></span>  
  
-   <span data-ttu-id="99dcd-156">**トレーラー スキーマ:** (なし)</span><span class="sxs-lookup"><span data-stu-id="99dcd-156">**Trailer schema:** (None)</span></span>  
  
### <a name="orchestration-schedule"></a><span data-ttu-id="99dcd-157">オーケストレーション スケジュール</span><span class="sxs-lookup"><span data-stu-id="99dcd-157">Orchestration Schedule</span></span>  
 <span data-ttu-id="99dcd-158">オーケストレーション スケジュール (CMP.odx) は、すべてのメイン処理が行われる場所です。</span><span class="sxs-lookup"><span data-stu-id="99dcd-158">Orchestration schedule (CMP.odx) is where all the main processing happens.</span></span> <span data-ttu-id="99dcd-159">具体的には、次のアクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="99dcd-159">Specifically the following actions are performed:</span></span>  
  
-   <span data-ttu-id="99dcd-160">受信パイプラインを実行して、注文書インターチェンジを逆アセンブルする</span><span class="sxs-lookup"><span data-stu-id="99dcd-160">Receive pipeline is executed to disassemble purchase order interchange</span></span>  
  
-   <span data-ttu-id="99dcd-161">受信パイプラインのすべての出力メッセージを変換する</span><span class="sxs-lookup"><span data-stu-id="99dcd-161">Every output message of receive pipeline is transformed</span></span>  
  
-   <span data-ttu-id="99dcd-162">送信パイプラインを実行して、請求書インターチェンジをアセンブルする</span><span class="sxs-lookup"><span data-stu-id="99dcd-162">Send pipeline is executed to assemble an invoice interchange</span></span>  
  
#### <a name="creating-orchestration-schedule-and-defining-global-variables"></a><span data-ttu-id="99dcd-163">オーケストレーション スケジュールの作成とグローバル変数の定義</span><span class="sxs-lookup"><span data-stu-id="99dcd-163">Creating Orchestration Schedule and Defining Global Variables</span></span>  
 <span data-ttu-id="99dcd-164">オーケストレーションはフラット ファイル インターチェンジを入力として受信し、フラット ファイル インターチェンジを出力として送信します。</span><span class="sxs-lookup"><span data-stu-id="99dcd-164">Our orchestration will receive a flat file interchange as an input and will send a flat file interchange as an output.</span></span> <span data-ttu-id="99dcd-165">このため、入力メッセージと出力メッセージ (それぞれ InputInterchange および OutputInterchange) を、種類に関係のないメッセージ (System.Xml.XmlDocument 型を持つなど) として定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99dcd-165">Because of that, we need to define input and output messages (called InputInterchange and OutputInterchange respectively) as type agnostic (i.e. having type of System.Xml.XmlDocument).</span></span>  
  
 <span data-ttu-id="99dcd-166">また、メッセージを処理するアトミックのスコープも定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99dcd-166">Also, we need to define an atomic scope where we will process messages.</span></span> <span data-ttu-id="99dcd-167">これが必要なのは、受信パイプラインが、アトミックのスコープ内で実行可能であるためです。</span><span class="sxs-lookup"><span data-stu-id="99dcd-167">This is required because the receive pipeline can be executed within atomic scope.</span></span>  
  
#### <a name="executing-receive-pipeline"></a><span data-ttu-id="99dcd-168">受信パイプラインの実行</span><span class="sxs-lookup"><span data-stu-id="99dcd-168">Executing Receive Pipeline</span></span>  
 <span data-ttu-id="99dcd-169">次のステップではロジックを追加して、オーケストレーションで受信したメッセージの受信パイプラインを実行します。</span><span class="sxs-lookup"><span data-stu-id="99dcd-169">As a next step, we will add logic to execute a receive pipeline for the message that was received in orchestration.</span></span> <span data-ttu-id="99dcd-170">この操作を行うには、まず、スコープ内で Microsoft.XLANGs.Pipeline.ReceivePipelineOutputMessages の種類の変数 (RcvPipeOutput) を宣言します。</span><span class="sxs-lookup"><span data-stu-id="99dcd-170">To do this, first we declare a variable (called RcvPipeOutput) of type Microsoft.XLANGs.Pipeline.ReceivePipelineOutputMessages within the scope.</span></span> <span data-ttu-id="99dcd-171">この変数は、受信パイプライン出力メッセージを順番に表示する列挙子です。</span><span class="sxs-lookup"><span data-stu-id="99dcd-171">This variable is an enumerator that allows us to cycle through the receive pipeline output messages.</span></span> <span data-ttu-id="99dcd-172">この種類、およびパイプラインを実行するその他の種類にオーケストレーションからアクセスするには、次のアセンブリに参照を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99dcd-172">Note that in order to access this type, as well as all the other types for execution of pipelines from orchestration, you need to add references to the following assemblies:</span></span>  
  
-   <span data-ttu-id="99dcd-173">Microsoft.XLANGs.Pipeline.dll</span><span class="sxs-lookup"><span data-stu-id="99dcd-173">Microsoft.XLANGs.Pipeline.dll</span></span>  
  
-   <span data-ttu-id="99dcd-174">Microsoft.BizTalk.Pipeline.dll</span><span class="sxs-lookup"><span data-stu-id="99dcd-174">Microsoft.BizTalk.Pipeline.dll</span></span>  
  
 <span data-ttu-id="99dcd-175">受信パイプラインが常に正常に実行されるという保証はありません。</span><span class="sxs-lookup"><span data-stu-id="99dcd-175">There is no guarantee that the receive pipeline will always execute successfully.</span></span> <span data-ttu-id="99dcd-176">メッセージの形式が正しくないために、パイプライン処理が失敗することがあります。</span><span class="sxs-lookup"><span data-stu-id="99dcd-176">Sometimes messages may be malformed, which would cause the pipeline processing to fail.</span></span> <span data-ttu-id="99dcd-177">オーケストレーションでパイプラインの実行に失敗すると、例外がスローされます。これをキャッチして、エラー処理ロジックを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="99dcd-177">When a pipeline fails execution in the orchestration, there is an exception thrown that can be caught and the error handling logic can be performed.</span></span> <span data-ttu-id="99dcd-178">パイプラインでスローされた例外をキャッチするには、非アトミックなスコープで例外処理を使用して、パイプラインを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99dcd-178">In order for us to catch the exception thrown by pipeline, we need to execute the pipeline within a non-atomic scope with an exception handling.</span></span> <span data-ttu-id="99dcd-179">パイプラインを実行する実際のコードは、そのスコープの式図形から呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="99dcd-179">The actual code to execute pipeline is invoked from an expression shape within that scope.</span></span>  
  
 <span data-ttu-id="99dcd-180">ExecuteRcvPipe 式図形に次のコード行を書き込んで、受信パイプラインを実行します。</span><span class="sxs-lookup"><span data-stu-id="99dcd-180">In the ExecuteRcvPipe expression shape, write the following line of code to execute the receive pipeline:</span></span>  
  
```  
RcvPipeOutput = Microsoft.XLANGs.Pipeline.XLANGPipelineManager.ExecuteReceivePipeline(typeof(PipelinesAndSchemas.FFReceivePipeline), InputInterchange);  
```  
  
 <span data-ttu-id="99dcd-181">このコード行を、もう少し詳しく分析しましょう。</span><span class="sxs-lookup"><span data-stu-id="99dcd-181">Let's analyze this line of code in more detail.</span></span> <span data-ttu-id="99dcd-182">この例からわかるとおり、受信パイプラインの種類をパラメータとして使用する静的メソッド ExecuteReceivePipeline を呼び出して、入力メッセージを実行します。</span><span class="sxs-lookup"><span data-stu-id="99dcd-182">As you can see, we call a static method ExecuteReceivePipeline that takes as a parameter a type of receive pipeline to execute and an input message.</span></span> <span data-ttu-id="99dcd-183">この結果、出力メッセージのセットを持つ列挙子オブジェクトが生成されます。</span><span class="sxs-lookup"><span data-stu-id="99dcd-183">As a result, it produces an enumerator object with the set of output messages.</span></span> <span data-ttu-id="99dcd-184">この結果は、このスコープで以前に定義した ReceivePipelineOutputMessages 型の変数に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="99dcd-184">The result is assigned to a variable of type ReceivePipelineOutputMessages that was defined in this scope before.</span></span>  
  
 <span data-ttu-id="99dcd-185">また、パイプライン実行スコープの例外処理ブロックも含めました。</span><span class="sxs-lookup"><span data-stu-id="99dcd-185">We have also included an exception handling block for the pipeline execution scope.</span></span> <span data-ttu-id="99dcd-186">このブロックでは、XLANGPipelineManagerException 型の例外をキャッチした後、簡単にするために、オーケストレーション インスタンスを終了して、カスタマイズされたエラー メッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="99dcd-186">This block catches the exception of type XLANGPipelineManagerException and then for simplicity reasons just terminates an orchestration instance with customized error message.</span></span>  
  
 <span data-ttu-id="99dcd-187">より複雑なシナリオでは、生成やエラー通知メッセージなどの追加のエラー処理を実行し、電子メールを使用して、それをビジネス ユーザーや管理者に送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="99dcd-187">In more complex scenarios, additional error handling can be performed here, such as generation or the error notification message and sending it to a business user or administrator using email.</span></span>  
  
#### <a name="transforming-pipeline-output-messages"></a><span data-ttu-id="99dcd-188">パイプライン出力メッセージの変換</span><span class="sxs-lookup"><span data-stu-id="99dcd-188">Transforming Pipeline Output Messages</span></span>  
 <span data-ttu-id="99dcd-189">パイプラインを実行した後に、逆アセンブルされたメッセージのセットが生成されたら、各出力メッセージを別の形式に変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99dcd-189">After the pipeline has been executed and the set of disassembled messages has been produced, we need to transform each output message into a different format.</span></span>  
  
 <span data-ttu-id="99dcd-190">オーケストレーションで変換を使用するには、変換入力と変換出力の 2 つのメッセージを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99dcd-190">To use transformation in orchestration we need to define two messages – transformation input and output.</span></span> <span data-ttu-id="99dcd-191">これらのメッセージをアトミックのスコープ内に定義します。</span><span class="sxs-lookup"><span data-stu-id="99dcd-191">We will define those messages within the atomic scope.</span></span> <span data-ttu-id="99dcd-192">TmpMessageIn という変換入力メッセージは、PipelinesAndSchemas.PO 型になります。</span><span class="sxs-lookup"><span data-stu-id="99dcd-192">The transformation input message called TmpMessageIn will be of type PipelinesAndSchemas.PO.</span></span> <span data-ttu-id="99dcd-193">TmpMessageOut という変換出力メッセージは、PipeliensAndSchemas.Invoice 型になります。</span><span class="sxs-lookup"><span data-stu-id="99dcd-193">The transformation output message called TmpMessageOut will be of type PipeliensAndSchemas.Invoice.</span></span> <span data-ttu-id="99dcd-194">PipelinesAndSchemas プロジェクトで定義したマップ、PO2Invoice.btm を適用します。</span><span class="sxs-lookup"><span data-stu-id="99dcd-194">We will apply the map PO2Invoice.btm that is defined in project PipelinesAndSchemas.</span></span>  
  
 <span data-ttu-id="99dcd-195">各パイプライン出力メッセージにマップするよう、ループ内で変換を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99dcd-195">As we want to map each pipeline output message we need to perform transformation in the loop.</span></span> <span data-ttu-id="99dcd-196">以下の終了条件を持つループ図形を使用します。</span><span class="sxs-lookup"><span data-stu-id="99dcd-196">We will use a loop shape with the condition for exiting as below:</span></span>  
  
```  
RcvPipeOutput.MoveNext()  
```  
  
 <span data-ttu-id="99dcd-197">MoveNext() メソッドは、パイプライン出力メッセージのコレクション内で移動できる IEnumerator .NET インターフェイスの標準メソッドです。</span><span class="sxs-lookup"><span data-stu-id="99dcd-197">MoveNext() method is a standard method of IEnumerator .NET interface that allows to move within the collection of pipeline output messages.</span></span> <span data-ttu-id="99dcd-198">コレクションの最後に達すると、false を返します。</span><span class="sxs-lookup"><span data-stu-id="99dcd-198">When it reaches the end of collection it returns false.</span></span>  
  
 <span data-ttu-id="99dcd-199">最初の構築図形を使用して、パイプライン出力メッセージからオーケストレーション メッセージ TmpMessageIn を構築します。</span><span class="sxs-lookup"><span data-stu-id="99dcd-199">The first construct shape is used to construct an orchestration message TmpMessageIn out of the pipeline output message.</span></span>  
  
 <span data-ttu-id="99dcd-200">構築図形のコード : </span><span class="sxs-lookup"><span data-stu-id="99dcd-200">The code in the construct shape:</span></span>  
  
```  
TmpMessageIn = null;  
RcvPipeOutput.GetCurrent(TmpMessageIn);  
```  
  
 <span data-ttu-id="99dcd-201">このコードでは、まず、オーケストレーション メッセージを Null に初期化してから、これをパイプライン出力メッセージ コレクションから現在のメッセージに設定します。</span><span class="sxs-lookup"><span data-stu-id="99dcd-201">In this code we first initialize orchestration message to null and then set it to the current message from the pipeline output messages collection.</span></span>  
  
 <span data-ttu-id="99dcd-202">2 番目の構築図形では、TmpMessageIn の実際の変換が実行され、PipelinesAndSchemas.Invoice 型の TmpMessageOut が構築されます。</span><span class="sxs-lookup"><span data-stu-id="99dcd-202">In second construct shape the actual transformation of the TmpMessageIn is performed and the TmpMessageOut of type PipelinesAndSchemas.Invoice is constructed.</span></span>  
  
#### <a name="executing-send-pipeline"></a><span data-ttu-id="99dcd-203">送信パイプラインの実行</span><span class="sxs-lookup"><span data-stu-id="99dcd-203">Executing Send Pipeline</span></span>  
 <span data-ttu-id="99dcd-204">オーケストレーションの最後の処理ステップでは、フラット ファイル送信パイプラインを実行して、変換されたすべての xml メッセージを 1 つのフラット ファイル インターチェンジにアセンブルします。</span><span class="sxs-lookup"><span data-stu-id="99dcd-204">Last processing step in orchestration is to execute flat file send pipeline to assemble all the transformed xml messages into one flat file interchange.</span></span>  
  
 <span data-ttu-id="99dcd-205">送信パイプラインを実行するためには、送信パイプラインで処理しなければならないオーケストレーション メッセージのコレクションを保持する、SendPipeInput と呼ばれる Microsoft.XLANGs.Pipeline.SendPipelineInputMessages 型の変数を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99dcd-205">In order to execute a send pipeline we need to use a variable of type Microsoft.XLANGs.Pipeline.SendPipelineInputMessages called SendPipeInput that will hold a collection of orchestration messages that need to be processed in a send pipeline.</span></span>  
  
 <span data-ttu-id="99dcd-206">変換を実行したループの最後の式で、変換された各メッセージを送信パイプラインのメッセージ コレクションに追加するコードを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="99dcd-206">In the last expression of the loop where we performed transformation we will write a code that will add each transformed message to a message collection for send pipeline:</span></span>  
  
```  
SendPipeInput.Add(TmpMessageOut);  
```  
  
 <span data-ttu-id="99dcd-207">受信パイプラインを実行する部分と同様に、送信パイプラインの実行コードが、例外処理ブロックと共に非アトミックなスコープ内に配置されます。</span><span class="sxs-lookup"><span data-stu-id="99dcd-207">Similar to the part where we execute receive pipeline the code for execution of send pipeline is placed within a non-atomic scope with exception handling block.</span></span> <span data-ttu-id="99dcd-208">送信パイプライン実行コードは、構築ブロックのメッセージの割り当て図形内にあります。</span><span class="sxs-lookup"><span data-stu-id="99dcd-208">The send pipeline execution code is located in the message assignment shape of the construct block.</span></span>  
  
```  
OutputInterchange = null;  
Microsoft.XLANGs.Pipeline.XLANGPipelineManager.ExecuteSendPipeline(typeof(PipelinesAndSchemas.FFSendPipeline), SendPipeInput, OutputInterchange);  
```  
  
 <span data-ttu-id="99dcd-209">構築ブロックを使用して、型に依存しない (System.Xml.XmlDocument など) パイプライン出力メッセージ OutputInterchange を構築します。</span><span class="sxs-lookup"><span data-stu-id="99dcd-209">The construct block is used to construct type agnostic (i.e. System.Xml.XmlDocument) pipeline output message OutputInterchange.</span></span> <span data-ttu-id="99dcd-210">次に、メッセージの割り当て図形で、新しく構築されたメッセージが Null に初期化されます。</span><span class="sxs-lookup"><span data-stu-id="99dcd-210">Then in the message assignment shape the newly constructed message is initialized to null.</span></span> <span data-ttu-id="99dcd-211">その後、静的メソッドの ExecuteSendPipeline を呼び出して、送信パイプラインを実行します。</span><span class="sxs-lookup"><span data-stu-id="99dcd-211">After that the static method ExecuteSendPipeline is invoked to execute a send pipeline.</span></span> <span data-ttu-id="99dcd-212">このメソッドは、送信パイプラインの種類をパラメータとして、入力メッセージ、およびパイプライン出力が保存される出力メッセージの参照を実行します。</span><span class="sxs-lookup"><span data-stu-id="99dcd-212">This method takes as a parameter a type of the send pipeline to execute, the input message and the reference to output message where the pipeline output will be stored.</span></span>  
  
 <span data-ttu-id="99dcd-213">受信パイプラインの例外と同様に、ここにもパイプライン実行スコープの例外処理ブロックがあります。</span><span class="sxs-lookup"><span data-stu-id="99dcd-213">As with the execution of the receive pipeline, here we also have an exception handling block for the pipeline execution scope.</span></span> <span data-ttu-id="99dcd-214">このブロックでは、XLANGPipelineManagerException 型の例外をキャッチした後、簡単にするために、オーケストレーション インスタンスを終了して、カスタマイズされたエラー メッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="99dcd-214">This block catches the exception of type XLANGPipelineManagerException and then for simplicity reasons just terminates an orchestration instance with customized error message.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="99dcd-215">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="99dcd-215">Where to Find This Sample</span></span>  
 <span data-ttu-id="99dcd-216">次の表に、このサンプルのファイル一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="99dcd-216">The following table lists the files for this sample.</span></span>  
  
|<span data-ttu-id="99dcd-217">ファイル</span><span class="sxs-lookup"><span data-stu-id="99dcd-217">File(s)</span></span>|<span data-ttu-id="99dcd-218">Description</span><span class="sxs-lookup"><span data-stu-id="99dcd-218">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="99dcd-219">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="99dcd-219">Cleanup.bat</span></span>|<span data-ttu-id="99dcd-220">アセンブリを展開解除し、グローバル アセンブリ キャッシュ (GAC) から削除するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="99dcd-220">Used to undeploy assemblies and remove them from the global assembly cache (GAC).</span></span><br /><br /> <span data-ttu-id="99dcd-221">送信ポートと受信ポートが削除されます。</span><span class="sxs-lookup"><span data-stu-id="99dcd-221">Removes send and receive ports.</span></span><br /><br /> <span data-ttu-id="99dcd-222">必要に応じて、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。</span><span class="sxs-lookup"><span data-stu-id="99dcd-222">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="99dcd-223">ComposedMessageProcessor.sln</span><span class="sxs-lookup"><span data-stu-id="99dcd-223">ComposedMessageProcessor.sln</span></span>|<span data-ttu-id="99dcd-224">サンプルの Visual Studio ソリューション ファイルです。</span><span class="sxs-lookup"><span data-stu-id="99dcd-224">Visual Studio solution file for the sample.</span></span>|  
|<span data-ttu-id="99dcd-225">ComposedMessageProcessorBinding.xml</span><span class="sxs-lookup"><span data-stu-id="99dcd-225">ComposedMessageProcessorBinding.xml</span></span>|<span data-ttu-id="99dcd-226">サンプルのバインド ファイルです。</span><span class="sxs-lookup"><span data-stu-id="99dcd-226">Binding file for the sample.</span></span>|  
|<span data-ttu-id="99dcd-227">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="99dcd-227">Setup.bat</span></span>|<span data-ttu-id="99dcd-228">このサンプルをビルドおよび初期化するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="99dcd-228">Used to build and initialize this sample.</span></span>|  
|<span data-ttu-id="99dcd-229">Orchestration フォルダー: </span><span class="sxs-lookup"><span data-stu-id="99dcd-229">In Orchestration folder:</span></span><br /><br /> <span data-ttu-id="99dcd-230">CMP.odx</span><span class="sxs-lookup"><span data-stu-id="99dcd-230">CMP.odx</span></span>|<span data-ttu-id="99dcd-231">受信パイプラインを実行して、メッセージを逆アセンブルし、逆アセンブルされた各メッセージを変換した後に送信パイプラインを実行して、メッセージをインターチェンジにアセンブルするオーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="99dcd-231">Orchestration that runs the receive pipeline to disassembler message, transforms each disassembled message and then runs send pipeline to assemble messages into an interchange.</span></span>|  
|<span data-ttu-id="99dcd-232">Orchestration フォルダー: </span><span class="sxs-lookup"><span data-stu-id="99dcd-232">In Orchestration folder:</span></span><br /><br /> <span data-ttu-id="99dcd-233">Orchestration.btproj</span><span class="sxs-lookup"><span data-stu-id="99dcd-233">Orchestration.btproj</span></span>|<span data-ttu-id="99dcd-234">オーケストレーションの BizTalk プロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="99dcd-234">BizTalk project for orchestration.</span></span>|  
|<span data-ttu-id="99dcd-235">Orchestration フォルダー: </span><span class="sxs-lookup"><span data-stu-id="99dcd-235">In Orchestration folder:</span></span><br /><br /> <span data-ttu-id="99dcd-236">SuspendMessage.odx</span><span class="sxs-lookup"><span data-stu-id="99dcd-236">SuspendMessage.odx</span></span>|<span data-ttu-id="99dcd-237">パイプライン処理が失敗したメッセージの中断に使用されるオーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="99dcd-237">Orchestration used for suspending messages that fail pipeline processing.</span></span>|  
|<span data-ttu-id="99dcd-238">PipelinesAndSchemas フォルダー内: </span><span class="sxs-lookup"><span data-stu-id="99dcd-238">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="99dcd-239">CMPInput.xml、CMPOutput.xml</span><span class="sxs-lookup"><span data-stu-id="99dcd-239">CMPInput.xml, CMPOutput.xml</span></span>|<span data-ttu-id="99dcd-240">サンプルの入力ドキュメント インスタンスおよび出力ドキュメント インスタンスです。</span><span class="sxs-lookup"><span data-stu-id="99dcd-240">Input and output document instances for the sample.</span></span>|  
|<span data-ttu-id="99dcd-241">PipelinesAndSchemas フォルダー内: </span><span class="sxs-lookup"><span data-stu-id="99dcd-241">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="99dcd-242">FFReceivePipeline.btp、FFSendPipeline.btp</span><span class="sxs-lookup"><span data-stu-id="99dcd-242">FFReceivePipeline.btp, FFSendPipeline.btp</span></span>|<span data-ttu-id="99dcd-243">フラット ファイル コンポーネントを持つ受信パイプラインと送信パイプラインです。</span><span class="sxs-lookup"><span data-stu-id="99dcd-243">Receive and send pipelines with flat file components.</span></span> <span data-ttu-id="99dcd-244">これらのパイプラインはオーケストレーション内で実行されます。</span><span class="sxs-lookup"><span data-stu-id="99dcd-244">These pipelines are run within orchestration.</span></span>|  
|<span data-ttu-id="99dcd-245">PipelinesAndSchemas フォルダー内: </span><span class="sxs-lookup"><span data-stu-id="99dcd-245">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="99dcd-246">Invoice.xsd、InvoiceHeader.xsd</span><span class="sxs-lookup"><span data-stu-id="99dcd-246">Invoice.xsd, InvoiceHeader.xsd</span></span>|<span data-ttu-id="99dcd-247">出力ドキュメント、およびヘッダーのフラット ファイル スキーマです。</span><span class="sxs-lookup"><span data-stu-id="99dcd-247">Flat file schemas for the output document and header.</span></span>|  
|<span data-ttu-id="99dcd-248">PipelinesAndSchemas フォルダー内: </span><span class="sxs-lookup"><span data-stu-id="99dcd-248">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="99dcd-249">PO.xsd、POHeader.xsd</span><span class="sxs-lookup"><span data-stu-id="99dcd-249">PO.xsd, POHeader.xsd</span></span>|<span data-ttu-id="99dcd-250">入力ドキュメント、およびヘッダーのフラット ファイル スキーマです。</span><span class="sxs-lookup"><span data-stu-id="99dcd-250">Flat file schemas for the input document and header.</span></span>|  
|<span data-ttu-id="99dcd-251">PipelinesAndSchemas フォルダー内: </span><span class="sxs-lookup"><span data-stu-id="99dcd-251">In PipelinesAndSchemas folder:</span></span><br /><br /> <span data-ttu-id="99dcd-252">PropertySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="99dcd-252">PropertySchema.xsd</span></span>|<span data-ttu-id="99dcd-253">サンプルのプロパティ スキーマです。</span><span class="sxs-lookup"><span data-stu-id="99dcd-253">Property schema for the sample.</span></span>|  
  
## <a name="building-and-initializing-the-sample"></a><span data-ttu-id="99dcd-254">サンプルのビルドおよび初期化</span><span class="sxs-lookup"><span data-stu-id="99dcd-254">Building and Initializing the Sample</span></span>  
 <span data-ttu-id="99dcd-255">次の手順を使用して、Compose サンプルをビルドおよび初期化します。</span><span class="sxs-lookup"><span data-stu-id="99dcd-255">Use the following procedure to build and initialize the Compose sample.</span></span>  
  
#### <a name="to-build-and-initialize-the-compose-sample"></a><span data-ttu-id="99dcd-256">Compose サンプルをビルドして初期化するには</span><span class="sxs-lookup"><span data-stu-id="99dcd-256">To build and initialize the Compose sample</span></span>  
  
1.  <span data-ttu-id="99dcd-257">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="99dcd-257">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="99dcd-258">\<サンプル パス > \Pipelines\ComposedMessageProcessor</span><span class="sxs-lookup"><span data-stu-id="99dcd-258">\<Samples Path>\Pipelines\ComposedMessageProcessor</span></span>  
  
2.  <span data-ttu-id="99dcd-259">次の操作を実行する Setup.bat ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="99dcd-259">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="99dcd-260">次のフォルダに、このサンプル用の入力 (In) フォルダと出力 (Out) フォルダを作成します。</span><span class="sxs-lookup"><span data-stu-id="99dcd-260">Creates the input (In) and output (Out) folders for this sample in the folder:</span></span>  
  
         <span data-ttu-id="99dcd-261">\<サンプル パス > \Pipelines\ComposedMessageProcessor</span><span class="sxs-lookup"><span data-stu-id="99dcd-261">\<Samples Path>\Pipelines\ComposedMessageProcessor</span></span>  
  
    -   <span data-ttu-id="99dcd-262">このサンプル用に Visual Studio プロジェクトをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="99dcd-262">Compiles the Visual Studio projects for this sample.</span></span>  
  
    -   <span data-ttu-id="99dcd-263">"CMP Sample" という新しいアプリケーションを作成し、そこにサンプル アセンブリを展開します。</span><span class="sxs-lookup"><span data-stu-id="99dcd-263">Creates a new application called "CMP Sample" and deploys the sample assemblies into it.</span></span>  
  
    -   <span data-ttu-id="99dcd-264">BizTalk Server の受信場所、送信ポート、および受信ポートを作成しバインドします。</span><span class="sxs-lookup"><span data-stu-id="99dcd-264">Creates and binds the BizTalk Server receive location, and the send and receive ports.</span></span>  
  
    -   <span data-ttu-id="99dcd-265">オーケストレーションを参加させて開始し、受信場所を有効化し、送信ポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="99dcd-265">Enlists and starts orchestration, enables the receive location, and starts the send port.</span></span>  
  
         <span data-ttu-id="99dcd-266">開き、Setup.bat ファイルを実行せずにこのサンプルのプロジェクトをビルドする場合は、まず、.NET Framework の厳密名ユーティリティ (sn.exe) を使用して、厳密な名前のキー ペアを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99dcd-266">If you choose to open and build the projects in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name utility (sn.exe).</span></span> <span data-ttu-id="99dcd-267">このキー ペアが結果として得られるアセンブリの署名に使用されるを使用します。</span><span class="sxs-lookup"><span data-stu-id="99dcd-267">Use this key pair is used to sign the resulting assemblies.</span></span>  
  
3.  <span data-ttu-id="99dcd-268">このサンプルを実行する前に、BizTalk Server において、作成プロセスおよび初期化プロセスでエラーが報告されていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="99dcd-268">Before attempting to run this sample, confirm that BizTalk Server did not report any errors during the build and initialization process.</span></span>  
  
     <span data-ttu-id="99dcd-269">Setup.bat による変更を元に戻すには、次の作業を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="99dcd-269">To undo changes made by Setup.bat, you must do the following:</span></span>  
  
    1.  <span data-ttu-id="99dcd-270">BizTalk Server 管理コンソールでホスト インスタンスを 1 度停止し、再開します。</span><span class="sxs-lookup"><span data-stu-id="99dcd-270">Stop and restart the host instance from the BizTalk Server Administration console.</span></span>  
  
    2.  <span data-ttu-id="99dcd-271">Cleanup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="99dcd-271">Run Cleanup.bat.</span></span> <span data-ttu-id="99dcd-272">Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。</span><span class="sxs-lookup"><span data-stu-id="99dcd-272">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  
  
## <a name="running-the-sample"></a><span data-ttu-id="99dcd-273">サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="99dcd-273">Running the sample</span></span>  
 <span data-ttu-id="99dcd-274">次の手順を使用して、ComposedMessageProcessor サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="99dcd-274">Use the following procedure to run the ComposedMessageProcessor sample.</span></span>  
  
#### <a name="to-run-the-composedmessageprocessor-sample"></a><span data-ttu-id="99dcd-275">ComposedMessageProcessor サンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="99dcd-275">To run the ComposedMessageProcessor sample</span></span>  
  
1.  <span data-ttu-id="99dcd-276">PipelinesAndSchemas フォルダーのテキスト ファイル CMPInput.txt をコピーします。</span><span class="sxs-lookup"><span data-stu-id="99dcd-276">Copy the text file CMPInput.txt located in the PipelinesAndSchemas folder.</span></span> <span data-ttu-id="99dcd-277">このファイルを In フォルダに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="99dcd-277">Paste the file into the folder In.</span></span>  
  
2.  <span data-ttu-id="99dcd-278">テキスト ファイルが Out フォルダに作成されることを確認します。このファイルには、CMPInput.txt と同じレコードが含まれますが、ファイルのデータ形式が異なります。</span><span class="sxs-lookup"><span data-stu-id="99dcd-278">Observe the text file created in the folder Out. This file contains the same records as the CMPInput.txt, but the format of data in the file is different.</span></span>  
  
     <span data-ttu-id="99dcd-279">メッセージが BizTalk Server を通過すると、次のことが行われます。</span><span class="sxs-lookup"><span data-stu-id="99dcd-279">As the message passes through the BizTalk Server, the following happens:</span></span>  
  
    1.  <span data-ttu-id="99dcd-280">メッセージが逆アセンブルされ、XML メッセージに変換されます。</span><span class="sxs-lookup"><span data-stu-id="99dcd-280">The message gets disassembled and converted into XML messages.</span></span> <span data-ttu-id="99dcd-281">各メッセージが別の形式にマップされます。</span><span class="sxs-lookup"><span data-stu-id="99dcd-281">Each message is mapped to a different format.</span></span>  
  
    2.  <span data-ttu-id="99dcd-282">マップされたメッセージは一緒にアセンブルされ、フラット ファイル形式に変換されます。</span><span class="sxs-lookup"><span data-stu-id="99dcd-282">All mapped messages are assembled together and converted into the flat file format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99dcd-283">参照</span><span class="sxs-lookup"><span data-stu-id="99dcd-283">See Also</span></span>  
 [<span data-ttu-id="99dcd-284">パイプライン (BizTalk Server Samples フォルダ)</span><span class="sxs-lookup"><span data-stu-id="99dcd-284">Pipelines (BizTalk Server Samples Folder)</span></span>](../core/pipelines-biztalk-server-samples-folder.md)