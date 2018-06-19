---
title: サイズの大きいメッセージを MSMQ に |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1fb87b46-5656-42c0-be99-8ab66e51bb4d
caps.latest.revision: 35
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 008e6c2d775fc5d46977ca4672b6d3376349b3f0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25976112"
---
# <a name="large-message-to-msmq"></a><span data-ttu-id="76583-102">MSMQ にサイズの大きいメッセージ</span><span class="sxs-lookup"><span data-stu-id="76583-102">Large Message to MSMQ</span></span>
<span data-ttu-id="76583-103">MSMQ のサンプル サイズの大きいメッセージは、.xml ドキュメント 4 メガバイト (MB) よりも大きいメッセージ キュー (MSMQ とも呼ばれます) から BizTalk MSMQ アダプターを使用して送信する方法を示します、 **MQSendLargeMessage** API によって実装されていませんMQRTLarge.dll です。</span><span class="sxs-lookup"><span data-stu-id="76583-103">The Large Message to MSMQ sample demonstrates how to send an .xml document larger than 4 megabytes (MB) from Message Queuing (also known as MSMQ) to the BizTalk MSMQ adapter by using the **MQSendLargeMessage** API implemented by MQRTLarge.dll.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="76583-104">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="76583-104">What This Sample Does</span></span>  
 <span data-ttu-id="76583-105">このサンプルの動作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="76583-105">The sample works as follows:</span></span>  
  
1.  <span data-ttu-id="76583-106">ユーザーが SendLargeMessage.exe を使用して、サイズの大きい .xml ファイルをローカル コンピューター上のキューに送信します。</span><span class="sxs-lookup"><span data-stu-id="76583-106">A user uses SendLargeMessage.exe to send a large .xml file to a queue on a local computer.</span></span>  
  
2.  <span data-ttu-id="76583-107">BizTalk Server では、キューからサイズの大きい .xml ファイルを受信し、ローカル ディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="76583-107">BizTalk Server receives the large .xml file from the queue and copies it to a local directory.</span></span>  
  
 <span data-ttu-id="76583-108">メッセージ キューの多くの操作は非同期です。</span><span class="sxs-lookup"><span data-stu-id="76583-108">Many operations in Message Queuing are asynchronous.</span></span> <span data-ttu-id="76583-109">多くは、MSMQ API 呼び出し (たとえば、 **MQSendLargeMessage**)、要求された操作が完全に完了する前に、呼び出し元に戻ります。</span><span class="sxs-lookup"><span data-stu-id="76583-109">That is, many MSMQ API calls (for example, **MQSendLargeMessage**) return to the caller before the requested operation has fully completed.</span></span>  
  
 <span data-ttu-id="76583-110">MSMQ には、操作完了後にアプリケーションにフィードバックを配信するメカニズムが用意されています。</span><span class="sxs-lookup"><span data-stu-id="76583-110">MSMQ provides a mechanism to deliver feedback to the application after the operation has completed.</span></span> <span data-ttu-id="76583-111">このメカニズムでは、"管理キュー" を使用します。</span><span class="sxs-lookup"><span data-stu-id="76583-111">This mechanism involves the use of an "Admin Queue."</span></span> <span data-ttu-id="76583-112">MSMQ は管理キューにメッセージ形式でフィードバックを返します。</span><span class="sxs-lookup"><span data-stu-id="76583-112">MSMQ returns feedback in the form of a message in the Admin Queue.</span></span> <span data-ttu-id="76583-113">MSMQ がフィードバックを返す管理キューは、元の MSMQ API 呼び出しが行われたときに指定されます。</span><span class="sxs-lookup"><span data-stu-id="76583-113">The Admin Queue to which MSMQ will return feedback is specified when the original MSMQ API call is made.</span></span> <span data-ttu-id="76583-114">したがって、たとえばを使用してメッセージを送信するときに、 **MQSendLargeMessage** API アプリケーションを指定できます管理キューの名前を使用して、 **PROPID_M_ADMIN_QUEUE**メッセージのメッセージのプロパティ呼び出しで渡される**MQSendLargeMessage**です。</span><span class="sxs-lookup"><span data-stu-id="76583-114">So, for example, when sending a message using the **MQSendLargeMessage** API, the application can specify the name of an Admin Queue by using the **PROPID_M_ADMIN_QUEUE** message property on the message passed in the call to **MQSendLargeMessage**.</span></span> <span data-ttu-id="76583-115">アプリケーションは、成功した場合のリターン コードを取得する可能性がある場合でも、 **MQSendLargeMessage**呼び出し、メッセージ送信操作に、後で失敗した場合、MSMQ メッセージを書き込みますそれを指定の管理キューにします。</span><span class="sxs-lookup"><span data-stu-id="76583-115">Even though the application may get a successful return code on the **MQSendLargeMessage** call, if the message send operation subsequently fails, MSMQ writes a message to that effect to the specified Admin Queue.</span></span>  
  
 <span data-ttu-id="76583-116">メッセージが消失し、診断がキャプチャされませんで送信エラーの結果、アプリケーションでは、管理キューを指定しない場合、実際には、メッセージは証拠も残らない表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="76583-116">If the application does not specify an Admin Queue, a send failure results in the message being lost and no diagnostics captured — in effect, the message disappears without any evidence.</span></span> <span data-ttu-id="76583-117">MSMQ にはこの現象が発生するエラー状況が多数あります。たとえば、トランザクション キューにトランザクション以外の送信が行われる場合などです。</span><span class="sxs-lookup"><span data-stu-id="76583-117">A number of error situations in MSMQ can cause this to happen, for example, doing a non-transactional send to a transactional queue.</span></span>  
  
 <span data-ttu-id="76583-118">このサンプルのコンテキストでは、コードが呼び出しでは、トランザクションの種類を指定することが重要**MQSendLargeMessage**メッセージが送信キューの指定されたトランザクションのサポートと一貫性があるようにします。</span><span class="sxs-lookup"><span data-stu-id="76583-118">In the context of this sample, it is important that the code specify a transaction type in the call to **MQSendLargeMessage** that is consistent with the transaction support specified for the queue to which the message is sent.</span></span> <span data-ttu-id="76583-119">この処理が行われない場合や、(このサンプルのように) 管理キューが指定されていない場合、MSMQ は何の通知もなく送信メッセージを破棄します (つまり、アプリケーションにエラー コードが返されたり、イベント ログに診断が書き込まれたりすることはありません)。</span><span class="sxs-lookup"><span data-stu-id="76583-119">If this is not done and if no Admin Queue is specified (as is the case in this sample), then MSMQ discards the sent message with no indication that it has done so (that is, no error code returned to the application, no diagnostics written to the event log, and so on).</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="76583-120">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="76583-120">Where to Find This Sample</span></span>  
 <span data-ttu-id="76583-121">\<パスのサンプル\>\AdaptersUsage\MSMQLarge</span><span class="sxs-lookup"><span data-stu-id="76583-121">\<Samples Path\>\AdaptersUsage\MSMQLarge</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="76583-122">サンプルにインストールする場合は、64 ビット バージョンの Windows および BizTalk Server を使用して、 **C:\Program Files (x86) \Microsoft BizTalk Server\<バージョン\>\SDK\Samples\AdaptersUsage\MSMQLarge**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="76583-122">If using a 64-bit version of Windows and BizTalk Server, the sample will be installed in the **C:\Program Files (x86)\Microsoft BizTalk Server \<version\>\SDK\Samples\AdaptersUsage\MSMQLarge** folder.</span></span>  <span data-ttu-id="76583-123">使用してこのドキュメントでその他の手順については、この変更に注意してください、 **C:\Program Files**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="76583-123">Note this change for any other instructions in this document using the **C:\Program Files** folder.</span></span>  
  
 <span data-ttu-id="76583-124">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="76583-124">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="76583-125">**ファイル**</span><span class="sxs-lookup"><span data-stu-id="76583-125">**File**</span></span>|<span data-ttu-id="76583-126">**Description**</span><span class="sxs-lookup"><span data-stu-id="76583-126">**Description**</span></span>|  
|--------------|---------------------|  
|<span data-ttu-id="76583-127">**MQRTLarge.dll**</span><span class="sxs-lookup"><span data-stu-id="76583-127">**MQRTLarge.dll**</span></span>|<span data-ttu-id="76583-128">ネイティブのメッセージ キュー用のアドオンを提供します。</span><span class="sxs-lookup"><span data-stu-id="76583-128">Provides an add-on for native message queuing.</span></span> <span data-ttu-id="76583-129">公開、 **MQSendLargeMessage**と**MQReceiveLargeMessage** Api です。</span><span class="sxs-lookup"><span data-stu-id="76583-129">Exposes the **MQSendLargeMessage** and **MQReceiveLargeMessage** APIs.</span></span><br /><br /> <span data-ttu-id="76583-130">64 ビット版の MQRTLarge.dll にアクセスするのには、64 ビット バージョンの Windows で BizTalk Server をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="76583-130">You must install BizTalk Server on a 64-bit version of Windows in order to access the 64-bit version of MQRTLarge.dll.</span></span><br /><br /> <span data-ttu-id="76583-131">BizTalk Server なしの MSMQ ソリューションでは、引き続き、MQRTLarge.dll から正常に機能します。</span><span class="sxs-lookup"><span data-stu-id="76583-131">For an MSMQ solution without BizTalk Server, the MQRTLarge.dll may still function correctly.</span></span> <span data-ttu-id="76583-132">ただし、これは Microsoft がサポートするための推奨構成ではありません、BizTalk Server 環境の外部で使用されている場合に、予期しない結果が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="76583-132">However, this is not a recommended configuration that Microsoft supports, and unexpected results may occur if used outside of the BizTalk Server environment.</span></span>|  
|||  
|<span data-ttu-id="76583-133">**Largemessages.sln という**</span><span class="sxs-lookup"><span data-stu-id="76583-133">**LargeMessages.sln**</span></span>|<span data-ttu-id="76583-134">サンプルで使用する SendLargeMessage 実行可能ファイルを作成するための Visual Studio ソリューションを提供します。</span><span class="sxs-lookup"><span data-stu-id="76583-134">Provides a Visual Studio solution to create the SendLargeMessage executable used in the sample.</span></span>|  
|<span data-ttu-id="76583-135">**XMLCreator.sln**</span><span class="sxs-lookup"><span data-stu-id="76583-135">**XMLCreator.sln**</span></span>|<span data-ttu-id="76583-136">XMLCreator 実行可能ファイルを作成して SDK サンプルのテスト用 .xml ファイルを生成するための Visual Studio ソリューションを提供します。</span><span class="sxs-lookup"><span data-stu-id="76583-136">Provides a Visual Studio solution to create the XMLCreator executable to generate a test .xml file for the SDK sample.</span></span>|  
  
## <a name="configure-biztalk-and-create-the-msmq-queue"></a><span data-ttu-id="76583-137">BizTalk の構成し、MSMQ キューの作成</span><span class="sxs-lookup"><span data-stu-id="76583-137">Configure BizTalk and Create the MSMQ Queue</span></span>  
 <span data-ttu-id="76583-138">Visual Studio、Microsoft メッセージ キュー、および BizTalk Server がインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="76583-138">Ensure that Visual Studio, Microsoft Message Queuing, and BizTalk Server installed.</span></span>  
  
#### <a name="to-configure-biztalk-server"></a><span data-ttu-id="76583-139">BizTalk Server を構成するには</span><span class="sxs-lookup"><span data-stu-id="76583-139">To configure BizTalk Server</span></span>  
  
1.  <span data-ttu-id="76583-140">Visual Studio で開く、 **C:\Program files \microsoft BizTalk Server\<バージョン\>\SDK\Samples\AdaptersUsage\MSMQLarge\LargeMessages.sln**ソリューション ファイルです。</span><span class="sxs-lookup"><span data-stu-id="76583-140">In Visual Studio, open the **C:\Program Files\Microsoft BizTalk Server \<version\>\SDK\Samples\AdaptersUsage\MSMQLarge\LargeMessages.sln** solution file.</span></span>  <span data-ttu-id="76583-141">サンプルをビルドします。</span><span class="sxs-lookup"><span data-stu-id="76583-141">Build the sample.</span></span>  
  
2.  <span data-ttu-id="76583-142">作成、 **C:\Demo** BizTalk Server が MSMQ からメッセージを配置するディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="76583-142">Create a **C:\Demo** directory where BizTalk Server will place the messages from MSMQ.</span></span>  
  
3.  <span data-ttu-id="76583-143">開く、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="76583-143">Open the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
4.  <span data-ttu-id="76583-144">サンプルでメッセージを書き込む送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="76583-144">Create a send port for the sample to write the message.</span></span>  
  
    -   <span data-ttu-id="76583-145">展開**BizTalk グループ**、展開**アプリケーション**、展開**BizTalk アプリケーション 1**を右クリックして**送信ポート**をクリックして**新規**、クリックして**静的な一方向送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="76583-145">Expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, right-click **Send Ports**, click **New**, and then click **Static One-Way Send Port**.</span></span>  
  
5.  <span data-ttu-id="76583-146">**静的な一方向送信ポート プロパティ** ダイアログ ボックスで、ポートの名前を設定**MySendPort**です。</span><span class="sxs-lookup"><span data-stu-id="76583-146">In the **Static One-Way Send Port Properties** dialog box, set the name of the port to **MySendPort**.</span></span>  
  
6.  <span data-ttu-id="76583-147">トランスポートの種類を設定**ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="76583-147">Set the transport type to **File**.</span></span>  
  
7.  <span data-ttu-id="76583-148">クリックして、**構成**を開く ボタン、 **File トランスポートのプロパティ**フォーム。</span><span class="sxs-lookup"><span data-stu-id="76583-148">Click the **Configure** button to open the **File Transport Properties** form.</span></span> <span data-ttu-id="76583-149">入力**C:\Demo**で**コピー先フォルダー**です。</span><span class="sxs-lookup"><span data-stu-id="76583-149">Enter **C:\Demo** in **Destination Folder**.</span></span> <span data-ttu-id="76583-150">ホスト インスタンス ID で C:\Demo フォルダーにアクセスできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="76583-150">Ensure that the host instance identity has access to the C:\Demo folder.</span></span>  
  
8.  <span data-ttu-id="76583-151">いることを確認**ファイル名**に設定されている **%MessageID%.xml**です。</span><span class="sxs-lookup"><span data-stu-id="76583-151">Ensure that **File Name** is set to **%MessageID%.xml**.</span></span> <span data-ttu-id="76583-152">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76583-152">Click **OK**.</span></span>  
  
9. <span data-ttu-id="76583-153">**[フィルター]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76583-153">Click **Filters**.</span></span>  
  
    1.  <span data-ttu-id="76583-154">設定**プロパティ**に**BTS です。ReceivePortName**です。</span><span class="sxs-lookup"><span data-stu-id="76583-154">Set **Property** to **BTS.ReceivePortName**.</span></span>  
  
    2.  <span data-ttu-id="76583-155">設定**演算子**に **=** です。</span><span class="sxs-lookup"><span data-stu-id="76583-155">Set **Operator** to **=**.</span></span>  
  
    3.  <span data-ttu-id="76583-156">設定**値**に**MyReceivePort**です。</span><span class="sxs-lookup"><span data-stu-id="76583-156">Set **Value** to **MyReceivePort**.</span></span>  
  
    4.  <span data-ttu-id="76583-157">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76583-157">Click **OK**.</span></span>  
  
10. <span data-ttu-id="76583-158">MSMQ からのメッセージを受け付ける受信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="76583-158">Create a receive port to accept the message from MSMQ.</span></span>  
  
    1.  <span data-ttu-id="76583-159">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックして**受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="76583-159">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click **Receive Ports**.</span></span>  
  
    2.  <span data-ttu-id="76583-160">をクリックして**新規**、クリックして**一方向の受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="76583-160">Click **New**, and then click **One-way Receive Port**.</span></span>  
  
11. <span data-ttu-id="76583-161">**受信ポートのプロパティ** ダイアログ ボックスで、ポートの名前を設定**MyReceivePort**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="76583-161">In the **Receive Port Properties** dialog box, set the name of the port to **MyReceivePort**, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="76583-162">サンプル用の受信ポートを作成したら、受信場所を作成します。</span><span class="sxs-lookup"><span data-stu-id="76583-162">After creating a receive port for the sample, you must create a receive location.</span></span>  
  
    1.  <span data-ttu-id="76583-163">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックして**受信場所**です。</span><span class="sxs-lookup"><span data-stu-id="76583-163">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click **Receive Locations**.</span></span>  
  
    2.  <span data-ttu-id="76583-164">をクリックして**新規**、クリックして**一方向の受信場所**です。</span><span class="sxs-lookup"><span data-stu-id="76583-164">Click **New**, and then click **One-way Receive Location**.</span></span>  
  
    3.  <span data-ttu-id="76583-165">受信場所の名前を設定**MSMQReceiveLocation**です。</span><span class="sxs-lookup"><span data-stu-id="76583-165">Set the name of the receive location to **MSMQReceiveLocation**.</span></span>  
  
    4.  <span data-ttu-id="76583-166">**受信ポートの選択**ダイアログ ボックスで、 **MyReceivePort**です。</span><span class="sxs-lookup"><span data-stu-id="76583-166">In the **Select a Receive Port** dialog box, select **MyReceivePort**.</span></span>  
  
    5.  <span data-ttu-id="76583-167">**受信場所のプロパティ**ダイアログ ボックスで、セット**トランスポートの種類**に**MSMQ**です。</span><span class="sxs-lookup"><span data-stu-id="76583-167">In the **Receive Location Properties** dialog box, set **Transport Type** to **MSMQ**.</span></span>  
  
    6.  <span data-ttu-id="76583-168">**アドレス (URI)** セクションで、**構成**を開くには、 **MSMQ トランスポートのプロパティ**フォーム。</span><span class="sxs-lookup"><span data-stu-id="76583-168">In the **Address (URI)** section, click **Configure** to open the **MSMQ Transport Properties** form.</span></span> <span data-ttu-id="76583-169">設定**キュー**に**localhost \private$ \test**です。</span><span class="sxs-lookup"><span data-stu-id="76583-169">Set **Queue** to **localhost\private$\test**.</span></span>  
  
    7.  <span data-ttu-id="76583-170">設定**トランザクション**に`True`、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="76583-170">Set **Transactional** to `True`, and then click **OK**.</span></span>  
  
13. <span data-ttu-id="76583-171">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで、使用できるポートと受信場所を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="76583-171">You must make the ports and receive locations available for use through the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
    1.  <span data-ttu-id="76583-172">右クリック**MySendPort**、クリックして**Enlist**です。</span><span class="sxs-lookup"><span data-stu-id="76583-172">Right-click **MySendPort**, and then click **Enlist**.</span></span>  
  
    2.  <span data-ttu-id="76583-173">右クリック**MySendPort**、クリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="76583-173">Right-click **MySendPort**, and then click **Start**.</span></span>  
  
    3.  <span data-ttu-id="76583-174">右クリック**MSMQReceiveLocation**、クリックして**を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="76583-174">Right-click **MSMQReceiveLocation**, and then click **Enable**.</span></span>  
  
#### <a name="to-create-the-msmq-queue-in-windows-server"></a><span data-ttu-id="76583-175">Windows Server の MSMQ キューを作成するには</span><span class="sxs-lookup"><span data-stu-id="76583-175">To create the MSMQ queue in Windows Server</span></span>
  
1.  <span data-ttu-id="76583-176">をクリックして**開始**を右クリックして**コンピューター**、順にクリック**管理**です。</span><span class="sxs-lookup"><span data-stu-id="76583-176">Click **Start**, right-click **Computer**, and then click **Manage**.</span></span>  
  
2.  <span data-ttu-id="76583-177">展開して、**機能**ノード。</span><span class="sxs-lookup"><span data-stu-id="76583-177">Expand the **Features** node.</span></span>  
  
3.  <span data-ttu-id="76583-178">展開して、**メッセージ キュー**ノード。</span><span class="sxs-lookup"><span data-stu-id="76583-178">Expand the **Message Queuing** node.</span></span>  
  
4.  <span data-ttu-id="76583-179">右クリックし、**専用キュー**ノード、をクリックして**新規**、順にクリック**プライベート キュー**です。</span><span class="sxs-lookup"><span data-stu-id="76583-179">Right-click the **Private Queues** node, click **New**, and then click **Private Queue**.</span></span>  
  
5.  <span data-ttu-id="76583-180">**キュー名**、入力**テスト**です。</span><span class="sxs-lookup"><span data-stu-id="76583-180">Under **Queue name**, enter **test**.</span></span> <span data-ttu-id="76583-181">いることを確認、**トランザクション** チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="76583-181">Ensure that the **Transactional** check box is selected.</span></span>  
  
6.  <span data-ttu-id="76583-182">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76583-182">Click **OK**.</span></span>  
  
#### <a name="to-create-the-msmq-queue-in-windows"></a><span data-ttu-id="76583-183">Windows で MSMQ キューを作成するには</span><span class="sxs-lookup"><span data-stu-id="76583-183">To create the MSMQ queue in Windows</span></span> 
  
1.  <span data-ttu-id="76583-184">をクリックして**開始**を右クリックして**コンピューター**、順にクリック**管理**です。</span><span class="sxs-lookup"><span data-stu-id="76583-184">Click **Start**, right-click **Computer**, and then click **Manage**.</span></span>  
  
2.  <span data-ttu-id="76583-185">展開**サービスとアプリケーション**の順に展開し、**メッセージ キュー**ノード。</span><span class="sxs-lookup"><span data-stu-id="76583-185">Expand **Services and Applications**, and then expand the **Message Queuing** node.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="76583-186">場合**メッセージ キュー**がコンピューターにインストールされていないに移動して**コントロール パネル] > プログラム > プログラムと機能**、し、[ **Windows の機能のオンまたはオフ**です。</span><span class="sxs-lookup"><span data-stu-id="76583-186">If **Message Queuing** is not installed in the computer, go to **Control Panel > Programs > Programs and Features**, and then select **Turn Windows features on or off**.</span></span> <span data-ttu-id="76583-187">下のすべての機能を確認して**Microsoft メッセージ キュー (MSMQ) Server**、順にクリック **[ok]** です。</span><span class="sxs-lookup"><span data-stu-id="76583-187">Check all the features under **Microsoft Message Queue (MSMQ) Server**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="76583-188">右クリックし、**専用キュー**ノード、をクリックして**新規**、順にクリック**プライベート キュー**です。</span><span class="sxs-lookup"><span data-stu-id="76583-188">Right-click the **Private Queues** node, click **New**, and then click **Private Queue**.</span></span>  
  
4.  <span data-ttu-id="76583-189">**キュー名**、入力**テスト**です。</span><span class="sxs-lookup"><span data-stu-id="76583-189">Under **Queue name**, enter **test**.</span></span> <span data-ttu-id="76583-190">いることを確認、**トランザクション** チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="76583-190">Ensure that the **Transactional** check box is selected.</span></span>  
  
5.  <span data-ttu-id="76583-191">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76583-191">Click **OK**.</span></span>  
  
## <a name="creating-a-test-file-and-running-the-sample"></a><span data-ttu-id="76583-192">テスト ファイルの作成とサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="76583-192">Creating a Test File and Running the Sample</span></span>  
  
#### <a name="to-create-a-large-test-file"></a><span data-ttu-id="76583-193">サイズの大きいテスト ファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="76583-193">To create a large test file</span></span>  
  
1.  <span data-ttu-id="76583-194">Visual Studio でソリューションを開いて**C:\Program files \microsoft BizTalk Server\<バージョン\>\SDK\Samples\AdaptersUsage\MSMQLarge\XMLCreator\XMLCreator.sln**です。</span><span class="sxs-lookup"><span data-stu-id="76583-194">In Visual Studio, open the solution **C:\Program Files\Microsoft BizTalk Server \<version\>\SDK\Samples\AdaptersUsage\MSMQLarge\XMLCreator\XMLCreator.sln**.</span></span>  
  
2.  <span data-ttu-id="76583-195">プロジェクトをビルドおよび実行します。</span><span class="sxs-lookup"><span data-stu-id="76583-195">Build and run the project.</span></span>  
  
3.  <span data-ttu-id="76583-196">**XML 本文**、型**これは、テスト メッセージ**です。</span><span class="sxs-lookup"><span data-stu-id="76583-196">Under **XML Body**, type **This is a test message**.</span></span>  
  
4.  <span data-ttu-id="76583-197">**XML 本文をコピーする時期の #**、型`250000`です。</span><span class="sxs-lookup"><span data-stu-id="76583-197">Under **# of times to copy XML body**, type `250000`.</span></span>  
  
5.  <span data-ttu-id="76583-198">**XML ファイルの場所**、型`C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\AdaptersUsage\MSMQLarge\LargeFile.xml`です。</span><span class="sxs-lookup"><span data-stu-id="76583-198">Under **XML File Location**, type `C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\AdaptersUsage\MSMQLarge\LargeFile.xml`.</span></span>  
  
6.  <span data-ttu-id="76583-199">をクリックして**XML の作成**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="76583-199">Click **Create XML**, and then click **OK**.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="76583-200">サンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="76583-200">To run the sample</span></span>  
  
1.  <span data-ttu-id="76583-201">コマンド プロンプトを開き、ディレクトリに移動**C:\Program files \microsoft BizTalk Server\<バージョン\>\SDK\Samples\AdaptersUsage\MSMQLarge\SendLargeMessage\bin\debug**です。</span><span class="sxs-lookup"><span data-stu-id="76583-201">Open a command prompt and change directory to **C:\Program Files\Microsoft BizTalk Server \<version\>\SDK\Samples\AdaptersUsage\MSMQLarge\SendLargeMessage\bin\debug**.</span></span>  
  
2.  <span data-ttu-id="76583-202">コマンド プロンプトで実行して**SendLargeMessage.exe**です。</span><span class="sxs-lookup"><span data-stu-id="76583-202">At the command prompt, run **SendLargeMessage.exe**.</span></span> <span data-ttu-id="76583-203">SendLargeMessage 実行可能ファイルでは 2 つの変数を使用します。1 つ目の変数は MSMQ キューの場所を示し、2 つ目の変数は送信する .xml ファイルの場所を示します。</span><span class="sxs-lookup"><span data-stu-id="76583-203">The SendLargeMessage executable accepts two variables — the first is the location of the MSMQ queue, and the second is the location of the .xml file to send:</span></span>  
  
    ```  
    DIRECT=OS:localhost\private$\Test  "C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\AdaptersUsage\MSMQLarge\LargeFile.xml"  
    ```  
  
3.  <span data-ttu-id="76583-204">BizTalk Server コンピューターで、同じサイズのファイルが作成されたことを確認してください、 **C:\Demo**ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="76583-204">Verify that a file of the same size was created on the BizTalk Server computer in the **C:\Demo** directory.</span></span> <span data-ttu-id="76583-205">これが MySendPort 送信ポートで識別されたディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="76583-205">This is the directory you identified in the MySendPort send port.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="76583-206">コメント</span><span class="sxs-lookup"><span data-stu-id="76583-206">Comments</span></span>  
 <span data-ttu-id="76583-207">SendLargeMessage.exe 参照、 **LargeMessages** API で、さらに、BizTalk メッセージ キュー大きいメッセージ用拡張機能 (MQRTLarge.dll) API を参照します。</span><span class="sxs-lookup"><span data-stu-id="76583-207">SendLargeMessage.exe references the **LargeMessages** API, which in turn references the BizTalk Message Queuing Large Message Extension (MQRTLarge.dll) API.</span></span> <span data-ttu-id="76583-208">メッセージ キューのサイズの大きいメッセージ用拡張機能 API はネイティブのメッセージ キュー用のアドオンで、ネイティブのメッセージ キューでは処理できない、4 MB の制限を超えるメッセージを処理できます。</span><span class="sxs-lookup"><span data-stu-id="76583-208">The Message Queuing Large Message Extension API is an add-on for native message queuing that enables the processing of messages larger than the 4 MB limit of native message queuing.</span></span>  
  
 <span data-ttu-id="76583-209">このサンプルでは、 **MQSendLargeMessage** API API を公開、.NET framework を使用して、 **LargeMessages** API です。</span><span class="sxs-lookup"><span data-stu-id="76583-209">This sample uses the **MQSendLargeMessage** API and exposes the API to the .NET Framework by using the **LargeMessages** API.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76583-210">参照</span><span class="sxs-lookup"><span data-stu-id="76583-210">See Also</span></span>  
 <span data-ttu-id="76583-211">[BizTalk メッセージ キューの大きいメッセージ用拡張機能](../core/biztalk-message-queuing-large-message-extension.md) </span><span class="sxs-lookup"><span data-stu-id="76583-211">[BizTalk Message Queuing Large Message Extension](../core/biztalk-message-queuing-large-message-extension.md) </span></span>  
 [<span data-ttu-id="76583-212">アダプタ サンプル – 使用法</span><span class="sxs-lookup"><span data-stu-id="76583-212">Adapter Samples - Usage</span></span>](../core/adapter-samples-usage.md)