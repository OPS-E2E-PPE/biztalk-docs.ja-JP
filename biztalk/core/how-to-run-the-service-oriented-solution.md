---
title: 指向ソリューションのサービスを実行する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service solution tutorial, client applications
- service solution tutorial, starting solution
- service solution tutorial, sending requests
- service solution tutorial, SOAP transports
ms.assetid: 764a5ddc-e571-41d8-9e2f-6d0fb3361b2f
caps.latest.revision: 31
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8aa1fed4a695eef0e21a3199854416436bf2af13
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384071"
---
# <a name="how-to-run-the-service-oriented-solution"></a><span data-ttu-id="474db-102">指向ソリューションのサービスを実行する方法</span><span class="sxs-lookup"><span data-stu-id="474db-102">How to Run the Service Oriented Solution</span></span>
<span data-ttu-id="474db-103">次の手順を実行し、1 台のコンピューターでサービス指向ソリューションを検証する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="474db-103">The following steps describe how to run and validate the service oriented solution on a single computer.</span></span> <span data-ttu-id="474db-104">Payment Tracker シミュレーターを開始した後 (個別の手順をサービス指向ソリューションのバージョンのアダプターとインライン バージョンでは) を SOAP または MQSeries トランスポートを使用して要求を送信できます。</span><span class="sxs-lookup"><span data-stu-id="474db-104">After starting the Payment Tracker simulator, you can send requests using either the SOAP or MQSeries transport (with separate procedures for the adapter and inline versions of the service oriented solution).</span></span>  
  
-   [<span data-ttu-id="474db-105">クライアント アプリケーション (スタブ バージョン) を使用して SOAP トランスポートによる要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="474db-105">Send requests by SOAP transport using the client application (stub version)</span></span>](#step1)  
  
-   [<span data-ttu-id="474db-106">クライアント アプリケーション (アダプタ バージョン) を使用して要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="474db-106">Send requests using the client application (adapter version)</span></span>](#step3)  
  
-   [<span data-ttu-id="474db-107">クライアント アプリケーション (インライン バージョン) を使用して要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="474db-107">Send requests using the client application (inline version)</span></span>](#step5)  
  
##  <a name="step1"></a> <span data-ttu-id="474db-108">クライアント アプリケーション (スタブ バージョン) を使用して SOAP トランスポートによる要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="474db-108">Send requests by SOAP transport using the client application (stub version)</span></span>  
  
#### <a name="to-send-requests-by-soap-transport-using-the-client-application-stub-version"></a><span data-ttu-id="474db-109">クライアント アプリケーション (スタブ バージョン) を使用して SOAP トランスポートによる要求を送信するには</span><span class="sxs-lookup"><span data-stu-id="474db-109">To send requests by SOAP transport using the client application (stub version)</span></span>  
  
1.  <span data-ttu-id="474db-110">コマンド プロンプトを開き、ディレクトリを\< *BizTalk Server のインストール ディレクトリ*\>\SDK\Scenarios\SO\BTSSoln\SimpleClient\bin\Release とし、BTSScnSOSimpleClient.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="474db-110">Open a command prompt, change the directory to the \<*BizTalk Server install Directory*\>\SDK\Scenarios\SO\BTSSoln\SimpleClient\bin\Release, and then run the BTSScnSOSimpleClient.exe.</span></span>  
  
2.  <span data-ttu-id="474db-111">任意の文字を入力、 **RequestType**、 **RequestSource**、および**RequestID**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="474db-111">Type any characters in the **RequestType**, **RequestSource**, and **RequestID** text boxes.</span></span>  
  
3.  <span data-ttu-id="474db-112">任意の 16 桁の数字を入力、**アカウント番号**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="474db-112">Type any 16-digit number in the **Account Number** text box.</span></span>  
  
4.  <span data-ttu-id="474db-113">選択**SOAP (WS Call)** と**スタブ**で、 **Select Transport and Parameters**グループ ボックス。</span><span class="sxs-lookup"><span data-stu-id="474db-113">Select **SOAP (WS Call)** and **Stub** in the **Select Transport and Parameters** group box.</span></span>  
  
5.  <span data-ttu-id="474db-114">次の URL を入力、 **URL**テキスト ボックスに、たとえば。</span><span class="sxs-lookup"><span data-stu-id="474db-114">Type the following URL in the **URL** text box, for example:</span></span>  
  
6.  `http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Stub/CustomerServicePort.asmx`  
  
7.  <span data-ttu-id="474db-115">型`ZipCode`で、**名前**下にあるテキスト ボックス**認証要素**、任意の文字を入力し、**値**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="474db-115">Type `ZipCode` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
8.  <span data-ttu-id="474db-116">型`CustomerName`で、**名前**下にあるテキスト ボックス**認証要素**、任意の文字を入力し、**値**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="474db-116">Type `CustomerName` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
9. <span data-ttu-id="474db-117">クリックして **、バランス**します。</span><span class="sxs-lookup"><span data-stu-id="474db-117">Click **Get my balance**.</span></span>  
  
10. <span data-ttu-id="474db-118">応答が表示されます、**応答**テキスト ボックス。**成功**場合に表示されます、要求が正常に処理されます。 要求が失敗した場合、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="474db-118">The response is displayed in the **Response** text box: **SUCCESS** appears if the request is handled successfully; an error message appears if the request fails.</span></span>  
  
     <span data-ttu-id="474db-119">![スタブ バージョン用のクライアント アプリケーションを実行](../core/media/bts-cp-so-deploy-stubversion-success.gif "BTS_CP_SO_Deploy_StubVersion_Success")</span><span class="sxs-lookup"><span data-stu-id="474db-119">![Run the client application for the stub version](../core/media/bts-cp-so-deploy-stubversion-success.gif "BTS_CP_SO_Deploy_StubVersion_Success")</span></span>  
  
##  <a name="step3"></a> <span data-ttu-id="474db-120">クライアント アプリケーション (アダプタ バージョン) を使用して要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="474db-120">Send requests using the client application (adapter version)</span></span>  
  
#### <a name="to-send-requests-using-the-client-application-adapter-version"></a><span data-ttu-id="474db-121">クライアント アプリケーション (アダプタ バージョン) を使用して要求を送信するには</span><span class="sxs-lookup"><span data-stu-id="474db-121">To send requests using the client application (adapter version)</span></span>  
  
1.  <span data-ttu-id="474db-122">コマンド プロンプトを開き、ディレクトリに移動します\< *BizTalk Server のインストール ディレクトリ*\>\SDK\Scenarios\SO\BTSSoln\PaymentTracker\bin\Debug、および開始する、次のコマンドを実行し、PaymentTracker シミュレーターの場合:</span><span class="sxs-lookup"><span data-stu-id="474db-122">Open a command prompt, change the directory to \<*BizTalk Server install Directory*\>\SDK\Scenarios\SO\BTSSoln\PaymentTracker\bin\Debug and, then run the following command to start the PaymentTracker simulator:</span></span>  
  
     <span data-ttu-id="474db-123">`BTSScnSOPaymentTracker.exe LastPaymentsInputQueue LastPaymentsOutputQueue <` *キュー マネージャー名* `> 5 [<` *チャネルの定義* `>]`</span><span class="sxs-lookup"><span data-stu-id="474db-123">`BTSScnSOPaymentTracker.exe LastPaymentsInputQueue LastPaymentsOutputQueue <` *Queue Manager Name* `> 5 [<` *Channel Definition* `>]`</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="474db-124">チャネル定義は、リモートの MQSeries サーバーでない場合は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="474db-124">The channel definition is optional if it is not remote MQSeries Server.</span></span>  
  
    -   <span data-ttu-id="474db-125">Payment Tracker シミュレーターが実行されているままにします。</span><span class="sxs-lookup"><span data-stu-id="474db-125">Leave the Payment Tracker simulator running.</span></span>  
  
2.  <span data-ttu-id="474db-126">コマンド プロンプトを開き、ディレクトリを\< *BizTalk Server のインストール ディレクトリ*\>\SDK\Scenarios\SO\BTSSoln\SimpleClient\bin\Release とし、BTSScnSOSimpleClient.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="474db-126">Open a command prompt, change the directory to the \<*BizTalk Server install Directory*\>\SDK\Scenarios\SO\BTSSoln\SimpleClient\bin\Release, and then run the BTSScnSOSimpleClient.exe.</span></span>  
  
3.  <span data-ttu-id="474db-127">BTSScnSOSimpleClient.exe で、SOAP トランスポートによる要求としてを使用して送信次に示します。</span><span class="sxs-lookup"><span data-stu-id="474db-127">In the BTSScnSOSimpleClient.exe, send a request by SOAP transport using the as follows:</span></span>  
  
    1.  <span data-ttu-id="474db-128">任意の文字を入力、 **RequestType**、 **RequestSource**、および**RequestID**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="474db-128">Type any characters in the **RequestType**, **RequestSource**, and **RequestID** text boxes.</span></span>  
  
    2.  <span data-ttu-id="474db-129">任意の 16 桁の数字を入力、**アカウント番号**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="474db-129">Type any 16-digit number in the **Account Number** text box.</span></span>  
  
    3.  <span data-ttu-id="474db-130">選択**SOAP (WS Call)** と**アダプター**で、 **Select Transport and Parameters**グループ ボックス。</span><span class="sxs-lookup"><span data-stu-id="474db-130">Select **SOAP (WS Call)** and **Adapter** in the **Select Transport and Parameters** group box.</span></span>  
  
    4.  <span data-ttu-id="474db-131">次の URL を入力、 **URL**テキスト ボックスに、たとえば。</span><span class="sxs-lookup"><span data-stu-id="474db-131">Type the following URL in the **URL** text box, for example:</span></span>  
  
         `http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Adapter/CustomerServicePort.asmx`  
  
    5.  <span data-ttu-id="474db-132">型`ZipCode`で、**名前**下にあるテキスト ボックス**認証要素**、任意の文字を入力し、**値**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="474db-132">Type `ZipCode` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
    6.  <span data-ttu-id="474db-133">型`CustomerName`で、**名前**下にあるテキスト ボックス**認証要素**、任意の文字を入力し、**値**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="474db-133">Type `CustomerName` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
    7.  <span data-ttu-id="474db-134">クリックして **、バランス**します。</span><span class="sxs-lookup"><span data-stu-id="474db-134">Click **Get my balance**.</span></span>  
  
    8.  <span data-ttu-id="474db-135">応答が表示されます、**応答**テキスト ボックス。**成功**場合に表示されます、要求が正常に処理されます。 要求が失敗した場合、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="474db-135">The response is displayed in the **Response** text box: **SUCCESS** appears if the request is handled successfully; an error message appears if the request fails.</span></span>  
  
         <span data-ttu-id="474db-136">![アダプター バージョンのクライアント アプリケーションを実行](../core/media/soap-transport-adapter-success.gif "SOAP_Transport_adapter_success")</span><span class="sxs-lookup"><span data-stu-id="474db-136">![Run the client application for the adapter version](../core/media/soap-transport-adapter-success.gif "SOAP_Transport_adapter_success")</span></span>  
  
4.  <span data-ttu-id="474db-137">BTSScnSOSimpleClient.exe で、次のように MQSeries トランスポート、要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="474db-137">In the BTSScnSOSimpleClient.exe, send requests by MQSeries transport as follows:</span></span>  
  
    1.  <span data-ttu-id="474db-138">任意の文字を入力、 **RequestType**、 **RequestSource**、および**RequestID**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="474db-138">Type any characters in the **RequestType**, **RequestSource**, and **RequestID** text boxes.</span></span>  
  
    2.  <span data-ttu-id="474db-139">16 桁の数字を入力、**アカウント番号**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="474db-139">Type a 16-digit number in the **Account Number** text box.</span></span>  
  
    3.  <span data-ttu-id="474db-140">選択**MQSeries**で、 **Select Transport and Parameters**グループ ボックス。</span><span class="sxs-lookup"><span data-stu-id="474db-140">Select **MQSeries** in the **Select Transport and Parameters** group box.</span></span>  
  
    4.  <span data-ttu-id="474db-141">型\<*キュー マネージャ名*\>で、**キュー マネージャー**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="474db-141">Type \<*Queue Manager Name*\> in the **Queue Manager** text box.</span></span> <span data-ttu-id="474db-142">Qm _\<*コンピューター名を*\>の既定値は、 \<*キュー マネージャ名*\>します。</span><span class="sxs-lookup"><span data-stu-id="474db-142">QM_\<*Your Computer Name*\> is the default value for \<*Queue Manager Name*\>.</span></span>  
  
    5.  <span data-ttu-id="474db-143">型`AdapterSOAInputQueue`で、 **Input Queue**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="474db-143">Type `AdapterSOAInputQueue` in the **Input Queue** text box.</span></span>  
  
    6.  <span data-ttu-id="474db-144">型`AdapterSOAOutputQueue`で、**出力キュー**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="474db-144">Type `AdapterSOAOutputQueue` in the **Output Queue** text box.</span></span>  
  
    7.  <span data-ttu-id="474db-145">型\<*チャネル定義*\>で、**チャネル定義**ボックス。</span><span class="sxs-lookup"><span data-stu-id="474db-145">Type \<*Channel Definition*\> in the **Channel Definition** box.</span></span> <span data-ttu-id="474db-146">S _\<*コンピューター名を*\>/tcp/\<*コンピューター名を*\>(1414) の既定値は、 \< *チャネル定義*\>します。</span><span class="sxs-lookup"><span data-stu-id="474db-146">S_\<*Your Computer Name*\>/TCP/\<*Your Computer Name*\>(1414) is the default value for \<*Channel Definition*\>.</span></span>  
  
    8.  <span data-ttu-id="474db-147">型`ZipCode`で、**名前**下にあるテキスト ボックス**認証要素**、任意の文字を入力し、**値**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="474db-147">Type `ZipCode` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
    9. <span data-ttu-id="474db-148">型`CustomerName`で、**名前**下にあるテキスト ボックス**認証要素**、任意の文字を入力し、**値**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="474db-148">Type `CustomerName` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
    10. <span data-ttu-id="474db-149">クリックして **、バランス**します。</span><span class="sxs-lookup"><span data-stu-id="474db-149">Click **Get my balance**.</span></span>  
  
    11. <span data-ttu-id="474db-150">応答が表示されます、**応答**テキスト ボックス。**成功**場合に表示されます、要求が正常に処理されます。 要求が失敗した場合、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="474db-150">The response is displayed in the **Response** text box: **SUCCESS** appears if the request is handled successfully; an error message appears if the request fails.</span></span>  
  
         <span data-ttu-id="474db-151">![アダプター バージョンのクライアント アプリケーションを実行](../core/media/mqseries-transport-adapter.gif "MQSeries_Transport_adapter")</span><span class="sxs-lookup"><span data-stu-id="474db-151">![Run the client application for the adapter version](../core/media/mqseries-transport-adapter.gif "MQSeries_Transport_adapter")</span></span>  
  
##  <a name="step5"></a> <span data-ttu-id="474db-152">クライアント アプリケーション (インライン バージョン) を使用して要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="474db-152">Send requests using the client application (inline version)</span></span>  
  
#### <a name="to-send-requests-using-the-client-application-inline-version"></a><span data-ttu-id="474db-153">クライアント アプリケーション (インライン バージョン) を使用して要求を送信するには</span><span class="sxs-lookup"><span data-stu-id="474db-153">To send requests using the client application (inline version)</span></span>  
  
1.  <span data-ttu-id="474db-154">コマンド プロンプトを開き、ディレクトリに移動します\< *BizTalk Server のインストール ディレクトリ*\>\SDK\Scenarios\SO\BTSSoln\PaymentTracker\bin\Debug および開始する、次のコマンドを実行し、PaymentTracker シミュレーターの場合:</span><span class="sxs-lookup"><span data-stu-id="474db-154">Open a command prompt, change the directory to \<*BizTalk Server install Directory*\>\SDK\Scenarios\SO\BTSSoln\PaymentTracker\bin\Debug, and then run the following command to start the PaymentTracker simulator:</span></span>  
  
     <span data-ttu-id="474db-155">`BTSScnSOPaymentTracker.exe LastPaymentsInputQueue LastPaymentsOutputQueue <` *キュー マネージャー名* `> 5 [<` *チャネルの定義* `>]`</span><span class="sxs-lookup"><span data-stu-id="474db-155">`BTSScnSOPaymentTracker.exe LastPaymentsInputQueue LastPaymentsOutputQueue <` *Queue Manager Name* `> 5 [<` *Channel Definition* `>]`</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="474db-156">チャネル定義は、リモートの MQSeries サーバーでない場合は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="474db-156">The channel definition is optional if it is not remote MQSeries Server.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="474db-157">PaymentTracker シミュレーターが既に実行されている場合は、この手順をスキップします。</span><span class="sxs-lookup"><span data-stu-id="474db-157">Skip this step if the PaymentTracker simulator is already running.</span></span>  
  
    -   <span data-ttu-id="474db-158">Payment Tracker シミュレーターが実行されているままにします。</span><span class="sxs-lookup"><span data-stu-id="474db-158">Leave the Payment Tracker simulator running.</span></span>  
  
2.  <span data-ttu-id="474db-159">**BizTalk Server 管理コンソール**、展開 **[btsscn.so.customerservice]**、] をクリックして**受信場所**、右クリックして **[PaymentTrackingSystemOutputQueue**右側のウィンドウでクリック**を無効にする**します。</span><span class="sxs-lookup"><span data-stu-id="474db-159">In the **BizTalk Server Administration Console**, expand **BTSScn.SO.CustomerService**, click **Receive Locations**, right-click **PaymentTrackingSystemOutputQueue** in the right pane, and then click **Disable**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="474db-160">アダプター バージョンおよびインライン バージョンは、同じ MQSeries キュー LastPaymentsOutputQueue を使用します。</span><span class="sxs-lookup"><span data-stu-id="474db-160">The adapter version and inline version uses the same MQSeries queue, LastPaymentsOutputQueue.</span></span> <span data-ttu-id="474db-161">2 つのバージョン間の競合状態を回避するため、アダプター バージョンを無効にするは、MQSeries キューでリッスンしている場所を受信します。</span><span class="sxs-lookup"><span data-stu-id="474db-161">To avoid the race condition between two versions, disable the adapter version's receive location listening on the MQSeries queue.</span></span>  
  
3.  <span data-ttu-id="474db-162">コマンド プロンプトを開き、ディレクトリを\< *BizTalk Server のインストール ディレクトリ*\>\SDK\Scenarios\SO\BTSSoln\SimpleClient\bin\Release とし、BTSScnSOSimpleClient.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="474db-162">Open a command prompt, change the directory to the \<*BizTalk Server install Directory*\>\SDK\Scenarios\SO\BTSSoln\SimpleClient\bin\Release, and then run the BTSScnSOSimpleClient.exe.</span></span>  
  
4.  <span data-ttu-id="474db-163">BTSScnSOSimpleClient.exe で、SOAP トランスポートによる要求としてを使用して送信次に示します。</span><span class="sxs-lookup"><span data-stu-id="474db-163">In the BTSScnSOSimpleClient.exe, send a request by SOAP transport using the as follows:</span></span>  
  
    1.  <span data-ttu-id="474db-164">任意の文字を入力、 **RequestType**、 **RequestSource**、および**RequestID**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="474db-164">Type any characters in the **RequestType**, **RequestSource**, and **RequestID** text boxes.</span></span>  
  
    2.  <span data-ttu-id="474db-165">任意の 16 桁の数字を入力、**アカウント番号**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="474db-165">Type any 16-digit number in the **Account Number** text box.</span></span>  
  
    3.  <span data-ttu-id="474db-166">選択**SOAP (WS Call)** と**インライン**で、 **Select Transport and Parameters**グループ ボックス。</span><span class="sxs-lookup"><span data-stu-id="474db-166">Select **SOAP (WS Call)** and **Inline** in the **Select Transport and Parameters** group box.</span></span>  
  
    4.  <span data-ttu-id="474db-167">次の URL を入力、 **URL**テキスト ボックスに、たとえば。</span><span class="sxs-lookup"><span data-stu-id="474db-167">Type the following URL in the **URL** text box, for example:</span></span>  
  
         `http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Inline/CustomerServicePort.asmx`  
  
    5.  <span data-ttu-id="474db-168">型`ZipCode`で、**名前**下にあるテキスト ボックス**認証要素**、任意の文字を入力し、**値**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="474db-168">Type `ZipCode` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
    6.  <span data-ttu-id="474db-169">型`CustomerName`で、**名前**下にあるテキスト ボックス**認証要素**、任意の文字を入力し、**値**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="474db-169">Type `CustomerName` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
    7.  <span data-ttu-id="474db-170">クリックして **、バランス**します。</span><span class="sxs-lookup"><span data-stu-id="474db-170">Click **Get my balance**.</span></span>  
  
    8.  <span data-ttu-id="474db-171">応答が表示されます、**応答**テキスト ボックス。**成功**場合に表示されます、要求が正常に処理されます。 要求が失敗した場合、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="474db-171">The response is displayed in the **Response** text box: **SUCCESS** appears if the request is handled successfully; an error message appears if the request fails.</span></span>  
  
         <span data-ttu-id="474db-172">![インライン バージョンのクライアント アプリケーションを実行](../core/media/soap-transport-inline.gif "SOAP_Transport_inline")</span><span class="sxs-lookup"><span data-stu-id="474db-172">![Run the client application for the inline version](../core/media/soap-transport-inline.gif "SOAP_Transport_inline")</span></span>  
  
5.  <span data-ttu-id="474db-173">BTSScnSOSimpleClient.exe で、次のように MQSeries トランスポート、要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="474db-173">In the BTSScnSOSimpleClient.exe, send requests by MQSeries transport as follows:</span></span>  
  
    1.  <span data-ttu-id="474db-174">任意の文字を入力、 **RequestType**、 **RequestSource**、および**RequestID**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="474db-174">Type any characters in the **RequestType**, **RequestSource**, and **RequestID** text boxes.</span></span>  
  
    2.  <span data-ttu-id="474db-175">16 桁の数字を入力、**アカウント番号**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="474db-175">Type a 16-digit number in the **Account Number** text box.</span></span>  
  
    3.  <span data-ttu-id="474db-176">選択**MQSeries**で、 **Select Transport and Parameters**グループ ボックス。</span><span class="sxs-lookup"><span data-stu-id="474db-176">Select **MQSeries** in the **Select Transport and Parameters** group box.</span></span>  
  
    4.  <span data-ttu-id="474db-177">型\<*キュー マネージャ名*\>で、**キュー マネージャー**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="474db-177">Type \<*Queue Manager Name*\> in the **Queue Manager** text box.</span></span> <span data-ttu-id="474db-178">Qm _\<*コンピューター名を*\>の既定値は、 \<*キュー マネージャ名*\>します。</span><span class="sxs-lookup"><span data-stu-id="474db-178">QM_\<*Your Computer Name*\> is the default value for \<*Queue Manager Name*\>.</span></span>  
  
    5.  <span data-ttu-id="474db-179">型`InlineSOAInputQueue`で、 **Input Queue**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="474db-179">Type `InlineSOAInputQueue` in the **Input Queue** text box.</span></span>  
  
    6.  <span data-ttu-id="474db-180">型`InlineSOAOutputQueue`で、**出力キュー**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="474db-180">Type `InlineSOAOutputQueue` in the **Output Queue** text box.</span></span>  
  
    7.  <span data-ttu-id="474db-181">型\<*チャネル定義*\>で、**チャネル定義**ボックス。</span><span class="sxs-lookup"><span data-stu-id="474db-181">Type \<*Channel Definition*\> in the **Channel Definition** box.</span></span> <span data-ttu-id="474db-182">S _\<*コンピューター名を*\>/tcp/\<*コンピューター名を*\>(1414) の既定値は、 \< *チャネル定義*\>します。</span><span class="sxs-lookup"><span data-stu-id="474db-182">S_\<*Your Computer Name*\>/TCP/\<*Your Computer Name*\>(1414) is the default value for \<*Channel Definition*\>.</span></span>  
  
    8.  <span data-ttu-id="474db-183">型`ZipCode`で、**名前**下にあるテキスト ボックス**認証要素**、任意の文字を入力し、**値**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="474db-183">Type `ZipCode` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
    9. <span data-ttu-id="474db-184">型`CustomerName`で、**名前**下にあるテキスト ボックス**認証要素**、任意の文字を入力し、**値**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="474db-184">Type `CustomerName` in the **Name** text box under **Authentication Elements**, and then type any characters in the **Value** text box.</span></span>  
  
    10. <span data-ttu-id="474db-185">クリックして **、バランス**します。</span><span class="sxs-lookup"><span data-stu-id="474db-185">Click **Get my balance**.</span></span>  
  
    11. <span data-ttu-id="474db-186">応答が表示されます、**応答**テキスト ボックス。**成功**場合に表示されます、要求が正常に処理されます。 要求が失敗した場合、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="474db-186">The response is displayed in the **Response** text box: **SUCCESS** appears if the request is handled successfully; an error message appears if the request fails.</span></span>  
  
         <span data-ttu-id="474db-187">![インライン バージョンのクライアント アプリケーションを実行](../core/media/mqseries-transport-inline.gif "MQSeries_Transport_inline")</span><span class="sxs-lookup"><span data-stu-id="474db-187">![Run the client application for the inline version](../core/media/mqseries-transport-inline.gif "MQSeries_Transport_inline")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="474db-188">参照</span><span class="sxs-lookup"><span data-stu-id="474db-188">See Also</span></span>  
 <span data-ttu-id="474db-189">[サービス指向ソリューションをインストールする前に](../core/before-installing-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="474db-189">[Before Installing the Service Oriented Solution](../core/before-installing-the-service-oriented-solution.md) </span></span>  
 <span data-ttu-id="474db-190">[指向ソリューションのスタブ バージョンのサービスをインストールする方法](../core/how-to-install-the-stub-version-of-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="474db-190">[How to Install the Stub Version of the Service Oriented Solution](../core/how-to-install-the-stub-version-of-the-service-oriented-solution.md) </span></span>  
 <span data-ttu-id="474db-191">[指向ソリューションのインライン バージョンおよびアダプター バージョンのサービスをインストールする方法](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="474db-191">[How to Install the Inline and Adapter Versions of the Service Oriented Solution](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md) </span></span>  
 [<span data-ttu-id="474db-192">サービス指向ソリューションに対する開発者のコンピューター設定</span><span class="sxs-lookup"><span data-stu-id="474db-192">Developer Machine Setup for the Service Oriented Solution</span></span>](../core/developer-machine-setup-for-the-service-oriented-solution.md)