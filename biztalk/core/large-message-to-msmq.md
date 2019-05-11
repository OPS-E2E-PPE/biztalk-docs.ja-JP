---
title: サイズの大きいメッセージを MSMQ に |Microsoft Docs
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
ms.openlocfilehash: d92428426b7032de36ab63cfd2be286ce3c67569
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329819"
---
# <a name="large-message-to-msmq"></a><span data-ttu-id="3c21e-102">MSMQ にサイズの大きいメッセージ</span><span class="sxs-lookup"><span data-stu-id="3c21e-102">Large Message to MSMQ</span></span>
<span data-ttu-id="3c21e-103">MSMQ のサンプル サイズの大きいメッセージが .xml ドキュメント 4 メガバイト (MB) よりも大きいメッセージ キュー (MSMQ とも呼ばれます) から BizTalk MSMQ アダプターを使用して送信する方法を示します、 **MQSendLargeMessage**によって実装される APIMQRTLarge.dll します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-103">The Large Message to MSMQ sample demonstrates how to send an .xml document larger than 4 megabytes (MB) from Message Queuing (also known as MSMQ) to the BizTalk MSMQ adapter by using the **MQSendLargeMessage** API implemented by MQRTLarge.dll.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="3c21e-104">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="3c21e-104">What This Sample Does</span></span>  
 <span data-ttu-id="3c21e-105">このサンプルはように動作します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-105">The sample works as follows:</span></span>  
  
1. <span data-ttu-id="3c21e-106">ユーザーは、サイズの大きい .xml ファイルをローカル コンピューター上のキューに送信するのに SendLargeMessage.exe を使用します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-106">A user uses SendLargeMessage.exe to send a large .xml file to a queue on a local computer.</span></span>  
  
2. <span data-ttu-id="3c21e-107">BizTalk Server では、キューからサイズの大きい .xml ファイルを受信し、ローカル ディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="3c21e-107">BizTalk Server receives the large .xml file from the queue and copies it to a local directory.</span></span>  
  
   <span data-ttu-id="3c21e-108">メッセージ キューの多くの操作は非同期です。</span><span class="sxs-lookup"><span data-stu-id="3c21e-108">Many operations in Message Queuing are asynchronous.</span></span> <span data-ttu-id="3c21e-109">多くは、MSMQ API 呼び出し (たとえば、 **MQSendLargeMessage**)、要求された操作が完全に完了する前に、呼び出し元に戻ります。</span><span class="sxs-lookup"><span data-stu-id="3c21e-109">That is, many MSMQ API calls (for example, **MQSendLargeMessage**) return to the caller before the requested operation has fully completed.</span></span>  
  
   <span data-ttu-id="3c21e-110">MSMQ では、操作が完了した後、アプリケーションにフィードバックを配信するためのメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-110">MSMQ provides a mechanism to deliver feedback to the application after the operation has completed.</span></span> <span data-ttu-id="3c21e-111">このメカニズムでは、「管理キュー」の使用</span><span class="sxs-lookup"><span data-stu-id="3c21e-111">This mechanism involves the use of an "Admin Queue."</span></span> <span data-ttu-id="3c21e-112">MSMQ 管理キューにメッセージの形式でフィードバックを返します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-112">MSMQ returns feedback in the form of a message in the Admin Queue.</span></span> <span data-ttu-id="3c21e-113">MSMQ がフィードバックを返す管理キューは、元の MSMQ API 呼び出しが行われたときに指定します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-113">The Admin Queue to which MSMQ will return feedback is specified when the original MSMQ API call is made.</span></span> <span data-ttu-id="3c21e-114">そのため、たとえばを使用してメッセージを送信するときに、 **MQSendLargeMessage** API、アプリケーションを指定できます管理キューの名前を使用して、 **PROPID_M_ADMIN_QUEUE**メッセージのメッセージのプロパティ呼び出しで渡される**MQSendLargeMessage**します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-114">So, for example, when sending a message using the **MQSendLargeMessage** API, the application can specify the name of an Admin Queue by using the **PROPID_M_ADMIN_QUEUE** message property on the message passed in the call to **MQSendLargeMessage**.</span></span> <span data-ttu-id="3c21e-115">アプリケーションの成功を示すリターン コードが取得場合でも、 **MQSendLargeMessage**呼び出し、メッセージの送信操作後で失敗した場合、MSMQ メッセージを書き込みますそれに対応する指定の管理キューにします。</span><span class="sxs-lookup"><span data-stu-id="3c21e-115">Even though the application may get a successful return code on the **MQSendLargeMessage** call, if the message send operation subsequently fails, MSMQ writes a message to that effect to the specified Admin Queue.</span></span>  
  
   <span data-ttu-id="3c21e-116">送信エラーによりメッセージが消失と診断がキャプチャされません、アプリケーションが管理キューを指定しない場合、実際には、メッセージは証拠も残らない表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="3c21e-116">If the application does not specify an Admin Queue, a send failure results in the message being lost and no diagnostics captured — in effect, the message disappears without any evidence.</span></span> <span data-ttu-id="3c21e-117">さまざまな MSMQ でのエラー状況可能性があります、この例では、トランザクション キューにトランザクション以外の送信を行います。</span><span class="sxs-lookup"><span data-stu-id="3c21e-117">A number of error situations in MSMQ can cause this to happen, for example, doing a non-transactional send to a transactional queue.</span></span>  
  
   <span data-ttu-id="3c21e-118">このサンプルのコンテキストでは、コードが呼び出しでトランザクションの種類を指定することが重要**MQSendLargeMessage**は、メッセージの送信先キューに指定されたトランザクションのサポートと一貫性があるようにします。</span><span class="sxs-lookup"><span data-stu-id="3c21e-118">In the context of this sample, it is important that the code specify a transaction type in the call to **MQSendLargeMessage** that is consistent with the transaction support specified for the queue to which the message is sent.</span></span> <span data-ttu-id="3c21e-119">これを行わないし、管理キューが指定されていない場合 (このサンプルの場合と同様)、し、MSMQ 送信はメッセージを破棄することが示されない場合 (つまり、エラー コードが返さ、アプリケーションでは、診断がイベント ログに書き込まれたりするには、など)。</span><span class="sxs-lookup"><span data-stu-id="3c21e-119">If this is not done and if no Admin Queue is specified (as is the case in this sample), then MSMQ discards the sent message with no indication that it has done so (that is, no error code returned to the application, no diagnostics written to the event log, and so on).</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="3c21e-120">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="3c21e-120">Where to Find This Sample</span></span>  
 <span data-ttu-id="3c21e-121">\<パスのサンプル\>\AdaptersUsage\MSMQLarge</span><span class="sxs-lookup"><span data-stu-id="3c21e-121">\<Samples Path\>\AdaptersUsage\MSMQLarge</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3c21e-122">サンプルにインストールする場合は、Windows と BizTalk Server の 64 ビット バージョンを使用して、 **C:\Program Files (x86) \Microsoft BizTalk Server\<バージョン\>\SDK\Samples\AdaptersUsage\MSMQLarge**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="3c21e-122">If using a 64-bit version of Windows and BizTalk Server, the sample will be installed in the **C:\Program Files (x86)\Microsoft BizTalk Server \<version\>\SDK\Samples\AdaptersUsage\MSMQLarge** folder.</span></span>  <span data-ttu-id="3c21e-123">使用してこのドキュメントでその他の手順については、この変更に注意してください、 **C:\Program Files**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="3c21e-123">Note this change for any other instructions in this document using the **C:\Program Files** folder.</span></span>  
  
 <span data-ttu-id="3c21e-124">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="3c21e-124">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="3c21e-125">**[最近使ったファイル]**</span><span class="sxs-lookup"><span data-stu-id="3c21e-125">**File**</span></span>|<span data-ttu-id="3c21e-126">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="3c21e-126">**Description**</span></span>|  
|--------------|---------------------|  
|<span data-ttu-id="3c21e-127">**MQRTLarge.dll**</span><span class="sxs-lookup"><span data-stu-id="3c21e-127">**MQRTLarge.dll**</span></span>|<span data-ttu-id="3c21e-128">ネイティブのメッセージ キューのアドオンを提供します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-128">Provides an add-on for native message queuing.</span></span> <span data-ttu-id="3c21e-129">公開、 **MQSendLargeMessage**と**MQReceiveLargeMessage** Api。</span><span class="sxs-lookup"><span data-stu-id="3c21e-129">Exposes the **MQSendLargeMessage** and **MQReceiveLargeMessage** APIs.</span></span><br /><br /> <span data-ttu-id="3c21e-130">BizTalk Server は、64 ビット版の MQRTLarge.dll にアクセスするために Windows の 64 ビット バージョンをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c21e-130">You must install BizTalk Server on a 64-bit version of Windows in order to access the 64-bit version of MQRTLarge.dll.</span></span><br /><br /> <span data-ttu-id="3c21e-131">BizTalk Server なしの MSMQ ソリューションでは、可能性があります、まだ、MQRTLarge.dll から正常に機能します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-131">For an MSMQ solution without BizTalk Server, the MQRTLarge.dll may still function correctly.</span></span> <span data-ttu-id="3c21e-132">ただし、これは Microsoft がサポートしている推奨構成ではありませんし、BizTalk Server 環境の外部で使用されている場合に、予期しない結果が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3c21e-132">However, this is not a recommended configuration that Microsoft supports, and unexpected results may occur if used outside of the BizTalk Server environment.</span></span>|  
|||  
|<span data-ttu-id="3c21e-133">**LargeMessages.sln**</span><span class="sxs-lookup"><span data-stu-id="3c21e-133">**LargeMessages.sln**</span></span>|<span data-ttu-id="3c21e-134">このサンプルで使用される SendLargeMessage 実行可能ファイルを作成する Visual Studio ソリューションを提供します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-134">Provides a Visual Studio solution to create the SendLargeMessage executable used in the sample.</span></span>|  
|<span data-ttu-id="3c21e-135">**XMLCreator.sln**</span><span class="sxs-lookup"><span data-stu-id="3c21e-135">**XMLCreator.sln**</span></span>|<span data-ttu-id="3c21e-136">XMLCreator の SDK サンプルのテストの .xml ファイルを生成する実行可能ファイルを作成する Visual Studio ソリューションを提供します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-136">Provides a Visual Studio solution to create the XMLCreator executable to generate a test .xml file for the SDK sample.</span></span>|  
  
## <a name="configure-biztalk-and-create-the-msmq-queue"></a><span data-ttu-id="3c21e-137">BizTalk の構成し、MSMQ キューを作成</span><span class="sxs-lookup"><span data-stu-id="3c21e-137">Configure BizTalk and Create the MSMQ Queue</span></span>  
 <span data-ttu-id="3c21e-138">Visual Studio、Microsoft メッセージ キュー、および BizTalk Server がインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-138">Ensure that Visual Studio, Microsoft Message Queuing, and BizTalk Server installed.</span></span>  
  
#### <a name="to-configure-biztalk-server"></a><span data-ttu-id="3c21e-139">BizTalk Server を構成するには</span><span class="sxs-lookup"><span data-stu-id="3c21e-139">To configure BizTalk Server</span></span>  
  
1. <span data-ttu-id="3c21e-140">Visual Studio で開く、 **C:\Program files \microsoft BizTalk Server\<バージョン\>\SDK\Samples\AdaptersUsage\MSMQLarge\LargeMessages.sln**ソリューション ファイル。</span><span class="sxs-lookup"><span data-stu-id="3c21e-140">In Visual Studio, open the **C:\Program Files\Microsoft BizTalk Server \<version\>\SDK\Samples\AdaptersUsage\MSMQLarge\LargeMessages.sln** solution file.</span></span>  <span data-ttu-id="3c21e-141">サンプルをビルドします。</span><span class="sxs-lookup"><span data-stu-id="3c21e-141">Build the sample.</span></span>  
  
2. <span data-ttu-id="3c21e-142">作成、 **C:\Demo**ディレクトリが BizTalk Server が MSMQ からのメッセージを配置する場所。</span><span class="sxs-lookup"><span data-stu-id="3c21e-142">Create a **C:\Demo** directory where BizTalk Server will place the messages from MSMQ.</span></span>  
  
3. <span data-ttu-id="3c21e-143">開く、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="3c21e-143">Open the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
4. <span data-ttu-id="3c21e-144">メッセージを書き込む、サンプルの送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-144">Create a send port for the sample to write the message.</span></span>  
  
   -   <span data-ttu-id="3c21e-145">展開**BizTalk グループ**、展開**アプリケーション**、展開**BizTalk アプリケーション 1**、右クリック**送信ポート**をクリックします **。新規**、 をクリックし、**静的な一方向送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-145">Expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, right-click **Send Ports**, click **New**, and then click **Static One-Way Send Port**.</span></span>  
  
5. <span data-ttu-id="3c21e-146">**静的な一方向送信ポート プロパティ** ダイアログ ボックスで、ポートの名前、設定**MySendPort**します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-146">In the **Static One-Way Send Port Properties** dialog box, set the name of the port to **MySendPort**.</span></span>  
  
6. <span data-ttu-id="3c21e-147">トランスポートの種類を設定**ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-147">Set the transport type to **File**.</span></span>  
  
7. <span data-ttu-id="3c21e-148">をクリックして、**構成**ボタンをクリックする、 **File トランスポートのプロパティ**フォーム。</span><span class="sxs-lookup"><span data-stu-id="3c21e-148">Click the **Configure** button to open the **File Transport Properties** form.</span></span> <span data-ttu-id="3c21e-149">入力**C:\Demo**で**先フォルダー**します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-149">Enter **C:\Demo** in **Destination Folder**.</span></span> <span data-ttu-id="3c21e-150">ホスト インスタンスの id に C:\Demo フォルダーにアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="3c21e-150">Ensure that the host instance identity has access to the C:\Demo folder.</span></span>  
  
8. <span data-ttu-id="3c21e-151">いることを確認**ファイル名**に設定されている **%MessageID%.xml**します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-151">Ensure that **File Name** is set to **%MessageID%.xml**.</span></span> <span data-ttu-id="3c21e-152">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c21e-152">Click **OK**.</span></span>  
  
9. <span data-ttu-id="3c21e-153">**[フィルター]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c21e-153">Click **Filters**.</span></span>  
  
    1.  <span data-ttu-id="3c21e-154">設定**プロパティ**に**BTS します。ReceivePortName**します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-154">Set **Property** to **BTS.ReceivePortName**.</span></span>  
  
    2.  <span data-ttu-id="3c21e-155">設定**演算子**に **=** します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-155">Set **Operator** to **=**.</span></span>  
  
    3.  <span data-ttu-id="3c21e-156">設定**値**に**MyReceivePort**します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-156">Set **Value** to **MyReceivePort**.</span></span>  
  
    4.  <span data-ttu-id="3c21e-157">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c21e-157">Click **OK**.</span></span>  
  
10. <span data-ttu-id="3c21e-158">MSMQ からのメッセージをそのまま使用する受信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-158">Create a receive port to accept the message from MSMQ.</span></span>  
  
    1. <span data-ttu-id="3c21e-159">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックして**受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-159">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click **Receive Ports**.</span></span>  
  
    2. <span data-ttu-id="3c21e-160">クリックして**新規**、 をクリックし、**一方向の受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-160">Click **New**, and then click **One-way Receive Port**.</span></span>  
  
11. <span data-ttu-id="3c21e-161">**受信ポートのプロパティ** ダイアログ ボックスで、ポートの名前、設定**MyReceivePort**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-161">In the **Receive Port Properties** dialog box, set the name of the port to **MyReceivePort**, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="3c21e-162">サンプル用の受信ポートを作成した後は、受信場所を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c21e-162">After creating a receive port for the sample, you must create a receive location.</span></span>  
  
    1. <span data-ttu-id="3c21e-163">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックして**受信場所**します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-163">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click **Receive Locations**.</span></span>  
  
    2. <span data-ttu-id="3c21e-164">クリックして**新規**、 をクリックし、**一方向の受信場所**します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-164">Click **New**, and then click **One-way Receive Location**.</span></span>  
  
    3. <span data-ttu-id="3c21e-165">受信場所の名前を設定**MSMQReceiveLocation**します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-165">Set the name of the receive location to **MSMQReceiveLocation**.</span></span>  
  
    4. <span data-ttu-id="3c21e-166">**受信ポートの選択**ダイアログ ボックスで、 **MyReceivePort**します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-166">In the **Select a Receive Port** dialog box, select **MyReceivePort**.</span></span>  
  
    5. <span data-ttu-id="3c21e-167">**受信場所のプロパティ**ダイアログ ボックスで、セット**トランスポートの種類**に**MSMQ**します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-167">In the **Receive Location Properties** dialog box, set **Transport Type** to **MSMQ**.</span></span>  
  
    6. <span data-ttu-id="3c21e-168">**アドレス (URI)** セクションで、**構成**を開く、 **MSMQ トランスポートのプロパティ**フォーム。</span><span class="sxs-lookup"><span data-stu-id="3c21e-168">In the **Address (URI)** section, click **Configure** to open the **MSMQ Transport Properties** form.</span></span> <span data-ttu-id="3c21e-169">設定**キュー**に**localhost \private$ \test**します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-169">Set **Queue** to **localhost\private$\test**.</span></span>  
  
    7. <span data-ttu-id="3c21e-170">設定**トランザクション**に`True`、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-170">Set **Transactional** to `True`, and then click **OK**.</span></span>  
  
13. <span data-ttu-id="3c21e-171">ポートを作成し、受信場所を通じて使用できる必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="3c21e-171">You must make the ports and receive locations available for use through the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
    1.  <span data-ttu-id="3c21e-172">右クリックして**MySendPort**、 をクリックし、**参加**します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-172">Right-click **MySendPort**, and then click **Enlist**.</span></span>  
  
    2.  <span data-ttu-id="3c21e-173">右クリック**MySendPort**、 をクリックし、**開始**します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-173">Right-click **MySendPort**, and then click **Start**.</span></span>  
  
    3.  <span data-ttu-id="3c21e-174">右クリックして**MSMQReceiveLocation**、 をクリックし、**を有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-174">Right-click **MSMQReceiveLocation**, and then click **Enable**.</span></span>  
  
#### <a name="to-create-the-msmq-queue-in-windows-server"></a><span data-ttu-id="3c21e-175">Windows Server の MSMQ キューを作成するには</span><span class="sxs-lookup"><span data-stu-id="3c21e-175">To create the MSMQ queue in Windows Server</span></span>
  
1.  <span data-ttu-id="3c21e-176">クリックして**開始**を右クリックして**コンピューター**、順にクリックします**管理**します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-176">Click **Start**, right-click **Computer**, and then click **Manage**.</span></span>  
  
2.  <span data-ttu-id="3c21e-177">展開、**機能**ノード。</span><span class="sxs-lookup"><span data-stu-id="3c21e-177">Expand the **Features** node.</span></span>  
  
3.  <span data-ttu-id="3c21e-178">展開、**メッセージ キュー**ノード。</span><span class="sxs-lookup"><span data-stu-id="3c21e-178">Expand the **Message Queuing** node.</span></span>  
  
4.  <span data-ttu-id="3c21e-179">右クリックし、**専用キュー**ノード、をクリックして**新規**、順にクリックします**プライベート キュー**します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-179">Right-click the **Private Queues** node, click **New**, and then click **Private Queue**.</span></span>  
  
5.  <span data-ttu-id="3c21e-180">**キュー名**、入力**テスト**します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-180">Under **Queue name**, enter **test**.</span></span> <span data-ttu-id="3c21e-181">いることを確認、**トランザクション** チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="3c21e-181">Ensure that the **Transactional** check box is selected.</span></span>  
  
6.  <span data-ttu-id="3c21e-182">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c21e-182">Click **OK**.</span></span>  
  
#### <a name="to-create-the-msmq-queue-in-windows"></a><span data-ttu-id="3c21e-183">Windows で MSMQ キューを作成するには</span><span class="sxs-lookup"><span data-stu-id="3c21e-183">To create the MSMQ queue in Windows</span></span> 
  
1.  <span data-ttu-id="3c21e-184">クリックして**開始**を右クリックして**コンピューター**、順にクリックします**管理**します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-184">Click **Start**, right-click **Computer**, and then click **Manage**.</span></span>  
  
2.  <span data-ttu-id="3c21e-185">展開**サービスとアプリケーション**の順に展開し、**メッセージ キュー**ノード。</span><span class="sxs-lookup"><span data-stu-id="3c21e-185">Expand **Services and Applications**, and then expand the **Message Queuing** node.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3c21e-186">場合**メッセージ キュー** 、コンピューターにインストールされていないに移動して**コントロール パネル > プログラム > プログラムと機能**、し、**オンまたはオフにする Windows 機能**します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-186">If **Message Queuing** is not installed in the computer, go to **Control Panel > Programs > Programs and Features**, and then select **Turn Windows features on or off**.</span></span> <span data-ttu-id="3c21e-187">すべての機能を確認**Microsoft メッセージ キュー (MSMQ) Server**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="3c21e-187">Check all the features under **Microsoft Message Queue (MSMQ) Server**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="3c21e-188">右クリックし、**専用キュー**ノード、をクリックして**新規**、順にクリックします**プライベート キュー**します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-188">Right-click the **Private Queues** node, click **New**, and then click **Private Queue**.</span></span>  
  
4.  <span data-ttu-id="3c21e-189">**キュー名**、入力**テスト**します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-189">Under **Queue name**, enter **test**.</span></span> <span data-ttu-id="3c21e-190">いることを確認、**トランザクション** チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="3c21e-190">Ensure that the **Transactional** check box is selected.</span></span>  
  
5.  <span data-ttu-id="3c21e-191">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c21e-191">Click **OK**.</span></span>  
  
## <a name="creating-a-test-file-and-running-the-sample"></a><span data-ttu-id="3c21e-192">テスト ファイルを作成し、サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-192">Creating a Test File and Running the Sample</span></span>  
  
#### <a name="to-create-a-large-test-file"></a><span data-ttu-id="3c21e-193">大規模なテスト ファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="3c21e-193">To create a large test file</span></span>  
  
1.  <span data-ttu-id="3c21e-194">Visual Studio でソリューションを開いて**C:\Program files \microsoft BizTalk Server\<バージョン\>\SDK\Samples\AdaptersUsage\MSMQLarge\XMLCreator\XMLCreator.sln**します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-194">In Visual Studio, open the solution **C:\Program Files\Microsoft BizTalk Server \<version\>\SDK\Samples\AdaptersUsage\MSMQLarge\XMLCreator\XMLCreator.sln**.</span></span>  
  
2.  <span data-ttu-id="3c21e-195">プロジェクトをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-195">Build and run the project.</span></span>  
  
3.  <span data-ttu-id="3c21e-196">**XML 本文**、型**これはテスト メッセージ**します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-196">Under **XML Body**, type **This is a test message**.</span></span>  
  
4.  <span data-ttu-id="3c21e-197">**XML 本文をコピーする回数**、型`250000`します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-197">Under **# of times to copy XML body**, type `250000`.</span></span>  
  
5.  <span data-ttu-id="3c21e-198">**XML ファイルの場所**、型`C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\AdaptersUsage\MSMQLarge\LargeFile.xml`します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-198">Under **XML File Location**, type `C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\AdaptersUsage\MSMQLarge\LargeFile.xml`.</span></span>  
  
6.  <span data-ttu-id="3c21e-199">クリックして**XML の作成**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-199">Click **Create XML**, and then click **OK**.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="3c21e-200">サンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="3c21e-200">To run the sample</span></span>  
  
1.  <span data-ttu-id="3c21e-201">コマンド プロンプトを開き、ディレクトリに移動**C:\Program files \microsoft BizTalk Server\<バージョン\>\SDK\Samples\AdaptersUsage\MSMQLarge\SendLargeMessage\bin\debug**します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-201">Open a command prompt and change directory to **C:\Program Files\Microsoft BizTalk Server \<version\>\SDK\Samples\AdaptersUsage\MSMQLarge\SendLargeMessage\bin\debug**.</span></span>  
  
2.  <span data-ttu-id="3c21e-202">コマンド プロンプトで次のように実行します。 **SendLargeMessage.exe**します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-202">At the command prompt, run **SendLargeMessage.exe**.</span></span> <span data-ttu-id="3c21e-203">SendLargeMessage 実行可能ファイルは、2 つの変数を受け入れる — 1 つは、MSMQ キューの場所と、2 つ目は、送信する .xml ファイルの場所。</span><span class="sxs-lookup"><span data-stu-id="3c21e-203">The SendLargeMessage executable accepts two variables — the first is the location of the MSMQ queue, and the second is the location of the .xml file to send:</span></span>  
  
    ```  
    DIRECT=OS:localhost\private$\Test  "C:\Program Files\Microsoft BizTalk Server <version>\SDK\Samples\AdaptersUsage\MSMQLarge\LargeFile.xml"  
    ```  
  
3.  <span data-ttu-id="3c21e-204">BizTalk Server コンピューターで同じサイズのファイルが作成されたことを確認、 **C:\Demo**ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="3c21e-204">Verify that a file of the same size was created on the BizTalk Server computer in the **C:\Demo** directory.</span></span> <span data-ttu-id="3c21e-205">これは、MySendPort 送信ポートで識別されたディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="3c21e-205">This is the directory you identified in the MySendPort send port.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="3c21e-206">コメント</span><span class="sxs-lookup"><span data-stu-id="3c21e-206">Comments</span></span>  
 <span data-ttu-id="3c21e-207">SendLargeMessage.exe 参照、 **LargeMessages** API で、さらに、BizTalk メッセージ キュー大きいメッセージ用拡張機能 (MQRTLarge.dll) API を参照します。</span><span class="sxs-lookup"><span data-stu-id="3c21e-207">SendLargeMessage.exe references the **LargeMessages** API, which in turn references the BizTalk Message Queuing Large Message Extension (MQRTLarge.dll) API.</span></span> <span data-ttu-id="3c21e-208">メッセージ キュー大きなメッセージ拡張機能 API では、ネイティブのメッセージをキュー用のアドオンがネイティブのメッセージ キューの 4 MB の制限を超えるメッセージの処理を実現できます。</span><span class="sxs-lookup"><span data-stu-id="3c21e-208">The Message Queuing Large Message Extension API is an add-on for native message queuing that enables the processing of messages larger than the 4 MB limit of native message queuing.</span></span>  
  
 <span data-ttu-id="3c21e-209">このサンプルでは、 **MQSendLargeMessage** API と公開 API を .NET Framework を使用して、 **LargeMessages** API。</span><span class="sxs-lookup"><span data-stu-id="3c21e-209">This sample uses the **MQSendLargeMessage** API and exposes the API to the .NET Framework by using the **LargeMessages** API.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c21e-210">参照</span><span class="sxs-lookup"><span data-stu-id="3c21e-210">See Also</span></span>  
 <span data-ttu-id="3c21e-211">[BizTalk メッセージ キューの大きいメッセージ用拡張機能](../core/biztalk-message-queuing-large-message-extension.md) </span><span class="sxs-lookup"><span data-stu-id="3c21e-211">[BizTalk Message Queuing Large Message Extension](../core/biztalk-message-queuing-large-message-extension.md) </span></span>  
 [<span data-ttu-id="3c21e-212">アダプタ サンプル – 使用法</span><span class="sxs-lookup"><span data-stu-id="3c21e-212">Adapter Samples - Usage</span></span>](../core/adapter-samples-usage.md)