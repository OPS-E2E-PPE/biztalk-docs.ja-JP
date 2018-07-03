---
title: 動的解決サンプルの一方向のメッセージング シナリオ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 38237840-e957-4298-84c9-700ec72f2bc5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 359b91a1a5da9ce435d3d9aa5884d6928d0e0a9b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987539"
---
# <a name="one-way-messaging-scenarios-for-the-dynamic-resolution-sample"></a><span data-ttu-id="811cc-102">動的解決サンプルの一方向のメッセージング シナリオ</span><span class="sxs-lookup"><span data-stu-id="811cc-102">One-Way Messaging Scenarios for the Dynamic Resolution Sample</span></span>
<span data-ttu-id="811cc-103">このトピックでは、の一方向メッセージング シナリオを実行する方法、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]動的解決サンプル。</span><span class="sxs-lookup"><span data-stu-id="811cc-103">This topic shows how you can run the one-way messaging scenarios for the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Dynamic Resolution sample.</span></span>  

 <span data-ttu-id="811cc-104">**動的解決サンプルの一方向メッセージング シナリオを実行するには**</span><span class="sxs-lookup"><span data-stu-id="811cc-104">**To run the one-way messaging scenarios for the Dynamic Resolution sample**</span></span>  

1. <span data-ttu-id="811cc-105">最初にこのサンプルを実行する前に、受信場所の URL を指している適切なディレクトリを確認します。</span><span class="sxs-lookup"><span data-stu-id="811cc-105">Before you run this sample for the first time, make sure that the receive location URL points to the appropriate directory.</span></span> <span data-ttu-id="811cc-106">ソースのサブフォルダー \Source\Samples\DynamicResolution\Test\Filedrop\In、DynamicResolution_FILE 受信場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="811cc-106">Specify the source subfolder \Source\Samples\DynamicResolution\Test\Filedrop\In for the DynamicResolution_FILE receive location.</span></span> <span data-ttu-id="811cc-107">さらに、DynamicResolutionOneWay をという名前の動的送信ポートが存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="811cc-107">Additionally, make sure that the dynamic send port named DynamicResolutionOneWay exists.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="811cc-108">動的解決サンプルでは、動的解決の機構を使用して、出力フォルダー、FTP サイト、または MQSeries キューにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="811cc-108">The Dynamic Resolution sample uses the dynamic resolution mechanism to send messages to the output folder, FTP site, or MQSeries queue.</span></span> <span data-ttu-id="811cc-109">このサンプルの静的な送信ポートが定義されていないためにです。</span><span class="sxs-lookup"><span data-stu-id="811cc-109">This is why a static send port is not defined for this sample.</span></span> <span data-ttu-id="811cc-110">動的解決のコンポーネントは、解像度から出力 URL を取得し、受信場所のアダプターのプロバイダー フレームワーク、DynamicResolution_FILE 内で構成されている ESBReceiveXml パイプラインによって呼び出されたときにします。</span><span class="sxs-lookup"><span data-stu-id="811cc-110">The Dynamic Resolution component retrieves the output URL from the Resolution and Adapter Provider Framework when called by the ESBReceiveXml pipeline, which is configured within the DynamicResolution_FILE receive location.</span></span>  

2. <span data-ttu-id="811cc-111">GlobalBank.ESB アプリケーションが実行されていない場合は、Microsoft の BizTalk 管理コンソールを使用して、開始します。</span><span class="sxs-lookup"><span data-stu-id="811cc-111">If the GlobalBank.ESB application is not already running, use the Microsoft BizTalk Administration Console to start it.</span></span>  

3. <span data-ttu-id="811cc-112">実行する例を決定します。</span><span class="sxs-lookup"><span data-stu-id="811cc-112">Decide which example you want to execute.</span></span> <span data-ttu-id="811cc-113">DynamicResolution_FILE という名前の受信場所に入力 NAOrderDoc.xml として \Source\Samples\DynamicResolution\Test\Data フォルダーにあるファイルをすべて一方向メッセージング (を除く、XPATH の競合回避モジュールを使用する 1 つ) の例を使用します。</span><span class="sxs-lookup"><span data-stu-id="811cc-113">All one-way messaging examples (except the one that uses the XPATH Resolver) use the file NAOrderDoc.xml located in the \Source\Samples\DynamicResolution\Test\Data folder as input to the receive location named DynamicResolution_FILE.</span></span> <span data-ttu-id="811cc-114">7 つの一方向メッセージングの例は、それぞれの一意のバインド ファイルで表されます。</span><span class="sxs-lookup"><span data-stu-id="811cc-114">There are seven one-way messaging examples, each represented by a unique binding file.</span></span> <span data-ttu-id="811cc-115">次の表は、その関連付けられたバインド ファイルの説明と、これらの例を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="811cc-115">The following tables list these examples, with their associated binding files and descriptions.</span></span>  

   |<span data-ttu-id="811cc-116">ファイルの受信ファイル、静的な競合回避モジュールを使用して送信する</span><span class="sxs-lookup"><span data-stu-id="811cc-116">File Inbound to File Outbound Using the STATIC Resolver</span></span>|  
   |-------------------------------------------------------------|  
   |<span data-ttu-id="811cc-117">受信場所を設定し、送信ポートのプロパティを GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_STATIC_Bindings.xml をという名前のバインド ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="811cc-117">Uses the binding file named GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_STATIC_Bindings.xml to set the receive location and send port properties.</span></span>|  
   |<span data-ttu-id="811cc-118">受信ポートでマップを静的に設定します。</span><span class="sxs-lookup"><span data-stu-id="811cc-118">Sets the maps statically at the receive port.</span></span>|  
   |<span data-ttu-id="811cc-119">ESB ディスパッチャーを受信場所でエンドポイントの解決を使用します。</span><span class="sxs-lookup"><span data-stu-id="811cc-119">Uses the ESB Dispatcher at the receive location for endpoint resolution.</span></span>|  

   |<span data-ttu-id="811cc-120">ファイルに着信する UDDI リゾルバーを使用して送信ファイル</span><span class="sxs-lookup"><span data-stu-id="811cc-120">File Inbound to File Outbound Using the UDDI Resolver</span></span>|  
   |-----------------------------------------------------------|  
   |<span data-ttu-id="811cc-121">受信場所を設定し、送信ポートのプロパティを GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_UDDI_Bindings.xml をという名前のバインド ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="811cc-121">Uses the binding file named GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_UDDI_Bindings.xml to set the receive location and send port properties.</span></span>|  
   |<span data-ttu-id="811cc-122">受信ポートでマップを静的に設定します。</span><span class="sxs-lookup"><span data-stu-id="811cc-122">Sets the maps statically at the receive port.</span></span>|  
   |<span data-ttu-id="811cc-123">ESB ディスパッチャーを受信場所でエンドポイントの解決を使用します。</span><span class="sxs-lookup"><span data-stu-id="811cc-123">Uses the ESB Dispatcher at the receive location for endpoint resolution.</span></span>|  

   |<span data-ttu-id="811cc-124">UDDI サービスのキーを使用して UDDI リゾルバーを使用して送信ファイルへのファイルの受信します。</span><span class="sxs-lookup"><span data-stu-id="811cc-124">File Inbound to File Outbound Using UDDI Resolver via UDDI Service Key</span></span>|  
   |----------------------------------------------------------------------------|  
   |<span data-ttu-id="811cc-125">受信場所を設定し、送信ポートのプロパティを GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_UDDI_SERVICEKEY_ Bindings.xml をという名前のバインド ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="811cc-125">Uses the binding file named GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_UDDI_SERVICEKEY_ Bindings.xml to set the receive location and send port properties.</span></span>|  
   |<span data-ttu-id="811cc-126">受信ポートでマップを静的に設定します。</span><span class="sxs-lookup"><span data-stu-id="811cc-126">Sets the maps statically at the receive port.</span></span>|  
   |<span data-ttu-id="811cc-127">ESB ディスパッチャーを受信場所でエンドポイントの解決を使用します。</span><span class="sxs-lookup"><span data-stu-id="811cc-127">Uses the ESB Dispatcher at the receive location for endpoint resolution.</span></span>|  

   > [!NOTE]
   >  <span data-ttu-id="811cc-128">前の例では、ターゲットの UDDI サーバー上に存在する 1 つに、バインド ファイルにサービス キーを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="811cc-128">For the preceding example, you must change the service key in the binding file to one that exists on the target UDDI server.</span></span>  

   |<span data-ttu-id="811cc-129">ファイルが着信 FTP 静的リゾルバーを使用して送信する</span><span class="sxs-lookup"><span data-stu-id="811cc-129">File Inbound to FTP Outbound Using the STATIC Resolver</span></span>|  
   |------------------------------------------------------------|  
   |<span data-ttu-id="811cc-130">受信場所を設定し、送信ポートのプロパティを GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FTP_STATIC_Bindings.xml をという名前のバインド ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="811cc-130">Uses the binding file named GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FTP_STATIC_Bindings.xml to set the receive location and send port properties.</span></span>|  
   |<span data-ttu-id="811cc-131">受信ポートでマップを静的に設定します。</span><span class="sxs-lookup"><span data-stu-id="811cc-131">Sets the maps statically at the receive port.</span></span>|  
   |<span data-ttu-id="811cc-132">ESB ディスパッチャーを受信場所でエンドポイントの解決を使用します。</span><span class="sxs-lookup"><span data-stu-id="811cc-132">Uses the ESB Dispatcher at the receive location for endpoint resolution.</span></span>|  

   |<span data-ttu-id="811cc-133">ファイルが着信 FTP 静的競合回避モジュールと ENDPOINTCONFIG パラメーターを使用して送信する</span><span class="sxs-lookup"><span data-stu-id="811cc-133">File Inbound to FTP Outbound Using the STATIC Resolver and ENDPOINTCONFIG Parameter</span></span>|  
   |-----------------------------------------------------------------------------------------|  
   |<span data-ttu-id="811cc-134">受信場所を設定し、送信ポートのプロパティを GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FTP_STATIC__ ENDPOINTCONFIG_Bindings.xml をという名前のバインド ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="811cc-134">Uses the binding file named GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FTP_STATIC__ ENDPOINTCONFIG_Bindings.xml to set the receive location and send port properties.</span></span>|  
   |<span data-ttu-id="811cc-135">受信ポートでマップを静的に設定します。</span><span class="sxs-lookup"><span data-stu-id="811cc-135">Sets the maps statically at the receive port.</span></span>|  
   |<span data-ttu-id="811cc-136">ESB ディスパッチャーを受信場所でエンドポイントの解決を使用します。</span><span class="sxs-lookup"><span data-stu-id="811cc-136">Uses the ESB Dispatcher at the receive location for endpoint resolution.</span></span>|  
   |<span data-ttu-id="811cc-137">設定するアダプター プロバイダーの追加の名前/値ペアを渡します。</span><span class="sxs-lookup"><span data-stu-id="811cc-137">Passes additional name/values pairs for the adapter provider to set.</span></span>|  

   |<span data-ttu-id="811cc-138">ファイルの着信 MQS 静的リゾルバーを使用して送信する</span><span class="sxs-lookup"><span data-stu-id="811cc-138">File Inbound to MQS Outbound Using the STATIC Resolver</span></span>|  
   |------------------------------------------------------------|  
   |<span data-ttu-id="811cc-139">受信場所を設定し、送信ポートのプロパティを GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_MQS_STATIC_Bindings.xml をという名前のバインド ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="811cc-139">Uses the binding file named GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_MQS_STATIC_Bindings.xml to set the receive location and send port properties.</span></span>|  
   |<span data-ttu-id="811cc-140">受信ポートでマップを静的に設定します。</span><span class="sxs-lookup"><span data-stu-id="811cc-140">Sets the maps statically at the receive port.</span></span>|  
   |<span data-ttu-id="811cc-141">ESB ディスパッチャーを受信場所でエンドポイントの解決を使用します。</span><span class="sxs-lookup"><span data-stu-id="811cc-141">Uses the ESB Dispatcher at the receive location for endpoint resolution.</span></span>|  

   |                                                                             <span data-ttu-id="811cc-142">ファイルの着信ファイルを XPATH の競合回避モジュールを使用して送信する</span><span class="sxs-lookup"><span data-stu-id="811cc-142">File Inbound to FILE Outbound Using the XPATH Resolver</span></span>                                                                             |
   |----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |                        <span data-ttu-id="811cc-143">受信場所を設定し、送信ポートのプロパティを GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_XPATH_STATIC_Bindings.xml をという名前のバインド ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="811cc-143">Uses the binding file named GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_XPATH_STATIC_Bindings.xml to set the receive location and send port properties.</span></span>                        |
   |                                                                                 <span data-ttu-id="811cc-144">受信ポートでマップを静的に設定します。</span><span class="sxs-lookup"><span data-stu-id="811cc-144">Sets the maps statically at the receive port.</span></span>                                                                                  |
   |                                                                    <span data-ttu-id="811cc-145">ESB ディスパッチャーを受信場所でエンドポイントの解決を使用します。</span><span class="sxs-lookup"><span data-stu-id="811cc-145">Uses the ESB Dispatcher at the receive location for endpoint resolution.</span></span>                                                                    |
   | <span data-ttu-id="811cc-146">メッセージ内の情報を使用して、適切なエンドポイントを決定します。</span><span class="sxs-lookup"><span data-stu-id="811cc-146">Uses information within the message to determine the appropriate endpoint.</span></span> <span data-ttu-id="811cc-147">この例で使用できるテスト ファイルには、NAOrderDoc_XPATH_FILE.xml、NAOrderDoc_XPATH_FTP.xml、NAOrderDoc_XPATH_MQS.xml が。</span><span class="sxs-lookup"><span data-stu-id="811cc-147">The test files you can use with this example are NAOrderDoc_XPATH_FILE.xml, NAOrderDoc_XPATH_FTP.xml, and NAOrderDoc_XPATH_MQS.xml.</span></span> |


4. <span data-ttu-id="811cc-148">メッセージングに GlobalBank.ESB アプリケーションを実行する例については、バインド ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="811cc-148">Import the binding file for the messaging example you want to execute into the GlobalBank.ESB application.</span></span>  

5. <span data-ttu-id="811cc-149">Windows エクスプ ローラーでフォルダー \Source\Samples\DynamicResolution\Test\Data 開きフォルダー \Source\Samples\DynamicResolution\Test\Filedrop\In に適切な入力ファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="811cc-149">In Windows Explorer, open the folder \Source\Samples\DynamicResolution\Test\Data and copy the appropriate input file into the folder \Source\Samples\DynamicResolution\Test\Filedrop\In.</span></span> <span data-ttu-id="811cc-150">使用するファイルは、実行することを決定した例では、によって異なります。</span><span class="sxs-lookup"><span data-stu-id="811cc-150">The file you use depends on the example you decided to execute:</span></span>  

   -   <span data-ttu-id="811cc-151">XPATH の例で、次のファイルのいずれかを使用: NAOrderDoc_XPATH_FILE.xml、NAOrderDoc_XPATH_FTP.xml、または NAOrderDoc_XPATH_MQS.xml します。</span><span class="sxs-lookup"><span data-stu-id="811cc-151">For the XPATH example, use one of the following files: NAOrderDoc_XPATH_FILE.xml, NAOrderDoc_XPATH_FTP.xml, or NAOrderDoc_XPATH_MQS.xml.</span></span>  

   -   <span data-ttu-id="811cc-152">その他のすべての例では、NAOrderDoc.xml ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="811cc-152">For all other examples, use the file NAOrderDoc.xml.</span></span>  

6. <span data-ttu-id="811cc-153">適切な場所に配信されたメッセージを確認します。</span><span class="sxs-lookup"><span data-stu-id="811cc-153">Look in the appropriate location for the delivered message.</span></span> <span data-ttu-id="811cc-154">場所は、使用するバインド ファイルに依存します。</span><span class="sxs-lookup"><span data-stu-id="811cc-154">The location depends on the binding file you used.</span></span> <span data-ttu-id="811cc-155">例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="811cc-155">The following are examples:</span></span>  

   -   <span data-ttu-id="811cc-156">FTP 送信の例は、ファイルの受信、メッセージを配信をという名前の FTP 仮想ディレクトリ、サンプルのインストール時に作成したこと。</span><span class="sxs-lookup"><span data-stu-id="811cc-156">The File Inbound to FTP Outbound example delivers the message to the FTP virtual directory named Out that you created when you installed the sample.</span></span>  

   -   <span data-ttu-id="811cc-157">\DynamicResolution\Test\Filedrop\Out サブフォルダーに、メッセージを配信する送信ファイルの例にファイルを受信します。</span><span class="sxs-lookup"><span data-stu-id="811cc-157">The File Inbound to FILE Outbound example delivers the message to the \DynamicResolution\Test\Filedrop\Out subfolder.</span></span>  

   -   <span data-ttu-id="811cc-158">MQS 送信の例は、ファイルの受信には、テストにメッセージが配信されます。時に作成したキューをサンプルのインストール。</span><span class="sxs-lookup"><span data-stu-id="811cc-158">The File Inbound to MQS Outbound example delivers the message to the TEST.OUT queue that you created when you installed the sample.</span></span>  

   -   <span data-ttu-id="811cc-159">ファイル送信の例では、XPATH の競合回避モジュールを使用するファイルの受信メッセージで指定した場所にメッセージが配信されます。</span><span class="sxs-lookup"><span data-stu-id="811cc-159">The File Inbound to FILE Outbound using the XPATH Resolver example delivers the message to the location specified in the message.</span></span> <span data-ttu-id="811cc-160">サンプル ドキュメントには、移行先の場所およびトランスポートの種類を含めることが (トランスポートの種類がメッセージのファイル名に追加されます。 たとえば、NAOrderDoc_XPATH_FTP.xml メッセージには、FTP トランスポートの型の仕様が含まれます。)。</span><span class="sxs-lookup"><span data-stu-id="811cc-160">The sample documents contain the destination location and transport type (the transport type is appended to the message file name; for example, the NAOrderDoc_XPATH_FTP.xml message contains the FTP transport type specification).</span></span>  

   <span data-ttu-id="811cc-161">ESB ディスパッチャーと ESB ディスパッチャー逆アセンブラー パイプライン コンポーネントのサンプルの使用については、次を参照してください。 [、動的解決サンプルのしくみ](../esb-toolkit/how-the-dynamic-resolution-sample-works.md)します。</span><span class="sxs-lookup"><span data-stu-id="811cc-161">To understand how the sample uses the ESB Dispatcher and ESB Dispatcher Disassembler pipeline components, see [How the Dynamic Resolution Sample Works](../esb-toolkit/how-the-dynamic-resolution-sample-works.md).</span></span>