---
title: BAM API サンプル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 32a925f2-c7f4-4111-9c59-8865f15c6a89
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4dbc1adba5ef1b0c0a86c456a86ac3cce627d34f
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528529"
---
# <a name="bam-api-biztalk-server-sample"></a><span data-ttu-id="ad4bf-102">BAM API (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="ad4bf-102">BAM API (BizTalk Server Sample)</span></span>
<span data-ttu-id="ad4bf-103">BAM API サンプルでは、BAM API の呼び出しを監視できるキーの情報を保存するアプリケーションに組み込む方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-103">The BAM API sample illustrates how to incorporate calls to the BAM API into an application to save key information that you can monitor.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="ad4bf-104">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="ad4bf-104">What This Sample Does</span></span>  
 <span data-ttu-id="ad4bf-105">このサンプルでは、単純な購入シナリオを実装します。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-105">This sample implements a simple purchasing scenario.</span></span> <span data-ttu-id="ad4bf-106">注文書の生成、各注文の処理、出荷、および作成し、請求書を処理します。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-106">It generates purchase orders, processes each purchase order, creates shipments, and creates and processes invoices.</span></span> <span data-ttu-id="ad4bf-107">サンプルを実行すると、作成し、詳細と注文書や請求書のディス ポジションを反映するように BAM アクティビティを更新します。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-107">As the sample runs, it creates and updates BAM activities to reflect the details and disposition of the purchase orders and invoices.</span></span>  
  
## <a name="how-this-sample-was-designed-and-why"></a><span data-ttu-id="ad4bf-108">このサンプルのデザイン方法とその理由</span><span class="sxs-lookup"><span data-stu-id="ad4bf-108">How This Sample Was Designed and Why</span></span>  
 <span data-ttu-id="ad4bf-109">このサンプルは、BAM を使用して、BizTalk オーケストレーションではないアプリケーションの情報を格納する方法を説明するために設計されました。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-109">This sample was designed to illustrate how to use BAM to store information from an application that is not a BizTalk orchestration.</span></span> <span data-ttu-id="ad4bf-110">アプリケーションは、単純なは、実稼働アプリケーションで使用する可能性がある BAM のいくつかの側面を示しています。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-110">While the application is simple, it illustrates several aspects of BAM that you are likely to use in a production application.</span></span> <span data-ttu-id="ad4bf-111">その一部を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-111">These include the following:</span></span>  
  
- <span data-ttu-id="ad4bf-112">1 つのアクティビティに影響を与える複数のスレッド</span><span class="sxs-lookup"><span data-stu-id="ad4bf-112">Multiple threads that contribute to a single activity</span></span>  
  
- <span data-ttu-id="ad4bf-113">2 つのアクティビティ間のリレーションシップを作成します。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-113">Creating a relationship between two activities</span></span>  
  
- <span data-ttu-id="ad4bf-114">Continuation を使用して、同じアクティビティに異なる Id を使用してアクセスを許可するには</span><span class="sxs-lookup"><span data-stu-id="ad4bf-114">Using a continuation to allow the same activity to be accessed with different IDs</span></span>  
  
  <span data-ttu-id="ad4bf-115">BAM API サンプルは、次の 3 つの主要なクラスで構成されます。 1 つは、出荷の処理、請求書を処理する 1 つに、注文購入を処理する 1 つ。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-115">The BAM API sample consists of three main classes: one to process purchase orders, one to process shipments, and one to process invoices.</span></span> <span data-ttu-id="ad4bf-116">各クラスには、 **RunOnce** 、キューからメッセージを取得し、メッセージを処理するメソッド。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-116">Each class has a **RunOnce** method that retrieves a message from a queue, and then processes the message.</span></span> <span data-ttu-id="ad4bf-117">各クラスにはまた、**実行**継続的に呼び出すメソッド、 **RunOnce**メソッド。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-117">Each class also has a **Run** method that continually calls the **RunOnce** method.</span></span>  
  
  <span data-ttu-id="ad4bf-118">**RunOnce**のメソッド、 **PoApplication**クラスは、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-118">The **RunOnce** method of the **PoApplication** class does the following:</span></span>  
  
1. <span data-ttu-id="ad4bf-119">注文書を表す XML メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-119">Creates an XML message that represents a purchase order.</span></span>  
  
2. <span data-ttu-id="ad4bf-120">BAMApiPo アクティビティを開始し、注文書について、および受信されたときに、アクティビティ情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-120">Begins a BAMApiPo activity and adds to the activity information about the purchase order and when it was received.</span></span>  
  
3. <span data-ttu-id="ad4bf-121">任意を承認または却下、注文します。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-121">Arbitrarily approves or rejects the purchase order.</span></span>  
  
4. <span data-ttu-id="ad4bf-122">注文書 (承認または拒否) のステータスを記録する BAMApiPo アクティビティを更新します。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-122">Updates the BAMApiPo activity to record the status of the purchase order (accepted or rejected).</span></span>  
  
5. <span data-ttu-id="ad4bf-123">注文書が承認された場合、 **RunOnce**メソッドも、次を行います。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-123">If the purchase order was accepted, the **RunOnce** method also does the following:</span></span>  
  
   1.  <span data-ttu-id="ad4bf-124">出荷するパッケージを表す XML メッセージを作成し、出荷のキューにメッセージを追加します。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-124">Creates an XML message to represent a package to be shipped, and adds the message to the queue of shipments.</span></span>  
  
   2.  <span data-ttu-id="ad4bf-125">請求書に含まれる発注書のキューに注文書を表す XML メッセージを追加します。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-125">Adds the XML message that represents the purchase order to the queue of purchase orders to be included in an invoice.</span></span>  
  
   3.  <span data-ttu-id="ad4bf-126">BAMApiPo アクティビティの continuation を有効にします。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-126">Enables continuation for the BAMApiPo activity.</span></span>  
  
   4.  <span data-ttu-id="ad4bf-127">BAMApiPo アクティビティを終了します。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-127">Ends the BAMApiPo activity.</span></span>  
  
   <span data-ttu-id="ad4bf-128">**RunOnce**のメソッド、 **ShipmentApplication**クラスは、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-128">The **RunOnce** method of the **ShipmentApplication** class does the following:</span></span>  
  
6. <span data-ttu-id="ad4bf-129">送付先であるパッケージを表す XML メッセージをキューから取得します。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-129">Retrieves from its queue an XML message that represents a package to be shipped.</span></span>  
  
7. <span data-ttu-id="ad4bf-130">パッケージが付属していた時間を記録する BAMApiPo アクティビティを更新します。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-130">Updates the BAMApiPo activity to record the time that the package was shipped.</span></span>  
  
8. <span data-ttu-id="ad4bf-131">BAMApiPo アクティビティを終了します。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-131">Ends the BAMApiPo activity.</span></span>  
  
   <span data-ttu-id="ad4bf-132">**RunOnce**のメソッド、 **InvoiceApplication**クラスは、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-132">The **RunOnce** method of the **InvoiceApplication** class does the following:</span></span>  
  
9. <span data-ttu-id="ad4bf-133">請求される注文書を表す XML メッセージをキューから取得します。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-133">Retrieves from its queue an XML message that represents a purchase order to be invoiced.</span></span>  
  
10. <span data-ttu-id="ad4bf-134">BAMApiInvoice アクティビティを開始します。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-134">Begins a BAMApiInvoice activity.</span></span>  
  
11. <span data-ttu-id="ad4bf-135">BAMApiInvoice アクティビティと BAMApiPo アクティビティを請求される注文書の間の BAM リレーションシップを作成します。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-135">Creates a BAM relationship between the BAMApiInvoice activity and the BAMApiPo activity for the purchase order that is being invoiced.</span></span>  
  
12. <span data-ttu-id="ad4bf-136">作成された、請求書と、時間に関する BAMApiPo アクティビティ情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-136">Adds to the BAMApiPo activity information about the invoice and the time it was created.</span></span>  
  
13. <span data-ttu-id="ad4bf-137">BAMApiInvoice アクティビティには時間の支払いに請求書の待機をシミュレートするために、請求書の支払いが行われた時刻を追加します。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-137">After an arbitrary delay to simulate waiting for the invoice to be paid, adds to the BAMApiInvoice activity the time the invoice was paid.</span></span>  
  
14. <span data-ttu-id="ad4bf-138">BAMApiInvoice アクティビティを終了します。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-138">Ends the BAMApiInvoice activity.</span></span>  
  
    <span data-ttu-id="ad4bf-139">**Main**のメソッド、 **MainApp**クラスが、アプリケーションを初期化します。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-139">The **Main** method of the **MainApp** class initializes the application.</span></span> <span data-ttu-id="ad4bf-140">その後、次の処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-140">It does the following:</span></span>  
  
15. <span data-ttu-id="ad4bf-141">作成、 **DirectEventStream**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-141">Creates a **DirectEventStream** object.</span></span>  
  
16. <span data-ttu-id="ad4bf-142">いくつかのスレッドを開始し、呼び出し、**実行**のメソッド、 **POApplication**各スレッドでオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-142">Starts several threads, and calls the **Run** method of the **POApplication** object in each thread.</span></span>  
  
17. <span data-ttu-id="ad4bf-143">いくつかのスレッドを開始し、呼び出し、**実行**のメソッド、 **ShipmentApplication**各スレッドでオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-143">Starts several threads, and calls the **Run** method of the **ShipmentApplication** object in each thread.</span></span>  
  
18. <span data-ttu-id="ad4bf-144">いくつかのスレッドを開始し、呼び出し、**実行**のメソッド、 **InvoiceApplication**各スレッドでオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-144">Starts several threads, and calls the **Run** method of the **InvoiceApplication** object in each thread.</span></span>  
  
    <span data-ttu-id="ad4bf-145">**Global**クラスを作成するスレッドの数や拒否する注文書の割合など、サンプル アプリケーションで使用される定数を定義します。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-145">The **Global** class defines constants that are used by the sample application, such as the number of threads to create and the percentage of purchase orders to reject.</span></span>  
  
    <span data-ttu-id="ad4bf-146">サンプルには、Visual Studio ソリューションに加え、アクティビティを定義する Microsoft Excel ファイルも含まれます。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-146">In addition to the Visual Studio solution, the sample also contains a Microsoft Excel file that defines the activities.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="ad4bf-147">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="ad4bf-147">Where to Find This Sample</span></span>  
 <span data-ttu-id="ad4bf-148">このサンプルで*\<サンプル パス\>* \BAM\BamApiSample します。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-148">You can find this sample at *\<Samples Path\>* \BAM\BamApiSample.</span></span>  
  
 <span data-ttu-id="ad4bf-149">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-149">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="ad4bf-150">ファイル</span><span class="sxs-lookup"><span data-stu-id="ad4bf-150">File</span></span>|<span data-ttu-id="ad4bf-151">説明</span><span class="sxs-lookup"><span data-stu-id="ad4bf-151">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="ad4bf-152">BamApiSample.cs</span><span class="sxs-lookup"><span data-stu-id="ad4bf-152">BamApiSample.cs</span></span>|<span data-ttu-id="ad4bf-153">インストルメント化されたアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-153">Instrumented application.</span></span>|  
|<span data-ttu-id="ad4bf-154">BamApiSample.csproj</span><span class="sxs-lookup"><span data-stu-id="ad4bf-154">BamApiSample.csproj</span></span>|<span data-ttu-id="ad4bf-155">インストルメント化されたアプリケーションのプロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-155">Instrumented application project.</span></span>|  
|<span data-ttu-id="ad4bf-156">BamApiSample.sln</span><span class="sxs-lookup"><span data-stu-id="ad4bf-156">BamApiSample.sln</span></span>|<span data-ttu-id="ad4bf-157">インストルメント化されたアプリケーションのソリューションです。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-157">Instrumented application solution.</span></span>|  
|<span data-ttu-id="ad4bf-158">BamApiSample.xls</span><span class="sxs-lookup"><span data-stu-id="ad4bf-158">BamApiSample.xls</span></span>|<span data-ttu-id="ad4bf-159">BAM 定義スタイル シートです。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-159">BAM definition style sheet.</span></span>|  
|<span data-ttu-id="ad4bf-160">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="ad4bf-160">Cleanup.bat</span></span>|<span data-ttu-id="ad4bf-161">デプロイされたサンプル ファイルを削除するバッチ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-161">Batch file to remove deployed sample files.</span></span>|  
|<span data-ttu-id="ad4bf-162">Input.txt</span><span class="sxs-lookup"><span data-stu-id="ad4bf-162">Input.txt</span></span>|<span data-ttu-id="ad4bf-163">サンプルのインターセプタ構成を入力します。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-163">Sample interceptor configuration input.</span></span>|  
|<span data-ttu-id="ad4bf-164">InterceptorConfig.cs</span><span class="sxs-lookup"><span data-stu-id="ad4bf-164">InterceptorConfig.cs</span></span>|<span data-ttu-id="ad4bf-165">API のサンプルのインターセプタ構成コード。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-165">Interceptor configuration code for API sample.</span></span>|  
|<span data-ttu-id="ad4bf-166">InterceptorConfig.csproj</span><span class="sxs-lookup"><span data-stu-id="ad4bf-166">InterceptorConfig.csproj</span></span>|<span data-ttu-id="ad4bf-167">インターセプタ構成プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-167">Interceptor configuration project.</span></span>|  
|<span data-ttu-id="ad4bf-168">Invoice_config.xml</span><span class="sxs-lookup"><span data-stu-id="ad4bf-168">Invoice_config.xml</span></span>|<span data-ttu-id="ad4bf-169">Invoice インターセプタ構成。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-169">Invoice interceptor configuration.</span></span>|  
|<span data-ttu-id="ad4bf-170">Invoice_interceptor.bin</span><span class="sxs-lookup"><span data-stu-id="ad4bf-170">Invoice_interceptor.bin</span></span>|<span data-ttu-id="ad4bf-171">シリアル化された invoice インターセプタ。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-171">Serialized invoice interceptor.</span></span>|  
|<span data-ttu-id="ad4bf-172">PurchaseOrder_config.xml</span><span class="sxs-lookup"><span data-stu-id="ad4bf-172">PurchaseOrder_config.xml</span></span>|<span data-ttu-id="ad4bf-173">PurchaseOrder インターセプタ構成。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-173">PurchaseOrder interceptor configuration.</span></span>|  
|<span data-ttu-id="ad4bf-174">PurchaseOrder_interceptor.bin</span><span class="sxs-lookup"><span data-stu-id="ad4bf-174">PurchaseOrder_interceptor.bin</span></span>|<span data-ttu-id="ad4bf-175">シリアル化された PurchaseOrder インターセプタ。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-175">Serialized PurchaseOrder interceptor.</span></span>|  
|<span data-ttu-id="ad4bf-176">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="ad4bf-176">Setup.bat</span></span>|<span data-ttu-id="ad4bf-177">バッチ ファイルを展開し、サンプル ファイルを参加させる。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-177">Batch file to deploy and enlist sample files.</span></span>|  
|<span data-ttu-id="ad4bf-178">Shipment_config.xml</span><span class="sxs-lookup"><span data-stu-id="ad4bf-178">Shipment_config.xml</span></span>|<span data-ttu-id="ad4bf-179">Shipment インターセプタ構成。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-179">Shipment interceptor configuration.</span></span>|  
|<span data-ttu-id="ad4bf-180">Shipment_interceptor.bin</span><span class="sxs-lookup"><span data-stu-id="ad4bf-180">Shipment_interceptor.bin</span></span>|<span data-ttu-id="ad4bf-181">シリアル化された shipment インターセプタ。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-181">Serialized shipment interceptor.</span></span>|  
  
## <a name="run-the-bam-api-sample"></a><span data-ttu-id="ad4bf-182">BAM API サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-182">Run the BAM API sample</span></span>  
  
1.  <span data-ttu-id="ad4bf-183">管理者は、コマンド プロンプトを開き、実行*\<サンプル パス\>* \BAM\ BamApiSample\setup.bat します。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-183">Open a command prompt as Administrator, and run *\<Samples Path\>* \BAM\ BamApiSample\setup.bat.</span></span>  
  
2.  <span data-ttu-id="ad4bf-184">管理者は、Visual Studio を起動し、開く、 *\<サンプル パス\>* \BAM\ BamApiSample\BamApiSample.sln ソリューション。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-184">Start Visual Studio as Administrator, and open the *\<Samples Path\>* \BAM\ BamApiSample\BamApiSample.sln solution.</span></span> 
  
    > [!IMPORTANT]
    >  <span data-ttu-id="ad4bf-185">行`//#define Interceptor`BamApiSample.cs ファイルで、アウト コメントする必要があります。削除しないでください、"//"この行から。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-185">The line `//#define Interceptor` in the BamApiSample.cs file must be commented out. Do not remove the “//” from this line.</span></span> <span data-ttu-id="ad4bf-186">BAM API サンプルは、内部でないコードのみを使用して、`#if Interceptor`プリプロセッサ ディレクティブです。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-186">The BAM API sample uses only the code that is not inside an `#if Interceptor` preprocessor directive.</span></span>  
  
3.  <span data-ttu-id="ad4bf-187">ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-187">Build the solution.</span></span>  
  
4.  <span data-ttu-id="ad4bf-188">実行*\<サンプル パス\>* \BAM\BamApiSample\bin\debug\BamApiSample.exe します。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-188">Run *\<Samples Path\>* \BAM\BamApiSample\bin\debug\BamApiSample.exe.</span></span>  
  
     <span data-ttu-id="ad4bf-189">出力は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-189">The output will resemble the following:</span></span>  
  
    ```  
    ...  
    New Purchase Order #17 Received  
    8 was shipped as pkg#87  
    New Purchase Order #18 Received.  
    Shipping package pkg#87 via DHL  
    13 was Approved.  
    18 was Rejected.  
    17 was Rejected.  
    11 was shipped as pkg#114  
    16 wsas Rejected.  
    Shipping package pkg#114 via DHL  
    Invoice #5 send for {2 5 1 9 4 8 11 }  
    Package pkg#49 was delivered  
    New Purchase Order #19 Received.  
    ...  
    ```  
  
5.  <span data-ttu-id="ad4bf-190">しばらくするとそのため、ctrl キーを押しながら C キーを押します。 または BamApiSample プログラムを停止するコマンド プロンプト ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-190">After a minute or so, press CTRL+C or close the Command Prompt window to stop the BamApiSample program.</span></span>  
  
## <a name="view-the-results"></a><span data-ttu-id="ad4bf-191">結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-191">View the results</span></span>
  
1.  <span data-ttu-id="ad4bf-192">SQL Server Management Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-192">Open SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="ad4bf-193">SQL Server Management studio で、サーバーを展開し、**データベース**、展開**BAMPrimaryImport**、順に展開**テーブル**します。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-193">In SQL Server Management Studio, expand the server, expand **Databases**, expand **BAMPrimaryImport**, and then expand **Tables**.</span></span>  
  
3.  <span data-ttu-id="ad4bf-194">右クリックして**dbo.bam_BAMApiInvoice_Active**  をクリックし、**テーブルを開く**します。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-194">Right-click **dbo.bam_BAMApiInvoice_Active** and then click **Open Table**.</span></span> <span data-ttu-id="ad4bf-195">SQL Server を使用している場合はクリックして**上位 1000 行を選択する**します。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-195">If you are using SQL Server, click **Select top 1000 rows**.</span></span>  
  
     <span data-ttu-id="ad4bf-196">Bam_BAMApiInvoice_Active テーブルの内容は、右側のウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-196">The contents of the bam_BAMApiInvoice_Active table are displayed in the right pane.</span></span> <span data-ttu-id="ad4bf-197">テーブルの各行が開始されたら、完了していない BAMApiInvoice アクティビティを表します。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-197">Each row in the table represents a BAMApiInvoice activity that has been started, but  has not been completed.</span></span>  
  
4.  <span data-ttu-id="ad4bf-198">右クリックして**dbo.bam_BAMApiPo_Completed**  をクリックし、**テーブルを開く**します。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-198">Right-click **dbo.bam_BAMApiPo_Completed** and then click **Open Table**.</span></span> <span data-ttu-id="ad4bf-199">SQL Server を使用している場合はクリックして**上位 1000 行を選択する**します。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-199">If you are using SQL Server, click **Select top 1000 rows**.</span></span>  
  
     <span data-ttu-id="ad4bf-200">Bam_BAMApiPo_Completed テーブルの内容は、右側のウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-200">The contents of the bam_BAMApiPo_Completed table are displayed in the right pane.</span></span> <span data-ttu-id="ad4bf-201">テーブルの各行は、完了した BAMApiPo アクティビティを表します。</span><span class="sxs-lookup"><span data-stu-id="ad4bf-201">Each row in the table represents a BAMApiPo activity that has been completed.</span></span>