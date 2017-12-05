---
title: "手順 2: エコー アダプターの受信ハンドラーのテスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 86dede9b-6b7e-4901-9c79-b75bfee9155f
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94e17bcc987949b9ca25ac25db9a1789ebe980eb
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-2-test-inbound-handler-of-the-echo-adapter"></a><span data-ttu-id="21e3d-102">手順 2: エコー アダプターの受信ハンドラーをテストします。</span><span class="sxs-lookup"><span data-stu-id="21e3d-102">Step 2: Test Inbound Handler of the Echo Adapter</span></span>
<span data-ttu-id="21e3d-103">![手順 2 の 2](../../adapters-and-accelerators/adapter-sql/media/step-2of2.gif "Step_2of2")</span><span class="sxs-lookup"><span data-stu-id="21e3d-103">![Step 2 of 2](../../adapters-and-accelerators/adapter-sql/media/step-2of2.gif "Step_2of2")</span></span>  
  
 <span data-ttu-id="21e3d-104">**所要時間:** 10 分</span><span class="sxs-lookup"><span data-stu-id="21e3d-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="21e3d-105">この手順では、エコー アダプターによって提供される受信サービスをテストします。</span><span class="sxs-lookup"><span data-stu-id="21e3d-105">In this step, you test the inbound service provided by the Echo Adapter.</span></span> <span data-ttu-id="21e3d-106">これを行う Visual Studio では、アダプター サービス参照を Visual Studio プラグインの追加とカスタム コードを使用します。</span><span class="sxs-lookup"><span data-stu-id="21e3d-106">You do this using Visual Studio, the Add Adapter Service Reference Visual Studio Plug-In and custom code.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="21e3d-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="21e3d-107">Prerequisites</span></span>  
 <span data-ttu-id="21e3d-108">この手順を完了する必要がありますを行った[チュートリアル 1: エコー アダプターを開発](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="21e3d-108">To complete this step, you must have completed [Tutorial 1: Develop the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md).</span></span> <span data-ttu-id="21e3d-109">この手順は、独立して完了できる[手順 1: エコー アダプターの送信ハンドラーのテスト](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-test-outbound-handler-of-the-echo-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="21e3d-109">This step can be completed independent of [Step 1: Test Outbound Handler of the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-test-outbound-handler-of-the-echo-adapter.md).</span></span>  
  
## <a name="create-a-visual-studio-project"></a><span data-ttu-id="21e3d-110">Visual Studio プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="21e3d-110">Create a Visual Studio project</span></span>  
  
1.  <span data-ttu-id="21e3d-111">Visual Studio を起動します。</span><span class="sxs-lookup"><span data-stu-id="21e3d-111">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="21e3d-112">Visual Studio での**ファイル** メニューのをポイント**新規**、順にクリック**プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="21e3d-112">In Visual Studio, on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="21e3d-113">**新しいプロジェクト** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="21e3d-113">In the **New Project** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="21e3d-114">プロパティ</span><span class="sxs-lookup"><span data-stu-id="21e3d-114">Use this</span></span>|<span data-ttu-id="21e3d-115">目的</span><span class="sxs-lookup"><span data-stu-id="21e3d-115">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="21e3d-116">**プロジェクトの種類**</span><span class="sxs-lookup"><span data-stu-id="21e3d-116">**Project types**</span></span>|<span data-ttu-id="21e3d-117">をクリックして**Visual c#**です。</span><span class="sxs-lookup"><span data-stu-id="21e3d-117">Click **Visual C#**.</span></span>|  
    |<span data-ttu-id="21e3d-118">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="21e3d-118">**Templates**</span></span>|<span data-ttu-id="21e3d-119">をクリックして**コンソール アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="21e3d-119">Click **Console Application**.</span></span>|  
    |<span data-ttu-id="21e3d-120">**名前**</span><span class="sxs-lookup"><span data-stu-id="21e3d-120">**Name**</span></span>|<span data-ttu-id="21e3d-121">型**ConsumeEchoAdapter_Inbound**です。</span><span class="sxs-lookup"><span data-stu-id="21e3d-121">Type **ConsumeEchoAdapter_Inbound**.</span></span>|  
    |<span data-ttu-id="21e3d-122">**場所**</span><span class="sxs-lookup"><span data-stu-id="21e3d-122">**Location**</span></span>|<span data-ttu-id="21e3d-123">型**C:\Tutorials**です。</span><span class="sxs-lookup"><span data-stu-id="21e3d-123">Type **C:\Tutorials**.</span></span>|  
    |<span data-ttu-id="21e3d-124">**[ソリューション名]**</span><span class="sxs-lookup"><span data-stu-id="21e3d-124">**Solution Name**</span></span>|<span data-ttu-id="21e3d-125">型**ConsumeEchoAdapter_Inbound**です。</span><span class="sxs-lookup"><span data-stu-id="21e3d-125">Type **ConsumeEchoAdapter_Inbound**.</span></span>|  
  
4.  <span data-ttu-id="21e3d-126">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="21e3d-126">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="21e3d-127">Visual Studio での**ファイル** メニューのをクリックして**すべて保存**です。</span><span class="sxs-lookup"><span data-stu-id="21e3d-127">In Visual Studio, on the **File** menu, click **Save All**.</span></span>  
  
## <a name="browse-search-and-generate-the-wcf-service"></a><span data-ttu-id="21e3d-128">参照、検索、および WCF サービスを生成</span><span class="sxs-lookup"><span data-stu-id="21e3d-128">Browse, search, and generate the WCF service</span></span>  
  
1.  <span data-ttu-id="21e3d-129">ウィンドウで、Visual Studio のソリューションを右クリックして**ConsumeEchoAdapter_Inbound**プロジェクトを選択し、**アダプター サービス参照の追加**アダプター サービス参照の追加プラグインを起動します。</span><span class="sxs-lookup"><span data-stu-id="21e3d-129">In the Visual Studio Solution pane, right-click **ConsumeEchoAdapter_Inbound** project then choose **Add Adapter Service Reference** to launch the Add Adapter Service Reference plug-in.</span></span>  
  
2.  <span data-ttu-id="21e3d-130">**アダプター サービス参照の追加**画面で、バインディングを選択します。</span><span class="sxs-lookup"><span data-stu-id="21e3d-130">In the **Add Adapter Service Reference** screen, choose a binding.</span></span> <span data-ttu-id="21e3d-131">これは、選択で**echoAdapterBindingV2**です。</span><span class="sxs-lookup"><span data-stu-id="21e3d-131">This is done by choosing **echoAdapterBindingV2**.</span></span>  
  
3.  <span data-ttu-id="21e3d-132">次に、アダプターとの接続のプロパティを構成する をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="21e3d-132">Next, configure the adapter and connection properties by clicking **Configure**.</span></span>  <span data-ttu-id="21e3d-133">開き、**アダプターの構成**画面。</span><span class="sxs-lookup"><span data-stu-id="21e3d-133">This opens the **Configure Adapter** screen.</span></span>  
  
4.  <span data-ttu-id="21e3d-134">**アダプターの構成**画面で、、**バインド プロパティ**タブでアダプターのプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="21e3d-134">In the **Configure Adapter** screen, select the **Binding Properties** tab to configure the adapter properties.</span></span> <span data-ttu-id="21e3d-135">注意してカスタムのカテゴリのエコー アダプター**受信**と**その他**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="21e3d-135">Notice that the custom Echo Adapter categories **Inbound** and **Misc** are shown.</span></span> <span data-ttu-id="21e3d-136">下にある、**その他**カテゴリで、をクリックして**InboundFileSystemWatcherFolder**し監視するディレクトリを入力します。</span><span class="sxs-lookup"><span data-stu-id="21e3d-136">Under the **Misc** category, click **InboundFileSystemWatcherFolder** and then enter the directory you want to monitor.</span></span>  
  
5.  <span data-ttu-id="21e3d-137">をクリックして**[ok]**を閉じる、**アダプターの構成**画面およびに戻り、**アダプター サービス参照の追加**画面。</span><span class="sxs-lookup"><span data-stu-id="21e3d-137">Click **OK** to close the **Configure Adapter** screen and return to the **Add Adapter Service Reference** screen.</span></span>  
  
6.  <span data-ttu-id="21e3d-138">次に、をクリックして**接続**エコー アダプタ (およびの仮定の基幹業務システムをサポートしています) に接続します。</span><span class="sxs-lookup"><span data-stu-id="21e3d-138">Next, click **Connect** to connect to the Echo Adapter (and hypothetical line-of-business system it supports).</span></span> <span data-ttu-id="21e3d-139">しばらくすると、接続の状態を変更する必要があります**接続**とカテゴリ ツリー (**カテゴリを選択**) 設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="21e3d-139">After a few moments, the connection status should change to **Connected** and the Category Tree (under **Select a category**) should be populated.</span></span>  
  
7.  <span data-ttu-id="21e3d-140">使用可能な受信操作を表示するには、変更、**サービス コントラクト型**に**サービス (入力方向の操作)**です。</span><span class="sxs-lookup"><span data-stu-id="21e3d-140">To view available inbound operations, change the **Service contract type** to **Service (Inbound operations)**.</span></span>  
  
8.  <span data-ttu-id="21e3d-141">分類ツリーで、をクリックして**メイン カテゴリ**です。</span><span class="sxs-lookup"><span data-stu-id="21e3d-141">In the Category Tree, click **Main Category**.</span></span> <span data-ttu-id="21e3d-142">これには、利用可能なカテゴリと操作を 1 つの受信操作の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="21e3d-142">This populates the list of available categories and operations with a single inbound operation.</span></span> <span data-ttu-id="21e3d-143">カテゴリはありません。</span><span class="sxs-lookup"><span data-stu-id="21e3d-143">There are no categories.</span></span>  
  
9. <span data-ttu-id="21e3d-144">**利用可能なカテゴリと操作**、select、 **OnReceiveEcho**操作します。</span><span class="sxs-lookup"><span data-stu-id="21e3d-144">In the **Available Categories and Operations**, select the **OnReceiveEcho** operation.</span></span> <span data-ttu-id="21e3d-145">をクリックして**追加**生成した WCF インターフェイスの選択した操作の一部に取り入れるためです。</span><span class="sxs-lookup"><span data-stu-id="21e3d-145">Click **Add** to make the selected operations part of the generated WCF interface.</span></span>  
  
10. <span data-ttu-id="21e3d-146">をクリックして**OK** WCF インターフェイスを生成します。</span><span class="sxs-lookup"><span data-stu-id="21e3d-146">Click **OK** to generate the WCF interface.</span></span> <span data-ttu-id="21e3d-147">これにより、アプリケーション構成ファイル (app.config)、WCF インターフェイス (EchoAdapterBindingInterface.cs) および WCF サービス (EchoAdapterBindingService.cs) がプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="21e3d-147">This adds an application configuration file (app.config), a WCF interface (EchoAdapterBindingInterface.cs) and a WCF service (EchoAdapterBindingService.cs) to the project.</span></span>  
  
11. <span data-ttu-id="21e3d-148">をクリックして**ファイル**上、 **Visual Studio**メニューを選択し、**すべてを保存**です。</span><span class="sxs-lookup"><span data-stu-id="21e3d-148">Click **File** on the **Visual Studio** menu and choose **Save All**.</span></span>  
  
## <a name="test-the-echo-adapter"></a><span data-ttu-id="21e3d-149">エコー アダプターをテストします。</span><span class="sxs-lookup"><span data-stu-id="21e3d-149">Test the Echo Adapter</span></span>  
  
1.  <span data-ttu-id="21e3d-150">ソリューション エクスプ ローラーで、 **EchoAdapterBindingService.cs**ファイル。</span><span class="sxs-lookup"><span data-stu-id="21e3d-150">In Solution Explorer, double-click the **EchoAdapterBindingService.cs** file.</span></span>  
  
2.  <span data-ttu-id="21e3d-151">Visual Studio エディターで、内部、 **OnReceiveEcho**メソッド、既存の実装を次に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="21e3d-151">In the Visual Studio editor, inside the **OnReceiveEcho** method, replace the existing implementation with the following:</span></span>  
  
    ```csharp  
    System.Console.WriteLine("path = " + path + ", len = " + length);  
    ```  
  
3.  <span data-ttu-id="21e3d-152">ソリューション エクスプ ローラーで、 **Program.cs**ファイル。</span><span class="sxs-lookup"><span data-stu-id="21e3d-152">In Solution Explorer, double-click the **Program.cs** file.</span></span>  
  
4.  <span data-ttu-id="21e3d-153">Main メソッド内の Visual Studio エディターでは、次のコードを WCF サービスのホストを追加します。</span><span class="sxs-lookup"><span data-stu-id="21e3d-153">In the Visual Studio editor, inside the Main method, add the following code to host the WCF service.</span></span>  
  
    ```csharp  
    try  
    {  
        // Create a ServiceHost for the EchoServiceImpl type  
        // and use the base address from app.config  
        System.ServiceModel.ServiceHost host = new System.ServiceModel.ServiceHost(typeof(EchoAdapterBindingNamespace.EchoAdapterBindingService));  
  
        // Open the ServiceHost to start listening for messages  
        host.Open();  
  
        Console.WriteLine("The service is ready.");  
        Console.WriteLine("Press <ENTER> to terminate service.");  
        Console.ReadLine();  
  
        // Close the ServiceHost  
        host.Close();  
    }  
    catch (TimeoutException ex)  
    {  
        Console.WriteLine(ex.Message);  
        Console.WriteLine();  
    }  
    catch (System.ServiceModel.CommunicationException ex)  
    {  
        Console.WriteLine(ex.Message);  
        Console.WriteLine();  
    }  
    ```  
  
5.  <span data-ttu-id="21e3d-154">Visual Studio での**ファイル** メニューのをクリックして**すべて保存**です。</span><span class="sxs-lookup"><span data-stu-id="21e3d-154">In Visual Studio, on the **File** menu, click **Save All**.</span></span>  
  
6.  <span data-ttu-id="21e3d-155">F5 キーを押してサンプルを開始します。</span><span class="sxs-lookup"><span data-stu-id="21e3d-155">Press F5 to start the sample.</span></span>  
  
7.  <span data-ttu-id="21e3d-156">このチュートリアルで以前に指定されたディレクトリを"txt"の拡張子を持つファイルをドロップします。</span><span class="sxs-lookup"><span data-stu-id="21e3d-156">Drop a file with the "txt" extension into the directory specified earlier in this tutorial.</span></span> <span data-ttu-id="21e3d-157">プログラムは、出力ウィンドウでは、次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="21e3d-157">You should see information similar to the following in the program output window:</span></span>  
  
     <span data-ttu-id="21e3d-158">**サービス準備ができました。**</span><span class="sxs-lookup"><span data-stu-id="21e3d-158">**The service is ready.**</span></span>  
  
     <span data-ttu-id="21e3d-159">**キーを押して\<ENTER\>サービスを終了します。**</span><span class="sxs-lookup"><span data-stu-id="21e3d-159">**Press \<ENTER\> to terminate service.**</span></span>  
  
     <span data-ttu-id="21e3d-160">**パス = file:///C:/Tutorial/InboundTest/InboundTest.txt、len 229179 を =**</span><span class="sxs-lookup"><span data-stu-id="21e3d-160">**path = file:///C:/Tutorial/InboundTest/InboundTest.txt, len = 229179**</span></span>  
  
8.  <span data-ttu-id="21e3d-161">サービスを停止して、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="21e3d-161">Press the Enter key to stop the service.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="21e3d-162">でしただけは何ですか。</span><span class="sxs-lookup"><span data-stu-id="21e3d-162">What Did I Just Do?</span></span>  
 <span data-ttu-id="21e3d-163">この手順で作成したテスト アプリケーションで開発されたエコー アダプターによって公開されている受信操作の[チュートリアル 1: エコー アダプターを開発](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="21e3d-163">In this step, you created a test application for the inbound operation exposed by the Echo Adapter developed in [Tutorial 1: Develop the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md).</span></span> <span data-ttu-id="21e3d-164">これを行うには、WCF サービスを生成、および WCF サービスをホストするためのコードを提供する、Visual Studio プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="21e3d-164">To do this, you created a Visual Studio project, generated a WCF Service, and provided code to host the WCF Service.</span></span> <span data-ttu-id="21e3d-165">最後に、テスト アプリケーションを実行しました。</span><span class="sxs-lookup"><span data-stu-id="21e3d-165">Finally, you ran the test application.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="21e3d-166">次の手順</span><span class="sxs-lookup"><span data-stu-id="21e3d-166">Next Steps</span></span>  
 <span data-ttu-id="21e3d-167">これは、このチュートリアルの最後の手順です。</span><span class="sxs-lookup"><span data-stu-id="21e3d-167">This is the last step of the tutorial.</span></span> <span data-ttu-id="21e3d-168">受信操作の詳細については、次を参照してください。`Microsoft.ServiceModel.Channels.Common.IInboundHandler`です。</span><span class="sxs-lookup"><span data-stu-id="21e3d-168">For more information about Inbound operations, see `Microsoft.ServiceModel.Channels.Common.IInboundHandler`.</span></span> <span data-ttu-id="21e3d-169">エコー アダプターおよびテストのコードでのダウンロードを表示して、SDK には認証を必要とする WCF サービスをホストする方法を示しますが、 [http://go.microsoft.com/fwlink/?LinkID=96184](http://go.microsoft.com/fwlink/?LinkID=96184)です。</span><span class="sxs-lookup"><span data-stu-id="21e3d-169">To see an example SDK that demonstrates how to host a WCF Service that requires authentication, download the echo adapter and test code at [http://go.microsoft.com/fwlink/?LinkID=96184](http://go.microsoft.com/fwlink/?LinkID=96184).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21e3d-170">参照</span><span class="sxs-lookup"><span data-stu-id="21e3d-170">See Also</span></span>  
 <span data-ttu-id="21e3d-171">[チュートリアル 2: .NET からエコー アダプターを使用します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md) </span><span class="sxs-lookup"><span data-stu-id="21e3d-171">[Tutorial 2: Consume the Echo Adapter from .NET](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md) </span></span>  
 [<span data-ttu-id="21e3d-172">チュートリアル 1: エコー アダプターを開発する</span><span class="sxs-lookup"><span data-stu-id="21e3d-172">Tutorial 1: Develop the Echo Adapter</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)