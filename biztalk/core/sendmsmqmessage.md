---
title: SendMSMQMessage |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, examples
- examples, MSMQ adapters
ms.assetid: 398bc396-0c66-4d55-886a-0d9bdab6476f
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27c6a0f6b9e35b68fccd38d62fe7e1ae86f4f6ad
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024496"
---
# <a name="sendmsmqmessage"></a><span data-ttu-id="8370f-102">SendMSMQMessage</span><span class="sxs-lookup"><span data-stu-id="8370f-102">SendMSMQMessage</span></span>
<span data-ttu-id="8370f-103">SendMSMQMessage サンプルは、.NET ベースのアプリケーションから MSMQ ポートにメッセージを送信する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8370f-103">The SendMSMQMessage sample demonstrates how to send a message to an MSMQ port from a .NET-based application.</span></span> <span data-ttu-id="8370f-104">Microsoft を構成する方法についても用意されています。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MSMQ 受信場所を使用します。</span><span class="sxs-lookup"><span data-stu-id="8370f-104">It also provides instructions about how to configure Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to use an MSMQ receive location.</span></span>  

 <span data-ttu-id="8370f-105">メッセージ キューの多くの操作が非同期であることに注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="8370f-105">You should be aware that many operations in Message Queuing are asynchronous.</span></span> <span data-ttu-id="8370f-106">多くは、MSMQ API 呼び出し (たとえば、 **System.Messaging.MessageQueue.Send**)、要求された操作が完全に完了する前に、呼び出し元に戻ります。</span><span class="sxs-lookup"><span data-stu-id="8370f-106">That is, many MSMQ API calls (for example, **System.Messaging.MessageQueue.Send**) return to the caller before the requested operation has fully completed.</span></span> <span data-ttu-id="8370f-107">MSMQ には、操作完了後にアプリケーションにフィードバックを配信するメカニズムが用意されています。</span><span class="sxs-lookup"><span data-stu-id="8370f-107">MSMQ provides a mechanism to deliver feedback to the application after the operation has completed.</span></span> <span data-ttu-id="8370f-108">このメカニズムでは、"管理キュー" を使用します。</span><span class="sxs-lookup"><span data-stu-id="8370f-108">This mechanism involves the use of an "Admin Queue."</span></span> <span data-ttu-id="8370f-109">MSMQ は管理キューにメッセージ形式でフィードバックを返します。</span><span class="sxs-lookup"><span data-stu-id="8370f-109">MSMQ returns feedback in the form of a message in the Admin Queue.</span></span> <span data-ttu-id="8370f-110">MSMQ がフィードバックを返す管理キューは、元の MSMQ API 呼び出しが行われたときに指定されます。</span><span class="sxs-lookup"><span data-stu-id="8370f-110">The Admin Queue to which MSMQ will return feedback is specified when the original MSMQ API call is made.</span></span> <span data-ttu-id="8370f-111">そのため、たとえばを使用してメッセージを送信するときに、 **System.Messaging.MessageQueue.Send** API、アプリケーションを指定できます管理キューの名前を使用して、 **PROPID_M_ADMIN_QUEUE**メッセージ プロパティ呼び出しで渡されるメッセージの**System.Messaging.MessageQueue.Send**します。</span><span class="sxs-lookup"><span data-stu-id="8370f-111">So, for example, when sending a message using the **System.Messaging.MessageQueue.Send** API, the application can specify the name of an Admin Queue by using the **PROPID_M_ADMIN_QUEUE** message property on the message passed in the call to **System.Messaging.MessageQueue.Send**.</span></span> <span data-ttu-id="8370f-112">アプリケーションの成功を示すリターン コードが取得場合でも、 **System.Messaging.MessageQueue.Send**呼び出し、メッセージの送信操作後で失敗した場合、MSMQ メッセージを書き込みますそれに対応する指定の管理キューにします。</span><span class="sxs-lookup"><span data-stu-id="8370f-112">Even though the application may get a successful return code on the **System.Messaging.MessageQueue.Send** call, if the message send operation subsequently fails, MSMQ writes a message to that effect to the specified Admin Queue.</span></span> <span data-ttu-id="8370f-113">送信エラーによりメッセージが消失と診断がキャプチャされません、アプリケーションが管理キューを指定しない場合、実際には、メッセージは証拠も残らない表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="8370f-113">If the application does not specify an Admin Queue, the send failure results in the message being lost and no diagnostics captured — in effect, the message disappears without any evidence.</span></span> <span data-ttu-id="8370f-114">エラーの可能性がある、この例では、非トランザクションを行うための MSMQ の場合は、トランザクション キューに送信を数多くあります。</span><span class="sxs-lookup"><span data-stu-id="8370f-114">There are a number of error situations in MSMQ that can cause this to happen, for example, doing a non-transactional send to a transactional queue.</span></span>  

 <span data-ttu-id="8370f-115">このサンプルのコンテキストでは、コードが呼び出しでトランザクションの種類を指定することが重要**System.Messaging.MessageQueue.Send**メッセージをキューに指定されたトランザクションのサポートと一貫性があります。送信されます。</span><span class="sxs-lookup"><span data-stu-id="8370f-115">In the context of this sample, it is important that the code specify a transaction type in the call to **System.Messaging.MessageQueue.Send** that is consistent with the transaction support specified for the queue to which the message is sent.</span></span> <span data-ttu-id="8370f-116">この処理が行われない場合や、(このサンプルのように) 管理キューが指定されていない場合、MSMQ は何の通知もなく送信メッセージを破棄します (つまり、アプリケーションにエラー コードが返されたり、イベント ログに診断が書き込まれたりすることはありません)。</span><span class="sxs-lookup"><span data-stu-id="8370f-116">If this is not done and if no Admin Queue is specified (as is the case in this sample), then MSMQ discards the sent message with no indication that it has done so (that is, no error code returned to the application, no diagnostics written to the event log, and so on).</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="8370f-117">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="8370f-117">Where to Find This Sample</span></span>  
 <span data-ttu-id="8370f-118">\<パスのサンプル\>\AdaptersUsage\SendMSMQMessage\\</span><span class="sxs-lookup"><span data-stu-id="8370f-118">\<Samples Path\>\AdaptersUsage\SendMSMQMessage\\</span></span>  

 <span data-ttu-id="8370f-119">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="8370f-119">The following table shows the files in this sample and describes their purpose.</span></span>  


|                                 <span data-ttu-id="8370f-120">[ファイル]</span><span class="sxs-lookup"><span data-stu-id="8370f-120">Files</span></span>                                 |                                                                      <span data-ttu-id="8370f-121">説明</span><span class="sxs-lookup"><span data-stu-id="8370f-121">Description</span></span>                                                                       |
|-----------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="8370f-122">App.ico、AssemblyInfo.cs、SendMSMQMessage.csproj、SendMSMQMessage.sln</span><span class="sxs-lookup"><span data-stu-id="8370f-122">App.ico, AssemblyInfo.cs, SendMSMQMessage.csproj, SendMSMQMessage.sln</span></span> |                           <span data-ttu-id="8370f-123">プロジェクト、ソリューション、およびこのサンプルの簡単なグラフィカル アプリケーションの他の関連ファイルを提供します。</span><span class="sxs-lookup"><span data-stu-id="8370f-123">Provide project, solution, and related files for the simple graphical application for this sample.</span></span>                           |
|                         <span data-ttu-id="8370f-124">Form1.cs、Form1.resx</span><span class="sxs-lookup"><span data-stu-id="8370f-124">Form1.cs, Form1.resx</span></span>                          | <span data-ttu-id="8370f-125">このサンプル用の簡単なグラフィカル アプリケーションの Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)].NET ソース ファイルおよびフォーム ファイルを提供します。</span><span class="sxs-lookup"><span data-stu-id="8370f-125">Provide Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)].NET source and form files for the simple graphical application for this sample.</span></span> |

## <a name="how-to-use-this-sample"></a><span data-ttu-id="8370f-126">このサンプルの使用方法</span><span class="sxs-lookup"><span data-stu-id="8370f-126">How to Use This Sample</span></span>  
 <span data-ttu-id="8370f-127">このサンプルに含まれている簡単なグラフィカル アプリケーションのコードは、Microsoft Office などの .NET 対応のアプリケーションや ASP.NET ページなどから [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 内の MSMQ 受信場所へメッセージを送信する方法の例として使用できます。</span><span class="sxs-lookup"><span data-stu-id="8370f-127">You can use the code in the simple graphical application included with this sample as an example of how to send messages to MSMQ receive locations within [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] from .NET-enabled applications such as Microsoft Office, from ASP.NET pages, and so on.</span></span>  

## <a name="building-and-initializing-the-sample"></a><span data-ttu-id="8370f-128">サンプルのビルドおよび初期化</span><span class="sxs-lookup"><span data-stu-id="8370f-128">Building and Initializing the Sample</span></span>  

#### <a name="to-build-the-sample-executable"></a><span data-ttu-id="8370f-129">実行可能サンプル ファイルをビルドするには</span><span class="sxs-lookup"><span data-stu-id="8370f-129">To build the sample executable</span></span>  

1. <span data-ttu-id="8370f-130">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を使用して、ソリューション ファイル SendMSMQMessage.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="8370f-130">Using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution file SendMSMQMessage.sln.</span></span>  

2. <span data-ttu-id="8370f-131">**[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8370f-131">On the **Build** menu, click **Build Solution**.</span></span>  

## <a name="configuring-biztalk-server-and-creating-the-msmq-queue"></a><span data-ttu-id="8370f-132">BizTalk Server の構成と MSMQ キューの作成</span><span class="sxs-lookup"><span data-stu-id="8370f-132">Configuring BizTalk Server and Creating the MSMQ Queue</span></span>  
 <span data-ttu-id="8370f-133">次の手順を使用して [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成し、サンプルを実行するための MSMQ キューを作成します。</span><span class="sxs-lookup"><span data-stu-id="8370f-133">Use the following procedures to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and create the MSMQ queue for running the sample.</span></span>  

#### <a name="to-create-the-msmq-queue-in-windows-server-2008-r2-or-windows-server-2008-sp2"></a><span data-ttu-id="8370f-134">Windows Server 2008 R2 または Windows Server 2008 SP2 で MSMQ キューを作成するには</span><span class="sxs-lookup"><span data-stu-id="8370f-134">To create the MSMQ queue in Windows Server 2008 R2 or Windows Server 2008 SP2</span></span>  

1.  <span data-ttu-id="8370f-135">クリックして**開始**を右クリックして**コンピューター**、順にクリックします**管理**します。</span><span class="sxs-lookup"><span data-stu-id="8370f-135">Click **Start**, right-click **Computer**, and then click **Manage**.</span></span>  

2.  <span data-ttu-id="8370f-136">展開、**機能**ノード。</span><span class="sxs-lookup"><span data-stu-id="8370f-136">Expand the **Features** node.</span></span>  <span data-ttu-id="8370f-137">場合**メッセージ キュー**は右クリックしてインストールされていない**機能**選択**機能の追加**。</span><span class="sxs-lookup"><span data-stu-id="8370f-137">If **Message Queuing** is not installed, right-click **Features** and select **Add Features**.</span></span>  <span data-ttu-id="8370f-138">確認**メッセージ キュー**、 をクリックして**次**、順にクリックします**インストール**そのシステムで MSMQ をインストールします。</span><span class="sxs-lookup"><span data-stu-id="8370f-138">Check **Message Queuing**, click **Next**, and then click **Install** to install MSMQ on that system.</span></span>  

3.  <span data-ttu-id="8370f-139">展開、**メッセージ キュー**ノード。</span><span class="sxs-lookup"><span data-stu-id="8370f-139">Expand the **Message Queuing** node.</span></span>  

4.  <span data-ttu-id="8370f-140">右クリックし、**専用キュー**ノード、をクリックして**新規**、順にクリックします**プライベート キュー**します。</span><span class="sxs-lookup"><span data-stu-id="8370f-140">Right-click the **Private Queues** node, click **New**, and then click **Private Queue**.</span></span>  

5.  <span data-ttu-id="8370f-141">**キュー名**、入力`test`します。</span><span class="sxs-lookup"><span data-stu-id="8370f-141">Under **Queue name**, enter `test`.</span></span> <span data-ttu-id="8370f-142">いることを確認、**トランザクション** チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="8370f-142">Ensure that the **Transactional** check box is selected.</span></span>  

6.  <span data-ttu-id="8370f-143">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8370f-143">Click **OK**.</span></span>  

#### <a name="to-create-the-msmq-queue-in-windows-7-or-windows-vista-sp2"></a><span data-ttu-id="8370f-144">Windows 7 または Windows Vista SP2 で MSMQ キューを作成するには</span><span class="sxs-lookup"><span data-stu-id="8370f-144">To create the MSMQ queue in Windows 7 or Windows Vista SP2</span></span>  

1.  <span data-ttu-id="8370f-145">クリックして**開始**を右クリックして**コンピューター**、順にクリックします**管理**します。</span><span class="sxs-lookup"><span data-stu-id="8370f-145">Click **Start**, right-click **Computer**, and then click **Manage**.</span></span>  

2.  <span data-ttu-id="8370f-146">展開**サービスとアプリケーション**の順に展開し、**メッセージ キュー**ノード。</span><span class="sxs-lookup"><span data-stu-id="8370f-146">Expand **Services and Applications**, and then expand the **Message Queuing** node.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="8370f-147">場合**メッセージ キュー** 、コンピューターにインストールされていないに移動して**コントロール パネル > プログラム > プログラムと機能**、し、**オンまたはオフにする Windows 機能**します。</span><span class="sxs-lookup"><span data-stu-id="8370f-147">If **Message Queuing** is not installed in the computer, go to **Control Panel > Programs > Programs and Features**, and then select **Turn Windows features on or off**.</span></span> <span data-ttu-id="8370f-148">すべての機能を確認**Microsoft メッセージ キュー (MSMQ) Server**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="8370f-148">Check all the features under **Microsoft Message Queue (MSMQ) Server**, and then click **OK**.</span></span>  

3.  <span data-ttu-id="8370f-149">右クリックし、**専用キュー**ノード、をクリックして**新規**、順にクリックします**プライベート キュー**します。</span><span class="sxs-lookup"><span data-stu-id="8370f-149">Right-click the **Private Queues** node, click **New**, and then click **Private Queue**.</span></span>  

4.  <span data-ttu-id="8370f-150">**キュー名**、入力**テスト**します。</span><span class="sxs-lookup"><span data-stu-id="8370f-150">Under **Queue name**, enter **test**.</span></span> <span data-ttu-id="8370f-151">いることを確認、**トランザクション** チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="8370f-151">Ensure that the **Transactional** check box is selected.</span></span>  

5.  <span data-ttu-id="8370f-152">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8370f-152">Click **OK**.</span></span>  

#### <a name="to-configure-biztalk-server"></a><span data-ttu-id="8370f-153">BizTalk Server を構成するには</span><span class="sxs-lookup"><span data-stu-id="8370f-153">To configure BizTalk Server</span></span>  

1. <span data-ttu-id="8370f-154">メッセージを受信するフォルダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="8370f-154">Select a folder in which to receive messages.</span></span> <span data-ttu-id="8370f-155">次の手順は、C:\Demo\Report を選択したが、別のフォルダーに必要な手順を調整することを想定しています。</span><span class="sxs-lookup"><span data-stu-id="8370f-155">The following steps assume that you have selected C:\Demo\Report, but you can adjust the steps as necessary for another folder.</span></span>  

2. <span data-ttu-id="8370f-156">開く、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="8370f-156">Open the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

3. <span data-ttu-id="8370f-157">という名前の新しいアプリケーションを作成する**MSMQSample**します。</span><span class="sxs-lookup"><span data-stu-id="8370f-157">Create a new application named **MSMQSample**.</span></span>  

4. <span data-ttu-id="8370f-158">右クリック**受信ポート**、 をクリックして**新規**、 をクリックし、**一方向の受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="8370f-158">Right-click **Receive Ports**, click **New**, and then click **One-way Receive Port**.</span></span>  

5. <span data-ttu-id="8370f-159">**受信ポートのプロパティ** ダイアログ ボックスで、**名前**ボックスの入力**MyReceivePort**、順にクリックします**ok**します。</span><span class="sxs-lookup"><span data-stu-id="8370f-159">In the **Receive Port Properties** dialog box, in the **Name** box enter **MyReceivePort**, and then click **OK**.</span></span>  

6. <span data-ttu-id="8370f-160">右クリック**受信場所**、 をクリックして**新規**、 をクリックし、**一方向の受信場所**します。</span><span class="sxs-lookup"><span data-stu-id="8370f-160">Right-click **Receive Locations**, click **New**, and then click **One-way Receive Location**.</span></span> <span data-ttu-id="8370f-161">**受信ポートの選択**ダイアログ ボックスで、選択した受信ポートが作成され、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="8370f-161">In the **Select a Receive Port** dialog box, select the receive port you just created and click **OK**.</span></span>  

7. <span data-ttu-id="8370f-162">**受信場所のプロパティ** ダイアログ ボックスで、**名前**ボックスに、受信ポートの名前を入力します。 **MSMQReceiveLocation**します。</span><span class="sxs-lookup"><span data-stu-id="8370f-162">In the **Receive Location Properties** dialog box, in the **Name** box, type a name for the receive port, such as **MSMQReceiveLocation**.</span></span>  

8. <span data-ttu-id="8370f-163">**受信場所のプロパティ** ダイアログ ボックスで、トランスポートの種類を選択します**MSMQ**します。</span><span class="sxs-lookup"><span data-stu-id="8370f-163">In the **Receive Location Properties** dialog box, for the transport type, select **MSMQ** .</span></span>  

9. <span data-ttu-id="8370f-164">クリックして**構成**を開く、 **MSMQ トランスポートのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="8370f-164">Click **Configure** to open the **MSMQ Transport Properties** dialog box.</span></span> <span data-ttu-id="8370f-165">設定**キュー**に`localhost\private$\test`に設定して、**トランザクション**に`True`、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="8370f-165">Set **Queue** to `localhost\private$\test`, set **Transactional** to `True`, and then click **OK**.</span></span>  

10. <span data-ttu-id="8370f-166">アプリケーションを展開し、選択**送信ポート**を選択します**新規**、**静的な一方向送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="8370f-166">Expand the application, select **Send Ports**, select **New**, select **Static One-way Send Port**.</span></span>  

11. <span data-ttu-id="8370f-167">**送信ポートのプロパティ** ダイアログ ボックスで、**名前**ボックスで、送信ポートの名前を入力します。 **MySendPort**します。</span><span class="sxs-lookup"><span data-stu-id="8370f-167">In the **Send Port Properties** dialog box, in the **Name** box, type a name for the send port, such as **MySendPort**.</span></span>  

12. <span data-ttu-id="8370f-168">設定、**トランスポートの種類**プロパティを**ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="8370f-168">Set the **Transport Type** property to **FILE**.</span></span>  

13. <span data-ttu-id="8370f-169">クリックして**構成**を開く、 **File トランスポートのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="8370f-169">Click **Configure** to open the **File Transport Properties** dialog box.</span></span>  

14. <span data-ttu-id="8370f-170">**FILE トランスポートのプロパティ**ダイアログ ボックスで、セット、**先フォルダー**プロパティを**C:\Demo\Report**、他のプロパティの既定の設定を保持し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="8370f-170">In the **FILE Transport Properties** dialog box, set the **Destination Folder** property to **C:\Demo\Report**, keep the default settings for the other properties, and then click **OK**.</span></span>  

15. <span data-ttu-id="8370f-171">選択**フィルター**、設定して新しい行を追加および**プロパティ**に**BTS します。ReceivePortName**します。</span><span class="sxs-lookup"><span data-stu-id="8370f-171">Select **Filters**, and then add a new row by setting **Property** to **BTS.ReceivePortName**.</span></span> <span data-ttu-id="8370f-172">ままに、**演算子**列に設定**==**、設定、**値**列を**MyReceivePort**をクリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="8370f-172">Leave the **Operator** column set to **==**, set the **Value** column to **MyReceivePort**, and then click **OK**.</span></span>  

16. <span data-ttu-id="8370f-173">右クリックし、新しい送信ポート をクリックし、**参加**します。</span><span class="sxs-lookup"><span data-stu-id="8370f-173">Right-click your new send port, and then click **Enlist**.</span></span>  

17. <span data-ttu-id="8370f-174">右クリックし、新しい送信ポートをもう一度 をクリックし、**開始**します。</span><span class="sxs-lookup"><span data-stu-id="8370f-174">Right-click your new send port again, and then click **Start**.</span></span>  

18. <span data-ttu-id="8370f-175">右クリックし、新しい受信場所 をクリックし、**を有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="8370f-175">Right-click your new receive location, and then click **Enable**.</span></span>  

    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="8370f-176"> このサンプルを使用する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="8370f-176"> is now ready to work with this sample.</span></span>  

## <a name="running-the-sample"></a><span data-ttu-id="8370f-177">サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="8370f-177">Running the Sample</span></span>  
 <span data-ttu-id="8370f-178">次の手順を使用して、SendMSMQMessage サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="8370f-178">Use the following procedure to run the SendMSMQMessage sample.</span></span>  

#### <a name="to-run-the-sample"></a><span data-ttu-id="8370f-179">サンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="8370f-179">To run the sample</span></span>  

1. <span data-ttu-id="8370f-180">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="8370f-180">In a command window, navigate to the following folder:</span></span>  

    <span data-ttu-id="8370f-181">\<パスのサンプル\>\AdaptersUsage\SendMSMQMessage\bin\Debug</span><span class="sxs-lookup"><span data-stu-id="8370f-181">\<Samples Path\>\AdaptersUsage\SendMSMQMessage\bin\Debug</span></span>  

2. <span data-ttu-id="8370f-182">SendMSMQMessage.exe ファイルを実行すると、このサンプルのユーザー インターフェイスを提供するグラフィカル アプリケーションが起動します。</span><span class="sxs-lookup"><span data-stu-id="8370f-182">Run the file SendMSMQMessage.exe, which starts the graphical application that provides the user interface for this sample.</span></span>  

3. <span data-ttu-id="8370f-183">グラフィカル アプリケーションでの**BizTalk コンピューター名**ボックスに、ローカル コンピューターの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="8370f-183">In the graphical application, in the **BizTalk machine name** box, type the name of the local computer.</span></span>  

4. <span data-ttu-id="8370f-184">お試しください、 **Send Wrapped**オプション。</span><span class="sxs-lookup"><span data-stu-id="8370f-184">Try the **Send Wrapped** option:</span></span>  

   1. <span data-ttu-id="8370f-185">内のテキストを変更する必要に応じて、**メッセージ本文**ボックス。</span><span class="sxs-lookup"><span data-stu-id="8370f-185">Optionally change the text in the **Message body** box.</span></span>  

   2. <span data-ttu-id="8370f-186">クリックして**ラップされた送信**します。</span><span class="sxs-lookup"><span data-stu-id="8370f-186">Click **Send wrapped**.</span></span>  

      <span data-ttu-id="8370f-187">操作が成功すると、次の操作が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8370f-187">If the operation succeeds, you will see the following:</span></span>  

   - <span data-ttu-id="8370f-188">単語**成功**ボタンのすぐ上のボックスに赤いフォントで表示されます。</span><span class="sxs-lookup"><span data-stu-id="8370f-188">The word **Success** appears in red font in the box immediately above the buttons.</span></span>  

   - <span data-ttu-id="8370f-189">送信先フォルダー C:\Demo\Reports にファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8370f-189">A file appears in your destination folder, C:\Demo\Reports.</span></span> <span data-ttu-id="8370f-190">このファイルにはからテキストが含まれています、**メッセージ本文**ボックス .NET メッセージ キュー ライブラリによって単純な XML タグにラップします。</span><span class="sxs-lookup"><span data-stu-id="8370f-190">This file contains the text from the **Message body** box wrapped in simple XML tags by the .NET message queuing library.</span></span>  

     <span data-ttu-id="8370f-191">操作に失敗すると、ボタンのすぐ上のボックスにエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8370f-191">If the operation fails, you will see an error message in the box immediately above the buttons.</span></span>  

5. <span data-ttu-id="8370f-192">お試しください、 **Send Exact**オプション。</span><span class="sxs-lookup"><span data-stu-id="8370f-192">Try the **Send Exact** option:</span></span>  

   1. <span data-ttu-id="8370f-193">内のテキストを変更する必要に応じて、**メッセージ本文**ボックス。</span><span class="sxs-lookup"><span data-stu-id="8370f-193">Optionally change the text in the **Message body** box.</span></span>  

   2. <span data-ttu-id="8370f-194">クリックして**Send exact**します。</span><span class="sxs-lookup"><span data-stu-id="8370f-194">Click **Send exact**.</span></span>  

      <span data-ttu-id="8370f-195">操作が成功すると、次の操作が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8370f-195">If the operation succeeds, you will see the following:</span></span>  

   - <span data-ttu-id="8370f-196">単語**成功**ボタンのすぐ上のボックスに赤いフォントで表示されます。</span><span class="sxs-lookup"><span data-stu-id="8370f-196">The word **Success** appears in red font in the box immediately above the buttons.</span></span>  

   - <span data-ttu-id="8370f-197">送信先フォルダー C:\Demo\Reports にファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8370f-197">A file appears in your destination folder, C:\Demo\Reports.</span></span> <span data-ttu-id="8370f-198">このファイルにはからテキストが含まれています、**メッセージ本文**ボックス、テキスト ボックスに表示されているとおりです。</span><span class="sxs-lookup"><span data-stu-id="8370f-198">This file contains the text from the **Message body** box exactly as it appears in the text box.</span></span>  

     <span data-ttu-id="8370f-199">操作に失敗すると、ボタンのすぐ上のボックスにエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8370f-199">If the operation fails, you will see an error message in the box immediately above the buttons.</span></span>  

## <a name="see-also"></a><span data-ttu-id="8370f-200">参照</span><span class="sxs-lookup"><span data-stu-id="8370f-200">See Also</span></span>  
 [<span data-ttu-id="8370f-201">アダプタ サンプル – 使用法</span><span class="sxs-lookup"><span data-stu-id="8370f-201">Adapter Samples - Usage</span></span>](../core/adapter-samples-usage.md)