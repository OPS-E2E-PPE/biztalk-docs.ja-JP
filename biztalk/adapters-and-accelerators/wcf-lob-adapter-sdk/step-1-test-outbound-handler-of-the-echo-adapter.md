---
title: 手順 1:エコー アダプターの送信ハンドラーをテストする |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ad4a8164-a584-436f-b20b-4c884f6e2b37
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 597c4059cb2fc673a557a6e68c5d544db1700522
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363355"
---
# <a name="step-1-test-outbound-handler-of-the-echo-adapter"></a><span data-ttu-id="cf412-102">手順 1:エコー アダプターの送信ハンドラーをテストします。</span><span class="sxs-lookup"><span data-stu-id="cf412-102">Step 1: Test Outbound Handler of the Echo Adapter</span></span>
<span data-ttu-id="cf412-103">![手順 2 の 1](../../adapters-and-accelerators/adapter-sql/media/step-1of2.gif "Step_1of2")</span><span class="sxs-lookup"><span data-stu-id="cf412-103">![Step 1 of 2](../../adapters-and-accelerators/adapter-sql/media/step-1of2.gif "Step_1of2")</span></span>  
  
 <span data-ttu-id="cf412-104">**完了までの時間:** 15 分</span><span class="sxs-lookup"><span data-stu-id="cf412-104">**Time to Complete:** 15 minutes</span></span>  
  
 <span data-ttu-id="cf412-105">この手順では、エコー アダプターによって提供される次の 3 つの送信操作をテストします。</span><span class="sxs-lookup"><span data-stu-id="cf412-105">In this step, you will test the three outbound operations provided by the Echo Adapter.</span></span> <span data-ttu-id="cf412-106">Visual Studio では、アダプター サービス参照を Visual Studio プラグインの追加、カスタム コードを使用してこれが実行されます。</span><span class="sxs-lookup"><span data-stu-id="cf412-106">You will do this using Visual Studio, the Add Adapter Service Reference Visual Studio Plug-In and custom code.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="cf412-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="cf412-107">Prerequisites</span></span>  
 <span data-ttu-id="cf412-108">この手順を完了する必要がありますを行った[チュートリアル 1。エコー アダプターを開発](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="cf412-108">To complete this step, you must have completed [Tutorial 1: Develop the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md).</span></span>  
  
## <a name="create-a-visual-studio-project"></a><span data-ttu-id="cf412-109">Visual Studio プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="cf412-109">Create a Visual Studio project</span></span>  
  
1.  <span data-ttu-id="cf412-110">Visual Studio を起動します。</span><span class="sxs-lookup"><span data-stu-id="cf412-110">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="cf412-111">Visual Studio での**ファイル**メニューで、**新規**、順にクリックします**プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="cf412-111">In Visual Studio, on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="cf412-112">**新しいプロジェクト** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="cf412-112">In the **New Project** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="cf412-113">プロパティ</span><span class="sxs-lookup"><span data-stu-id="cf412-113">Use this</span></span>|<span data-ttu-id="cf412-114">目的</span><span class="sxs-lookup"><span data-stu-id="cf412-114">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="cf412-115">**プロジェクトの種類**</span><span class="sxs-lookup"><span data-stu-id="cf412-115">**Project types**</span></span>|<span data-ttu-id="cf412-116">クリックして**Visual c#** します。</span><span class="sxs-lookup"><span data-stu-id="cf412-116">Click **Visual C#**.</span></span>|  
    |<span data-ttu-id="cf412-117">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="cf412-117">**Templates**</span></span>|<span data-ttu-id="cf412-118">クリックして**コンソール アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="cf412-118">Click **Console Application**.</span></span>|  
    |<span data-ttu-id="cf412-119">**名前**</span><span class="sxs-lookup"><span data-stu-id="cf412-119">**Name**</span></span>|<span data-ttu-id="cf412-120">型**ConsumeEchoAdapter_Outbound**します。</span><span class="sxs-lookup"><span data-stu-id="cf412-120">Type **ConsumeEchoAdapter_Outbound**.</span></span>|  
    |<span data-ttu-id="cf412-121">**場所**</span><span class="sxs-lookup"><span data-stu-id="cf412-121">**Location**</span></span>|<span data-ttu-id="cf412-122">型**C:\Tutorials**します。</span><span class="sxs-lookup"><span data-stu-id="cf412-122">Type **C:\Tutorials**.</span></span>|  
    |<span data-ttu-id="cf412-123">**[ソリューション名]**</span><span class="sxs-lookup"><span data-stu-id="cf412-123">**Solution Name**</span></span>|<span data-ttu-id="cf412-124">型**ConsumeEchoAdapter_Outbound**します。</span><span class="sxs-lookup"><span data-stu-id="cf412-124">Type **ConsumeEchoAdapter_Outbound**.</span></span>|  
  
4.  <span data-ttu-id="cf412-125">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf412-125">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="cf412-126">Visual Studio での**ファイル** メニューのをクリックして**すべて保存**します。</span><span class="sxs-lookup"><span data-stu-id="cf412-126">In Visual Studio, on the **File** menu, click **Save All**.</span></span>  
  
## <a name="browse-search-and-generate-the-wcf-client"></a><span data-ttu-id="cf412-127">参照、検索、および WCF クライアントの生成</span><span class="sxs-lookup"><span data-stu-id="cf412-127">Browse, search, and generate the WCF client</span></span>  
  
1.  <span data-ttu-id="cf412-128">Visual Studio ソリューション ウィンドウで右クリック**ConsumeEchoAdapter_Outbound**プロジェクトを選択し、**アダプター サービス参照の追加**アダプター サービス参照の追加プラグインを起動します。</span><span class="sxs-lookup"><span data-stu-id="cf412-128">In the Visual Studio Solution pane, right-click **ConsumeEchoAdapter_Outbound** project, then choose **Add Adapter Service Reference** to launch the Add Adapter Service Reference plug-in.</span></span>  
  
2.  <span data-ttu-id="cf412-129">**アダプター サービス参照の追加**画面で、バインドを選択します。</span><span class="sxs-lookup"><span data-stu-id="cf412-129">In the **Add Adapter Service Reference** screen, choose a binding.</span></span> <span data-ttu-id="cf412-130">これは、選択で**echoAdapterBindingV2**します。</span><span class="sxs-lookup"><span data-stu-id="cf412-130">This is done by choosing **echoAdapterBindingV2**.</span></span>  
  
3.  <span data-ttu-id="cf412-131">次に、アダプターとの接続のプロパティを構成する をクリックして**構成しています**.</span><span class="sxs-lookup"><span data-stu-id="cf412-131">Next, configure the adapter and connection properties by clicking **Configure…**.</span></span>  <span data-ttu-id="cf412-132">これが表示されます、**アダプターの構成**画面。</span><span class="sxs-lookup"><span data-stu-id="cf412-132">This will bring up the **Configure Adapter** screen.</span></span>  
  
4.  <span data-ttu-id="cf412-133">**アダプターの構成**画面で、、 **URI プロパティ**タブを接続のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="cf412-133">In the **Configure Adapter** screen, select the **URI Properties** tab to configure connection properties.</span></span> <span data-ttu-id="cf412-134">エコー アダプターのカスタム カテゴリに表示される通知-**接続**と**形式**します。</span><span class="sxs-lookup"><span data-stu-id="cf412-134">Notice that the custom Echo Adapter categories are shown — **Connection** and **Format**.</span></span> <span data-ttu-id="cf412-135">下、**形式**カテゴリで、変更**EchoInUpperCase**に**True**します。</span><span class="sxs-lookup"><span data-stu-id="cf412-135">Under the **Format** category, change **EchoInUpperCase** to **True**.</span></span>  
  
5.  <span data-ttu-id="cf412-136">**アダプターの構成**画面で、、**バインドのプロパティ**タブをアダプターのプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="cf412-136">In the **Configure Adapter** screen, select the **Binding Properties** tab to configure the adapter properties.</span></span> <span data-ttu-id="cf412-137">注意してエコー アダプターのカスタム カテゴリ**受信**と**Misc**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cf412-137">Notice that the custom Echo Adapter categories **Inbound** and **Misc** are shown.</span></span> <span data-ttu-id="cf412-138">、 **Misc**カテゴリで、変更**数**に**3**。</span><span class="sxs-lookup"><span data-stu-id="cf412-138">Under the **Misc** category, change **Count** to **3**.</span></span>  
  
6.  <span data-ttu-id="cf412-139">をクリックして**OK**を閉じる、**アダプターの構成**画面に戻って、**アダプター サービス参照の追加**画面。</span><span class="sxs-lookup"><span data-stu-id="cf412-139">Click **OK** to close the **Configure Adapter** screen and return to the **Add Adapter Service Reference** screen.</span></span>  
  
7.  <span data-ttu-id="cf412-140">次に、クリックして**Connect**エコー アダプター (および仮定の基幹業務システムをサポートしています) に接続します。</span><span class="sxs-lookup"><span data-stu-id="cf412-140">Next, click **Connect** to connect to the Echo Adapter (and hypothetical line-of-business system it supports).</span></span> <span data-ttu-id="cf412-141">しばらくすると、接続の状態を変更する必要があります**接続**とカテゴリ ツリー (**カテゴリを選択**) 設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf412-141">After a few moments, the connection status should change to **Connected** and the Category Tree (under **Select a category**) should be populated.</span></span>  
  
8.  <span data-ttu-id="cf412-142">カテゴリのツリーで、クリックして**メイン カテゴリ**します。</span><span class="sxs-lookup"><span data-stu-id="cf412-142">In the Category Tree, click **Main Category**.</span></span> <span data-ttu-id="cf412-143">利用可能なカテゴリと操作と、次の 3 つの送信操作の一覧が設定されます。</span><span class="sxs-lookup"><span data-stu-id="cf412-143">This will populate the list of available categories and operations with three outbound operations.</span></span> <span data-ttu-id="cf412-144">カテゴリされません。</span><span class="sxs-lookup"><span data-stu-id="cf412-144">There will be no categories.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cf412-145">既定のコントラクトの種類は、送信します。</span><span class="sxs-lookup"><span data-stu-id="cf412-145">The default contract type is Outbound.</span></span> <span data-ttu-id="cf412-146">カテゴリの結果には、このコントラクトの型は一致します。</span><span class="sxs-lookup"><span data-stu-id="cf412-146">Category results will match this contract type.</span></span>  
  
9. <span data-ttu-id="cf412-147">**利用可能なカテゴリと操作**、3 つすべての操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="cf412-147">In the **Available Categories and Operations**, select all three operations.</span></span> <span data-ttu-id="cf412-148">多数の操作が存在する場合、選択範囲を絞り込むために検索を使用する場合があります。ここでは 3 種類のみです。</span><span class="sxs-lookup"><span data-stu-id="cf412-148">When there are a large number of operations, you might use search to narrow down the selection; in this case, there are only three.</span></span> <span data-ttu-id="cf412-149">クリックして**追加**選択した操作を生成した WCF インターフェイスの一部にします。</span><span class="sxs-lookup"><span data-stu-id="cf412-149">Click **Add** to make the selected operations part of the generated WCF interface.</span></span>  
  
10. <span data-ttu-id="cf412-150">クリックして**OK** WCF インターフェイスを生成します。</span><span class="sxs-lookup"><span data-stu-id="cf412-150">Click **OK** to generate the WCF interface.</span></span> <span data-ttu-id="cf412-151">アプリケーション構成ファイル (app.config) と WCF クライアント プロキシ (EchoAdapterBindingClient.cs) は、プロジェクトにこれと追加されます。</span><span class="sxs-lookup"><span data-stu-id="cf412-151">This will add an application configuration file (app.config) and a WCF client proxy (EchoAdapterBindingClient.cs) to the project.</span></span>  
  
11. <span data-ttu-id="cf412-152">をクリックして**ファイル**、Visual Studio のメニューで選択**すべて保存**します。</span><span class="sxs-lookup"><span data-stu-id="cf412-152">Click **File** on the Visual Studio menu and choose **Save All**.</span></span>  
  
## <a name="configure-adapter-authentication"></a><span data-ttu-id="cf412-153">アダプターの認証を構成します。</span><span class="sxs-lookup"><span data-stu-id="cf412-153">Configure adapter authentication</span></span>  
  
1.  <span data-ttu-id="cf412-154">Visual Studio ソリューションのウィンドウで**app.config**します。</span><span class="sxs-lookup"><span data-stu-id="cf412-154">In Visual Studio Solution pane, double-click **app.config**.</span></span>  
  
2.  <span data-ttu-id="cf412-155">検索、`address`属性、`endpoint`要素。</span><span class="sxs-lookup"><span data-stu-id="cf412-155">Find the `address` attribute in the `endpoint` element.</span></span> <span data-ttu-id="cf412-156">これは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="cf412-156">It should look similar to the following:</span></span>  
  
    ```  
    <endpoint address="echov2://lobhostname/lobapplication?enableAuthentication=False&echoInUpperCase=True"  
        binding="echoAdapterBindingV2" bindingConfiguration="EchoAdapterBinding"  
        contract="EchoOutboundContract" name="EchoAdapterBinding_EchoOutboundContract" />  
    ```  
  
     <span data-ttu-id="cf412-157">変更**enableAuthentication**から**False**に**True**次のようです。</span><span class="sxs-lookup"><span data-stu-id="cf412-157">Change **enableAuthentication** from **False** to **True** as shown below.</span></span> <span data-ttu-id="cf412-158">アダプターに資格情報を渡すには、呼び出し元のアプリケーションが必要になります。</span><span class="sxs-lookup"><span data-stu-id="cf412-158">This will require the calling application to pass credentials to the adapter.</span></span>  
  
    ```  
    <endpoint address="echov2://lobhostname/lobapplication?enableAuthentication=True&echoInUpperCase=True"  
        binding="echoAdapterBindingV2" bindingConfiguration="EchoAdapterBinding"  
        contract="EchoOutboundContract" name="EchoAdapterBinding_EchoOutboundContract" />  
    ```  
  
3.  <span data-ttu-id="cf412-159">クリックして、ソリューションを保存**ファイル**Visual Studio でメニューを選択し、**すべて保存**します。</span><span class="sxs-lookup"><span data-stu-id="cf412-159">Save the solution by clicking **File** on the Visual Studio menu and choosing **Save All**.</span></span>  
  
## <a name="create-a-sample-xml-file"></a><span data-ttu-id="cf412-160">サンプル XML ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="cf412-160">Create a sample XML file</span></span>  
  
1.  <span data-ttu-id="cf412-161">メモ帳のインスタンスを起動します。</span><span class="sxs-lookup"><span data-stu-id="cf412-161">Start an instance of Notepad.</span></span> <span data-ttu-id="cf412-162">[スタート] メニューを使用してをクリックして**すべてのプログラム** &#124; **アクセサリ**選び、**メモ帳**。</span><span class="sxs-lookup"><span data-stu-id="cf412-162">Using the Start menu, click **All Programs** &#124; **Accessories** and then choose **Notepad**.</span></span>  
  
2.  <span data-ttu-id="cf412-163">メモ帳などのエディターには、次のサンプル データをコピーします。</span><span class="sxs-lookup"><span data-stu-id="cf412-163">Copy the following sample data into the Notepad editor.</span></span>  
  
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
  
3.  <span data-ttu-id="cf412-164">メモ帳のメニューをクリックして**ファイル**を選択し**名前を付けて保存しています**.</span><span class="sxs-lookup"><span data-stu-id="cf412-164">On the Notepad menu, click **File** and then choose **Save As…**.</span></span> <span data-ttu-id="cf412-165">"CustomGreetingInstance.xml"ファイル名の入力し、エンコーディングの Unicode を選択し、プロジェクト ディレクトリまたは別の適切な場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="cf412-165">Type in "CustomGreetingInstance.xml" for the file name and choose Unicode for the encoding and then save it to the project directory or another suitable location.</span></span> <span data-ttu-id="cf412-166">完全なパスとファイル名の後で参照に注意してください。</span><span class="sxs-lookup"><span data-stu-id="cf412-166">Note the full path and filename for later reference.</span></span>  
  
4.  <span data-ttu-id="cf412-167">ファイルが正常に保存するときに、テキスト エディターを閉じます。</span><span class="sxs-lookup"><span data-stu-id="cf412-167">Close the text editor when the file is successfully saved.</span></span>  
  
## <a name="test-the-echo-adapter"></a><span data-ttu-id="cf412-168">エコー アダプターをテストします。</span><span class="sxs-lookup"><span data-stu-id="cf412-168">Test the Echo Adapter</span></span>  
  
1.  <span data-ttu-id="cf412-169">ソリューション エクスプ ローラーで、 **Program.cs**ファイル。</span><span class="sxs-lookup"><span data-stu-id="cf412-169">In Solution Explorer, double-click the **Program.cs** file.</span></span>  
  
2.  <span data-ttu-id="cf412-170">Visual Studio エディターでの内部、 **Main**メソッド、生成された WCF クライアントのインスタンスを作成するコードの次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="cf412-170">In the Visual Studio editor, inside the **Main** method, add the following line of code to create an instance of the generated WCF client.</span></span>  
  
    ```csharp  
    EchoOutboundContractClient client = new EchoOutboundContractClient();  
    ```  
  
3.  <span data-ttu-id="cf412-171">これで、アダプターの資格情報を確立するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="cf412-171">Now add code that establishes credentials for the adapter.</span></span> <span data-ttu-id="cf412-172">エコー アダプターで認証が有効な場合はユーザー名の存在が確認されますが、値は確認されません。</span><span class="sxs-lookup"><span data-stu-id="cf412-172">When authentication is enabled in the Echo Adapter, it will check for the existence of a user name but will not check the value.</span></span>  
  
    ```csharp  
    // pass client credentials  
    client.ClientCredentials.UserName.UserName = "username";  
    ```  
  
4.  <span data-ttu-id="cf412-173">EchoStrings 操作を呼び出すコードを追加して続行します。</span><span class="sxs-lookup"><span data-stu-id="cf412-173">Continue by adding code to invoke the EchoStrings operation.</span></span>  
  
    ```csharp  
    // Invoke EchoStrings()  
    Console.WriteLine("Invoking EchoStrings() method against the adapter...");  
    string[] response = client.EchoStrings("Bonjour!");  
    foreach (string data in response)  
    {  
        Console.WriteLine(data);  
    }  
    ```  
  
5.  <span data-ttu-id="cf412-174">EchoGreetings 操作を呼び出すコードを追加して続行します。</span><span class="sxs-lookup"><span data-stu-id="cf412-174">Continue by adding code to invoke the EchoGreetings operation.</span></span>  
  
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
  
6.  <span data-ttu-id="cf412-175">EchoCustomGreetingsFromFile 操作を呼び出すコードを追加して続行します。</span><span class="sxs-lookup"><span data-stu-id="cf412-175">Continue by adding code to invoke the EchoCustomGreetingsFromFile operation.</span></span>  
  
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
  
7.  <span data-ttu-id="cf412-176">EchoCustomGreetingsFromFile テスト コードでカスタムあいさつ文は、前の手順で作成したファイルを使用しているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="cf412-176">In the EchoCustomGreetingsFromFile test code, make sure the custom greeting uses the file you created in a previous procedure.</span></span> <span data-ttu-id="cf412-177">ファイルの場所を反映するようにコードを変更します。</span><span class="sxs-lookup"><span data-stu-id="cf412-177">Change the code to reflect the location of your file.</span></span>  
  
8.  <span data-ttu-id="cf412-178">Visual Studio での**ファイル** メニューのをクリックして**すべて保存**します。</span><span class="sxs-lookup"><span data-stu-id="cf412-178">In Visual Studio, on the **File** menu, click **Save All**.</span></span>  
  
9. <span data-ttu-id="cf412-179">アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="cf412-179">Run the application.</span></span> <span data-ttu-id="cf412-180">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cf412-180">You should see output similar to the following:</span></span>  
  
     <span data-ttu-id="cf412-181">**アダプターに対する EchoStrings() メソッドを呼び出す.**</span><span class="sxs-lookup"><span data-stu-id="cf412-181">**Invoking EchoStrings() method against the adapter...**</span></span>  
  
     <span data-ttu-id="cf412-182">**Bonjour!**</span><span class="sxs-lookup"><span data-stu-id="cf412-182">**Bonjour!**</span></span>  
  
     <span data-ttu-id="cf412-183">**Bonjour!**</span><span class="sxs-lookup"><span data-stu-id="cf412-183">**Bonjour!**</span></span>  
  
     <span data-ttu-id="cf412-184">**Bonjour!**</span><span class="sxs-lookup"><span data-stu-id="cf412-184">**Bonjour!**</span></span>  
  
     <span data-ttu-id="cf412-185">**Bonjour!**</span><span class="sxs-lookup"><span data-stu-id="cf412-185">**Bonjour!**</span></span>  
  
     <span data-ttu-id="cf412-186">**Bonjour!**</span><span class="sxs-lookup"><span data-stu-id="cf412-186">**Bonjour!**</span></span>  
  
     <span data-ttu-id="cf412-187">**アダプターに対する EchoGreetings() メソッドを呼び出す.**</span><span class="sxs-lookup"><span data-stu-id="cf412-187">**Invoking EchoGreetings() method against the adapter...**</span></span>  
  
     <span data-ttu-id="cf412-188">**179665bb-db21-42ac-810e-77ebfa99d460 2007 年 9 月 13 日午後 3時 18分: 07 Hello World!Jane**</span><span class="sxs-lookup"><span data-stu-id="cf412-188">**179665bb-db21-42ac-810e-77ebfa99d460 9/13/2007 3:18:07 PM Hello World! Jane**</span></span>  
  
     <span data-ttu-id="cf412-189">**179665bb-db21-42ac-810e-77ebfa99d460 2007 年 9 月 13 日午後 3時 18分: 07 Hello World!Jane**</span><span class="sxs-lookup"><span data-stu-id="cf412-189">**179665bb-db21-42ac-810e-77ebfa99d460 9/13/2007 3:18:07 PM Hello World! Jane**</span></span>  
  
     <span data-ttu-id="cf412-190">**179665bb-db21-42ac-810e-77ebfa99d460 2007 年 9 月 13 日午後 3時 18分: 07 Hello World!Jane**</span><span class="sxs-lookup"><span data-stu-id="cf412-190">**179665bb-db21-42ac-810e-77ebfa99d460 9/13/2007 3:18:07 PM Hello World! Jane**</span></span>  
  
     <span data-ttu-id="cf412-191">**179665bb-db21-42ac-810e-77ebfa99d460 2007 年 9 月 13 日午後 3時 18分: 07 Hello World!Jane**</span><span class="sxs-lookup"><span data-stu-id="cf412-191">**179665bb-db21-42ac-810e-77ebfa99d460 9/13/2007 3:18:07 PM Hello World! Jane**</span></span>  
  
     <span data-ttu-id="cf412-192">**179665bb-db21-42ac-810e-77ebfa99d460 2007 年 9 月 13 日午後 3時 18分: 07 Hello World!Jane**</span><span class="sxs-lookup"><span data-stu-id="cf412-192">**179665bb-db21-42ac-810e-77ebfa99d460 9/13/2007 3:18:07 PM Hello World! Jane**</span></span>  
  
     <span data-ttu-id="cf412-193">**アダプターに対する EchoCustomGreetingFromFile() メソッドを呼び出す.**</span><span class="sxs-lookup"><span data-stu-id="cf412-193">**Invoking EchoCustomGreetingFromFile() method against the adapter ...**</span></span>  
  
     <span data-ttu-id="cf412-194">**Redmond へようこそ!Redmond**</span><span class="sxs-lookup"><span data-stu-id="cf412-194">**Welcome to Redmond! Redmond**</span></span>  
  
10. <span data-ttu-id="cf412-195">プログラムを停止して Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="cf412-195">Press the Enter key to stop the program.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="cf412-196">でしただけ何か。</span><span class="sxs-lookup"><span data-stu-id="cf412-196">What Did I Just Do?</span></span>  
 <span data-ttu-id="cf412-197">この手順では、チュートリアル 1 で開発されたエコー アダプターによって公開される 3 つの送信操作のテスト アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="cf412-197">In this step, you created a test application for the three outbound operations exposed by the Echo Adapter developed in Tutorial 1.</span></span> <span data-ttu-id="cf412-198">これを行うには、WCF サービスでは、生成された、および WCF サービスをホストするためのコードを提供する Visual Studio プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="cf412-198">To do this, you created a Visual Studio project, generated a WCF Service, and provided code to host the WCF Service.</span></span> <span data-ttu-id="cf412-199">最後に、テスト アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="cf412-199">Finally, you ran the test application.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="cf412-200">次の手順</span><span class="sxs-lookup"><span data-stu-id="cf412-200">Next Steps</span></span>  
 <span data-ttu-id="cf412-201">受信操作をテストに進みます[手順 2。エコー アダプターの受信ハンドラーをテストする](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-test-inbound-handler-of-the-echo-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="cf412-201">To test the Inbound operation, proceed to [Step 2: Test Inbound Handler of the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-test-inbound-handler-of-the-echo-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf412-202">参照</span><span class="sxs-lookup"><span data-stu-id="cf412-202">See Also</span></span>  
  <span data-ttu-id="cf412-203">[チュートリアル 2: .NET からエコー アダプターを使用します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md) </span><span class="sxs-lookup"><span data-stu-id="cf412-203">[Tutorial 2: Consume the Echo Adapter from .NET](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md) </span></span>  
 [<span data-ttu-id="cf412-204">手順 2:エコー アダプターの受信ハンドラーをテストする</span><span class="sxs-lookup"><span data-stu-id="cf412-204">Step 2: Test Inbound Handler of the Echo Adapter</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-test-inbound-handler-of-the-echo-adapter.md)