---
title: DynamicReceive サンプル (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0fa7c934-7ec3-45ad-b226-c8c53934ecb1
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 38cde24f8bc91fc5a2fc741978ebfac9d7283c51
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350610"
---
# <a name="dynamicreceive-sample-biztalk-server-sample"></a><span data-ttu-id="9537b-102">DynamicReceive サンプル (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="9537b-102">DynamicReceive Sample (BizTalk Server Sample)</span></span>
<span data-ttu-id="9537b-103">DynamicReceive サンプルでは、受信[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]MQSeries からメッセージ キュー MQSeries キューの URI を動的に指定します。</span><span class="sxs-lookup"><span data-stu-id="9537b-103">The DynamicReceive sample demonstrates how to receive [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] messages from an MQSeries queue when the URI for the MQSeries queue is specified dynamically.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="9537b-104">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="9537b-104">What This Sample Does</span></span>  
 <span data-ttu-id="9537b-105">このサンプルで指定された MQSeries キューを動的に作成する、 **queueManager**、**キュー**、および**server**変数。</span><span class="sxs-lookup"><span data-stu-id="9537b-105">This sample dynamically creates an MQSeries queue as specified by the **queueManager**, **queue**, and **server** variables.</span></span> <span data-ttu-id="9537b-106">これにより、動的なシナリオを受信し、取得[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で指定したフィルター条件に基づいて動的に指定された MQSeries キューからメッセージを**MQMD_MsgId**と**MQMD_CorrelId**メッセージ プロパティ。</span><span class="sxs-lookup"><span data-stu-id="9537b-106">It enables a dynamic receive scenario and obtains [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] messages from the dynamically specified MQSeries queue based on the filter criteria specified in the **MQMD_MsgId** and **MQMD_CorrelId** message properties.</span></span>  
  
## <a name="how-this-sample-was-designed-and-why"></a><span data-ttu-id="9537b-107">このサンプルのデザイン方法とその理由</span><span class="sxs-lookup"><span data-stu-id="9537b-107">How This Sample Was Designed and Why</span></span>  
 <span data-ttu-id="9537b-108">MQSeries アダプターはメッセージをオーケストレーションで、キューの URI アドレスを指定することで、MQSeries キューから受信動的にできます。</span><span class="sxs-lookup"><span data-stu-id="9537b-108">The MQSeries adapter can dynamically receive messages from an MQSeries queue by specifying the URI address of the queue in the orchestration.</span></span> <span data-ttu-id="9537b-109">この機能は、オーケストレーションの送信請求-応答送信ポートを使用して実現されます。</span><span class="sxs-lookup"><span data-stu-id="9537b-109">This functionality is achieved by using a solicit-response send port in the orchestration.</span></span>  
  
 <span data-ttu-id="9537b-110">動的にメッセージを受信するでは、次を指定します、**式**オーケストレーションの図形。</span><span class="sxs-lookup"><span data-stu-id="9537b-110">To dynamically receive messages, specify the following in an **Expression** shape in the orchestration:</span></span>  
  
1. <span data-ttu-id="9537b-111">次のプロパティを設定の受信を有効にする動的、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ。**MQSeries.DynamicReceive** = `'Yes'`</span><span class="sxs-lookup"><span data-stu-id="9537b-111">Enable dynamic receive by setting the following property on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] message: **MQSeries.DynamicReceive** = `'Yes'`</span></span>  
  
2. <span data-ttu-id="9537b-112">ポート URI を設定して、メッセージの取得元のアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="9537b-112">Specify the address from which to get the messages by setting the port URI.</span></span> <span data-ttu-id="9537b-113">必要に応じて、次のように指定できます。</span><span class="sxs-lookup"><span data-stu-id="9537b-113">Optionally you can specify the following:</span></span>  
  
   -   <span data-ttu-id="9537b-114">使用して、メッセージを取得する前に、待機間隔を指定、 **MQSeries.WaitInterval**メッセージのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="9537b-114">Specify the wait interval before getting the messages by using the **MQSeries.WaitInterval** property on the message.</span></span>  
  
   -   <span data-ttu-id="9537b-115">メッセージを受信するための一致条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="9537b-115">Specify match criteria for receiving messages.</span></span> <span data-ttu-id="9537b-116">一致条件のオプションは**メッセージ ID**、 **CorrelationID**、 **GroupID**、および**MessageSequenceNumber**します。</span><span class="sxs-lookup"><span data-stu-id="9537b-116">The match criteria options are **Message ID**, **CorrelationID**, **GroupID**, and **MessageSequenceNumber**.</span></span> <span data-ttu-id="9537b-117">「プロパティ Related to BizTalk Server」を参照してください[ http://go.microsoft.com/fwlink/?LinkId=89396 ](http://go.microsoft.com/fwlink/?LinkId=89396)の詳細。</span><span class="sxs-lookup"><span data-stu-id="9537b-117">See "Properties Related to BizTalk Server" at [http://go.microsoft.com/fwlink/?LinkId=89396](http://go.microsoft.com/fwlink/?LinkId=89396) for more details.</span></span>  
  
   <span data-ttu-id="9537b-118">これらのプロパティで、メッセージが作成された後、送信請求-応答の送信ポートを使用して MQSeries キューに送信されます。</span><span class="sxs-lookup"><span data-stu-id="9537b-118">After the message is created with these properties it is sent to the MQSeries queue by using a solicit-response send port.</span></span> <span data-ttu-id="9537b-119">ポートは、一致オプションを使用して、指定した URI からメッセージを受信アダプターを指定します。</span><span class="sxs-lookup"><span data-stu-id="9537b-119">The port specifies the adapter to receive messages from the specified URI with the indicated match options.</span></span> <span data-ttu-id="9537b-120">次の操作の結果:</span><span class="sxs-lookup"><span data-stu-id="9537b-120">The following actions result:</span></span>  
  
- <span data-ttu-id="9537b-121">メッセージを取得するフィルター条件が満たされている場合、メッセージはキューから取得され、オーケストレーションに返されます。</span><span class="sxs-lookup"><span data-stu-id="9537b-121">If the filter criteria to obtain a message are satisfied, then the message is retrieved from the queue and is sent back to the orchestration.</span></span>  
  
- <span data-ttu-id="9537b-122">メッセージを取得するフィルター条件が満たされない場合は、ダミーの応答が返されます。</span><span class="sxs-lookup"><span data-stu-id="9537b-122">If the filter criteria to obtain a message are not satisfied, a dummy response is returned.</span></span> <span data-ttu-id="9537b-123">これは、指定したオプション返さなかったことのすべてのメッセージ キューからを示します。</span><span class="sxs-lookup"><span data-stu-id="9537b-123">This is an indication that the specified options did not return any messages from the queue.</span></span>  
  
  <span data-ttu-id="9537b-124">機能の提供をさらに柔軟のため、固定した受信場所必要はありませんが表示される動的を使用します。</span><span class="sxs-lookup"><span data-stu-id="9537b-124">Using the dynamic receive functionality gives you additional flexibility because a fixed receive location is not required.</span></span> <span data-ttu-id="9537b-125">場合によってを知らなくても、URI 実行時までです。</span><span class="sxs-lookup"><span data-stu-id="9537b-125">In some cases, you may not know the URI until run time.</span></span> <span data-ttu-id="9537b-126">動的受信機能メッセージを取得する場所からを動的に決定することができます。</span><span class="sxs-lookup"><span data-stu-id="9537b-126">Dynamic receive functionality allows you to dynamically determine from where to obtain messages.</span></span> <span data-ttu-id="9537b-127">また、オーケストレーション内でキュー コントラクトを実装する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9537b-127">It also means you do not need to implement a queuing contract within an orchestration.</span></span>  <span data-ttu-id="9537b-128">指定した一致条件に基づいて MQSeries キューから動的に指定された URI を使用してメッセージを取得するを待機することができます。</span><span class="sxs-lookup"><span data-stu-id="9537b-128">You can wait to obtain messages by using a dynamically specified URI from the MQSeries queue based on the specified match criteria.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="9537b-129">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="9537b-129">Where to Find This Sample</span></span>  
 <span data-ttu-id="9537b-130">\<*Samples Path*\>\Samples\AdaptersUsage\MQSeriesAdapter\DynamicReceive</span><span class="sxs-lookup"><span data-stu-id="9537b-130">\<*Samples Path*\>\Samples\AdaptersUsage\MQSeriesAdapter\DynamicReceive</span></span>  
  
 <span data-ttu-id="9537b-131">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="9537b-131">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9537b-132">ファイル</span><span class="sxs-lookup"><span data-stu-id="9537b-132">File</span></span>|<span data-ttu-id="9537b-133">説明</span><span class="sxs-lookup"><span data-stu-id="9537b-133">Description</span></span>|  
|<span data-ttu-id="9537b-134">DynamicReceive.btproj,</span><span class="sxs-lookup"><span data-stu-id="9537b-134">DynamicReceive.btproj,</span></span><br /><br /> <span data-ttu-id="9537b-135">DynamicReceive.sln</span><span class="sxs-lookup"><span data-stu-id="9537b-135">DynamicReceive.sln</span></span>|<span data-ttu-id="9537b-136">アプリケーションのプロジェクトおよびソリューション ファイル。</span><span class="sxs-lookup"><span data-stu-id="9537b-136">Project and solution files for the application.</span></span>|  
|<span data-ttu-id="9537b-137">DynamicReceive e.odx</span><span class="sxs-lookup"><span data-stu-id="9537b-137">DynamicReceive e.odx</span></span>|<span data-ttu-id="9537b-138">アプリケーションの BizTalk オーケストレーション ファイル。</span><span class="sxs-lookup"><span data-stu-id="9537b-138">The BizTalk orchestration file for the application.</span></span>|  
|<span data-ttu-id="9537b-139">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="9537b-139">Setup.bat</span></span>|<span data-ttu-id="9537b-140">キー ファイルを作成、プロジェクトをコンパイルしてデプロイするバッチ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="9537b-140">Batch file to create the key file, compile the project, and deploy it.</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="9537b-141">このサンプルの使用方法</span><span class="sxs-lookup"><span data-stu-id="9537b-141">How to Use This Sample</span></span>  
 <span data-ttu-id="9537b-142">指定、 **Microsoft.XLANGs.BaseTypes.Address**ソリューションに合理的です。</span><span class="sxs-lookup"><span data-stu-id="9537b-142">Specify the **Microsoft.XLANGs.BaseTypes.Address** that makes sense for your solution.</span></span> <span data-ttu-id="9537b-143">変更、 **MQSeries.WaitInterval**応答メッセージの受信を予期したタイミングを指定します。</span><span class="sxs-lookup"><span data-stu-id="9537b-143">Change the **MQSeries.WaitInterval** to specify when you expect to receive the response messages.</span></span> <span data-ttu-id="9537b-144">一致オプションを更新する (または追加する) またはすべてのメッセージを取得する予定の場合は、それらを削除します。</span><span class="sxs-lookup"><span data-stu-id="9537b-144">Update (or add) the match options, or remove them if you plan to obtain all messages.</span></span>  
  
## <a name="building-and-running-the-sample"></a><span data-ttu-id="9537b-145">ビルドとサンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="9537b-145">Building and Running the Sample</span></span>  
  
#### <a name="to-create-the-sample"></a><span data-ttu-id="9537b-146">サンプルを作成するには</span><span class="sxs-lookup"><span data-stu-id="9537b-146">To create the sample</span></span>  
  
1. <span data-ttu-id="9537b-147">Microsoft で新しいオーケストレーション プロジェクトを作成[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="9537b-147">Create a new orchestration project in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
2. <span data-ttu-id="9537b-148">有効にする、動的受信操作を設定して、 **MQSeries.DynamicReceive**プロパティを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージを`'Yes'`します。</span><span class="sxs-lookup"><span data-stu-id="9537b-148">Enable the dynamic receive operation by setting the **MQSeries.DynamicReceive** property on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] message to `'Yes'`.</span></span>  
  
3. <span data-ttu-id="9537b-149">設定して、メッセージの取得元となるアドレス指定、**ポート URI**します。</span><span class="sxs-lookup"><span data-stu-id="9537b-149">Specify the address from which to obtain the messages by setting the **Port URI**.</span></span>  
  
4. <span data-ttu-id="9537b-150">必要に応じて次の 2 つのプロパティを指定できます。</span><span class="sxs-lookup"><span data-stu-id="9537b-150">Optionally the following two properties can be specified:</span></span>  
  
   1.  <span data-ttu-id="9537b-151">使用して、メッセージを取得する前に待機間隔を指定、 **MQSeries.WaitInterval**メッセージのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="9537b-151">Specify a wait interval before getting the messages by using the **MQSeries.WaitInterval** property on the message.</span></span>  
  
   2.  <span data-ttu-id="9537b-152">メッセージを受信するための一致条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="9537b-152">Specify match criteria for receiving messages.</span></span> <span data-ttu-id="9537b-153">詳細については、「オプションに一致する」のヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9537b-153">See "Match options" help for more details.</span></span>  
  
5. <span data-ttu-id="9537b-154">オーケストレーションからメッセージを取得する場所を指定するには、次の変数を変更します。</span><span class="sxs-lookup"><span data-stu-id="9537b-154">Change the following variables in the orchestration to specify where to get the messages from:</span></span>  
  
   -   <span data-ttu-id="9537b-155">**キュー**、 **queueManager**、および**server**します。</span><span class="sxs-lookup"><span data-stu-id="9537b-155">**Queue**, **queueManager**, and **server**.</span></span> <span data-ttu-id="9537b-156">これら URI を作成に使用されます、**式**図形。</span><span class="sxs-lookup"><span data-stu-id="9537b-156">These are used to build the URI in the **Expression** shape.</span></span>  
  
6. <span data-ttu-id="9537b-157">変更、**式**図形に応じて動的キュー作成と一致オプションをコメントにします。</span><span class="sxs-lookup"><span data-stu-id="9537b-157">Modify the **Expression** shape to comment out dynamic queue creation and match options as necessary.</span></span>  
  
7. <span data-ttu-id="9537b-158">ビルドして、次の方法のいずれかでプロジェクトを配置します。</span><span class="sxs-lookup"><span data-stu-id="9537b-158">You can build and deploy the project in either of the following ways:</span></span>  
  
   -   <span data-ttu-id="9537b-159">ソリューションを開き、ソリューション エクスプ ローラーでプロジェクトを右クリックしてをクリックして**プロパティ**プロジェクトのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="9537b-159">Open the solution, right click the project in Solution explorer and click **Properties** to view project properties.</span></span> <span data-ttu-id="9537b-160">[署名] タブをクリックして**\<新規.\>** で、**厳密な名前キー ファイルを選択して**ボックスの一覧します。</span><span class="sxs-lookup"><span data-stu-id="9537b-160">On the Signing tab click **\<New...\>** in the **Choose a strong name key file** drop down box.</span></span> <span data-ttu-id="9537b-161">キー ファイル名を指定し、デプロイします。</span><span class="sxs-lookup"><span data-stu-id="9537b-161">Then provide a key file name and deploy.</span></span>  
  
   -   <span data-ttu-id="9537b-162">または、キー ファイルを作成し、プロジェクトをビルドし、それを展開する setup.bat ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="9537b-162">Alternatively, run the setup.bat file which creates the key file, builds the project and deploys it.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="9537b-163">サンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="9537b-163">To run the sample</span></span>  
  
1.  <span data-ttu-id="9537b-164">BizTalk ホストにオーケストレーションをバインドします。</span><span class="sxs-lookup"><span data-stu-id="9537b-164">Bind the orchestration to the BizTalk Host.</span></span>  
  
2.  <span data-ttu-id="9537b-165">により、ファイルは、オーケストレーションによって作成されたポートを受信できます。</span><span class="sxs-lookup"><span data-stu-id="9537b-165">Enable the file receive port created by the orchestration.</span></span> <span data-ttu-id="9537b-166">変更、ファイル受信場所から**c:\temp\in**適切なファイル フォルダーにします。</span><span class="sxs-lookup"><span data-stu-id="9537b-166">Change the file receive location from **c:\temp\in** to the proper file folder.</span></span>  
  
3.  <span data-ttu-id="9537b-167">参加させ、作成された 2 つの送信ポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="9537b-167">Enlist and start the two send ports that were created.</span></span> <span data-ttu-id="9537b-168">1 つのポートと動的な送信請求-応答ポートの種類は file 送信ポートをメッセージの送信先キューには、その他。</span><span class="sxs-lookup"><span data-stu-id="9537b-168">One port is a dynamic solicit-response port type, while the other is a file send port and is the queue where the message will be sent.</span></span> <span data-ttu-id="9537b-169">これが、適切な場所に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9537b-169">Ensure that this is set to the correct location.</span></span>  
  
4.  <span data-ttu-id="9537b-170">オーケストレーションは、開始するには、入力フォルダーにファイルをドロップします。</span><span class="sxs-lookup"><span data-stu-id="9537b-170">To start the orchestration, drop a file in the input folder.</span></span> <span data-ttu-id="9537b-171">MQSeries アダプターと呼び出しが起動、 **MQSAgent2**メッセージを取得する指定されたサーバー上の COM + コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="9537b-171">This invokes the MQSeries adapter and calls the **MQSAgent2** COM+ component on the specified server to obtain the message.</span></span> <span data-ttu-id="9537b-172">File 送信ポートで指定されたフォルダーの場所で受信したメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9537b-172">The received message appears in the folder location specified in the file send port.</span></span>  
  
5.  <span data-ttu-id="9537b-173">指定された条件に一致するメッセージがない場合、**式**図形、ダミーのメッセージが出力フォルダーにドロップします。</span><span class="sxs-lookup"><span data-stu-id="9537b-173">If no message is found that matches the criteria specified in the **Expression** shape, a dummy message is dropped into the output folder.</span></span> <span data-ttu-id="9537b-174">一致オプションを無効にするで最後の 2 つの行をコメント アウト、**式**図形。</span><span class="sxs-lookup"><span data-stu-id="9537b-174">To disable match options, comment out the last two lines in the **Expression** shape.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="9537b-175">コメント</span><span class="sxs-lookup"><span data-stu-id="9537b-175">Comments</span></span>  
  
-   <span data-ttu-id="9537b-176">キューが作成される場合に動的に、削除ですが、エラーになります次のオーケストレーション インスタンスがアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="9537b-176">If the queue is being dynamically created, but not deleted, it will result in errors when the next orchestration instance is activated.</span></span>  
  
-   <span data-ttu-id="9537b-177">URI を動的に設定するには、その他の方法があります。このサンプルでは、1 つのオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="9537b-177">There are other ways to set the URI dynamically; this sample specifies just one option.</span></span> <span data-ttu-id="9537b-178">たとえば、URI を設定して、メッセージ コンテキストのプロパティを読み込むことでした。</span><span class="sxs-lookup"><span data-stu-id="9537b-178">For example, the URI could be set by reading some property in the message context.</span></span>  
  
-   <span data-ttu-id="9537b-179">一致オプションに適合する、キュー内のメッセージがない場合は、ダミーのメッセージが返されます。</span><span class="sxs-lookup"><span data-stu-id="9537b-179">If there are no messages in the queue that satisfy the match options, a dummy message is returned.</span></span>  
  
-   <span data-ttu-id="9537b-180">このサンプルでは、動的送信ポートを使用するため、その他のオプションは、再試行やトランザクションなど、指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9537b-180">Because this sample uses dynamic send ports, other options may need to be specified, such as retry and transactions.</span></span> <span data-ttu-id="9537b-181">動的な送信請求-応答ポートにメッセージを送信する前にこれらのオプションを設定するのにには、アダプターによって公開されるコンテキスト プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="9537b-181">Use the context properties exposed by the adapter to set these options before sending the message out to the dynamic solicit-response port.</span></span>  
  
-   <span data-ttu-id="9537b-182">MQSeries キューを作成しを使用して動的に削除、 **MQSAdapterAdmin2**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="9537b-182">MQSeries queues can be created and deleted dynamically by using the **MQSAdapterAdmin2** interface.</span></span> <span data-ttu-id="9537b-183">MQSeries キューを動的に作成する方法の例を参照してください"Support for Queue Management" [ http://go.microsoft.com/fwlink/?LinkId=89400](http://go.microsoft.com/fwlink/?LinkId=89400)します。</span><span class="sxs-lookup"><span data-stu-id="9537b-183">For an example of how to dynamically create MQSeries queues, see "Support for Queue Management" at [http://go.microsoft.com/fwlink/?LinkId=89400](http://go.microsoft.com/fwlink/?LinkId=89400).</span></span>