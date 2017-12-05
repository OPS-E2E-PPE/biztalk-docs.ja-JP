---
title: "指向ソリューションのサービスを実行する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- service solution tutorial, client applications
- service solution tutorial, starting solution
- service solution tutorial, sending requests
- service solution tutorial, SOAP transports
ms.assetid: 764a5ddc-e571-41d8-9e2f-6d0fb3361b2f
caps.latest.revision: "31"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35c33b914ecbb9f385e5546d100b7572b4b48b6a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-run-the-service-oriented-solution"></a><span data-ttu-id="b086d-102">サービス指向ソリューションの実行方法</span><span class="sxs-lookup"><span data-stu-id="b086d-102">How to Run the Service Oriented Solution</span></span>
<span data-ttu-id="b086d-103">次の手順では、単一のコンピュータでサービス指向ソリューションを実行および検証する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b086d-103">The following steps describe how to run and validate the service oriented solution on a single computer.</span></span> <span data-ttu-id="b086d-104">Payment Tracker シミュレーターを開始してから、SOAP トランスポートまたは MQSeries トランスポートを使用して、要求を送信できます (アダプター バージョンおよびインライン バージョンのサービス指向ソリューションには個別の手順を使用します)。</span><span class="sxs-lookup"><span data-stu-id="b086d-104">After starting the Payment Tracker simulator, you can send requests using either the SOAP or MQSeries transport (with separate procedures for the adapter and inline versions of the service oriented solution).</span></span>  
  
-   [<span data-ttu-id="b086d-105">クライアント アプリケーション (スタブ バージョン) を使用して SOAP トランスポートによる要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="b086d-105">Send requests by SOAP transport using the client application (stub version)</span></span>](#step1)  
  
-   [<span data-ttu-id="b086d-106">クライアント アプリケーション (アダプタ バージョン) を使用して要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="b086d-106">Send requests using the client application (adapter version)</span></span>](#step3)  
  
-   [<span data-ttu-id="b086d-107">クライアント アプリケーション (インライン バージョン) を使用して要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="b086d-107">Send requests using the client application (inline version)</span></span>](#step5)  
  
##  <a name="step1"></a><span data-ttu-id="b086d-108">クライアント アプリケーション (スタブ バージョン) を使用して SOAP トランスポートによる要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="b086d-108">Send requests by SOAP transport using the client application (stub version)</span></span>  
  
#### <a name="to-send-requests-by-soap-transport-using-the-client-application-stub-version"></a><span data-ttu-id="b086d-109">クライアント アプリケーション (スタブ バージョン) で SOAP トランスポートによる要求を送信するには</span><span class="sxs-lookup"><span data-stu-id="b086d-109">To send requests by SOAP transport using the client application (stub version)</span></span>  
  
1.  <span data-ttu-id="b086d-110">コマンド プロンプトを開き、ディレクトリに移動、 \< *BizTalk Server のインストール ディレクトリ*\>\SDK\Scenarios\SO\BTSSoln\SimpleClient\bin\Release とし、BTSScnSOSimpleClient.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="b086d-110">Open a command prompt, change the directory to the \<*BizTalk Server install Directory*\>\SDK\Scenarios\SO\BTSSoln\SimpleClient\bin\Release, and then run the BTSScnSOSimpleClient.exe.</span></span>  
  
2.  <span data-ttu-id="b086d-111">文字を入力、 **RequestType**、 **RequestSource**、および**RequestID**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="b086d-111">Type any characters in the **RequestType**, **RequestSource**, and **RequestID** text boxes.</span></span>  
  
3.  <span data-ttu-id="b086d-112">任意の 16 桁の数値を入力、**アカウント番号**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="b086d-112">Type any 16-digit number in the **Account Number** text box.</span></span>  
  
4.  <span data-ttu-id="b086d-113">選択**SOAP (WS Call)**と**スタブ**で、 **Select Transport and Parameters**グループ ボックス。</span><span class="sxs-lookup"><span data-stu-id="b086d-113">Select **SOAP (WS Call)** and **Stub** in the **Select Transport and Parameters** group box.</span></span>  
  
5.  <span data-ttu-id="b086d-114">次の URL を入力、 **URL**などのテキスト ボックスします。</span><span class="sxs-lookup"><span data-stu-id="b086d-114">Type the following URL in the **URL** text box, for example:</span></span>  
  
6.  `http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Stub/CustomerServicePort.asmx`  
  
7.  <span data-ttu-id="b086d-115">型`ZipCode`で、**名前**下のテキスト ボックス**Authentication Elements**、内の文字を入力し、**値**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="b086d-115">Type `ZipCode` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
8.  <span data-ttu-id="b086d-116">型`CustomerName`で、**名前**下のテキスト ボックス**Authentication Elements**、内の文字を入力し、**値**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="b086d-116">Type `CustomerName` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
9. <span data-ttu-id="b086d-117">をクリックして**my バランス**です。</span><span class="sxs-lookup"><span data-stu-id="b086d-117">Click **Get my balance**.</span></span>  
  
10. <span data-ttu-id="b086d-118">応答が表示されます、**応答**テキスト ボックス:**成功**場合に表示されます、要求が正常に処理以外の場合は、要求が失敗した場合、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b086d-118">The response is displayed in the **Response** text box: **SUCCESS** appears if the request is handled successfully; an error message appears if the request fails.</span></span>  
  
     <span data-ttu-id="b086d-119">![スタブ バージョン用のクライアント アプリケーション実行](../core/media/bts-cp-so-deploy-stubversion-success.gif "BTS_CP_SO_Deploy_StubVersion_Success")</span><span class="sxs-lookup"><span data-stu-id="b086d-119">![Run the client application for the stub version](../core/media/bts-cp-so-deploy-stubversion-success.gif "BTS_CP_SO_Deploy_StubVersion_Success")</span></span>  
  
##  <a name="step3"></a><span data-ttu-id="b086d-120">クライアント アプリケーション (アダプタ バージョン) を使用して要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="b086d-120">Send requests using the client application (adapter version)</span></span>  
  
#### <a name="to-send-requests-using-the-client-application-adapter-version"></a><span data-ttu-id="b086d-121">クライアント アプリケーション (アダプタ バージョン) での要求を送信するには</span><span class="sxs-lookup"><span data-stu-id="b086d-121">To send requests using the client application (adapter version)</span></span>  
  
1.  <span data-ttu-id="b086d-122">コマンド プロンプトを開き、ディレクトリに移動\< *BizTalk Server のインストール ディレクトリ*\>\SDK\Scenarios\SO\BTSSoln\PaymentTracker\bin\Debug と、次のコマンドを起動し実行しますPaymentTracker シミュレーターの場合:</span><span class="sxs-lookup"><span data-stu-id="b086d-122">Open a command prompt, change the directory to \<*BizTalk Server install Directory*\>\SDK\Scenarios\SO\BTSSoln\PaymentTracker\bin\Debug and, then run the following command to start the PaymentTracker simulator:</span></span>  
  
     <span data-ttu-id="b086d-123">`BTSScnSOPaymentTracker.exe LastPaymentsInputQueue LastPaymentsOutputQueue <`*キュー マネージャ名* `> 5 [<` *チャネル定義*`>]`</span><span class="sxs-lookup"><span data-stu-id="b086d-123">`BTSScnSOPaymentTracker.exe LastPaymentsInputQueue LastPaymentsOutputQueue <` *Queue Manager Name* `> 5 [<` *Channel Definition* `>]`</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b086d-124">チャネル定義は、リモート MQSeries Server ではない場合、省略可能です。</span><span class="sxs-lookup"><span data-stu-id="b086d-124">The channel definition is optional if it is not remote MQSeries Server.</span></span>  
  
    -   <span data-ttu-id="b086d-125">Payment Tracker シミュレータを起動したままにします。</span><span class="sxs-lookup"><span data-stu-id="b086d-125">Leave the Payment Tracker simulator running.</span></span>  
  
2.  <span data-ttu-id="b086d-126">コマンド プロンプトを開き、ディレクトリに移動、 \< *BizTalk Server のインストール ディレクトリ*\>\SDK\Scenarios\SO\BTSSoln\SimpleClient\bin\Release とし、BTSScnSOSimpleClient.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="b086d-126">Open a command prompt, change the directory to the \<*BizTalk Server install Directory*\>\SDK\Scenarios\SO\BTSSoln\SimpleClient\bin\Release, and then run the BTSScnSOSimpleClient.exe.</span></span>  
  
3.  <span data-ttu-id="b086d-127">BTSScnSOSimpleClient.exe で、次に示すように、SOAP トランスポートによる要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="b086d-127">In the BTSScnSOSimpleClient.exe, send a request by SOAP transport using the as follows:</span></span>  
  
    1.  <span data-ttu-id="b086d-128">文字を入力、 **RequestType**、 **RequestSource**、および**RequestID**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="b086d-128">Type any characters in the **RequestType**, **RequestSource**, and **RequestID** text boxes.</span></span>  
  
    2.  <span data-ttu-id="b086d-129">任意の 16 桁の数値を入力、**アカウント番号**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="b086d-129">Type any 16-digit number in the **Account Number** text box.</span></span>  
  
    3.  <span data-ttu-id="b086d-130">選択**SOAP (WS Call)**と**アダプター**で、 **Select Transport and Parameters**グループ ボックス。</span><span class="sxs-lookup"><span data-stu-id="b086d-130">Select **SOAP (WS Call)** and **Adapter** in the **Select Transport and Parameters** group box.</span></span>  
  
    4.  <span data-ttu-id="b086d-131">次の URL を入力、 **URL**などのテキスト ボックスします。</span><span class="sxs-lookup"><span data-stu-id="b086d-131">Type the following URL in the **URL** text box, for example:</span></span>  
  
         `http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Adapter/CustomerServicePort.asmx`  
  
    5.  <span data-ttu-id="b086d-132">型`ZipCode`で、**名前**下のテキスト ボックス**Authentication Elements**、内の文字を入力し、**値**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="b086d-132">Type `ZipCode` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
    6.  <span data-ttu-id="b086d-133">型`CustomerName`で、**名前**下のテキスト ボックス**Authentication Elements**、内の文字を入力し、**値**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="b086d-133">Type `CustomerName` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
    7.  <span data-ttu-id="b086d-134">をクリックして**my バランス**です。</span><span class="sxs-lookup"><span data-stu-id="b086d-134">Click **Get my balance**.</span></span>  
  
    8.  <span data-ttu-id="b086d-135">応答が表示されます、**応答**テキスト ボックス:**成功**場合に表示されます、要求が正常に処理以外の場合は、要求が失敗した場合、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b086d-135">The response is displayed in the **Response** text box: **SUCCESS** appears if the request is handled successfully; an error message appears if the request fails.</span></span>  
  
         <span data-ttu-id="b086d-136">![アダプター バージョンのクライアント アプリケーションを実行](../core/media/soap-transport-adapter-success.gif "SOAP_Transport_adapter_success")</span><span class="sxs-lookup"><span data-stu-id="b086d-136">![Run the client application for the adapter version](../core/media/soap-transport-adapter-success.gif "SOAP_Transport_adapter_success")</span></span>  
  
4.  <span data-ttu-id="b086d-137">BTSScnSOSimpleClient.exe で、MQSeries トランスポートを使用して要求を送信するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b086d-137">In the BTSScnSOSimpleClient.exe, send requests by MQSeries transport as follows:</span></span>  
  
    1.  <span data-ttu-id="b086d-138">文字を入力、 **RequestType**、 **RequestSource**、および**RequestID**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="b086d-138">Type any characters in the **RequestType**, **RequestSource**, and **RequestID** text boxes.</span></span>  
  
    2.  <span data-ttu-id="b086d-139">16 桁の数字を入力、**アカウント番号**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="b086d-139">Type a 16-digit number in the **Account Number** text box.</span></span>  
  
    3.  <span data-ttu-id="b086d-140">選択**MQSeries**で、 **Select Transport and Parameters**グループ ボックス。</span><span class="sxs-lookup"><span data-stu-id="b086d-140">Select **MQSeries** in the **Select Transport and Parameters** group box.</span></span>  
  
    4.  <span data-ttu-id="b086d-141">型\<*キュー マネージャ名*\>で、**キュー マネージャー**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="b086d-141">Type \<*Queue Manager Name*\> in the **Queue Manager** text box.</span></span> <span data-ttu-id="b086d-142">Qm _\<*コンピューター名を*\>の既定値は、 \<*キュー マネージャ名*\>です。</span><span class="sxs-lookup"><span data-stu-id="b086d-142">QM_\<*Your Computer Name*\> is the default value for \<*Queue Manager Name*\>.</span></span>  
  
    5.  <span data-ttu-id="b086d-143">型`AdapterSOAInputQueue`で、 **Input Queue**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="b086d-143">Type `AdapterSOAInputQueue` in the **Input Queue** text box.</span></span>  
  
    6.  <span data-ttu-id="b086d-144">型`AdapterSOAOutputQueue`で、**出力キュー**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="b086d-144">Type `AdapterSOAOutputQueue` in the **Output Queue** text box.</span></span>  
  
    7.  <span data-ttu-id="b086d-145">型\<*チャネル定義*\>で、**チャネル定義**ボックス。</span><span class="sxs-lookup"><span data-stu-id="b086d-145">Type \<*Channel Definition*\> in the **Channel Definition** box.</span></span> <span data-ttu-id="b086d-146">S _\<*コンピューター名を*\>/tcp/\<*コンピューター名を*\>(1414) の既定値は、 \< *チャネル定義*\>です。</span><span class="sxs-lookup"><span data-stu-id="b086d-146">S_\<*Your Computer Name*\>/TCP/\<*Your Computer Name*\>(1414) is the default value for \<*Channel Definition*\>.</span></span>  
  
    8.  <span data-ttu-id="b086d-147">型`ZipCode`で、**名前**下のテキスト ボックス**Authentication Elements**、内の文字を入力し、**値**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="b086d-147">Type `ZipCode` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
    9. <span data-ttu-id="b086d-148">型`CustomerName`で、**名前**下のテキスト ボックス**Authentication Elements**、内の文字を入力し、**値**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="b086d-148">Type `CustomerName` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
    10. <span data-ttu-id="b086d-149">をクリックして**my バランス**です。</span><span class="sxs-lookup"><span data-stu-id="b086d-149">Click **Get my balance**.</span></span>  
  
    11. <span data-ttu-id="b086d-150">応答が表示されます、**応答**テキスト ボックス:**成功**場合に表示されます、要求が正常に処理以外の場合は、要求が失敗した場合、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b086d-150">The response is displayed in the **Response** text box: **SUCCESS** appears if the request is handled successfully; an error message appears if the request fails.</span></span>  
  
         <span data-ttu-id="b086d-151">![アダプター バージョンのクライアント アプリケーションを実行](../core/media/mqseries-transport-adapter.gif "MQSeries_Transport_adapter")</span><span class="sxs-lookup"><span data-stu-id="b086d-151">![Run the client application for the adapter version](../core/media/mqseries-transport-adapter.gif "MQSeries_Transport_adapter")</span></span>  
  
##  <a name="step5"></a><span data-ttu-id="b086d-152">クライアント アプリケーション (インライン バージョン) を使用して要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="b086d-152">Send requests using the client application (inline version)</span></span>  
  
#### <a name="to-send-requests-using-the-client-application-inline-version"></a><span data-ttu-id="b086d-153">クライアント アプリケーション (インライン バージョン) での要求を送信するには</span><span class="sxs-lookup"><span data-stu-id="b086d-153">To send requests using the client application (inline version)</span></span>  
  
1.  <span data-ttu-id="b086d-154">コマンド プロンプトを開き、ディレクトリに移動\< *BizTalk Server のインストール ディレクトリ*\>\SDK\Scenarios\SO\BTSSoln\PaymentTracker\bin\Debug してから実行して、次のコマンドを開始する、PaymentTracker シミュレーターの場合:</span><span class="sxs-lookup"><span data-stu-id="b086d-154">Open a command prompt, change the directory to \<*BizTalk Server install Directory*\>\SDK\Scenarios\SO\BTSSoln\PaymentTracker\bin\Debug, and then run the following command to start the PaymentTracker simulator:</span></span>  
  
     <span data-ttu-id="b086d-155">`BTSScnSOPaymentTracker.exe LastPaymentsInputQueue LastPaymentsOutputQueue <`*キュー マネージャ名* `> 5 [<` *チャネル定義*`>]`</span><span class="sxs-lookup"><span data-stu-id="b086d-155">`BTSScnSOPaymentTracker.exe LastPaymentsInputQueue LastPaymentsOutputQueue <` *Queue Manager Name* `> 5 [<` *Channel Definition* `>]`</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b086d-156">チャネル定義は、リモート MQSeries Server ではない場合、省略可能です。</span><span class="sxs-lookup"><span data-stu-id="b086d-156">The channel definition is optional if it is not remote MQSeries Server.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b086d-157">PaymentTracker シミュレーターが既に実行されている場合は、この手順をスキップします。</span><span class="sxs-lookup"><span data-stu-id="b086d-157">Skip this step if the PaymentTracker simulator is already running.</span></span>  
  
    -   <span data-ttu-id="b086d-158">Payment Tracker シミュレータを起動したままにします。</span><span class="sxs-lookup"><span data-stu-id="b086d-158">Leave the Payment Tracker simulator running.</span></span>  
  
2.  <span data-ttu-id="b086d-159">**BizTalk Server 管理コンソール**、展開**[btsscn.so.customerservice]**をクリックして**受信場所**を右クリックして**[Paymenttrackingsystemoutputqueue]**をクリックして右側のウィンドウ**を無効にする**です。</span><span class="sxs-lookup"><span data-stu-id="b086d-159">In the **BizTalk Server Administration Console**, expand **BTSScn.SO.CustomerService**, click **Receive Locations**, right-click **PaymentTrackingSystemOutputQueue** in the right pane, and then click **Disable**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b086d-160">アダプタ バージョンとインライン バージョンでは、同じ MQSeries キュー (LastPaymentsOutputQueue) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="b086d-160">The adapter version and inline version uses the same MQSeries queue, LastPaymentsOutputQueue.</span></span> <span data-ttu-id="b086d-161">2 つのバージョンの競合状態を避けるには、MQSeries キューで受信を待機しているアダプタのバージョンの受信場所を無効にします。</span><span class="sxs-lookup"><span data-stu-id="b086d-161">To avoid the race condition between two versions, disable the adapter version's receive location listening on the MQSeries queue.</span></span>  
  
3.  <span data-ttu-id="b086d-162">コマンド プロンプトを開き、ディレクトリに移動、 \< *BizTalk Server のインストール ディレクトリ*\>\SDK\Scenarios\SO\BTSSoln\SimpleClient\bin\Release とし、BTSScnSOSimpleClient.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="b086d-162">Open a command prompt, change the directory to the \<*BizTalk Server install Directory*\>\SDK\Scenarios\SO\BTSSoln\SimpleClient\bin\Release, and then run the BTSScnSOSimpleClient.exe.</span></span>  
  
4.  <span data-ttu-id="b086d-163">BTSScnSOSimpleClient.exe で、次に示すように、SOAP トランスポートによる要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="b086d-163">In the BTSScnSOSimpleClient.exe, send a request by SOAP transport using the as follows:</span></span>  
  
    1.  <span data-ttu-id="b086d-164">文字を入力、 **RequestType**、 **RequestSource**、および**RequestID**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="b086d-164">Type any characters in the **RequestType**, **RequestSource**, and **RequestID** text boxes.</span></span>  
  
    2.  <span data-ttu-id="b086d-165">任意の 16 桁の数値を入力、**アカウント番号**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="b086d-165">Type any 16-digit number in the **Account Number** text box.</span></span>  
  
    3.  <span data-ttu-id="b086d-166">選択**SOAP (WS Call)**と**インライン**で、 **Select Transport and Parameters**グループ ボックス。</span><span class="sxs-lookup"><span data-stu-id="b086d-166">Select **SOAP (WS Call)** and **Inline** in the **Select Transport and Parameters** group box.</span></span>  
  
    4.  <span data-ttu-id="b086d-167">次の URL を入力、 **URL**などのテキスト ボックスします。</span><span class="sxs-lookup"><span data-stu-id="b086d-167">Type the following URL in the **URL** text box, for example:</span></span>  
  
         `http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Inline/CustomerServicePort.asmx`  
  
    5.  <span data-ttu-id="b086d-168">型`ZipCode`で、**名前**下のテキスト ボックス**Authentication Elements**、内の文字を入力し、**値**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="b086d-168">Type `ZipCode` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
    6.  <span data-ttu-id="b086d-169">型`CustomerName`で、**名前**下のテキスト ボックス**Authentication Elements**、内の文字を入力し、**値**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="b086d-169">Type `CustomerName` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
    7.  <span data-ttu-id="b086d-170">をクリックして**my バランス**です。</span><span class="sxs-lookup"><span data-stu-id="b086d-170">Click **Get my balance**.</span></span>  
  
    8.  <span data-ttu-id="b086d-171">応答が表示されます、**応答**テキスト ボックス:**成功**場合に表示されます、要求が正常に処理以外の場合は、要求が失敗した場合、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b086d-171">The response is displayed in the **Response** text box: **SUCCESS** appears if the request is handled successfully; an error message appears if the request fails.</span></span>  
  
         <span data-ttu-id="b086d-172">![インライン バージョンのクライアント アプリケーションを実行](../core/media/soap-transport-inline.gif "SOAP_Transport_inline")</span><span class="sxs-lookup"><span data-stu-id="b086d-172">![Run the client application for the inline version](../core/media/soap-transport-inline.gif "SOAP_Transport_inline")</span></span>  
  
5.  <span data-ttu-id="b086d-173">BTSScnSOSimpleClient.exe で、MQSeries トランスポートを使用して要求を送信するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b086d-173">In the BTSScnSOSimpleClient.exe, send requests by MQSeries transport as follows:</span></span>  
  
    1.  <span data-ttu-id="b086d-174">文字を入力、 **RequestType**、 **RequestSource**、および**RequestID**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="b086d-174">Type any characters in the **RequestType**, **RequestSource**, and **RequestID** text boxes.</span></span>  
  
    2.  <span data-ttu-id="b086d-175">16 桁の数字を入力、**アカウント番号**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="b086d-175">Type a 16-digit number in the **Account Number** text box.</span></span>  
  
    3.  <span data-ttu-id="b086d-176">選択**MQSeries**で、 **Select Transport and Parameters**グループ ボックス。</span><span class="sxs-lookup"><span data-stu-id="b086d-176">Select **MQSeries** in the **Select Transport and Parameters** group box.</span></span>  
  
    4.  <span data-ttu-id="b086d-177">型\<*キュー マネージャ名*\>で、**キュー マネージャー**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="b086d-177">Type \<*Queue Manager Name*\> in the **Queue Manager** text box.</span></span> <span data-ttu-id="b086d-178">Qm _\<*コンピューター名を*\>の既定値は、 \<*キュー マネージャ名*\>です。</span><span class="sxs-lookup"><span data-stu-id="b086d-178">QM_\<*Your Computer Name*\> is the default value for \<*Queue Manager Name*\>.</span></span>  
  
    5.  <span data-ttu-id="b086d-179">型`InlineSOAInputQueue`で、 **Input Queue**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="b086d-179">Type `InlineSOAInputQueue` in the **Input Queue** text box.</span></span>  
  
    6.  <span data-ttu-id="b086d-180">型`InlineSOAOutputQueue`で、**出力キュー**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="b086d-180">Type `InlineSOAOutputQueue` in the **Output Queue** text box.</span></span>  
  
    7.  <span data-ttu-id="b086d-181">型\<*チャネル定義*\>で、**チャネル定義**ボックス。</span><span class="sxs-lookup"><span data-stu-id="b086d-181">Type \<*Channel Definition*\> in the **Channel Definition** box.</span></span> <span data-ttu-id="b086d-182">S _\<*コンピューター名を*\>/tcp/\<*コンピューター名を*\>(1414) の既定値は、 \< *チャネル定義*\>です。</span><span class="sxs-lookup"><span data-stu-id="b086d-182">S_\<*Your Computer Name*\>/TCP/\<*Your Computer Name*\>(1414) is the default value for \<*Channel Definition*\>.</span></span>  
  
    8.  <span data-ttu-id="b086d-183">型`ZipCode`で、**名前**下のテキスト ボックス**Authentication Elements**、内の文字を入力し、**値**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="b086d-183">Type `ZipCode` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
    9. <span data-ttu-id="b086d-184">型`CustomerName`で、**名前**下のテキスト ボックス**Authentication Elements**、内の文字を入力し、**値**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="b086d-184">Type `CustomerName` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
    10. <span data-ttu-id="b086d-185">をクリックして**my バランス**です。</span><span class="sxs-lookup"><span data-stu-id="b086d-185">Click **Get my balance**.</span></span>  
  
    11. <span data-ttu-id="b086d-186">応答が表示されます、**応答**テキスト ボックス:**成功**場合に表示されます、要求が正常に処理以外の場合は、要求が失敗した場合、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b086d-186">The response is displayed in the **Response** text box: **SUCCESS** appears if the request is handled successfully; an error message appears if the request fails.</span></span>  
  
         <span data-ttu-id="b086d-187">![インライン バージョンのクライアント アプリケーションを実行](../core/media/mqseries-transport-inline.gif "MQSeries_Transport_inline")</span><span class="sxs-lookup"><span data-stu-id="b086d-187">![Run the client application for the inline version](../core/media/mqseries-transport-inline.gif "MQSeries_Transport_inline")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b086d-188">参照</span><span class="sxs-lookup"><span data-stu-id="b086d-188">See Also</span></span>  
 <span data-ttu-id="b086d-189">[サービス指向ソリューションをインストールする前に](../core/before-installing-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="b086d-189">[Before Installing the Service Oriented Solution](../core/before-installing-the-service-oriented-solution.md) </span></span>  
 <span data-ttu-id="b086d-190">[指向ソリューションのスタブ バージョンのサービスをインストールする方法](../core/how-to-install-the-stub-version-of-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="b086d-190">[How to Install the Stub Version of the Service Oriented Solution](../core/how-to-install-the-stub-version-of-the-service-oriented-solution.md) </span></span>  
 <span data-ttu-id="b086d-191">[指向ソリューションのインライン バージョンおよびアダプター バージョンのサービスをインストールする方法](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="b086d-191">[How to Install the Inline and Adapter Versions of the Service Oriented Solution](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md) </span></span>  
 [<span data-ttu-id="b086d-192">サービス指向ソリューションに対する開発者のコンピューター設定</span><span class="sxs-lookup"><span data-stu-id="b086d-192">Developer Machine Setup for the Service Oriented Solution</span></span>](../core/developer-machine-setup-for-the-service-oriented-solution.md)