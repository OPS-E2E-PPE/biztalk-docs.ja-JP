---
title: "動的解決のサンプルの一方向のメッセージング シナリオ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 38237840-e957-4298-84c9-700ec72f2bc5
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8296c46561a8afa928033ae6002e3de621170234
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="one-way-messaging-scenarios-for-the-dynamic-resolution-sample"></a><span data-ttu-id="d79d6-102">動的解決のサンプルの一方向のメッセージング シナリオ</span><span class="sxs-lookup"><span data-stu-id="d79d6-102">One-Way Messaging Scenarios for the Dynamic Resolution Sample</span></span>
<span data-ttu-id="d79d6-103">このトピックの一方向のメッセージング シナリオを実行する方法を示しています、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]動的解決のサンプルです。</span><span class="sxs-lookup"><span data-stu-id="d79d6-103">This topic shows how you can run the one-way messaging scenarios for the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Dynamic Resolution sample.</span></span>  
  
 <span data-ttu-id="d79d6-104">**動的解決のサンプルの一方向のメッセージング シナリオを実行するには**</span><span class="sxs-lookup"><span data-stu-id="d79d6-104">**To run the one-way messaging scenarios for the Dynamic Resolution sample**</span></span>  
  
1.  <span data-ttu-id="d79d6-105">最初にこのサンプルを実行する前に、受信場所の URL を指している適切なディレクトリを確認します。</span><span class="sxs-lookup"><span data-stu-id="d79d6-105">Before you run this sample for the first time, make sure that the receive location URL points to the appropriate directory.</span></span> <span data-ttu-id="d79d6-106">ソース サブフォルダー \Source\Samples\DynamicResolution\Test\Filedrop\In、DynamicResolution_FILE 受信場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="d79d6-106">Specify the source subfolder \Source\Samples\DynamicResolution\Test\Filedrop\In for the DynamicResolution_FILE receive location.</span></span> <span data-ttu-id="d79d6-107">さらに、DynamicResolutionOneWay をという名前の動的送信ポートが存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="d79d6-107">Additionally, make sure that the dynamic send port named DynamicResolutionOneWay exists.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d79d6-108">動的解決の例では、動的な解決メカニズムを使用して、出力フォルダー、FTP サイト、または MQSeries キューにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="d79d6-108">The Dynamic Resolution sample uses the dynamic resolution mechanism to send messages to the output folder, FTP site, or MQSeries queue.</span></span> <span data-ttu-id="d79d6-109">このサンプルの静的な送信ポートが定義されていないためにです。</span><span class="sxs-lookup"><span data-stu-id="d79d6-109">This is why a static send port is not defined for this sample.</span></span> <span data-ttu-id="d79d6-110">動的解決のコンポーネントが解像度と出力 URL を取得し、受信場所のアダプターのプロバイダー フレームワーク、DynamicResolution_FILE 内で構成されている ESBReceiveXml パイプラインによって呼び出されたときにします。</span><span class="sxs-lookup"><span data-stu-id="d79d6-110">The Dynamic Resolution component retrieves the output URL from the Resolution and Adapter Provider Framework when called by the ESBReceiveXml pipeline, which is configured within the DynamicResolution_FILE receive location.</span></span>  
  
2.  <span data-ttu-id="d79d6-111">GlobalBank.ESB アプリケーションが既に実行されていない場合は、Microsoft BizTalk 管理コンソールを使用して、開始します。</span><span class="sxs-lookup"><span data-stu-id="d79d6-111">If the GlobalBank.ESB application is not already running, use the Microsoft BizTalk Administration Console to start it.</span></span>  
  
3.  <span data-ttu-id="d79d6-112">実行する例を決定します。</span><span class="sxs-lookup"><span data-stu-id="d79d6-112">Decide which example you want to execute.</span></span> <span data-ttu-id="d79d6-113">NAOrderDoc.xml フォルダーにある、\Source\Samples\DynamicResolution\Test\Data としてファイル入力 DynamicResolution_FILE をという名前の受信場所にすべて一方向メッセージング (を除く、XPATH の競合回避モジュールを使用する 1 つ) の例を使用してください。</span><span class="sxs-lookup"><span data-stu-id="d79d6-113">All one-way messaging examples (except the one that uses the XPATH Resolver) use the file NAOrderDoc.xml located in the \Source\Samples\DynamicResolution\Test\Data folder as input to the receive location named DynamicResolution_FILE.</span></span> <span data-ttu-id="d79d6-114">7 つの一方向メッセージングの例は、それぞれ固有のバインド ファイルで表されます。</span><span class="sxs-lookup"><span data-stu-id="d79d6-114">There are seven one-way messaging examples, each represented by a unique binding file.</span></span> <span data-ttu-id="d79d6-115">次の表では、これらの例は、その関連付けられたバインド ファイルと説明の一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="d79d6-115">The following tables list these examples, with their associated binding files and descriptions.</span></span>  
  
    |<span data-ttu-id="d79d6-116">ファイルのファイル、静的な競合回避モジュールを使用して送信する受信します。</span><span class="sxs-lookup"><span data-stu-id="d79d6-116">File Inbound to File Outbound Using the STATIC Resolver</span></span>|  
    |-------------------------------------------------------------|  
    |<span data-ttu-id="d79d6-117">GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_STATIC_Bindings.xml をという名前のバインド ファイルを使用して、受信場所を設定し、送信ポートのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="d79d6-117">Uses the binding file named GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_STATIC_Bindings.xml to set the receive location and send port properties.</span></span>|  
    |<span data-ttu-id="d79d6-118">受信ポートでマップを静的に設定します。</span><span class="sxs-lookup"><span data-stu-id="d79d6-118">Sets the maps statically at the receive port.</span></span>|  
    |<span data-ttu-id="d79d6-119">エンドポイント解決のため、受信場所で ESB ディスパッチャーを使用します。</span><span class="sxs-lookup"><span data-stu-id="d79d6-119">Uses the ESB Dispatcher at the receive location for endpoint resolution.</span></span>|  
  
    |<span data-ttu-id="d79d6-120">ファイルは、UDDI リゾルバーを使用して送信ファイルを受信します。</span><span class="sxs-lookup"><span data-stu-id="d79d6-120">File Inbound to File Outbound Using the UDDI Resolver</span></span>|  
    |-----------------------------------------------------------|  
    |<span data-ttu-id="d79d6-121">GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_UDDI_Bindings.xml をという名前のバインド ファイルを使用して、受信場所を設定し、送信ポートのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="d79d6-121">Uses the binding file named GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_UDDI_Bindings.xml to set the receive location and send port properties.</span></span>|  
    |<span data-ttu-id="d79d6-122">受信ポートでマップを静的に設定します。</span><span class="sxs-lookup"><span data-stu-id="d79d6-122">Sets the maps statically at the receive port.</span></span>|  
    |<span data-ttu-id="d79d6-123">エンドポイント解決のため、受信場所で ESB ディスパッチャーを使用します。</span><span class="sxs-lookup"><span data-stu-id="d79d6-123">Uses the ESB Dispatcher at the receive location for endpoint resolution.</span></span>|  
  
    |<span data-ttu-id="d79d6-124">ファイルは、UDDI サービスのキーを使用して UDDI リゾルバーを使用して送信ファイルを受信します。</span><span class="sxs-lookup"><span data-stu-id="d79d6-124">File Inbound to File Outbound Using UDDI Resolver via UDDI Service Key</span></span>|  
    |----------------------------------------------------------------------------|  
    |<span data-ttu-id="d79d6-125">GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_UDDI_SERVICEKEY_ Bindings.xml をという名前のバインド ファイルを使用して、受信場所を設定し、送信ポートのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="d79d6-125">Uses the binding file named GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_UDDI_SERVICEKEY_ Bindings.xml to set the receive location and send port properties.</span></span>|  
    |<span data-ttu-id="d79d6-126">受信ポートでマップを静的に設定します。</span><span class="sxs-lookup"><span data-stu-id="d79d6-126">Sets the maps statically at the receive port.</span></span>|  
    |<span data-ttu-id="d79d6-127">エンドポイント解決のため、受信場所で ESB ディスパッチャーを使用します。</span><span class="sxs-lookup"><span data-stu-id="d79d6-127">Uses the ESB Dispatcher at the receive location for endpoint resolution.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="d79d6-128">前の例では、ターゲット UDDI サーバー上に存在する 1 つに、バインド ファイル内のサービス キーを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d79d6-128">For the preceding example, you must change the service key in the binding file to one that exists on the target UDDI server.</span></span>  
  
    |<span data-ttu-id="d79d6-129">ファイルは、FTP、静的な競合回避モジュールを使用して送信する受信します。</span><span class="sxs-lookup"><span data-stu-id="d79d6-129">File Inbound to FTP Outbound Using the STATIC Resolver</span></span>|  
    |------------------------------------------------------------|  
    |<span data-ttu-id="d79d6-130">GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FTP_STATIC_Bindings.xml をという名前のバインド ファイルを使用して、受信場所を設定し、送信ポートのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="d79d6-130">Uses the binding file named GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FTP_STATIC_Bindings.xml to set the receive location and send port properties.</span></span>|  
    |<span data-ttu-id="d79d6-131">受信ポートでマップを静的に設定します。</span><span class="sxs-lookup"><span data-stu-id="d79d6-131">Sets the maps statically at the receive port.</span></span>|  
    |<span data-ttu-id="d79d6-132">エンドポイント解決のため、受信場所で ESB ディスパッチャーを使用します。</span><span class="sxs-lookup"><span data-stu-id="d79d6-132">Uses the ESB Dispatcher at the receive location for endpoint resolution.</span></span>|  
  
    |<span data-ttu-id="d79d6-133">FTP の静的な競合回避モジュールと ENDPOINTCONFIG パラメーターを使用して送信するファイルの受信します。</span><span class="sxs-lookup"><span data-stu-id="d79d6-133">File Inbound to FTP Outbound Using the STATIC Resolver and ENDPOINTCONFIG Parameter</span></span>|  
    |-----------------------------------------------------------------------------------------|  
    |<span data-ttu-id="d79d6-134">GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FTP_STATIC__ ENDPOINTCONFIG_Bindings.xml をという名前のバインド ファイルを使用して、受信場所を設定し、送信ポートのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="d79d6-134">Uses the binding file named GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FTP_STATIC__ ENDPOINTCONFIG_Bindings.xml to set the receive location and send port properties.</span></span>|  
    |<span data-ttu-id="d79d6-135">受信ポートでマップを静的に設定します。</span><span class="sxs-lookup"><span data-stu-id="d79d6-135">Sets the maps statically at the receive port.</span></span>|  
    |<span data-ttu-id="d79d6-136">エンドポイント解決のため、受信場所で ESB ディスパッチャーを使用します。</span><span class="sxs-lookup"><span data-stu-id="d79d6-136">Uses the ESB Dispatcher at the receive location for endpoint resolution.</span></span>|  
    |<span data-ttu-id="d79d6-137">設定するアダプター プロバイダーの追加の名前/値ペアを渡します。</span><span class="sxs-lookup"><span data-stu-id="d79d6-137">Passes additional name/values pairs for the adapter provider to set.</span></span>|  
  
    |<span data-ttu-id="d79d6-138">ファイルの MQS、静的な競合回避モジュールを使用して送信する受信します。</span><span class="sxs-lookup"><span data-stu-id="d79d6-138">File Inbound to MQS Outbound Using the STATIC Resolver</span></span>|  
    |------------------------------------------------------------|  
    |<span data-ttu-id="d79d6-139">GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_MQS_STATIC_Bindings.xml をという名前のバインド ファイルを使用して、受信場所を設定し、送信ポートのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="d79d6-139">Uses the binding file named GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_MQS_STATIC_Bindings.xml to set the receive location and send port properties.</span></span>|  
    |<span data-ttu-id="d79d6-140">受信ポートでマップを静的に設定します。</span><span class="sxs-lookup"><span data-stu-id="d79d6-140">Sets the maps statically at the receive port.</span></span>|  
    |<span data-ttu-id="d79d6-141">エンドポイント解決のため、受信場所で ESB ディスパッチャーを使用します。</span><span class="sxs-lookup"><span data-stu-id="d79d6-141">Uses the ESB Dispatcher at the receive location for endpoint resolution.</span></span>|  
  
    |<span data-ttu-id="d79d6-142">ファイルのファイルを XPATH の競合回避モジュールを使用して送信する受信します。</span><span class="sxs-lookup"><span data-stu-id="d79d6-142">File Inbound to FILE Outbound Using the XPATH Resolver</span></span>|  
    |------------------------------------------------------------|  
    |<span data-ttu-id="d79d6-143">GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_XPATH_STATIC_Bindings.xml をという名前のバインド ファイルを使用して、受信場所を設定し、送信ポートのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="d79d6-143">Uses the binding file named GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_XPATH_STATIC_Bindings.xml to set the receive location and send port properties.</span></span>|  
    |<span data-ttu-id="d79d6-144">受信ポートでマップを静的に設定します。</span><span class="sxs-lookup"><span data-stu-id="d79d6-144">Sets the maps statically at the receive port.</span></span>|  
    |<span data-ttu-id="d79d6-145">エンドポイント解決のため、受信場所で ESB ディスパッチャーを使用します。</span><span class="sxs-lookup"><span data-stu-id="d79d6-145">Uses the ESB Dispatcher at the receive location for endpoint resolution.</span></span>|  
    |<span data-ttu-id="d79d6-146">メッセージ内の情報を使用して、適切なエンドポイントを決定します。</span><span class="sxs-lookup"><span data-stu-id="d79d6-146">Uses information within the message to determine the appropriate endpoint.</span></span> <span data-ttu-id="d79d6-147">この例で使用できるテスト ファイルは NAOrderDoc_XPATH_FILE.xml、NAOrderDoc_XPATH_FTP.xml、および NAOrderDoc_XPATH_MQS.xml です。</span><span class="sxs-lookup"><span data-stu-id="d79d6-147">The test files you can use with this example are NAOrderDoc_XPATH_FILE.xml, NAOrderDoc_XPATH_FTP.xml, and NAOrderDoc_XPATH_MQS.xml.</span></span>|  
  
4.  <span data-ttu-id="d79d6-148">GlobalBank.ESB アプリケーションを実行するメッセージの例については、バインド ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="d79d6-148">Import the binding file for the messaging example you want to execute into the GlobalBank.ESB application.</span></span>  
  
5.  <span data-ttu-id="d79d6-149">Windows エクスプ ローラーでフォルダー \Source\Samples\DynamicResolution\Test\Data 開きフォルダー \Source\Samples\DynamicResolution\Test\Filedrop\In に適切な入力ファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="d79d6-149">In Windows Explorer, open the folder \Source\Samples\DynamicResolution\Test\Data and copy the appropriate input file into the folder \Source\Samples\DynamicResolution\Test\Filedrop\In.</span></span> <span data-ttu-id="d79d6-150">使用するファイルは、例を実行することが決定によって異なります。</span><span class="sxs-lookup"><span data-stu-id="d79d6-150">The file you use depends on the example you decided to execute:</span></span>  
  
    -   <span data-ttu-id="d79d6-151">XPATH の例を次のファイルのいずれかを使用: NAOrderDoc_XPATH_FILE.xml、NAOrderDoc_XPATH_FTP.xml、または NAOrderDoc_XPATH_MQS.xml です。</span><span class="sxs-lookup"><span data-stu-id="d79d6-151">For the XPATH example, use one of the following files: NAOrderDoc_XPATH_FILE.xml, NAOrderDoc_XPATH_FTP.xml, or NAOrderDoc_XPATH_MQS.xml.</span></span>  
  
    -   <span data-ttu-id="d79d6-152">その他のすべての例では、ファイル NAOrderDoc.xml を使用します。</span><span class="sxs-lookup"><span data-stu-id="d79d6-152">For all other examples, use the file NAOrderDoc.xml.</span></span>  
  
6.  <span data-ttu-id="d79d6-153">配信されたメッセージの適切な場所を検索します。</span><span class="sxs-lookup"><span data-stu-id="d79d6-153">Look in the appropriate location for the delivered message.</span></span> <span data-ttu-id="d79d6-154">場所を使用して、バインド ファイルに依存します。</span><span class="sxs-lookup"><span data-stu-id="d79d6-154">The location depends on the binding file you used.</span></span> <span data-ttu-id="d79d6-155">例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d79d6-155">The following are examples:</span></span>  
  
    -   <span data-ttu-id="d79d6-156">FTP 送信の例には、ファイルの受信メッセージが配信を Out という FTP 仮想ディレクトリに、サンプルのインストール時に作成したことです。</span><span class="sxs-lookup"><span data-stu-id="d79d6-156">The File Inbound to FTP Outbound example delivers the message to the FTP virtual directory named Out that you created when you installed the sample.</span></span>  
  
    -   <span data-ttu-id="d79d6-157">送信ファイルの例には、ファイルの受信メッセージを配信します \DynamicResolution\Test\Filedrop\Out サブフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="d79d6-157">The File Inbound to FILE Outbound example delivers the message to the \DynamicResolution\Test\Filedrop\Out subfolder.</span></span>  
  
    -   <span data-ttu-id="d79d6-158">MQS 送信の例には、ファイルの受信メッセージを配信しますテストします。ときに作成したキューをサンプルのインストール。</span><span class="sxs-lookup"><span data-stu-id="d79d6-158">The File Inbound to MQS Outbound example delivers the message to the TEST.OUT queue that you created when you installed the sample.</span></span>  
  
    -   <span data-ttu-id="d79d6-159">メッセージで指定された場所にメッセージを配信するファイル呼び出し力方向 XPATH 競合回避モジュールの使用例を使用してファイルを受信します。</span><span class="sxs-lookup"><span data-stu-id="d79d6-159">The File Inbound to FILE Outbound using the XPATH Resolver example delivers the message to the location specified in the message.</span></span> <span data-ttu-id="d79d6-160">サンプル ドキュメントには、移行先の場所およびトランスポートの種類が含まれて (トランスポートの種類は、メッセージのファイル名に追加されます。 たとえば、NAOrderDoc_XPATH_FTP.xml メッセージが FTP トランスポートの型の仕様が含まれます)。</span><span class="sxs-lookup"><span data-stu-id="d79d6-160">The sample documents contain the destination location and transport type (the transport type is appended to the message file name; for example, the NAOrderDoc_XPATH_FTP.xml message contains the FTP transport type specification).</span></span>  
  
 <span data-ttu-id="d79d6-161">このサンプルでの ESB ディスパッチャーと ESB ディスパッチャーの逆アセンブラー パイプライン コンポーネントの使用方法を理解するのを参照してください。 [「動的解決サンプルの動作](../esb-toolkit/how-the-dynamic-resolution-sample-works.md)です。</span><span class="sxs-lookup"><span data-stu-id="d79d6-161">To understand how the sample uses the ESB Dispatcher and ESB Dispatcher Disassembler pipeline components, see [How the Dynamic Resolution Sample Works](../esb-toolkit/how-the-dynamic-resolution-sample-works.md).</span></span>