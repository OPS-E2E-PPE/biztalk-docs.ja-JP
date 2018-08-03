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
ms.openlocfilehash: 899b28a95b6f07d7aec20868ea6b71138acfe60f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987379"
---
# <a name="bam-api-biztalk-server-sample"></a><span data-ttu-id="1707f-102">BAM API (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="1707f-102">BAM API (BizTalk Server Sample)</span></span>
<span data-ttu-id="1707f-103">BAM API サンプルでは、BAM API の呼び出しを監視できるキーの情報を保存するアプリケーションに組み込む方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1707f-103">The BAM API sample illustrates how to incorporate calls to the BAM API into an application to save key information that you can monitor.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="1707f-104">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="1707f-104">What This Sample Does</span></span>  
 <span data-ttu-id="1707f-105">このサンプルは、単純な購入のシナリオを実装します。</span><span class="sxs-lookup"><span data-stu-id="1707f-105">This sample implements a simple purchasing scenario.</span></span> <span data-ttu-id="1707f-106">注文書の生成、各注文書の処理、出荷、および請求書の作成と処理を行います。</span><span class="sxs-lookup"><span data-stu-id="1707f-106">It generates purchase orders, processes each purchase order, creates shipments, and creates and processes invoices.</span></span> <span data-ttu-id="1707f-107">このサンプルを実行すると、BAM アクティビティが作成および更新され、注文書と請求書の詳細と処理が反映されます。</span><span class="sxs-lookup"><span data-stu-id="1707f-107">As the sample runs, it creates and updates BAM activities to reflect the details and disposition of the purchase orders and invoices.</span></span>  
  
## <a name="how-this-sample-was-designed-and-why"></a><span data-ttu-id="1707f-108">このサンプルをデザインした方法とその理由</span><span class="sxs-lookup"><span data-stu-id="1707f-108">How This Sample Was Designed and Why</span></span>  
 <span data-ttu-id="1707f-109">このサンプルは、BAM を使用して、BizTalk オーケストレーションではないアプリケーションの情報を保存する方法を示すためにデザインされました。</span><span class="sxs-lookup"><span data-stu-id="1707f-109">This sample was designed to illustrate how to use BAM to store information from an application that is not a BizTalk orchestration.</span></span> <span data-ttu-id="1707f-110">アプリケーションは単純ですが、実稼働環境のアプリケーションでも使用できる BAM のいくつかの側面が示されています。</span><span class="sxs-lookup"><span data-stu-id="1707f-110">While the application is simple, it illustrates several aspects of BAM that you are likely to use in a production application.</span></span> <span data-ttu-id="1707f-111">その一部を次に示します。</span><span class="sxs-lookup"><span data-stu-id="1707f-111">These include the following:</span></span>  
  
- <span data-ttu-id="1707f-112">単一のアクティビティを構成する複数のスレッド</span><span class="sxs-lookup"><span data-stu-id="1707f-112">Multiple threads that contribute to a single activity</span></span>  
  
- <span data-ttu-id="1707f-113">2 つのアクティビティの間でリレーションシップの作成</span><span class="sxs-lookup"><span data-stu-id="1707f-113">Creating a relationship between two activities</span></span>  
  
- <span data-ttu-id="1707f-114">別の ID を使用して同じアクティビティにアクセスできるようにする Continuation の使用</span><span class="sxs-lookup"><span data-stu-id="1707f-114">Using a continuation to allow the same activity to be accessed with different IDs</span></span>  
  
  <span data-ttu-id="1707f-115">BAM API サンプルは、3 つのメイン クラスで構成されます。注文書を処理するためのクラス、出荷を処理するためのクラス、および請求書を処理するためのクラスです。</span><span class="sxs-lookup"><span data-stu-id="1707f-115">The BAM API sample consists of three main classes: one to process purchase orders, one to process shipments, and one to process invoices.</span></span> <span data-ttu-id="1707f-116">各クラスには、 **RunOnce** 、キューからメッセージを取得し、メッセージを処理するメソッド。</span><span class="sxs-lookup"><span data-stu-id="1707f-116">Each class has a **RunOnce** method that retrieves a message from a queue, and then processes the message.</span></span> <span data-ttu-id="1707f-117">各クラスにはまた、**実行**継続的に呼び出すメソッド、 **RunOnce**メソッド。</span><span class="sxs-lookup"><span data-stu-id="1707f-117">Each class also has a **Run** method that continually calls the **RunOnce** method.</span></span>  
  
  <span data-ttu-id="1707f-118">**RunOnce**のメソッド、 **PoApplication**クラスは、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="1707f-118">The **RunOnce** method of the **PoApplication** class does the following:</span></span>  
  
1. <span data-ttu-id="1707f-119">注文書を表す XML メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="1707f-119">Creates an XML message that represents a purchase order.</span></span>  
  
2. <span data-ttu-id="1707f-120">BAMApiPo アクティビティを開始し、注文書および注文書の受信時刻に関する情報をアクティビティに追加します。</span><span class="sxs-lookup"><span data-stu-id="1707f-120">Begins a BAMApiPo activity and adds to the activity information about the purchase order and when it was received.</span></span>  
  
3. <span data-ttu-id="1707f-121">適宜、注文書を承認または拒否します。</span><span class="sxs-lookup"><span data-stu-id="1707f-121">Arbitrarily approves or rejects the purchase order.</span></span>  
  
4. <span data-ttu-id="1707f-122">BAMApiPo アクティビティを更新して注文書の状況 (承認または拒否) を記録します。</span><span class="sxs-lookup"><span data-stu-id="1707f-122">Updates the BAMApiPo activity to record the status of the purchase order (accepted or rejected).</span></span>  
  
5. <span data-ttu-id="1707f-123">注文書が承認された場合、 **RunOnce**メソッドも、次を行います。</span><span class="sxs-lookup"><span data-stu-id="1707f-123">If the purchase order was accepted, the **RunOnce** method also does the following:</span></span>  
  
   1.  <span data-ttu-id="1707f-124">出荷されるパッケージを表す XML メッセージを作成し、出荷のキューにメッセージを追加します。</span><span class="sxs-lookup"><span data-stu-id="1707f-124">Creates an XML message to represent a package to be shipped, and adds the message to the queue of shipments.</span></span>  
  
   2.  <span data-ttu-id="1707f-125">注文書を表す XML メッセージを、請求書に含める注文書のキューに追加します。</span><span class="sxs-lookup"><span data-stu-id="1707f-125">Adds the XML message that represents the purchase order to the queue of purchase orders to be included in an invoice.</span></span>  
  
   3.  <span data-ttu-id="1707f-126">BAMApiPo アクティビティの Continuation を有効にします。</span><span class="sxs-lookup"><span data-stu-id="1707f-126">Enables continuation for the BAMApiPo activity.</span></span>  
  
   4.  <span data-ttu-id="1707f-127">BAMApiPo アクティビティを終了します。</span><span class="sxs-lookup"><span data-stu-id="1707f-127">Ends the BAMApiPo activity.</span></span>  
  
   <span data-ttu-id="1707f-128">**RunOnce**のメソッド、 **ShipmentApplication**クラスは、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="1707f-128">The **RunOnce** method of the **ShipmentApplication** class does the following:</span></span>  
  
6. <span data-ttu-id="1707f-129">出荷されるパッケージを表す XML メッセージをキューから取得します。</span><span class="sxs-lookup"><span data-stu-id="1707f-129">Retrieves from its queue an XML message that represents a package to be shipped.</span></span>  
  
7. <span data-ttu-id="1707f-130">BAMApiPo アクティビティを更新してパッケージが出荷された時刻を記録します。</span><span class="sxs-lookup"><span data-stu-id="1707f-130">Updates the BAMApiPo activity to record the time that the package was shipped.</span></span>  
  
8. <span data-ttu-id="1707f-131">BAMApiPo アクティビティを終了します。</span><span class="sxs-lookup"><span data-stu-id="1707f-131">Ends the BAMApiPo activity.</span></span>  
  
   <span data-ttu-id="1707f-132">**RunOnce**のメソッド、 **InvoiceApplication**クラスは、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="1707f-132">The **RunOnce** method of the **InvoiceApplication** class does the following:</span></span>  
  
9. <span data-ttu-id="1707f-133">請求される注文書を表す XML メッセージをキューから取得します。</span><span class="sxs-lookup"><span data-stu-id="1707f-133">Retrieves from its queue an XML message that represents a purchase order to be invoiced.</span></span>  
  
10. <span data-ttu-id="1707f-134">BAMApiInvoice アクティビティを開始します。</span><span class="sxs-lookup"><span data-stu-id="1707f-134">Begins a BAMApiInvoice activity.</span></span>  
  
11. <span data-ttu-id="1707f-135">請求される注文書の BAMApiInvoice アクティビティと BAMApiPo アクティビティの間に BAM リレーションシップを作成します。</span><span class="sxs-lookup"><span data-stu-id="1707f-135">Creates a BAM relationship between the BAMApiInvoice activity and the BAMApiPo activity for the purchase order that is being invoiced.</span></span>  
  
12. <span data-ttu-id="1707f-136">請求書と請求書の作成時刻に関する情報を BAMApiPo アクティビティに追加します。</span><span class="sxs-lookup"><span data-stu-id="1707f-136">Adds to the BAMApiPo activity information about the invoice and the time it was created.</span></span>  
  
13. <span data-ttu-id="1707f-137">請求書が支払われるまでの待機時間をシミュレートするためにしばらく間を置いて、BAMApiInvoice アクティビティに請求書の支払いが行われた時刻を追加します。</span><span class="sxs-lookup"><span data-stu-id="1707f-137">After an arbitrary delay to simulate waiting for the invoice to be paid, adds to the BAMApiInvoice activity the time the invoice was paid.</span></span>  
  
14. <span data-ttu-id="1707f-138">BAMApiInvoice アクティビティを終了します。</span><span class="sxs-lookup"><span data-stu-id="1707f-138">Ends the BAMApiInvoice activity.</span></span>  
  
    <span data-ttu-id="1707f-139">**Main**のメソッド、 **MainApp**クラスが、アプリケーションを初期化します。</span><span class="sxs-lookup"><span data-stu-id="1707f-139">The **Main** method of the **MainApp** class initializes the application.</span></span> <span data-ttu-id="1707f-140">その後、次の処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="1707f-140">It does the following:</span></span>  
  
15. <span data-ttu-id="1707f-141">作成、 **DirectEventStream**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1707f-141">Creates a **DirectEventStream** object.</span></span>  
  
16. <span data-ttu-id="1707f-142">いくつかのスレッドを開始し、呼び出し、**実行**のメソッド、 **POApplication**各スレッドでオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1707f-142">Starts several threads, and calls the **Run** method of the **POApplication** object in each thread.</span></span>  
  
17. <span data-ttu-id="1707f-143">いくつかのスレッドを開始し、呼び出し、**実行**のメソッド、 **ShipmentApplication**各スレッドでオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1707f-143">Starts several threads, and calls the **Run** method of the **ShipmentApplication** object in each thread.</span></span>  
  
18. <span data-ttu-id="1707f-144">いくつかのスレッドを開始し、呼び出し、**実行**のメソッド、 **InvoiceApplication**各スレッドでオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1707f-144">Starts several threads, and calls the **Run** method of the **InvoiceApplication** object in each thread.</span></span>  
  
    <span data-ttu-id="1707f-145">**Global**クラスを作成するスレッドの数や拒否する注文書の割合など、サンプル アプリケーションで使用される定数を定義します。</span><span class="sxs-lookup"><span data-stu-id="1707f-145">The **Global** class defines constants that are used by the sample application, such as the number of threads to create and the percentage of purchase orders to reject.</span></span>  
  
    <span data-ttu-id="1707f-146">サンプルには、Visual Studio ソリューションに加え、アクティビティを定義する Microsoft Excel ファイルも含まれます。</span><span class="sxs-lookup"><span data-stu-id="1707f-146">In addition to the Visual Studio solution, the sample also contains a Microsoft Excel file that defines the activities.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="1707f-147">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="1707f-147">Where to Find This Sample</span></span>  
 <span data-ttu-id="1707f-148">このサンプルで*\<サンプル パス\>* \BAM\BamApiSample します。</span><span class="sxs-lookup"><span data-stu-id="1707f-148">You can find this sample at *\<Samples Path\>* \BAM\BamApiSample.</span></span>  
  
 <span data-ttu-id="1707f-149">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="1707f-149">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="1707f-150">ファイル</span><span class="sxs-lookup"><span data-stu-id="1707f-150">File</span></span>|<span data-ttu-id="1707f-151">説明</span><span class="sxs-lookup"><span data-stu-id="1707f-151">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="1707f-152">BamApiSample.cs</span><span class="sxs-lookup"><span data-stu-id="1707f-152">BamApiSample.cs</span></span>|<span data-ttu-id="1707f-153">インストルメント化されたアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="1707f-153">Instrumented application.</span></span>|  
|<span data-ttu-id="1707f-154">BamApiSample.csproj</span><span class="sxs-lookup"><span data-stu-id="1707f-154">BamApiSample.csproj</span></span>|<span data-ttu-id="1707f-155">インストルメント化されたアプリケーション プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="1707f-155">Instrumented application project.</span></span>|  
|<span data-ttu-id="1707f-156">BamApiSample.sln</span><span class="sxs-lookup"><span data-stu-id="1707f-156">BamApiSample.sln</span></span>|<span data-ttu-id="1707f-157">インストルメント化されたアプリケーション ソリューション。</span><span class="sxs-lookup"><span data-stu-id="1707f-157">Instrumented application solution.</span></span>|  
|<span data-ttu-id="1707f-158">BamApiSample.xls</span><span class="sxs-lookup"><span data-stu-id="1707f-158">BamApiSample.xls</span></span>|<span data-ttu-id="1707f-159">BAM 定義スタイルシート。</span><span class="sxs-lookup"><span data-stu-id="1707f-159">BAM definition style sheet.</span></span>|  
|<span data-ttu-id="1707f-160">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="1707f-160">Cleanup.bat</span></span>|<span data-ttu-id="1707f-161">展開されたサンプル ファイルを削除するバッチ ファイル。</span><span class="sxs-lookup"><span data-stu-id="1707f-161">Batch file to remove deployed sample files.</span></span>|  
|<span data-ttu-id="1707f-162">Input.txt</span><span class="sxs-lookup"><span data-stu-id="1707f-162">Input.txt</span></span>|<span data-ttu-id="1707f-163">インターセプタ構成入力のサンプル。</span><span class="sxs-lookup"><span data-stu-id="1707f-163">Sample interceptor configuration input.</span></span>|  
|<span data-ttu-id="1707f-164">InterceptorConfig.cs</span><span class="sxs-lookup"><span data-stu-id="1707f-164">InterceptorConfig.cs</span></span>|<span data-ttu-id="1707f-165">API サンプルのインターセプタ構成コード。</span><span class="sxs-lookup"><span data-stu-id="1707f-165">Interceptor configuration code for API sample.</span></span>|  
|<span data-ttu-id="1707f-166">InterceptorConfig.csproj</span><span class="sxs-lookup"><span data-stu-id="1707f-166">InterceptorConfig.csproj</span></span>|<span data-ttu-id="1707f-167">インターセプタ構成プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="1707f-167">Interceptor configuration project.</span></span>|  
|<span data-ttu-id="1707f-168">Invoice_config.xml</span><span class="sxs-lookup"><span data-stu-id="1707f-168">Invoice_config.xml</span></span>|<span data-ttu-id="1707f-169">Invoice インターセプタ構成。</span><span class="sxs-lookup"><span data-stu-id="1707f-169">Invoice interceptor configuration.</span></span>|  
|<span data-ttu-id="1707f-170">Invoice_interceptor.bin</span><span class="sxs-lookup"><span data-stu-id="1707f-170">Invoice_interceptor.bin</span></span>|<span data-ttu-id="1707f-171">シリアル化された Invoice インターセプタ。</span><span class="sxs-lookup"><span data-stu-id="1707f-171">Serialized invoice interceptor.</span></span>|  
|<span data-ttu-id="1707f-172">PurchaseOrder_config.xml</span><span class="sxs-lookup"><span data-stu-id="1707f-172">PurchaseOrder_config.xml</span></span>|<span data-ttu-id="1707f-173">PurchaseOrder インターセプタ構成。</span><span class="sxs-lookup"><span data-stu-id="1707f-173">PurchaseOrder interceptor configuration.</span></span>|  
|<span data-ttu-id="1707f-174">PurchaseOrder_interceptor.bin</span><span class="sxs-lookup"><span data-stu-id="1707f-174">PurchaseOrder_interceptor.bin</span></span>|<span data-ttu-id="1707f-175">シリアル化された PurchaseOrder インターセプタ。</span><span class="sxs-lookup"><span data-stu-id="1707f-175">Serialized PurchaseOrder interceptor.</span></span>|  
|<span data-ttu-id="1707f-176">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="1707f-176">Setup.bat</span></span>|<span data-ttu-id="1707f-177">サンプル ファイルを展開して参加するバッチ ファイル。</span><span class="sxs-lookup"><span data-stu-id="1707f-177">Batch file to deploy and enlist sample files.</span></span>|  
|<span data-ttu-id="1707f-178">Shipment_config.xml</span><span class="sxs-lookup"><span data-stu-id="1707f-178">Shipment_config.xml</span></span>|<span data-ttu-id="1707f-179">Shipment インターセプタ構成。</span><span class="sxs-lookup"><span data-stu-id="1707f-179">Shipment interceptor configuration.</span></span>|  
|<span data-ttu-id="1707f-180">Shipment_interceptor.bin</span><span class="sxs-lookup"><span data-stu-id="1707f-180">Shipment_interceptor.bin</span></span>|<span data-ttu-id="1707f-181">シリアル化された Shipment インターセプター。</span><span class="sxs-lookup"><span data-stu-id="1707f-181">Serialized shipment interceptor.</span></span>|  
  
## <a name="run-the-bam-api-sample"></a><span data-ttu-id="1707f-182">BAM API サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="1707f-182">Run the BAM API sample</span></span>  
  
1.  <span data-ttu-id="1707f-183">管理者は、コマンド プロンプトを開き、実行*\<サンプル パス\>* \BAM\ BamApiSample\setup.bat します。</span><span class="sxs-lookup"><span data-stu-id="1707f-183">Open a command prompt as Administrator, and run *\<Samples Path\>* \BAM\ BamApiSample\setup.bat.</span></span>  
  
2.  <span data-ttu-id="1707f-184">管理者は、Visual Studio を起動し、開く、 *\<サンプル パス\>* \BAM\ BamApiSample\BamApiSample.sln ソリューション。</span><span class="sxs-lookup"><span data-stu-id="1707f-184">Start Visual Studio as Administrator, and open the *\<Samples Path\>* \BAM\ BamApiSample\BamApiSample.sln solution.</span></span> 
  
    > [!IMPORTANT]
    >  <span data-ttu-id="1707f-185">BamApiSample.cs ファイルの `//#define Interceptor` の行をコメント化します。この行から "//" を削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="1707f-185">The line `//#define Interceptor` in the BamApiSample.cs file must be commented out. Do not remove the “//” from this line.</span></span> <span data-ttu-id="1707f-186">BAM API サンプルでは、`#if Interceptor` プリプロセッサ ディレクティブ内にないコードのみを使用します。</span><span class="sxs-lookup"><span data-stu-id="1707f-186">The BAM API sample uses only the code that is not inside an `#if Interceptor` preprocessor directive.</span></span>  
  
3.  <span data-ttu-id="1707f-187">ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="1707f-187">Build the solution.</span></span>  
  
4.  <span data-ttu-id="1707f-188">実行*\<サンプル パス\>* \BAM\BamApiSample\bin\debug\BamApiSample.exe します。</span><span class="sxs-lookup"><span data-stu-id="1707f-188">Run *\<Samples Path\>* \BAM\BamApiSample\bin\debug\BamApiSample.exe.</span></span>  
  
     <span data-ttu-id="1707f-189">出力は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="1707f-189">The output will resemble the following:</span></span>  
  
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
  
5.  <span data-ttu-id="1707f-190">1 分ほど経ったら、Ctrl キーを押しながら C キーを押すか、コマンド プロンプト ウィンドウを閉じて、BamApiSample プログラムを停止します。</span><span class="sxs-lookup"><span data-stu-id="1707f-190">After a minute or so, press CTRL+C or close the Command Prompt window to stop the BamApiSample program.</span></span>  
  
## <a name="view-the-results"></a><span data-ttu-id="1707f-191">結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="1707f-191">View the results</span></span>
  
1.  <span data-ttu-id="1707f-192">SQL Server Management Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="1707f-192">Open SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="1707f-193">SQL Server Management studio で、サーバーを展開し、**データベース**、展開**BAMPrimaryImport**、順に展開**テーブル**します。</span><span class="sxs-lookup"><span data-stu-id="1707f-193">In SQL Server Management Studio, expand the server, expand **Databases**, expand **BAMPrimaryImport**, and then expand **Tables**.</span></span>  
  
3.  <span data-ttu-id="1707f-194">右クリックして**dbo.bam_BAMApiInvoice_Active**  をクリックし、**テーブルを開く**します。</span><span class="sxs-lookup"><span data-stu-id="1707f-194">Right-click **dbo.bam_BAMApiInvoice_Active** and then click **Open Table**.</span></span> <span data-ttu-id="1707f-195">SQL Server を使用している場合はクリックして**上位 1000 行を選択する**します。</span><span class="sxs-lookup"><span data-stu-id="1707f-195">If you are using SQL Server, click **Select top 1000 rows**.</span></span>  
  
     <span data-ttu-id="1707f-196">bam_BAMApiInvoice_Active テーブルの内容が右側のウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1707f-196">The contents of the bam_BAMApiInvoice_Active table are displayed in the right pane.</span></span> <span data-ttu-id="1707f-197">テーブルの各行は、開始されているが、完了していない BAMApiInvoice アクティビティを表します。</span><span class="sxs-lookup"><span data-stu-id="1707f-197">Each row in the table represents a BAMApiInvoice activity that has been started, but  has not been completed.</span></span>  
  
4.  <span data-ttu-id="1707f-198">右クリックして**dbo.bam_BAMApiPo_Completed**  をクリックし、**テーブルを開く**します。</span><span class="sxs-lookup"><span data-stu-id="1707f-198">Right-click **dbo.bam_BAMApiPo_Completed** and then click **Open Table**.</span></span> <span data-ttu-id="1707f-199">SQL Server を使用している場合はクリックして**上位 1000 行を選択する**します。</span><span class="sxs-lookup"><span data-stu-id="1707f-199">If you are using SQL Server, click **Select top 1000 rows**.</span></span>  
  
     <span data-ttu-id="1707f-200">bam_BAMApiPo_Completed テーブルの内容が右側のウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1707f-200">The contents of the bam_BAMApiPo_Completed table are displayed in the right pane.</span></span> <span data-ttu-id="1707f-201">テーブルの各行は、完了した BAMApiPo アクティビティを表します。</span><span class="sxs-lookup"><span data-stu-id="1707f-201">Each row in the table represents a BAMApiPo activity that has been completed.</span></span>