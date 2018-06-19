---
title: 'チュートリアル: は、POP3 アダプタを使用する BizTalk アプリケーションの作成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tutorials, POP3 adapters
- configuring [POP3 adapters], mailboxes
- configuring [POP3 adapters], tutorials
- POP3 adapters, mailboxes
- POP3 adapters, tutorials
- configuring [POP3 adapters], Outlook Express
ms.assetid: b44c3b1d-7b4f-425c-831a-1ce5f6379595
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e677a4fb68ad4f6991585c191c8065a60b3fc337
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25975944"
---
# <a name="walkthrough-creating-a-biztalk-application-that-uses-the-pop3-adapter"></a><span data-ttu-id="c2f5f-102">チュートリアル: POP3 アダプターを使用する BizTalk アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="c2f5f-102">Walkthrough: Creating a BizTalk Application That Uses the POP3 Adapter</span></span>
<span data-ttu-id="c2f5f-103">このセクションでは、POP3 アダプタを使用する簡単な Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーションを作成する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-103">This section takes you through creating a simple Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application using the POP3 adapter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c2f5f-104">このアプリケーションは、Microsoft [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] または [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] が実行されていて電子メール サービスがインストールおよび構成されているコンピューターに、アクセスできることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-104">The application assumes that you have access to a computer running Microsoft [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] with Email Services installed and configured.</span></span> <span data-ttu-id="c2f5f-105">[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] または [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] を電子メール サービスと共に構成する方法の詳細については、Windows Server のヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-105">For information about configuring [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] with Email Services see Windows Server Help.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c2f5f-106">この例では、電子メール クライアントに Microsoft Outlook Express を、電子メール サーバーに [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] または [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] を使用します。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-106">In this example Microsoft Outlook Express is used as the e-mail client and [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] is used as the e-mail server.</span></span> <span data-ttu-id="c2f5f-107">ただし、このシナリオでは任意の POP3 電子メール クライアントと RFC 準拠の POP3 サーバーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-107">However, any POP3 e-mail client and RFC-compliant POP3 server could be used for this scenario.</span></span>  
  
 <span data-ttu-id="c2f5f-108">このアプリケーションは、まだ送信ポートまたは受信場所を作成していないことを前提としています。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-108">This application assumes that you have not yet created any send ports or receive locations.</span></span> <span data-ttu-id="c2f5f-109">既存の送信ポートまたは受信場所がある場合、手順を実行する際に適切な名前に置き換えてください。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-109">If you have existing send ports or receive locations, substitute appropriate names when you work through the steps.</span></span>  
  
 <span data-ttu-id="c2f5f-110">このアプリケーションは、受信場所と送信ポートのみを使用する、コンテンツベースの単純なルーティング アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-110">The application is a simple content-based routing application using only a receive location and a send port.</span></span> <span data-ttu-id="c2f5f-111">受信場所を実行しているサーバー上のメールボックスから読み取り[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]または[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]("Windows server"\)です。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-111">The receive location reads from a mailbox on the server running [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]("the Windows server"\).</span></span> <span data-ttu-id="c2f5f-112">送信ポートは、受信場所からメッセージを取得して、そのメッセージを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のローカル ファイル システム上のフォルダーに送信します。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-112">The send port takes the message from the receive location and sends it to a folder on the local file system of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="c2f5f-113">このアプリケーションを作成するには、メールボックスの作成、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の受信場所と送信ポートの設定、送信ポートの開始と受信場所の有効化、およびメールボックスへのテスト メッセージの送信を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-113">To create the application, you have to create the mailbox, set up the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location and send port, start the send port and enable the receive location, and send a test message to the mailbox.</span></span> <span data-ttu-id="c2f5f-114">次の手順に従って、アプリケーションを作成してください。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-114">Follow the steps below to create the application.</span></span>  
  
## <a name="create-a-mailbox-on-windows-server-2003"></a><span data-ttu-id="c2f5f-115">Windows Server 2003 でのメールボックスの作成</span><span class="sxs-lookup"><span data-stu-id="c2f5f-115">Create a mailbox on Windows Server 2003</span></span>  
 <span data-ttu-id="c2f5f-116">電子メール サービスがインストールされた Windows Server 2003 でメールボックスを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-116">To create a mailbox on Windows Server 2003 with Email Services installed, follow these steps:</span></span>  
  
1.  <span data-ttu-id="c2f5f-117">をクリックして**開始**、 をポイント**プログラム**、 をポイント**管理ツール**、順にクリック**POP3 サービス**です。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-117">Click **Start**, point to **Programs**, point to **Administrative Tools**, and then click **POP3 Service**.</span></span>  
  
2.  <span data-ttu-id="c2f5f-118">展開 *\<servername\>* メールボックスを作成するにはドメイン をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-118">Expand *\<servername\>* and click the domain where you would like to create a mailbox.</span></span>  
  
3.  <span data-ttu-id="c2f5f-119">**POP3 サービス**ダイアログ ボックスの右側のウィンドウで、クリックして、**メールボックスの追加**オプション。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-119">In the **POP3 Service** dialog box, in the right pane, click the **Add Mailbox** option.</span></span>  
  
4.  <span data-ttu-id="c2f5f-120">**メールボックスの追加** ダイアログ ボックスで、**メールボックス名**ボックスに、入力**EmailTest**です。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-120">In the **Add Mailbox** dialog box, in the **Mailbox Name** box, type **EmailTest**.</span></span>  
  
5.  <span data-ttu-id="c2f5f-121">選択、**を作成するには、このメールボックスのユーザーが関連付けられている**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-121">Select the **Create associated user for this mailbox** check box.</span></span>  
  
6.  <span data-ttu-id="c2f5f-122">**パスワード**と**パスワードの確認**ボックスに、パスワードを入力し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-122">In the **Password** and **Confirm Password** boxes, type a password, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="c2f5f-123">メモ、**アカウント名**と**メール サーバー**にクリア テキスト認証で使用するために表示される情報のログオン、 **POP3 サービス**クリックしてダイアログ ボックスで、**OK**です。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-123">Make a note of the **Account name** and **Mail Server** log on information displayed for use with clear text authentication in the **POP3 Service** dialog box, and then click **OK**.</span></span> <span data-ttu-id="c2f5f-124">この情報は、トランスポートの種類 POP3 で構成する [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の受信場所によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-124">This information will be used by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location that you configure with the POP3 transport type.</span></span>  
  
## <a name="create-the-receive-location"></a><span data-ttu-id="c2f5f-125">受信場所を作成します。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-125">Create the receive location</span></span>  
 <span data-ttu-id="c2f5f-126">受信場所を作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-126">Follow these steps to create the receive location:</span></span>  
  
1.  <span data-ttu-id="c2f5f-127">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールが既定のデータベースをダブルクリックして **\<**  *machine_name***\>です。>.biztalkmgmtdb.dbo**ここで、 *machine_name*お使いのコンピューターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-127">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console double-click the default database **\<***machine_name***\>.BizTalkMgmtDb.dbo**, where *machine_name* is the name of your computer.</span></span> <span data-ttu-id="c2f5f-128">をクリックして**アプリケーション**をクリックし、 **[biztalk.application.1]** です。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-128">Click **Applications**, then click **BizTalk.Application.1**.</span></span>  
  
2.  <span data-ttu-id="c2f5f-129">右クリック**受信ポート**をクリックして**新規**、 をクリックして**一方向受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-129">Right-click **Receive Ports**, click **New**, click **One-way receive port**.</span></span>  
  
3.  <span data-ttu-id="c2f5f-130">**受信ポートのプロパティ** ダイアログ ボックスで、**名前**ボックスに、入力**POP3Receive**です。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-130">In the **Receive Port Properties** dialog box, in the **Name** box, type **POP3Receive**.</span></span>  
  
4.  <span data-ttu-id="c2f5f-131">をクリックして**受信場所**、クリックして**新規**です。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-131">Click **Receive Locations**, and then click **New**.</span></span>  <span data-ttu-id="c2f5f-132">**受信場所のプロパティ** ダイアログ ボックスで、**名前**ボックスに、入力**POP3Receive**です。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-132">In the **Receive Location Properties** dialog box, in the **Name** box, type **POP3Receive**.</span></span>  
  
5.  <span data-ttu-id="c2f5f-133">**トランスポートの種類**ボックスで、 **POP3**です。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-133">In the **Transport Type** box, select **POP3**.</span></span>  
  
6.  <span data-ttu-id="c2f5f-134">**受信ハンドラー**ボックスで、 **BizTalkServerApplication**です。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-134">In the **Receive Handler** box, select **BizTalkServerApplication**.</span></span>  
  
7.  <span data-ttu-id="c2f5f-135">**受信パイプライン**ボックスで、 **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**です。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-135">In the **Receive Pipeline** box, select **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**.</span></span>  
  
8.  <span data-ttu-id="c2f5f-136">**トランスポート**ボックスで、クリックして、**構成**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-136">In the **Transport** box, click the **Configure** button.</span></span>  
  
9. <span data-ttu-id="c2f5f-137">**POP3 トランスポートのプロパティ** ダイアログ ボックスで、 **MIME デコードの適用**ボックスで、 **False**です。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-137">In the **POP3 Transport Properties** dialog box, in the **Apply MIME Decoding** box, select **False**.</span></span>  
  
10. <span data-ttu-id="c2f5f-138">**メール サーバー**ボックスに、メールボックスを作成した Windows Server ベースのサーバーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-138">In the **Mail Server** box, type the name of the Windows Server-based server where you created a mailbox.</span></span>  
  
11. <span data-ttu-id="c2f5f-139">**認証スキーム**ボックスで、**基本**です。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-139">In the **Authentication Scheme** box, select **Basic**.</span></span>  
  
12. <span data-ttu-id="c2f5f-140">**パスワード**ボックス、ドロップダウン矢印をクリックし、メールボックスのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-140">In the **Password** box, click the drop-down arrow and type the password for the mailbox.</span></span>  
  
13. <span data-ttu-id="c2f5f-141">**ユーザー名**ボックスに、たとえば、メールボックスの完全修飾ユーザー名を入力*username@host.domain.toplevel_domainです。*</span><span class="sxs-lookup"><span data-stu-id="c2f5f-141">In the **User Name** box, type the fully qualified user name for the mailbox, for example *username@host.domain.toplevel_domain.*</span></span>  
  
14. <span data-ttu-id="c2f5f-142">**のポーリング間隔**ボックスに、入力**1**、 をクリックして**ok**、順にクリック**OK**もう一度です。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-142">In the **Polling Interval** box, type **1**, click **OK**, and then click **OK** again.</span></span>  
  
## <a name="create-the-send-port-and-destination-folder-on-the-biztalk-server"></a><span data-ttu-id="c2f5f-143">BizTalk サーバーでの送信ポートと送信先フォルダの作成</span><span class="sxs-lookup"><span data-stu-id="c2f5f-143">Create the send port and destination folder on the BizTalk server</span></span>  
 <span data-ttu-id="c2f5f-144">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に送信ポートと送信先フォルダーを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-144">Follow these steps to create the send port and destination folder on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span></span>  
  
1.  <span data-ttu-id="c2f5f-145">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ファイル システムにフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-145">Create a folder on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] file system.</span></span> <span data-ttu-id="c2f5f-146">このフォルダが送信ポートの送信先になります。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-146">This will be the destination for the send port.</span></span>  
  
2.  <span data-ttu-id="c2f5f-147">右クリック**送信ポート**、] をクリックして **、[新規**クリックして**静的な一方向送信ポート。**</span><span class="sxs-lookup"><span data-stu-id="c2f5f-147">Right-click **Send Ports**, click **New,** then click **Static one-way Send Port.**</span></span>  
  
3.  <span data-ttu-id="c2f5f-148">**送信ポートのプロパティ** ダイアログ ボックスで、**トランスポートの種類**ボックスで、**ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-148">In the **Send Port Properties** dialog box, in the **Transport Type** box, select **FILE**.</span></span>  
  
4.  <span data-ttu-id="c2f5f-149">**名前**ボックスに、入力**SendToFile**です。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-149">In the **Name** box, type **SendToFile**.</span></span>  
  
5.  <span data-ttu-id="c2f5f-150">**トランスポート**ボックスで、クリックして、**構成**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-150">In the **Transport** box, click the **Configure** button.</span></span>  
  
6.  <span data-ttu-id="c2f5f-151">横に、**コピー先フォルダー**ボックスで、をクリックして**参照**、上に作成したフォルダーを選択して、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、順にクリック **[ok]** です。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-151">Next to the **Destination folder** box, click **Browse**, select the folder that you created on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="c2f5f-152">**ファイル名**ボックスに、入力 **%MessageID%.txt**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-152">In the **File name** box, type **%MessageID%.txt**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="c2f5f-153">**送信パイプライン**ボックスで、 **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**です。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-153">In the **Send Pipeline** box, select **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**.</span></span>  
  
9. <span data-ttu-id="c2f5f-154">**[フィルター]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-154">Click **Filters**.</span></span>  
  
10. <span data-ttu-id="c2f5f-155">**プロパティ**ボックスで、 **BTS です。ReceivePortName**です。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-155">In the **Property** box, select **BTS.ReceivePortName**.</span></span>  
  
11. <span data-ttu-id="c2f5f-156">**値**ボックスに、入力**POP3Receive**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-156">In the **Value** box, type **POP3Receive**, and then click **OK**.</span></span>  
  
## <a name="enable-the-receive-location-and-start-the-send-port"></a><span data-ttu-id="c2f5f-157">受信場所を有効にして、送信ポートの開始</span><span class="sxs-lookup"><span data-stu-id="c2f5f-157">Enable the receive location and start the send port</span></span>  
 <span data-ttu-id="c2f5f-158">受信場所を有効にし、送信ポートを開始するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-158">Follow these steps to enable the receive location and start the send port:</span></span>  
  
1.  <span data-ttu-id="c2f5f-159">右クリックし、 **POP3Receive**受信場所をクリックして**を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-159">Right-click the **POP3Receive** receive location, and then click **Enable**.</span></span>  
  
2.  <span data-ttu-id="c2f5f-160">右クリックし、 **SendToFile**送信ポートをクリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-160">Right-click the **SendToFile** send port, and then click **Start**.</span></span>  
  
 <span data-ttu-id="c2f5f-161">次の手順では、受信場所によって監視されているメールボックスにテスト メッセージを送信することにより、アプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-161">The next step is to test the application by sending a test message to the mailbox monitored by the receive location.</span></span>  
  
## <a name="configure-outlook-express-to-send-an-e-mail-message-to-the-mailbox"></a><span data-ttu-id="c2f5f-162">電子メール メッセージをメールボックスに送信するように Outlook Express を構成</span><span class="sxs-lookup"><span data-stu-id="c2f5f-162">Configure Outlook Express to send an e-mail message to the mailbox</span></span>  
 <span data-ttu-id="c2f5f-163">電子メール メッセージをメールボックスに送信するように Outlook Express を構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-163">Follow these steps to configure Outlook Express to send an e-mail message to the mailbox:</span></span>  
  
1.  <span data-ttu-id="c2f5f-164">をクリックして**開始**、 をポイント**プログラム**、順にクリック**Outlook Express**です。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-164">Click **Start**, point to **Programs**, and then click **Outlook Express**.</span></span>  
  
2.  <span data-ttu-id="c2f5f-165">Outlook Express での**ツール** メニューのをクリックして**アカウント**です。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-165">In Outlook Express, on the **Tools** menu, click **Accounts**.</span></span>  
  
3.  <span data-ttu-id="c2f5f-166">をクリックして**追加** をクリックし、**メール**です。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-166">Click **Add** and then click **Mail**.</span></span>  
  
4.  <span data-ttu-id="c2f5f-167">**表示名**ボックスで、表示名を入力し、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-167">In the **Display name** box, type a display name, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="c2f5f-168">**インターネット電子メール アドレス**] ダイアログ ボックスで、**電子メール アドレス**ボックスに、入力**EmailTest @< domain_name >**、クリックして **[次へ**.</span><span class="sxs-lookup"><span data-stu-id="c2f5f-168">In the **Internet E-mail address** dialog box, in the **E-mail address** box, type **EmailTest@<domain_name>**, and then click **Next**.</span></span>  
  
     <span data-ttu-id="c2f5f-169">適切な値を入力することを確認 *< domain_name >* です。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-169">Make sure to enter the appropriate value for *<domain_name>*.</span></span> <span data-ttu-id="c2f5f-170">この値は、Windows サーバーの POP3 サービスの管理インターフェイスでこのメールボックスを作成したドメインの名前と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-170">This value should match the name of the domain under which this mailbox was created in the POP3 Service Administration interface on the Windows server.</span></span>  
  
6.  <span data-ttu-id="c2f5f-171">**電子メール サーバー名** ダイアログ ボックスで、**受信メール**と**発信メール**ボックスに、サーバー名または Windows server の IP アドレスを入力し、 をクリックして**次へ**です。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-171">In the **E-mail Server names** dialog box, in the **Incoming mail** and **Outgoing mail** boxes, type the server name or IP address of the Windows server, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="c2f5f-172">**インターネット メール ログオン** ダイアログ ボックスで、**アカウント名**ボックスに、入力**EmailTest**です。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-172">In the **Internet Mail Logon** dialog box, in the **Account name** box, type **EmailTest**.</span></span>  
  
8.  <span data-ttu-id="c2f5f-173">**パスワード**ボックスに、select、EmailTest アカウントのパスワードを入力、**パスワードを保存**オプションで、**次**、順にクリック**完了**.</span><span class="sxs-lookup"><span data-stu-id="c2f5f-173">In the **Password** box, type the password for the EmailTest account, select the **Remember password** option, click **Next**, and then click **Finish**.</span></span>  
  
9. <span data-ttu-id="c2f5f-174">作成したアカウントを選択する をクリックし、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-174">Click to select the account that you just created, and then click **Properties**.</span></span>  
  
10. <span data-ttu-id="c2f5f-175">**プロパティ**ダイアログ ボックスで、をクリックして、 **詳細設定**  タブで、オプションを選択してクリックして**サーバーにメッセージのコピーを残す**、順にクリック**ok**.</span><span class="sxs-lookup"><span data-stu-id="c2f5f-175">In the **Properties** dialog box, click the **Advanced** tab, click to select the option to **Leave a copy of messages on the server**, and then click **OK**.</span></span>  
  
11. <span data-ttu-id="c2f5f-176">**インターネット アカウント**ダイアログ ボックスで、をクリックして**閉じる**です。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-176">In the **Internet Accounts** dialog box, click **Close**.</span></span>  
  
12. <span data-ttu-id="c2f5f-177">Outlook Express を使用してテスト メッセージを作成する型**テスト**に、**サブジェクト**フィールド、および種類**EmailTest @< domain_name >** に、 **に**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-177">Use Outlook Express to compose a test message, type **Test** into the **Subject** field, and type **EmailTest@<domain_name>** into the **To** field.</span></span>  
  
13. <span data-ttu-id="c2f5f-178">をクリックして**送信**テスト メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-178">Click **Send** to send the test message.</span></span> <span data-ttu-id="c2f5f-179">確実に、Outlook Express メッセージを送信テストすぐに、をクリックして、**送受信**Outlook Express ツールバーのボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-179">To ensure that Outlook Express sends the test message immediately, click the **Send/Recv** button in the Outlook Express toolbar.</span></span>  
  
## <a name="view-the-message"></a><span data-ttu-id="c2f5f-180">メッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-180">View the message</span></span>  
 <span data-ttu-id="c2f5f-181">メッセージを表示するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-181">Follow these steps to view the message:</span></span>  
  
1.  <span data-ttu-id="c2f5f-182">Windows エクスプ ローラーを使用して、として指定したフォルダーを開く、**コピー先フォルダー**送信ポートのです。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-182">Use Windows Explorer to open the folder that you specified as the **Destination Folder** for the send port.</span></span>  
  
2.  <span data-ttu-id="c2f5f-183">フォルダ内のドキュメントをダブルクリックし、ドキュメントの内容をメモ帳で表示します。</span><span class="sxs-lookup"><span data-stu-id="c2f5f-183">Double click the document in the folder to view the contents of the document in Notepad.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2f5f-184">参照</span><span class="sxs-lookup"><span data-stu-id="c2f5f-184">See Also</span></span>  
 [<span data-ttu-id="c2f5f-185">POP3 アダプターについて</span><span class="sxs-lookup"><span data-stu-id="c2f5f-185">What Is the POP3 Adapter?</span></span>](../core/what-is-the-pop3-adapter.md)