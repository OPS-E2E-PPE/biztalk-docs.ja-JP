---
title: "SendMSMQMessage |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, examples
- examples, MSMQ adapters
ms.assetid: 398bc396-0c66-4d55-886a-0d9bdab6476f
caps.latest.revision: "26"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 39fd92c3d017e9ee88fe60f14c8baf9cb0ff941d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sendmsmqmessage"></a><span data-ttu-id="99e2c-102">SendMSMQMessage</span><span class="sxs-lookup"><span data-stu-id="99e2c-102">SendMSMQMessage</span></span>
<span data-ttu-id="99e2c-103">SendMSMQMessage サンプルは、.NET ベースのアプリケーションから MSMQ ポートにメッセージを送信する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="99e2c-103">The SendMSMQMessage sample demonstrates how to send a message to an MSMQ port from a .NET-based application.</span></span> <span data-ttu-id="99e2c-104">Microsoft を構成する方法についても用意されています。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MSMQ の受信場所を使用します。</span><span class="sxs-lookup"><span data-stu-id="99e2c-104">It also provides instructions about how to configure Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to use an MSMQ receive location.</span></span>  
  
 <span data-ttu-id="99e2c-105">メッセージ キューの多くの操作が非同期であることに注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="99e2c-105">You should be aware that many operations in Message Queuing are asynchronous.</span></span> <span data-ttu-id="99e2c-106">多くは、MSMQ API 呼び出し (たとえば、 **System.Messaging.MessageQueue.Send**)、要求された操作が完全に完了する前に、呼び出し元に戻ります。</span><span class="sxs-lookup"><span data-stu-id="99e2c-106">That is, many MSMQ API calls (for example, **System.Messaging.MessageQueue.Send**) return to the caller before the requested operation has fully completed.</span></span> <span data-ttu-id="99e2c-107">MSMQ には、操作完了後にアプリケーションにフィードバックを配信するメカニズムが用意されています。</span><span class="sxs-lookup"><span data-stu-id="99e2c-107">MSMQ provides a mechanism to deliver feedback to the application after the operation has completed.</span></span> <span data-ttu-id="99e2c-108">このメカニズムでは、"管理キュー" を使用します。</span><span class="sxs-lookup"><span data-stu-id="99e2c-108">This mechanism involves the use of an "Admin Queue."</span></span> <span data-ttu-id="99e2c-109">MSMQ は管理キューにメッセージ形式でフィードバックを返します。</span><span class="sxs-lookup"><span data-stu-id="99e2c-109">MSMQ returns feedback in the form of a message in the Admin Queue.</span></span> <span data-ttu-id="99e2c-110">MSMQ がフィードバックを返す管理キューは、元の MSMQ API 呼び出しが行われたときに指定されます。</span><span class="sxs-lookup"><span data-stu-id="99e2c-110">The Admin Queue to which MSMQ will return feedback is specified when the original MSMQ API call is made.</span></span> <span data-ttu-id="99e2c-111">したがって、たとえばを使用してメッセージを送信するときに、 **System.Messaging.MessageQueue.Send** API アプリケーションを指定できます管理キューの名前を使用して、 **PROPID_M_ADMIN_QUEUE** message プロパティ呼び出しで渡されるメッセージの**System.Messaging.MessageQueue.Send**です。</span><span class="sxs-lookup"><span data-stu-id="99e2c-111">So, for example, when sending a message using the **System.Messaging.MessageQueue.Send** API, the application can specify the name of an Admin Queue by using the **PROPID_M_ADMIN_QUEUE** message property on the message passed in the call to **System.Messaging.MessageQueue.Send**.</span></span> <span data-ttu-id="99e2c-112">アプリケーションは、成功した場合のリターン コードを取得する可能性がある場合でも、 **System.Messaging.MessageQueue.Send**呼び出し、メッセージ送信操作に、後で失敗した場合、MSMQ メッセージを書き込みますそれを指定の管理キューにします。</span><span class="sxs-lookup"><span data-stu-id="99e2c-112">Even though the application may get a successful return code on the **System.Messaging.MessageQueue.Send** call, if the message send operation subsequently fails, MSMQ writes a message to that effect to the specified Admin Queue.</span></span> <span data-ttu-id="99e2c-113">メッセージが消失と診断がキャプチャされません、送信エラーの結果、アプリケーションでは、管理キューを指定しない場合、実際には、メッセージは証拠も残らない表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="99e2c-113">If the application does not specify an Admin Queue, the send failure results in the message being lost and no diagnostics captured — in effect, the message disappears without any evidence.</span></span> <span data-ttu-id="99e2c-114">いくつかのエラーの原因となるこれが発生するなどの非トランザクションを実行する MSMQ のような状況が、トランザクション キューに送信します。</span><span class="sxs-lookup"><span data-stu-id="99e2c-114">There are a number of error situations in MSMQ that can cause this to happen, for example, doing a non-transactional send to a transactional queue.</span></span>  
  
 <span data-ttu-id="99e2c-115">このサンプルのコンテキストでは、コードが呼び出しでは、トランザクションの種類を指定することが重要**System.Messaging.MessageQueue.Send**メッセージをキューに指定されたトランザクションのサポートと一貫性があります。送信されます。</span><span class="sxs-lookup"><span data-stu-id="99e2c-115">In the context of this sample, it is important that the code specify a transaction type in the call to **System.Messaging.MessageQueue.Send** that is consistent with the transaction support specified for the queue to which the message is sent.</span></span> <span data-ttu-id="99e2c-116">この処理が行われない場合や、(このサンプルのように) 管理キューが指定されていない場合、MSMQ は何の通知もなく送信メッセージを破棄します (つまり、アプリケーションにエラー コードが返されたり、イベント ログに診断が書き込まれたりすることはありません)。</span><span class="sxs-lookup"><span data-stu-id="99e2c-116">If this is not done and if no Admin Queue is specified (as is the case in this sample), then MSMQ discards the sent message with no indication that it has done so (that is, no error code returned to the application, no diagnostics written to the event log, and so on).</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="99e2c-117">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="99e2c-117">Where to Find This Sample</span></span>  
 <span data-ttu-id="99e2c-118">\<サンプル パス > \AdaptersUsage\SendMSMQMessage\\</span><span class="sxs-lookup"><span data-stu-id="99e2c-118">\<Samples Path>\AdaptersUsage\SendMSMQMessage\\</span></span>  
  
 <span data-ttu-id="99e2c-119">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="99e2c-119">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="99e2c-120">[ファイル]</span><span class="sxs-lookup"><span data-stu-id="99e2c-120">Files</span></span>|<span data-ttu-id="99e2c-121">Description</span><span class="sxs-lookup"><span data-stu-id="99e2c-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="99e2c-122">App.ico、AssemblyInfo.cs、SendMSMQMessage.csproj、SendMSMQMessage.sln</span><span class="sxs-lookup"><span data-stu-id="99e2c-122">App.ico, AssemblyInfo.cs, SendMSMQMessage.csproj, SendMSMQMessage.sln</span></span>|<span data-ttu-id="99e2c-123">プロジェクト、ソリューション、および関連するファイルのこのサンプルの簡単なグラフィカル アプリケーションを提供します。</span><span class="sxs-lookup"><span data-stu-id="99e2c-123">Provide project, solution, and related files for the simple graphical application for this sample.</span></span>|  
|<span data-ttu-id="99e2c-124">Form1.cs、Form1.resx</span><span class="sxs-lookup"><span data-stu-id="99e2c-124">Form1.cs, Form1.resx</span></span>|<span data-ttu-id="99e2c-125">このサンプル用の簡単なグラフィカル アプリケーションの Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)].NET ソース ファイルおよびフォーム ファイルを提供します。</span><span class="sxs-lookup"><span data-stu-id="99e2c-125">Provide Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)].NET source and form files for the simple graphical application for this sample.</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="99e2c-126">このサンプルの使用方法</span><span class="sxs-lookup"><span data-stu-id="99e2c-126">How to Use This Sample</span></span>  
 <span data-ttu-id="99e2c-127">このサンプルに含まれている簡単なグラフィカル アプリケーションのコードは、Microsoft Office などの .NET 対応のアプリケーションや ASP.NET ページなどから [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 内の MSMQ 受信場所へメッセージを送信する方法の例として使用できます。</span><span class="sxs-lookup"><span data-stu-id="99e2c-127">You can use the code in the simple graphical application included with this sample as an example of how to send messages to MSMQ receive locations within [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] from .NET-enabled applications such as Microsoft Office, from ASP.NET pages, and so on.</span></span>  
  
## <a name="building-and-initializing-the-sample"></a><span data-ttu-id="99e2c-128">サンプルのビルドおよび初期化</span><span class="sxs-lookup"><span data-stu-id="99e2c-128">Building and Initializing the Sample</span></span>  
  
#### <a name="to-build-the-sample-executable"></a><span data-ttu-id="99e2c-129">実行可能サンプル ファイルをビルドするには</span><span class="sxs-lookup"><span data-stu-id="99e2c-129">To build the sample executable</span></span>  
  
1.  <span data-ttu-id="99e2c-130">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を使用して、ソリューション ファイル SendMSMQMessage.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="99e2c-130">Using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution file SendMSMQMessage.sln.</span></span>  
  
2.  <span data-ttu-id="99e2c-131">**[ビルド]** メニューの **[ソリューションのビルド]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="99e2c-131">On the **Build** menu, click **Build Solution**.</span></span>  
  
## <a name="configuring-biztalk-server-and-creating-the-msmq-queue"></a><span data-ttu-id="99e2c-132">BizTalk Server の構成と MSMQ キューの作成</span><span class="sxs-lookup"><span data-stu-id="99e2c-132">Configuring BizTalk Server and Creating the MSMQ Queue</span></span>  
 <span data-ttu-id="99e2c-133">次の手順を使用して [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成し、サンプルを実行するための MSMQ キューを作成します。</span><span class="sxs-lookup"><span data-stu-id="99e2c-133">Use the following procedures to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and create the MSMQ queue for running the sample.</span></span>  
  
#### <a name="to-create-the-msmq-queue-in-windows-server-2008-r2-or-windows-server-2008-sp2"></a><span data-ttu-id="99e2c-134">Windows Server 2008 R2 または Windows Server 2008 SP2 で MSMQ キューを作成するには</span><span class="sxs-lookup"><span data-stu-id="99e2c-134">To create the MSMQ queue in Windows Server 2008 R2 or Windows Server 2008 SP2</span></span>  
  
1.  <span data-ttu-id="99e2c-135">をクリックして**開始**を右クリックして**コンピューター**、順にクリック**管理**です。</span><span class="sxs-lookup"><span data-stu-id="99e2c-135">Click **Start**, right-click **Computer**, and then click **Manage**.</span></span>  
  
2.  <span data-ttu-id="99e2c-136">展開して、**機能**ノード。</span><span class="sxs-lookup"><span data-stu-id="99e2c-136">Expand the **Features** node.</span></span>  <span data-ttu-id="99e2c-137">場合**メッセージ キュー**がインストールされていないを右クリックして**機能**選択**機能の追加**です。</span><span class="sxs-lookup"><span data-stu-id="99e2c-137">If **Message Queuing** is not installed, right-click **Features** and select **Add Features**.</span></span>  <span data-ttu-id="99e2c-138">確認**メッセージ キュー**、 をクリックして**次へ**、順にクリック**インストール**そのシステムで MSMQ をインストールします。</span><span class="sxs-lookup"><span data-stu-id="99e2c-138">Check **Message Queuing**, click **Next**, and then click **Install** to install MSMQ on that system.</span></span>  
  
3.  <span data-ttu-id="99e2c-139">展開して、**メッセージ キュー**ノード。</span><span class="sxs-lookup"><span data-stu-id="99e2c-139">Expand the **Message Queuing** node.</span></span>  
  
4.  <span data-ttu-id="99e2c-140">右クリックし、**専用キュー**ノード、をクリックして**新規**、順にクリック**プライベート キュー**です。</span><span class="sxs-lookup"><span data-stu-id="99e2c-140">Right-click the **Private Queues** node, click **New**, and then click **Private Queue**.</span></span>  
  
5.  <span data-ttu-id="99e2c-141">**キュー名**、入力`test`です。</span><span class="sxs-lookup"><span data-stu-id="99e2c-141">Under **Queue name**, enter `test`.</span></span> <span data-ttu-id="99e2c-142">いることを確認、**トランザクション** チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="99e2c-142">Ensure that the **Transactional** check box is selected.</span></span>  
  
6.  <span data-ttu-id="99e2c-143">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="99e2c-143">Click **OK**.</span></span>  
  
#### <a name="to-create-the-msmq-queue-in-windows-7-or-windows-vista-sp2"></a><span data-ttu-id="99e2c-144">Windows 7 または Windows Vista SP2 で MSMQ キューを作成するには</span><span class="sxs-lookup"><span data-stu-id="99e2c-144">To create the MSMQ queue in Windows 7 or Windows Vista SP2</span></span>  
  
1.  <span data-ttu-id="99e2c-145">をクリックして**開始**を右クリックして**コンピューター**、順にクリック**管理**です。</span><span class="sxs-lookup"><span data-stu-id="99e2c-145">Click **Start**, right-click **Computer**, and then click **Manage**.</span></span>  
  
2.  <span data-ttu-id="99e2c-146">展開**サービスとアプリケーション**の順に展開し、**メッセージ キュー**ノード。</span><span class="sxs-lookup"><span data-stu-id="99e2c-146">Expand **Services and Applications**, and then expand the **Message Queuing** node.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="99e2c-147">場合**メッセージ キュー**がコンピューターにインストールされていないに移動して**コントロール パネル] > プログラム > プログラムと機能**、し、[ **Windows の機能のオンまたはオフ**です。</span><span class="sxs-lookup"><span data-stu-id="99e2c-147">If **Message Queuing** is not installed in the computer, go to **Control Panel > Programs > Programs and Features**, and then select **Turn Windows features on or off**.</span></span> <span data-ttu-id="99e2c-148">下のすべての機能を確認して**Microsoft メッセージ キュー (MSMQ) Server**、順にクリック**[ok]**です。</span><span class="sxs-lookup"><span data-stu-id="99e2c-148">Check all the features under **Microsoft Message Queue (MSMQ) Server**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="99e2c-149">右クリックし、**専用キュー**ノード、をクリックして**新規**、順にクリック**プライベート キュー**です。</span><span class="sxs-lookup"><span data-stu-id="99e2c-149">Right-click the **Private Queues** node, click **New**, and then click **Private Queue**.</span></span>  
  
4.  <span data-ttu-id="99e2c-150">**キュー名**、入力**テスト**です。</span><span class="sxs-lookup"><span data-stu-id="99e2c-150">Under **Queue name**, enter **test**.</span></span> <span data-ttu-id="99e2c-151">いることを確認、**トランザクション** チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="99e2c-151">Ensure that the **Transactional** check box is selected.</span></span>  
  
5.  <span data-ttu-id="99e2c-152">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="99e2c-152">Click **OK**.</span></span>  
  
#### <a name="to-configure-biztalk-server"></a><span data-ttu-id="99e2c-153">BizTalk Server を構成するには</span><span class="sxs-lookup"><span data-stu-id="99e2c-153">To configure BizTalk Server</span></span>  
  
1.  <span data-ttu-id="99e2c-154">メッセージを受信するフォルダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="99e2c-154">Select a folder in which to receive messages.</span></span> <span data-ttu-id="99e2c-155">次の手順には、C:\Demo\Report を選択しましたが、別のフォルダーに必要な手順を調整することがあるとします。</span><span class="sxs-lookup"><span data-stu-id="99e2c-155">The following steps assume that you have selected C:\Demo\Report, but you can adjust the steps as necessary for another folder.</span></span>  
  
2.  <span data-ttu-id="99e2c-156">開く、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="99e2c-156">Open the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
3.  <span data-ttu-id="99e2c-157">という新しいアプリケーションを作成**MSMQSample**です。</span><span class="sxs-lookup"><span data-stu-id="99e2c-157">Create a new application named **MSMQSample**.</span></span>  
  
4.  <span data-ttu-id="99e2c-158">右クリック**受信ポート**をクリックして**新規**、順にクリック**一方向の受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="99e2c-158">Right-click **Receive Ports**, click **New**, and then click **One-way Receive Port**.</span></span>  
  
5.  <span data-ttu-id="99e2c-159">**受信ポートのプロパティ** ダイアログ ボックスで、**名**ボックスに「 **MyReceivePort**、クリックしてして**ok**です。</span><span class="sxs-lookup"><span data-stu-id="99e2c-159">In the **Receive Port Properties** dialog box, in the **Name** box enter **MyReceivePort**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="99e2c-160">右クリック**受信場所**をクリックして**新規**、順にクリック**一方向の受信場所**です。</span><span class="sxs-lookup"><span data-stu-id="99e2c-160">Right-click **Receive Locations**, click **New**, and then click **One-way Receive Location**.</span></span> <span data-ttu-id="99e2c-161">**受信ポートの選択**ダイアログ ボックスで、選択した受信ポートが作成され、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="99e2c-161">In the **Select a Receive Port** dialog box, select the receive port you just created and click **OK**.</span></span>  
  
7.  <span data-ttu-id="99e2c-162">**受信場所のプロパティ** ダイアログ ボックスで、**名前**ボックスで、受信ポートの名前を入力します。 **MSMQReceiveLocation**です。</span><span class="sxs-lookup"><span data-stu-id="99e2c-162">In the **Receive Location Properties** dialog box, in the **Name** box, type a name for the receive port, such as **MSMQReceiveLocation**.</span></span>  
  
8.  <span data-ttu-id="99e2c-163">**受信場所のプロパティ**ダイアログ ボックスで、トランスポートの種類に対して、select **MSMQ**です。</span><span class="sxs-lookup"><span data-stu-id="99e2c-163">In the **Receive Location Properties** dialog box, for the transport type, select **MSMQ** .</span></span>  
  
9. <span data-ttu-id="99e2c-164">をクリックして**構成**を開くには、 **MSMQ トランスポートのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="99e2c-164">Click **Configure** to open the **MSMQ Transport Properties** dialog box.</span></span> <span data-ttu-id="99e2c-165">設定**キュー**に`localhost\private$\test`設定、**トランザクション**に`True`、順にクリック**[ok]**です。</span><span class="sxs-lookup"><span data-stu-id="99e2c-165">Set **Queue** to `localhost\private$\test`, set **Transactional** to `True`, and then click **OK**.</span></span>  
  
10. <span data-ttu-id="99e2c-166">アプリケーションを展開し、選択**送信ポート**を選択**新規****静的な一方向送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="99e2c-166">Expand the application, select **Send Ports**, select **New**, select **Static One-way Send Port**.</span></span>  
  
11. <span data-ttu-id="99e2c-167">**送信ポートのプロパティ** ダイアログ ボックスで、**名前**ボックスで、送信ポートの名前を入力します。 **MySendPort**です。</span><span class="sxs-lookup"><span data-stu-id="99e2c-167">In the **Send Port Properties** dialog box, in the **Name** box, type a name for the send port, such as **MySendPort**.</span></span>  
  
12. <span data-ttu-id="99e2c-168">設定、**トランスポートの種類**プロパティを**ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="99e2c-168">Set the **Transport Type** property to **FILE**.</span></span>  
  
13. <span data-ttu-id="99e2c-169">をクリックして**構成**を開くには、 **File トランスポートのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="99e2c-169">Click **Configure** to open the **File Transport Properties** dialog box.</span></span>  
  
14. <span data-ttu-id="99e2c-170">**FILE トランスポートのプロパティ**ダイアログ ボックスで、設定、**コピー先フォルダー**プロパティを**C:\Demo\Report**、他のプロパティの既定の設定を保持し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="99e2c-170">In the **FILE Transport Properties** dialog box, set the **Destination Folder** property to **C:\Demo\Report**, keep the default settings for the other properties, and then click **OK**.</span></span>  
  
15. <span data-ttu-id="99e2c-171">選択**フィルター**、設定して、新しい行を追加および**プロパティ**に**BTS です。ReceivePortName**です。</span><span class="sxs-lookup"><span data-stu-id="99e2c-171">Select **Filters**, and then add a new row by setting **Property** to **BTS.ReceivePortName**.</span></span> <span data-ttu-id="99e2c-172">ままにして、**演算子**列に設定 **==** 、設定、**値**列**MyReceivePort**をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="99e2c-172">Leave the **Operator** column set to **==**, set the **Value** column to **MyReceivePort**, and then click **OK**.</span></span>  
  
16. <span data-ttu-id="99e2c-173">右クリックし、新しい送信ポートを順にクリックして**Enlist**です。</span><span class="sxs-lookup"><span data-stu-id="99e2c-173">Right-click your new send port, and then click **Enlist**.</span></span>  
  
17. <span data-ttu-id="99e2c-174">右クリックし、新しい送信ポートをもう一度、をクリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="99e2c-174">Right-click your new send port again, and then click **Start**.</span></span>  
  
18. <span data-ttu-id="99e2c-175">右クリックし、新しい受信場所、をクリックして**を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="99e2c-175">Right-click your new receive location, and then click **Enable**.</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="99e2c-176">このサンプルを使用する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="99e2c-176"> is now ready to work with this sample.</span></span>  
  
## <a name="running-the-sample"></a><span data-ttu-id="99e2c-177">サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="99e2c-177">Running the Sample</span></span>  
 <span data-ttu-id="99e2c-178">次の手順を使用して、SendMSMQMessage サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="99e2c-178">Use the following procedure to run the SendMSMQMessage sample.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="99e2c-179">サンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="99e2c-179">To run the sample</span></span>  
  
1.  <span data-ttu-id="99e2c-180">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="99e2c-180">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="99e2c-181">\<サンプル パス > \AdaptersUsage\SendMSMQMessage\bin\Debug</span><span class="sxs-lookup"><span data-stu-id="99e2c-181">\<Samples Path>\AdaptersUsage\SendMSMQMessage\bin\Debug</span></span>  
  
2.  <span data-ttu-id="99e2c-182">SendMSMQMessage.exe ファイルを実行すると、このサンプルのユーザー インターフェイスを提供するグラフィカル アプリケーションが起動します。</span><span class="sxs-lookup"><span data-stu-id="99e2c-182">Run the file SendMSMQMessage.exe, which starts the graphical application that provides the user interface for this sample.</span></span>  
  
3.  <span data-ttu-id="99e2c-183">グラフィカル アプリケーションでの**BizTalk machine name**ボックスに、ローカル コンピューターの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="99e2c-183">In the graphical application, in the **BizTalk machine name** box, type the name of the local computer.</span></span>  
  
4.  <span data-ttu-id="99e2c-184">再試行、 **Send Wrapped**オプション。</span><span class="sxs-lookup"><span data-stu-id="99e2c-184">Try the **Send Wrapped** option:</span></span>  
  
    1.  <span data-ttu-id="99e2c-185">必要に応じて内のテキストを変更、**メッセージ本文**ボックス。</span><span class="sxs-lookup"><span data-stu-id="99e2c-185">Optionally change the text in the **Message body** box.</span></span>  
  
    2.  <span data-ttu-id="99e2c-186">をクリックして**ラップされた送信**です。</span><span class="sxs-lookup"><span data-stu-id="99e2c-186">Click **Send wrapped**.</span></span>  
  
     <span data-ttu-id="99e2c-187">操作が成功すると、次の操作が表示されます。</span><span class="sxs-lookup"><span data-stu-id="99e2c-187">If the operation succeeds, you will see the following:</span></span>  
  
    -   <span data-ttu-id="99e2c-188">単語**成功**ボタンのすぐ上のボックスに赤いフォントで表示されます。</span><span class="sxs-lookup"><span data-stu-id="99e2c-188">The word **Success** appears in red font in the box immediately above the buttons.</span></span>  
  
    -   <span data-ttu-id="99e2c-189">送信先フォルダー C:\Demo\Reports にファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="99e2c-189">A file appears in your destination folder, C:\Demo\Reports.</span></span> <span data-ttu-id="99e2c-190">このファイルにはからテキストが含まれています、**メッセージ本文**ボックス .NET メッセージ キュー ライブラリでの単純な XML タグにラップします。</span><span class="sxs-lookup"><span data-stu-id="99e2c-190">This file contains the text from the **Message body** box wrapped in simple XML tags by the .NET message queuing library.</span></span>  
  
     <span data-ttu-id="99e2c-191">操作に失敗すると、ボタンのすぐ上のボックスにエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="99e2c-191">If the operation fails, you will see an error message in the box immediately above the buttons.</span></span>  
  
5.  <span data-ttu-id="99e2c-192">再試行、 **Send Exact**オプション。</span><span class="sxs-lookup"><span data-stu-id="99e2c-192">Try the **Send Exact** option:</span></span>  
  
    1.  <span data-ttu-id="99e2c-193">必要に応じて内のテキストを変更、**メッセージ本文**ボックス。</span><span class="sxs-lookup"><span data-stu-id="99e2c-193">Optionally change the text in the **Message body** box.</span></span>  
  
    2.  <span data-ttu-id="99e2c-194">をクリックして**Send exact**です。</span><span class="sxs-lookup"><span data-stu-id="99e2c-194">Click **Send exact**.</span></span>  
  
     <span data-ttu-id="99e2c-195">操作が成功すると、次の操作が表示されます。</span><span class="sxs-lookup"><span data-stu-id="99e2c-195">If the operation succeeds, you will see the following:</span></span>  
  
    -   <span data-ttu-id="99e2c-196">単語**成功**ボタンのすぐ上のボックスに赤いフォントで表示されます。</span><span class="sxs-lookup"><span data-stu-id="99e2c-196">The word **Success** appears in red font in the box immediately above the buttons.</span></span>  
  
    -   <span data-ttu-id="99e2c-197">送信先フォルダー C:\Demo\Reports にファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="99e2c-197">A file appears in your destination folder, C:\Demo\Reports.</span></span> <span data-ttu-id="99e2c-198">このファイルにはからテキストが含まれています、**メッセージ本文**ボックス、テキスト ボックスに表示されているとおりです。</span><span class="sxs-lookup"><span data-stu-id="99e2c-198">This file contains the text from the **Message body** box exactly as it appears in the text box.</span></span>  
  
     <span data-ttu-id="99e2c-199">操作に失敗すると、ボタンのすぐ上のボックスにエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="99e2c-199">If the operation fails, you will see an error message in the box immediately above the buttons.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99e2c-200">参照</span><span class="sxs-lookup"><span data-stu-id="99e2c-200">See Also</span></span>  
 [<span data-ttu-id="99e2c-201">アダプタ サンプル – 使用状況</span><span class="sxs-lookup"><span data-stu-id="99e2c-201">Adapter Samples - Usage</span></span>](../core/adapter-samples-usage.md)