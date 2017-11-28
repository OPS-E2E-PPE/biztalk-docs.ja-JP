---
title: "手順 1: エコー アダプターの送信ハンドラーのテスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ad4a8164-a584-436f-b20b-4c884f6e2b37
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba2b1d6586588d17c58c0ca9a74cb11a7a9bd9f2
ms.sourcegitcommit: 6b6d905bbef7796c850178e99ac293578bb58317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2017
---
# <a name="step-1-test-outbound-handler-of-the-echo-adapter"></a><span data-ttu-id="90da5-102">手順 1: エコー アダプターの送信ハンドラーをテストします。</span><span class="sxs-lookup"><span data-stu-id="90da5-102">Step 1: Test Outbound Handler of the Echo Adapter</span></span>
<span data-ttu-id="90da5-103">![2 の手順 1.](../../adapters-and-accelerators/adapter-sql/media/step-1of2.gif "Step_1of2")</span><span class="sxs-lookup"><span data-stu-id="90da5-103">![Step 1 of 2](../../adapters-and-accelerators/adapter-sql/media/step-1of2.gif "Step_1of2")</span></span>  
  
 <span data-ttu-id="90da5-104">**完了時間:** 15 分</span><span class="sxs-lookup"><span data-stu-id="90da5-104">**Time to Complete:** 15 minutes</span></span>  
  
 <span data-ttu-id="90da5-105">この手順では、エコー アダプターによって提供される 3 つの送信操作をテストします。</span><span class="sxs-lookup"><span data-stu-id="90da5-105">In this step, you will test the three outbound operations provided by the Echo Adapter.</span></span> <span data-ttu-id="90da5-106">これを行う Visual Studio では、アダプター サービス参照を Visual Studio プラグインの追加とカスタム コードを使用します。</span><span class="sxs-lookup"><span data-stu-id="90da5-106">You will do this using Visual Studio, the Add Adapter Service Reference Visual Studio Plug-In and custom code.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="90da5-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="90da5-107">Prerequisites</span></span>  
 <span data-ttu-id="90da5-108">この手順を完了する必要がありますを行った[チュートリアル 1: エコー アダプターを開発](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="90da5-108">To complete this step, you must have completed [Tutorial 1: Develop the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md).</span></span>  
  
## <a name="create-a-visual-studio-project"></a><span data-ttu-id="90da5-109">Visual Studio プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="90da5-109">Create a Visual Studio project</span></span>  
  
1.  <span data-ttu-id="90da5-110">Visual Studio を起動します。</span><span class="sxs-lookup"><span data-stu-id="90da5-110">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="90da5-111">Visual Studio での**ファイル**メニューのをポイント**新規**、順にクリック**プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="90da5-111">In Visual Studio, on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="90da5-112">**新しいプロジェクト** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="90da5-112">In the **New Project** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="90da5-113">プロパティ</span><span class="sxs-lookup"><span data-stu-id="90da5-113">Use this</span></span>|<span data-ttu-id="90da5-114">目的</span><span class="sxs-lookup"><span data-stu-id="90da5-114">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="90da5-115">**プロジェクトの種類**</span><span class="sxs-lookup"><span data-stu-id="90da5-115">**Project types**</span></span>|<span data-ttu-id="90da5-116">をクリックして**Visual c#**です。</span><span class="sxs-lookup"><span data-stu-id="90da5-116">Click **Visual C#**.</span></span>|  
    |<span data-ttu-id="90da5-117">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="90da5-117">**Templates**</span></span>|<span data-ttu-id="90da5-118">をクリックして**コンソール アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="90da5-118">Click **Console Application**.</span></span>|  
    |<span data-ttu-id="90da5-119">**名前**</span><span class="sxs-lookup"><span data-stu-id="90da5-119">**Name**</span></span>|<span data-ttu-id="90da5-120">型**ConsumeEchoAdapter_Outbound**です。</span><span class="sxs-lookup"><span data-stu-id="90da5-120">Type **ConsumeEchoAdapter_Outbound**.</span></span>|  
    |<span data-ttu-id="90da5-121">**場所**</span><span class="sxs-lookup"><span data-stu-id="90da5-121">**Location**</span></span>|<span data-ttu-id="90da5-122">型**C:\Tutorials**です。</span><span class="sxs-lookup"><span data-stu-id="90da5-122">Type **C:\Tutorials**.</span></span>|  
    |<span data-ttu-id="90da5-123">**[ソリューション名]**</span><span class="sxs-lookup"><span data-stu-id="90da5-123">**Solution Name**</span></span>|<span data-ttu-id="90da5-124">型**ConsumeEchoAdapter_Outbound**です。</span><span class="sxs-lookup"><span data-stu-id="90da5-124">Type **ConsumeEchoAdapter_Outbound**.</span></span>|  
  
4.  <span data-ttu-id="90da5-125">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90da5-125">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="90da5-126">Visual Studio での**ファイル** メニューのをクリックして**すべて保存**です。</span><span class="sxs-lookup"><span data-stu-id="90da5-126">In Visual Studio, on the **File** menu, click **Save All**.</span></span>  
  
## <a name="browse-search-and-generate-the-wcf-client"></a><span data-ttu-id="90da5-127">参照、検索、および WCF クライアントの生成</span><span class="sxs-lookup"><span data-stu-id="90da5-127">Browse, search, and generate the WCF client</span></span>  
  
1.  <span data-ttu-id="90da5-128">ウィンドウで、Visual Studio のソリューションを右クリックして**ConsumeEchoAdapter_Outbound**を選択し、[プロジェクト]**アダプター サービス参照の追加**アダプター サービス参照の追加プラグインを起動します。</span><span class="sxs-lookup"><span data-stu-id="90da5-128">In the Visual Studio Solution pane, right-click **ConsumeEchoAdapter_Outbound** project, then choose **Add Adapter Service Reference** to launch the Add Adapter Service Reference plug-in.</span></span>  
  
2.  <span data-ttu-id="90da5-129">**アダプター サービス参照の追加**画面で、バインディングを選択します。</span><span class="sxs-lookup"><span data-stu-id="90da5-129">In the **Add Adapter Service Reference** screen, choose a binding.</span></span> <span data-ttu-id="90da5-130">これは、選択で**echoAdapterBindingV2**です。</span><span class="sxs-lookup"><span data-stu-id="90da5-130">This is done by choosing **echoAdapterBindingV2**.</span></span>  
  
3.  <span data-ttu-id="90da5-131">次に、アダプターとの接続のプロパティを構成する をクリックして**構成しています...**.</span><span class="sxs-lookup"><span data-stu-id="90da5-131">Next, configure the adapter and connection properties by clicking **Configure…**.</span></span>  <span data-ttu-id="90da5-132">これが表示されます、**アダプターの構成**画面。</span><span class="sxs-lookup"><span data-stu-id="90da5-132">This will bring up the **Configure Adapter** screen.</span></span>  
  
4.  <span data-ttu-id="90da5-133">**アダプターの構成**画面で、、 **URI プロパティ**タブで接続のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="90da5-133">In the **Configure Adapter** screen, select the **URI Properties** tab to configure connection properties.</span></span> <span data-ttu-id="90da5-134">カスタムのカテゴリのエコー アダプターが示されている通知:**接続**と**形式**です。</span><span class="sxs-lookup"><span data-stu-id="90da5-134">Notice that the custom Echo Adapter categories are shown — **Connection** and **Format**.</span></span> <span data-ttu-id="90da5-135">下にある、**形式**カテゴリで、変更**EchoInUpperCase**に**True**です。</span><span class="sxs-lookup"><span data-stu-id="90da5-135">Under the **Format** category, change **EchoInUpperCase** to **True**.</span></span>  
  
5.  <span data-ttu-id="90da5-136">**アダプターの構成**画面で、、**バインド プロパティ**タブでアダプターのプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="90da5-136">In the **Configure Adapter** screen, select the **Binding Properties** tab to configure the adapter properties.</span></span> <span data-ttu-id="90da5-137">注意してカスタムのカテゴリのエコー アダプター**受信**と**その他**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="90da5-137">Notice that the custom Echo Adapter categories **Inbound** and **Misc** are shown.</span></span> <span data-ttu-id="90da5-138">下にある、**その他**カテゴリで、変更**カウント**に**3**です。</span><span class="sxs-lookup"><span data-stu-id="90da5-138">Under the **Misc** category, change **Count** to **3**.</span></span>  
  
6.  <span data-ttu-id="90da5-139">をクリックして**[ok]**を閉じる、**アダプターの構成**画面およびに戻り、**アダプター サービス参照の追加**画面。</span><span class="sxs-lookup"><span data-stu-id="90da5-139">Click **OK** to close the **Configure Adapter** screen and return to the **Add Adapter Service Reference** screen.</span></span>  
  
7.  <span data-ttu-id="90da5-140">次に、をクリックして**接続**エコー アダプタ (およびの仮定の基幹業務システムをサポートしています) に接続します。</span><span class="sxs-lookup"><span data-stu-id="90da5-140">Next, click **Connect** to connect to the Echo Adapter (and hypothetical line-of-business system it supports).</span></span> <span data-ttu-id="90da5-141">しばらくすると、接続の状態を変更する必要があります**接続**とカテゴリ ツリー (**カテゴリを選択**) 設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90da5-141">After a few moments, the connection status should change to **Connected** and the Category Tree (under **Select a category**) should be populated.</span></span>  
  
8.  <span data-ttu-id="90da5-142">分類ツリーで、をクリックして**メイン カテゴリ**です。</span><span class="sxs-lookup"><span data-stu-id="90da5-142">In the Category Tree, click **Main Category**.</span></span> <span data-ttu-id="90da5-143">これにより、利用可能なカテゴリと操作と、次の 3 つの送信操作の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="90da5-143">This will populate the list of available categories and operations with three outbound operations.</span></span> <span data-ttu-id="90da5-144">カテゴリされません。</span><span class="sxs-lookup"><span data-stu-id="90da5-144">There will be no categories.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="90da5-145">既定のコントラクトの種類は、送信です。</span><span class="sxs-lookup"><span data-stu-id="90da5-145">The default contract type is Outbound.</span></span> <span data-ttu-id="90da5-146">カテゴリの結果には、このコントラクトの型は一致します。</span><span class="sxs-lookup"><span data-stu-id="90da5-146">Category results will match this contract type.</span></span>  
  
9. <span data-ttu-id="90da5-147">**利用可能なカテゴリと操作**、3 つすべての操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="90da5-147">In the **Available Categories and Operations**, select all three operations.</span></span> <span data-ttu-id="90da5-148">多数の操作が存在する場合、選択範囲を絞り込む検索を使用する可能性があります。この場合はのみ 3 つあります。</span><span class="sxs-lookup"><span data-stu-id="90da5-148">When there are a large number of operations, you might use search to narrow down the selection; in this case, there are only three.</span></span> <span data-ttu-id="90da5-149">をクリックして**追加**生成した WCF インターフェイスの選択した操作の一部に取り入れるためです。</span><span class="sxs-lookup"><span data-stu-id="90da5-149">Click **Add** to make the selected operations part of the generated WCF interface.</span></span>  
  
10. <span data-ttu-id="90da5-150">をクリックして**OK** WCF インターフェイスを生成します。</span><span class="sxs-lookup"><span data-stu-id="90da5-150">Click **OK** to generate the WCF interface.</span></span> <span data-ttu-id="90da5-151">アプリケーション構成ファイル (app.config) と WCF クライアント プロキシ (EchoAdapterBindingClient.cs) は、プロジェクトにこの追加されます。</span><span class="sxs-lookup"><span data-stu-id="90da5-151">This will add an application configuration file (app.config) and a WCF client proxy (EchoAdapterBindingClient.cs) to the project.</span></span>  
  
11. <span data-ttu-id="90da5-152">をクリックして**ファイル**Visual Studio のメニューで選択**すべてを保存**です。</span><span class="sxs-lookup"><span data-stu-id="90da5-152">Click **File** on the Visual Studio menu and choose **Save All**.</span></span>  
  
## <a name="configure-adapter-authentication"></a><span data-ttu-id="90da5-153">アダプターの認証を構成します。</span><span class="sxs-lookup"><span data-stu-id="90da5-153">Configure adapter authentication</span></span>  
  
1.  <span data-ttu-id="90da5-154">Visual Studio ソリューション ウィンドウで、ダブルクリック**app.config**です。</span><span class="sxs-lookup"><span data-stu-id="90da5-154">In Visual Studio Solution pane, double-click **app.config**.</span></span>  
  
2.  <span data-ttu-id="90da5-155">検索、`address`属性、`endpoint`要素。</span><span class="sxs-lookup"><span data-stu-id="90da5-155">Find the `address` attribute in the `endpoint` element.</span></span> <span data-ttu-id="90da5-156">これは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="90da5-156">It should look similar to the following:</span></span>  
  
    ```  
    <endpoint address="echov2://lobhostname/lobapplication?enableAuthentication=False&echoInUpperCase=True"  
        binding="echoAdapterBindingV2" bindingConfiguration="EchoAdapterBinding"  
        contract="EchoOutboundContract" name="EchoAdapterBinding_EchoOutboundContract" />  
    ```  
  
     <span data-ttu-id="90da5-157">変更**enableAuthentication**から**False**に**True**次のようにします。</span><span class="sxs-lookup"><span data-stu-id="90da5-157">Change **enableAuthentication** from **False** to **True** as shown below.</span></span> <span data-ttu-id="90da5-158">資格情報をアダプターに渡す呼び出し元のアプリケーションが必要になります。</span><span class="sxs-lookup"><span data-stu-id="90da5-158">This will require the calling application to pass credentials to the adapter.</span></span>  
  
    ```  
    <endpoint address="echov2://lobhostname/lobapplication?enableAuthentication=True&echoInUpperCase=True"  
        binding="echoAdapterBindingV2" bindingConfiguration="EchoAdapterBinding"  
        contract="EchoOutboundContract" name="EchoAdapterBinding_EchoOutboundContract" />  
    ```  
  
3.  <span data-ttu-id="90da5-159">クリックして、ソリューションを保存**ファイル**Visual Studio でメニュー**すべて保存**です。</span><span class="sxs-lookup"><span data-stu-id="90da5-159">Save the solution by clicking **File** on the Visual Studio menu and choosing **Save All**.</span></span>  
  
## <a name="create-a-sample-xml-file"></a><span data-ttu-id="90da5-160">サンプル XML ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="90da5-160">Create a sample XML file</span></span>  
  
1.  <span data-ttu-id="90da5-161">メモ帳のインスタンスを起動します。</span><span class="sxs-lookup"><span data-stu-id="90da5-161">Start an instance of Notepad.</span></span> <span data-ttu-id="90da5-162">[スタート] メニューを使用してクリックして**すべてのプログラム**& #124 です。**アクセサリ**を選択し**メモ帳**です。</span><span class="sxs-lookup"><span data-stu-id="90da5-162">Using the Start menu, click **All Programs** &#124; **Accessories** and then choose **Notepad**.</span></span>  
  
2.  <span data-ttu-id="90da5-163">メモ帳などのエディターに次のサンプル データをコピーします。</span><span class="sxs-lookup"><span data-stu-id="90da5-163">Copy the following sample data into the Notepad editor.</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-16"?>  
    <ns0:greeting xmlns:ns0="echov2://microsoft.adapters.samples.echov2/PreDefinedTypes">  
      <ns0:address>  
        <ns0:street1>123 Microsoft Way</ns0:street1>  
        <ns0:street2>Building # 4599</ns0:street2>  
        <ns0:city>Redmond</ns0:city>  
        <ns0:state>WA</ns0:state>  
        <ns0:zip>98052</ns0:zip>  
      </ns0:address>  
      <ns0:greetingText>Welcome to Redmond!</ns0:greetingText>  
    </ns0:greeting>              
    ```  
  
3.  <span data-ttu-id="90da5-164">メモ帳のメニューをクリックして**ファイル**を選択し**名前を付けて保存しています...**.</span><span class="sxs-lookup"><span data-stu-id="90da5-164">On the Notepad menu, click **File** and then choose **Save As…**.</span></span> <span data-ttu-id="90da5-165">"CustomGreetingInstance.xml"ファイル名の入力しのエンコーディングの Unicode を選択し、プロジェクト ディレクトリまたは別の適切な場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="90da5-165">Type in "CustomGreetingInstance.xml" for the file name and choose Unicode for the encoding and then save it to the project directory or another suitable location.</span></span> <span data-ttu-id="90da5-166">完全なパスとファイル名の後で参照に注意してください。</span><span class="sxs-lookup"><span data-stu-id="90da5-166">Note the full path and filename for later reference.</span></span>  
  
4.  <span data-ttu-id="90da5-167">ファイルが正常に保存されるときに、テキスト エディターを閉じます。</span><span class="sxs-lookup"><span data-stu-id="90da5-167">Close the text editor when the file is successfully saved.</span></span>  
  
## <a name="test-the-echo-adapter"></a><span data-ttu-id="90da5-168">エコー アダプターをテストします。</span><span class="sxs-lookup"><span data-stu-id="90da5-168">Test the Echo Adapter</span></span>  
  
1.  <span data-ttu-id="90da5-169">ソリューション エクスプ ローラーで、 **Program.cs**ファイル。</span><span class="sxs-lookup"><span data-stu-id="90da5-169">In Solution Explorer, double-click the **Program.cs** file.</span></span>  
  
2.  <span data-ttu-id="90da5-170">Visual Studio エディターで、内部、 **Main**メソッド、生成された WCF クライアントのインスタンスを作成するコードの次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="90da5-170">In the Visual Studio editor, inside the **Main** method, add the following line of code to create an instance of the generated WCF client.</span></span>  
  
    ```csharp  
    EchoOutboundContractClient client = new EchoOutboundContractClient();  
    ```  
  
3.  <span data-ttu-id="90da5-171">これでアダプター用の資格情報を確立するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="90da5-171">Now add code that establishes credentials for the adapter.</span></span> <span data-ttu-id="90da5-172">エコー アダプタで認証が有効の場合、ユーザー名の有無が確認されますが、値を確認できません。</span><span class="sxs-lookup"><span data-stu-id="90da5-172">When authentication is enabled in the Echo Adapter, it will check for the existence of a user name but will not check the value.</span></span>  
  
    ```csharp  
    // pass client credentials  
    client.ClientCredentials.UserName.UserName = "username";  
    ```  
  
4.  <span data-ttu-id="90da5-173">EchoStrings 操作を呼び出すコードを追加して続行します。</span><span class="sxs-lookup"><span data-stu-id="90da5-173">Continue by adding code to invoke the EchoStrings operation.</span></span>  
  
    ```csharp  
    // Invoke EchoStrings()  
    Console.WriteLine("Invoking EchoStrings() method against the adapter...");  
    string[] response = client.EchoStrings("Bonjour!");  
    foreach (string data in response)  
    {  
        Console.WriteLine(data);  
    }  
    ```  
  
5.  <span data-ttu-id="90da5-174">EchoGreetings 操作を呼び出すコードを追加して続行します。</span><span class="sxs-lookup"><span data-stu-id="90da5-174">Continue by adding code to invoke the EchoGreetings operation.</span></span>  
  
    ```csharp  
    // Invoke EchoGreetings()  
    Console.WriteLine("\nInvoking EchoGreetings() method against the adapter...");  
    microsoft.adapters.samples.echov2.Types.Greeting greeting = new microsoft.adapters.samples.echov2.Types.Greeting();  
    greeting.id = Guid.NewGuid();  
    greeting.sentDateTime = DateTime.Now;  
    greeting.greetingText = "Hello World!";  
    greeting.name = new microsoft.adapters.samples.echov2.Types.Name();  
    greeting.name.salutation = microsoft.adapters.samples.echov2.Types.Salutation.Miss;  
    greeting.name.firstName = "Jane";  
    greeting.name.middleName = "Z.";  
    greeting.name.lastName = "Smith";  
    microsoft.adapters.samples.echov2.Types.Greeting[] greetingArray = client.EchoGreetings(greeting);  
    foreach (microsoft.adapters.samples.echov2.Types.Greeting data in greetingArray)  
    {  
        Console.WriteLine(data.id + " " + data.sentDateTime + " " + data.greetingText + " " + data.name.firstName );  
    }  
    ```  
  
6.  <span data-ttu-id="90da5-175">EchoCustomGreetingsFromFile 操作を呼び出すコードを追加して続行します。</span><span class="sxs-lookup"><span data-stu-id="90da5-175">Continue by adding code to invoke the EchoCustomGreetingsFromFile operation.</span></span>  
  
    ```csharp  
    // Invoke EchoCustomGreetingFromFile()  
    Console.WriteLine("\nInvoking EchoCustomGreetingFromFile() method against the adapter ...");  
    // Copy the sample data from CustomGreeting-instance.xml file and place in appropriate folder  
    // as specified in the operation parameter  
    microsoft.adapters.samples.echov2.PreDefinedTypes.CustomGreeting   
    // change the Uri to point to the greeting instance xml file you created  
    customGreeting = client.EchoCustomGreetingFromFile(new Uri(@"c:\CustomGreetingInstance.xml"));  
    Console.WriteLine(customGreeting.greetingText + " " + customGreeting.address.city);  
    client.Close();  
    Console.ReadLine();  
    ```  
  
7.  <span data-ttu-id="90da5-176">EchoCustomGreetingsFromFile テスト コードでカスタムの案内応答は、前の手順で作成したファイルを使用しているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="90da5-176">In the EchoCustomGreetingsFromFile test code, make sure the custom greeting uses the file you created in a previous procedure.</span></span> <span data-ttu-id="90da5-177">ファイルの場所を反映するようにコードを変更します。</span><span class="sxs-lookup"><span data-stu-id="90da5-177">Change the code to reflect the location of your file.</span></span>  
  
8.  <span data-ttu-id="90da5-178">Visual Studio での**ファイル** メニューのをクリックして**すべて保存**です。</span><span class="sxs-lookup"><span data-stu-id="90da5-178">In Visual Studio, on the **File** menu, click **Save All**.</span></span>  
  
9. <span data-ttu-id="90da5-179">アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="90da5-179">Run the application.</span></span> <span data-ttu-id="90da5-180">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="90da5-180">You should see output similar to the following:</span></span>  
  
     <span data-ttu-id="90da5-181">**アダプターに対する EchoStrings() メソッドを呼び出す.**</span><span class="sxs-lookup"><span data-stu-id="90da5-181">**Invoking EchoStrings() method against the adapter...**</span></span>  
  
     <span data-ttu-id="90da5-182">**Bonjour!**</span><span class="sxs-lookup"><span data-stu-id="90da5-182">**Bonjour!**</span></span>  
  
     <span data-ttu-id="90da5-183">**Bonjour!**</span><span class="sxs-lookup"><span data-stu-id="90da5-183">**Bonjour!**</span></span>  
  
     <span data-ttu-id="90da5-184">**Bonjour!**</span><span class="sxs-lookup"><span data-stu-id="90da5-184">**Bonjour!**</span></span>  
  
     <span data-ttu-id="90da5-185">**Bonjour!**</span><span class="sxs-lookup"><span data-stu-id="90da5-185">**Bonjour!**</span></span>  
  
     <span data-ttu-id="90da5-186">**Bonjour!**</span><span class="sxs-lookup"><span data-stu-id="90da5-186">**Bonjour!**</span></span>  
  
     <span data-ttu-id="90da5-187">**アダプターに対する EchoGreetings() メソッドを呼び出す.**</span><span class="sxs-lookup"><span data-stu-id="90da5-187">**Invoking EchoGreetings() method against the adapter...**</span></span>  
  
     <span data-ttu-id="90da5-188">**179665bb-db21-42ac-810e-77ebfa99d460 9/13/2007 3時 18分: 07 PM Hello World!加藤さん**</span><span class="sxs-lookup"><span data-stu-id="90da5-188">**179665bb-db21-42ac-810e-77ebfa99d460 9/13/2007 3:18:07 PM Hello World! Jane**</span></span>  
  
     <span data-ttu-id="90da5-189">**179665bb-db21-42ac-810e-77ebfa99d460 9/13/2007 3時 18分: 07 PM Hello World!加藤さん**</span><span class="sxs-lookup"><span data-stu-id="90da5-189">**179665bb-db21-42ac-810e-77ebfa99d460 9/13/2007 3:18:07 PM Hello World! Jane**</span></span>  
  
     <span data-ttu-id="90da5-190">**179665bb-db21-42ac-810e-77ebfa99d460 9/13/2007 3時 18分: 07 PM Hello World!加藤さん**</span><span class="sxs-lookup"><span data-stu-id="90da5-190">**179665bb-db21-42ac-810e-77ebfa99d460 9/13/2007 3:18:07 PM Hello World! Jane**</span></span>  
  
     <span data-ttu-id="90da5-191">**179665bb-db21-42ac-810e-77ebfa99d460 9/13/2007 3時 18分: 07 PM Hello World!加藤さん**</span><span class="sxs-lookup"><span data-stu-id="90da5-191">**179665bb-db21-42ac-810e-77ebfa99d460 9/13/2007 3:18:07 PM Hello World! Jane**</span></span>  
  
     <span data-ttu-id="90da5-192">**179665bb-db21-42ac-810e-77ebfa99d460 9/13/2007 3時 18分: 07 PM Hello World!加藤さん**</span><span class="sxs-lookup"><span data-stu-id="90da5-192">**179665bb-db21-42ac-810e-77ebfa99d460 9/13/2007 3:18:07 PM Hello World! Jane**</span></span>  
  
     <span data-ttu-id="90da5-193">**アダプターに対する EchoCustomGreetingFromFile() メソッドを呼び出す.**</span><span class="sxs-lookup"><span data-stu-id="90da5-193">**Invoking EchoCustomGreetingFromFile() method against the adapter ...**</span></span>  
  
     <span data-ttu-id="90da5-194">**Redmond へようこそ!Redmond**</span><span class="sxs-lookup"><span data-stu-id="90da5-194">**Welcome to Redmond! Redmond**</span></span>  
  
10. <span data-ttu-id="90da5-195">プログラムを停止するのには Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="90da5-195">Press the Enter key to stop the program.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="90da5-196">でしただけは何ですか。</span><span class="sxs-lookup"><span data-stu-id="90da5-196">What Did I Just Do?</span></span>  
 <span data-ttu-id="90da5-197">このステップでは、チュートリアル 1 で開発されたエコー アダプターによって公開される 3 つの送信操作用のテスト アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="90da5-197">In this step, you created a test application for the three outbound operations exposed by the Echo Adapter developed in Tutorial 1.</span></span> <span data-ttu-id="90da5-198">これを行うには、WCF サービスを生成、および WCF サービスをホストするためのコードを提供する、Visual Studio プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="90da5-198">To do this, you created a Visual Studio project, generated a WCF Service, and provided code to host the WCF Service.</span></span> <span data-ttu-id="90da5-199">最後に、テスト アプリケーションを実行しました。</span><span class="sxs-lookup"><span data-stu-id="90da5-199">Finally, you ran the test application.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="90da5-200">次の手順</span><span class="sxs-lookup"><span data-stu-id="90da5-200">Next Steps</span></span>  
 <span data-ttu-id="90da5-201">受信操作をテストするに進みます[手順 2: エコー アダプターの受信ハンドラーのテスト](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-test-inbound-handler-of-the-echo-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="90da5-201">To test the Inbound operation, proceed to [Step 2: Test Inbound Handler of the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-test-inbound-handler-of-the-echo-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90da5-202">参照</span><span class="sxs-lookup"><span data-stu-id="90da5-202">See Also</span></span>  
  <span data-ttu-id="90da5-203">[チュートリアル 2: .NET からエコー アダプターを使用します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md) </span><span class="sxs-lookup"><span data-stu-id="90da5-203">[Tutorial 2: Consume the Echo Adapter from .NET](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md) </span></span>  
 [<span data-ttu-id="90da5-204">手順 2: エコー アダプターの受信ハンドラーをテストします。</span><span class="sxs-lookup"><span data-stu-id="90da5-204">Step 2: Test Inbound Handler of the Echo Adapter</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-test-inbound-handler-of-the-echo-adapter.md)