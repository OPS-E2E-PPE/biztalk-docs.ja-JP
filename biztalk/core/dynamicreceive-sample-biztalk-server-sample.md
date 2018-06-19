---
title: DynamicReceive サンプル (BizTalk Server サンプル) |Microsoft ドキュメント
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
ms.openlocfilehash: 9e0dc620d2d12933d34df0dce9eb02b697871bdc
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972744"
---
# <a name="dynamicreceive-sample-biztalk-server-sample"></a><span data-ttu-id="36c02-102">DynamicReceive サンプル (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="36c02-102">DynamicReceive Sample (BizTalk Server Sample)</span></span>
<span data-ttu-id="36c02-103">DynamicReceive サンプルは、MQSeries キューの URI が動的に指定される場合に MQSeries キューから [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] メッセージを受信する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="36c02-103">The DynamicReceive sample demonstrates how to receive [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] messages from an MQSeries queue when the URI for the MQSeries queue is specified dynamically.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="36c02-104">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="36c02-104">What This Sample Does</span></span>  
 <span data-ttu-id="36c02-105">このサンプルで指定された MQSeries キューを動的に作成する、 **queueManager**、**キュー**、および**サーバー**変数。</span><span class="sxs-lookup"><span data-stu-id="36c02-105">This sample dynamically creates an MQSeries queue as specified by the **queueManager**, **queue**, and **server** variables.</span></span> <span data-ttu-id="36c02-106">これにより、動的なシナリオを受信し、取得[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で指定したフィルター条件に基づいて動的に指定された MQSeries キューからメッセージを**MQMD_MsgId**と**MQMD_CorrelId**メッセージのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="36c02-106">It enables a dynamic receive scenario and obtains [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] messages from the dynamically specified MQSeries queue based on the filter criteria specified in the **MQMD_MsgId** and **MQMD_CorrelId** message properties.</span></span>  
  
## <a name="how-this-sample-was-designed-and-why"></a><span data-ttu-id="36c02-107">このサンプルをデザインした方法とその理由</span><span class="sxs-lookup"><span data-stu-id="36c02-107">How This Sample Was Designed and Why</span></span>  
 <span data-ttu-id="36c02-108">MQSeries アダプターは、オーケストレーション内のキューの URI アドレスを指定することで、MQSeries キューからメッセージを動的に受信できます。</span><span class="sxs-lookup"><span data-stu-id="36c02-108">The MQSeries adapter can dynamically receive messages from an MQSeries queue by specifying the URI address of the queue in the orchestration.</span></span> <span data-ttu-id="36c02-109">この機能は、オーケストレーションの送信請求 - 応答の送信ポートを使用して実行されます。</span><span class="sxs-lookup"><span data-stu-id="36c02-109">This functionality is achieved by using a solicit-response send port in the orchestration.</span></span>  
  
 <span data-ttu-id="36c02-110">動的にメッセージを受信するでは、次の指定、**式**オーケストレーションの図形。</span><span class="sxs-lookup"><span data-stu-id="36c02-110">To dynamically receive messages, specify the following in an **Expression** shape in the orchestration:</span></span>  
  
1.  <span data-ttu-id="36c02-111">次のプロパティを設定しての受信を可能にする動的、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ: **MQSeries.DynamicReceive** = `'Yes'`</span><span class="sxs-lookup"><span data-stu-id="36c02-111">Enable dynamic receive by setting the following property on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] message: **MQSeries.DynamicReceive** = `'Yes'`</span></span>  
  
2.  <span data-ttu-id="36c02-112">ポート URI を設定して、メッセージの取得元のアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="36c02-112">Specify the address from which to get the messages by setting the port URI.</span></span> <span data-ttu-id="36c02-113">必要に応じて、次の内容を指定できます。</span><span class="sxs-lookup"><span data-stu-id="36c02-113">Optionally you can specify the following:</span></span>  
  
    -   <span data-ttu-id="36c02-114">使用して、メッセージを取得する前に、待機間隔を指定、 **MQSeries.WaitInterval**メッセージのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="36c02-114">Specify the wait interval before getting the messages by using the **MQSeries.WaitInterval** property on the message.</span></span>  
  
    -   <span data-ttu-id="36c02-115">メッセージを受信するための一致条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="36c02-115">Specify match criteria for receiving messages.</span></span> <span data-ttu-id="36c02-116">一致条件オプションは**メッセージ ID**、 **CorrelationID**、 **GroupID**、および**MessageSequenceNumber**です。</span><span class="sxs-lookup"><span data-stu-id="36c02-116">The match criteria options are **Message ID**, **CorrelationID**, **GroupID**, and **MessageSequenceNumber**.</span></span> <span data-ttu-id="36c02-117">「プロパティ Related to BizTalk Server」を参照してください[http://go.microsoft.com/fwlink/?LinkId=89396](http://go.microsoft.com/fwlink/?LinkId=89396)詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="36c02-117">See "Properties Related to BizTalk Server" at [http://go.microsoft.com/fwlink/?LinkId=89396](http://go.microsoft.com/fwlink/?LinkId=89396) for more details.</span></span>  
  
 <span data-ttu-id="36c02-118">これらのプロパティを使用してメッセージを作成した後、送信請求 - 応答の送信ポートを使用してメッセージを MQSeries キューに送信します。</span><span class="sxs-lookup"><span data-stu-id="36c02-118">After the message is created with these properties it is sent to the MQSeries queue by using a solicit-response send port.</span></span> <span data-ttu-id="36c02-119">ポートによって、選択した一致オプションを使用して指定された URI からメッセージを受信するアダプターが指定されます。</span><span class="sxs-lookup"><span data-stu-id="36c02-119">The port specifies the adapter to receive messages from the specified URI with the indicated match options.</span></span> <span data-ttu-id="36c02-120">次の操作の結果:</span><span class="sxs-lookup"><span data-stu-id="36c02-120">The following actions result:</span></span>  
  
-   <span data-ttu-id="36c02-121">メッセージを取得するためのフィルター条件が満たされると、キューからメッセージが取得され、オーケストレーションに返されます。</span><span class="sxs-lookup"><span data-stu-id="36c02-121">If the filter criteria to obtain a message are satisfied, then the message is retrieved from the queue and is sent back to the orchestration.</span></span>  
  
-   <span data-ttu-id="36c02-122">メッセージを取得するためのフィルター条件が満たされない場合は、ダミーの応答が返されます。</span><span class="sxs-lookup"><span data-stu-id="36c02-122">If the filter criteria to obtain a message are not satisfied, a dummy response is returned.</span></span> <span data-ttu-id="36c02-123">これは、指定したオプションがキューからメッセージを返さなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="36c02-123">This is an indication that the specified options did not return any messages from the queue.</span></span>  
  
 <span data-ttu-id="36c02-124">動的受信機能を使用することで、固定した受信場所が不要になるため、柔軟性が高まります。</span><span class="sxs-lookup"><span data-stu-id="36c02-124">Using the dynamic receive functionality gives you additional flexibility because a fixed receive location is not required.</span></span> <span data-ttu-id="36c02-125">実行時まで URI がわからない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="36c02-125">In some cases, you may not know the URI until run time.</span></span> <span data-ttu-id="36c02-126">動的受信機能を使用すると、メッセージの取得元を動的に決定できます。</span><span class="sxs-lookup"><span data-stu-id="36c02-126">Dynamic receive functionality allows you to dynamically determine from where to obtain messages.</span></span> <span data-ttu-id="36c02-127">これは、オーケストレーション内でキュー コントラクトを実装する必要がないことも意味します。</span><span class="sxs-lookup"><span data-stu-id="36c02-127">It also means you do not need to implement a queuing contract within an orchestration.</span></span>  <span data-ttu-id="36c02-128">指定した一致条件に基づいて MQSeries キューから動的に指定された URI を使用することで、メッセージの取得を待機できます。</span><span class="sxs-lookup"><span data-stu-id="36c02-128">You can wait to obtain messages by using a dynamically specified URI from the MQSeries queue based on the specified match criteria.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="36c02-129">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="36c02-129">Where to Find This Sample</span></span>  
 <span data-ttu-id="36c02-130">\<*パスのサンプル*\>\Samples\AdaptersUsage\MQSeriesAdapter\DynamicReceive</span><span class="sxs-lookup"><span data-stu-id="36c02-130">\<*Samples Path*\>\Samples\AdaptersUsage\MQSeriesAdapter\DynamicReceive</span></span>  
  
 <span data-ttu-id="36c02-131">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="36c02-131">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="36c02-132">ファイル</span><span class="sxs-lookup"><span data-stu-id="36c02-132">File</span></span>|<span data-ttu-id="36c02-133">Description</span><span class="sxs-lookup"><span data-stu-id="36c02-133">Description</span></span>|  
|<span data-ttu-id="36c02-134">DynamicReceive.btproj、</span><span class="sxs-lookup"><span data-stu-id="36c02-134">DynamicReceive.btproj,</span></span><br /><br /> <span data-ttu-id="36c02-135">DynamicReceive.sln</span><span class="sxs-lookup"><span data-stu-id="36c02-135">DynamicReceive.sln</span></span>|<span data-ttu-id="36c02-136">アプリケーションのプロジェクトおよびソリューション ファイル。</span><span class="sxs-lookup"><span data-stu-id="36c02-136">Project and solution files for the application.</span></span>|  
|<span data-ttu-id="36c02-137">DynamicReceive e.odx</span><span class="sxs-lookup"><span data-stu-id="36c02-137">DynamicReceive e.odx</span></span>|<span data-ttu-id="36c02-138">アプリケーションの BizTalk オーケストレーション ファイル。</span><span class="sxs-lookup"><span data-stu-id="36c02-138">The BizTalk orchestration file for the application.</span></span>|  
|<span data-ttu-id="36c02-139">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="36c02-139">Setup.bat</span></span>|<span data-ttu-id="36c02-140">キー ファイルを作成し、プロジェクトをコンパイルして配置するバッチ ファイル。</span><span class="sxs-lookup"><span data-stu-id="36c02-140">Batch file to create the key file, compile the project, and deploy it.</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="36c02-141">このサンプルの使用方法</span><span class="sxs-lookup"><span data-stu-id="36c02-141">How to Use This Sample</span></span>  
 <span data-ttu-id="36c02-142">指定して、 **Microsoft.XLANGs.BaseTypes.Address**ソリューションに適したです。</span><span class="sxs-lookup"><span data-stu-id="36c02-142">Specify the **Microsoft.XLANGs.BaseTypes.Address** that makes sense for your solution.</span></span> <span data-ttu-id="36c02-143">変更、 **MQSeries.WaitInterval**を応答メッセージを受信する予期したタイミングを指定します。</span><span class="sxs-lookup"><span data-stu-id="36c02-143">Change the **MQSeries.WaitInterval** to specify when you expect to receive the response messages.</span></span> <span data-ttu-id="36c02-144">一致オプションを更新する (または追加する) か、すべてのメッセージを取得する場合は、それらを削除します。</span><span class="sxs-lookup"><span data-stu-id="36c02-144">Update (or add) the match options, or remove them if you plan to obtain all messages.</span></span>  
  
## <a name="building-and-running-the-sample"></a><span data-ttu-id="36c02-145">サンプルのビルドと実行</span><span class="sxs-lookup"><span data-stu-id="36c02-145">Building and Running the Sample</span></span>  
  
#### <a name="to-create-the-sample"></a><span data-ttu-id="36c02-146">サンプルを作成するには</span><span class="sxs-lookup"><span data-stu-id="36c02-146">To create the sample</span></span>  
  
1.  <span data-ttu-id="36c02-147">Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で新しいオーケストレーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="36c02-147">Create a new orchestration project in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="36c02-148">有効にする、動的受信操作を設定して、 **MQSeries.DynamicReceive**プロパティを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージごとに`'Yes'`です。</span><span class="sxs-lookup"><span data-stu-id="36c02-148">Enable the dynamic receive operation by setting the **MQSeries.DynamicReceive** property on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] message to `'Yes'`.</span></span>  
  
3.  <span data-ttu-id="36c02-149">設定して、メッセージを取得する対象のアドレスを指定して、**ポート URI**です。</span><span class="sxs-lookup"><span data-stu-id="36c02-149">Specify the address from which to obtain the messages by setting the **Port URI**.</span></span>  
  
4.  <span data-ttu-id="36c02-150">必要に応じて、次の 2 つのプロパティを指定できます。</span><span class="sxs-lookup"><span data-stu-id="36c02-150">Optionally the following two properties can be specified:</span></span>  
  
    1.  <span data-ttu-id="36c02-151">使用して、メッセージを取得する前に、待機間隔を指定、 **MQSeries.WaitInterval**メッセージのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="36c02-151">Specify a wait interval before getting the messages by using the **MQSeries.WaitInterval** property on the message.</span></span>  
  
    2.  <span data-ttu-id="36c02-152">メッセージを受信するための一致条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="36c02-152">Specify match criteria for receiving messages.</span></span> <span data-ttu-id="36c02-153">詳細については、「一致条件」のヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="36c02-153">See "Match options" help for more details.</span></span>  
  
5.  <span data-ttu-id="36c02-154">オーケストレーションの次の変数を変更して、メッセージの取得元を指定します。</span><span class="sxs-lookup"><span data-stu-id="36c02-154">Change the following variables in the orchestration to specify where to get the messages from:</span></span>  
  
    -   <span data-ttu-id="36c02-155">**キュー**、 **queueManager**、および**サーバー**です。</span><span class="sxs-lookup"><span data-stu-id="36c02-155">**Queue**, **queueManager**, and **server**.</span></span> <span data-ttu-id="36c02-156">これら URI をビルドに使用されます、**式**図形です。</span><span class="sxs-lookup"><span data-stu-id="36c02-156">These are used to build the URI in the **Expression** shape.</span></span>  
  
6.  <span data-ttu-id="36c02-157">変更、**式**図形を必要に応じて動的キュー作成と一致オプションをコメントにします。</span><span class="sxs-lookup"><span data-stu-id="36c02-157">Modify the **Expression** shape to comment out dynamic queue creation and match options as necessary.</span></span>  
  
7.  <span data-ttu-id="36c02-158">次のいずれかの方法で、プロジェクトをビルドおよび展開できます。</span><span class="sxs-lookup"><span data-stu-id="36c02-158">You can build and deploy the project in either of the following ways:</span></span>  
  
    -   <span data-ttu-id="36c02-159">ソリューションを開きます、ソリューション エクスプ ローラーでプロジェクトを右クリックし、をクリックして**プロパティ**プロジェクト プロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="36c02-159">Open the solution, right click the project in Solution explorer and click **Properties** to view project properties.</span></span> <span data-ttu-id="36c02-160">[署名] タブをクリックして**\<新規しています.\>** で、**厳密な名前キー ファイルを選択して**ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="36c02-160">On the Signing tab click **\<New...\>** in the **Choose a strong name key file** drop down box.</span></span> <span data-ttu-id="36c02-161">次に、キー ファイル名を指定して展開します。</span><span class="sxs-lookup"><span data-stu-id="36c02-161">Then provide a key file name and deploy.</span></span>  
  
    -   <span data-ttu-id="36c02-162">setup.bat ファイルを実行することもできます。このファイルは、キー ファイルを作成し、プロジェクトをビルドして展開します。</span><span class="sxs-lookup"><span data-stu-id="36c02-162">Alternatively, run the setup.bat file which creates the key file, builds the project and deploys it.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="36c02-163">サンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="36c02-163">To run the sample</span></span>  
  
1.  <span data-ttu-id="36c02-164">オーケストレーションを BizTalk ホストにバインドします。</span><span class="sxs-lookup"><span data-stu-id="36c02-164">Bind the orchestration to the BizTalk Host.</span></span>  
  
2.  <span data-ttu-id="36c02-165">オーケストレーションにより作成されたファイル受信ポートを有効にします。</span><span class="sxs-lookup"><span data-stu-id="36c02-165">Enable the file receive port created by the orchestration.</span></span> <span data-ttu-id="36c02-166">ファイルの変更の受信場所から**c:\temp\in**適切なファイル フォルダーにします。</span><span class="sxs-lookup"><span data-stu-id="36c02-166">Change the file receive location from **c:\temp\in** to the proper file folder.</span></span>  
  
3.  <span data-ttu-id="36c02-167">作成された 2 つの送信ポートを参加させ、開始します。</span><span class="sxs-lookup"><span data-stu-id="36c02-167">Enlist and start the two send ports that were created.</span></span> <span data-ttu-id="36c02-168">一方のポートは動的な送信要求 - 応答ポートで、もう一方はファイル送信ポートであり、メッセージが送信されるキューです。</span><span class="sxs-lookup"><span data-stu-id="36c02-168">One port is a dynamic solicit-response port type, while the other is a file send port and is the queue where the message will be sent.</span></span> <span data-ttu-id="36c02-169">これが正しい場所に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="36c02-169">Ensure that this is set to the correct location.</span></span>  
  
4.  <span data-ttu-id="36c02-170">オーケストレーションを開始するには、入力フォルダーのファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="36c02-170">To start the orchestration, drop a file in the input folder.</span></span> <span data-ttu-id="36c02-171">MQSeries アダプターと呼び出しが呼び出されます、 **MQSAgent2** COM + サーバー コンポーネントを指定された、メッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="36c02-171">This invokes the MQSeries adapter and calls the **MQSAgent2** COM+ component on the specified server to obtain the message.</span></span> <span data-ttu-id="36c02-172">受信したメッセージは、ファイル送信ポートで指定されているフォルダーの場所に表示されます。</span><span class="sxs-lookup"><span data-stu-id="36c02-172">The received message appears in the folder location specified in the file send port.</span></span>  
  
5.  <span data-ttu-id="36c02-173">指定された条件に一致するメッセージがない場合、**式**図形、ダミーのメッセージが出力フォルダーにドロップします。</span><span class="sxs-lookup"><span data-stu-id="36c02-173">If no message is found that matches the criteria specified in the **Expression** shape, a dummy message is dropped into the output folder.</span></span> <span data-ttu-id="36c02-174">一致オプションを無効には、最後の 2 つの行をコメント アウトする、**式**図形です。</span><span class="sxs-lookup"><span data-stu-id="36c02-174">To disable match options, comment out the last two lines in the **Expression** shape.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="36c02-175">コメント</span><span class="sxs-lookup"><span data-stu-id="36c02-175">Comments</span></span>  
  
-   <span data-ttu-id="36c02-176">動的に作成されたキューが削除されていない場合は、次のオーケストレーション インスタンスがアクティブ化されたときにエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="36c02-176">If the queue is being dynamically created, but not deleted, it will result in errors when the next orchestration instance is activated.</span></span>  
  
-   <span data-ttu-id="36c02-177">URI を動的に設定する方法は他にもあります。このサンプルでは、1 つのオプションのみを指定しています。</span><span class="sxs-lookup"><span data-stu-id="36c02-177">There are other ways to set the URI dynamically; this sample specifies just one option.</span></span> <span data-ttu-id="36c02-178">たとえば、メッセージ コンテキスト内のプロパティを読み込むことで、URI を設定できます。</span><span class="sxs-lookup"><span data-stu-id="36c02-178">For example, the URI could be set by reading some property in the message context.</span></span>  
  
-   <span data-ttu-id="36c02-179">一致オプションを満たすメッセージがキューにない場合は、ダミーのメッセージが返されます。</span><span class="sxs-lookup"><span data-stu-id="36c02-179">If there are no messages in the queue that satisfy the match options, a dummy message is returned.</span></span>  
  
-   <span data-ttu-id="36c02-180">このサンプルでは動的送信ポートが使用されているため、再試行やトランザクションなど、他のオプションを指定する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="36c02-180">Because this sample uses dynamic send ports, other options may need to be specified, such as retry and transactions.</span></span> <span data-ttu-id="36c02-181">アダプターによって公開されるコンテキスト プロパティを使用して、メッセージを動的な送信請求 - 応答ポートに送信する前にこれらのオプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="36c02-181">Use the context properties exposed by the adapter to set these options before sending the message out to the dynamic solicit-response port.</span></span>  
  
-   <span data-ttu-id="36c02-182">MQSeries キューを作成しを使用して動的に削除、 **MQSAdapterAdmin2**インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="36c02-182">MQSeries queues can be created and deleted dynamically by using the **MQSAdapterAdmin2** interface.</span></span> <span data-ttu-id="36c02-183">MQSeries キューを動的に作成する方法の例を参照してください"Support for Queue Management" [http://go.microsoft.com/fwlink/?LinkId=89400](http://go.microsoft.com/fwlink/?LinkId=89400)です。</span><span class="sxs-lookup"><span data-stu-id="36c02-183">For an example of how to dynamically create MQSeries queues, see "Support for Queue Management" at [http://go.microsoft.com/fwlink/?LinkId=89400](http://go.microsoft.com/fwlink/?LinkId=89400).</span></span>