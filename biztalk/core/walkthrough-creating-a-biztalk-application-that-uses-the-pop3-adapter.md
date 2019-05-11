---
title: 'チュートリアル: POP3 アダプタを使用する BizTalk アプリケーションの作成 |Microsoft Docs'
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
ms.openlocfilehash: 6f94c34361eb69f2e9838da26a3ea30f95cb3a85
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65250208"
---
# <a name="walkthrough-creating-a-biztalk-application-that-uses-the-pop3-adapter"></a><span data-ttu-id="a6829-102">チュートリアル: POP3 アダプタを使用する BizTalk アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="a6829-102">Walkthrough: Creating a BizTalk Application That Uses the POP3 Adapter</span></span>
<span data-ttu-id="a6829-103">このセクションで簡単な Microsoft の作成手順は[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]POP3 アダプターを使用するアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="a6829-103">This section takes you through creating a simple Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application using the POP3 adapter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a6829-104">アプリケーションでは、Microsoft を実行しているコンピューターへのアクセスがあると想定[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]または[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]電子メール サービスをインストールして構成します。</span><span class="sxs-lookup"><span data-stu-id="a6829-104">The application assumes that you have access to a computer running Microsoft [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] with Email Services installed and configured.</span></span> <span data-ttu-id="a6829-105">構成について[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]または[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]を電子メール サービスと共に Windows Server のヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6829-105">For information about configuring [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] with Email Services see Windows Server Help.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="a6829-106">この例での電子メール クライアントとして Microsoft Outlook Express を使用し、[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]または[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]電子メール サーバーとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="a6829-106">In this example Microsoft Outlook Express is used as the e-mail client and [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] is used as the e-mail server.</span></span> <span data-ttu-id="a6829-107">ただし、任意の POP3 電子メール クライアントと RFC 準拠の POP3 サーバーをこのシナリオで使用できます。</span><span class="sxs-lookup"><span data-stu-id="a6829-107">However, any POP3 e-mail client and RFC-compliant POP3 server could be used for this scenario.</span></span>  
  
 <span data-ttu-id="a6829-108">このアプリケーションは、または受信場所、送信ポートにまだ作成するいないと仮定します。</span><span class="sxs-lookup"><span data-stu-id="a6829-108">This application assumes that you have not yet created any send ports or receive locations.</span></span> <span data-ttu-id="a6829-109">既存の送信ポートまたは受信場所がある場合、手順を実行する際に適切な名前に置き換えてください。</span><span class="sxs-lookup"><span data-stu-id="a6829-109">If you have existing send ports or receive locations, substitute appropriate names when you work through the steps.</span></span>  
  
 <span data-ttu-id="a6829-110">アプリケーションは、単純なコンテンツ ベース ルーティング アプリケーションのみを受信場所と送信ポートを使用しています。</span><span class="sxs-lookup"><span data-stu-id="a6829-110">The application is a simple content-based routing application using only a receive location and a send port.</span></span> <span data-ttu-id="a6829-111">受信場所を実行しているサーバー上のメールボックスから読み取り[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]または[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]("Windows server"\)します。</span><span class="sxs-lookup"><span data-stu-id="a6829-111">The receive location reads from a mailbox on the server running [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]("the Windows server"\).</span></span> <span data-ttu-id="a6829-112">送信ポートの受信場所からメッセージを受け取るし、のローカル ファイル システム上のフォルダーに送信します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="a6829-112">The send port takes the message from the receive location and sends it to a folder on the local file system of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="a6829-113">アプリケーションを作成するには、メールボックスの作成、設定する必要がある、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]受信場所と送信ポート、送信ポートの開始し、受信場所を有効にして、メールボックスにテスト メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="a6829-113">To create the application, you have to create the mailbox, set up the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location and send port, start the send port and enable the receive location, and send a test message to the mailbox.</span></span> <span data-ttu-id="a6829-114">アプリケーションを作成するのには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="a6829-114">Follow the steps below to create the application.</span></span>  
  
## <a name="create-a-mailbox-on-windows-server-2003"></a><span data-ttu-id="a6829-115">Windows Server 2003 でメールボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="a6829-115">Create a mailbox on Windows Server 2003</span></span>  
 <span data-ttu-id="a6829-116">電子メール サービスがインストールされている Windows Server 2003 のメールボックスを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a6829-116">To create a mailbox on Windows Server 2003 with Email Services installed, follow these steps:</span></span>  
  
1. <span data-ttu-id="a6829-117">クリックして**開始**、 をポイント**プログラム**、 をポイント**管理ツール**、順にクリックします**POP3 サービス**します。</span><span class="sxs-lookup"><span data-stu-id="a6829-117">Click **Start**, point to **Programs**, point to **Administrative Tools**, and then click **POP3 Service**.</span></span>  
  
2. <span data-ttu-id="a6829-118">展開*\<servername\>* メールボックスを作成するドメインをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6829-118">Expand *\<servername\>* and click the domain where you would like to create a mailbox.</span></span>  
  
3. <span data-ttu-id="a6829-119">**POP3 サービス**ダイアログ ボックスの右側のウィンドウで、クリックして、**メールボックスの追加**オプション。</span><span class="sxs-lookup"><span data-stu-id="a6829-119">In the **POP3 Service** dialog box, in the right pane, click the **Add Mailbox** option.</span></span>  
  
4. <span data-ttu-id="a6829-120">**メールボックスの追加** ダイアログ ボックスで、**メールボックス名**ボックスに「 **EmailTest**します。</span><span class="sxs-lookup"><span data-stu-id="a6829-120">In the **Add Mailbox** dialog box, in the **Mailbox Name** box, type **EmailTest**.</span></span>  
  
5. <span data-ttu-id="a6829-121">選択、**を作成するには、このメールボックスのユーザーが関連付けられている**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="a6829-121">Select the **Create associated user for this mailbox** check box.</span></span>  
  
6. <span data-ttu-id="a6829-122">**パスワード**と**パスワードの確認**ボックス、パスワードを入力し、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="a6829-122">In the **Password** and **Confirm Password** boxes, type a password, and then click **OK**.</span></span>  
  
7. <span data-ttu-id="a6829-123">書き留めて、**アカウント名**と**メール サーバー**にクリア テキスト認証で使用するために表示される情報のログオン、 **POP3 サービス** ダイアログ ボックスをクリック**OK**します。</span><span class="sxs-lookup"><span data-stu-id="a6829-123">Make a note of the **Account name** and **Mail Server** log on information displayed for use with clear text authentication in the **POP3 Service** dialog box, and then click **OK**.</span></span> <span data-ttu-id="a6829-124">この情報を使って、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]受信トランスポートの種類 POP3 で構成する場所。</span><span class="sxs-lookup"><span data-stu-id="a6829-124">This information will be used by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location that you configure with the POP3 transport type.</span></span>  
  
## <a name="create-the-receive-location"></a><span data-ttu-id="a6829-125">受信場所を作成します。</span><span class="sxs-lookup"><span data-stu-id="a6829-125">Create the receive location</span></span>  
 <span data-ttu-id="a6829-126">受信場所を作成する次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="a6829-126">Follow these steps to create the receive location:</span></span>  
  
1. <span data-ttu-id="a6829-127">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールは、既定のデータベースをダブルクリックして**\<** <em>machine_name</em>**\>します。>.biztalkmgmtdb.dbo**ここで、 *machine_name*コンピューターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a6829-127">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console double-click the default database **\<**<em>machine_name</em>**\>.BizTalkMgmtDb.dbo**, where *machine_name* is the name of your computer.</span></span> <span data-ttu-id="a6829-128">クリックして**アプリケーション**、 をクリックし、 **biztalk.application.1**します。</span><span class="sxs-lookup"><span data-stu-id="a6829-128">Click **Applications**, then click **BizTalk.Application.1**.</span></span>  
  
2. <span data-ttu-id="a6829-129">右クリックして**受信ポート**、 をクリックして**新規**、 をクリックして**一方向受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="a6829-129">Right-click **Receive Ports**, click **New**, click **One-way receive port**.</span></span>  
  
3. <span data-ttu-id="a6829-130">**受信ポートのプロパティ** ダイアログ ボックスで、**名前**ボックスに「 **POP3Receive**します。</span><span class="sxs-lookup"><span data-stu-id="a6829-130">In the **Receive Port Properties** dialog box, in the **Name** box, type **POP3Receive**.</span></span>  
  
4. <span data-ttu-id="a6829-131">クリックして**受信場所**、 をクリックし、**新規**します。</span><span class="sxs-lookup"><span data-stu-id="a6829-131">Click **Receive Locations**, and then click **New**.</span></span>  <span data-ttu-id="a6829-132">**受信場所のプロパティ** ダイアログ ボックスで、**名前**ボックスに「 **POP3Receive**します。</span><span class="sxs-lookup"><span data-stu-id="a6829-132">In the **Receive Location Properties** dialog box, in the **Name** box, type **POP3Receive**.</span></span>  
  
5. <span data-ttu-id="a6829-133">**トランスポートの種類**ボックスで、 **POP3**します。</span><span class="sxs-lookup"><span data-stu-id="a6829-133">In the **Transport Type** box, select **POP3**.</span></span>  
  
6. <span data-ttu-id="a6829-134">**受信ハンドラー**ボックスで、 **BizTalkServerApplication**します。</span><span class="sxs-lookup"><span data-stu-id="a6829-134">In the **Receive Handler** box, select **BizTalkServerApplication**.</span></span>  
  
7. <span data-ttu-id="a6829-135">**受信パイプライン**ボックスで、 **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**します。</span><span class="sxs-lookup"><span data-stu-id="a6829-135">In the **Receive Pipeline** box, select **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**.</span></span>  
  
8. <span data-ttu-id="a6829-136">**トランスポート**ボックスで、、**構成**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6829-136">In the **Transport** box, click the **Configure** button.</span></span>  
  
9. <span data-ttu-id="a6829-137">**POP3 トランスポートのプロパティ** ダイアログ ボックスで、 **MIME デコードの適用**ボックスで、 **False**します。</span><span class="sxs-lookup"><span data-stu-id="a6829-137">In the **POP3 Transport Properties** dialog box, in the **Apply MIME Decoding** box, select **False**.</span></span>  
  
10. <span data-ttu-id="a6829-138">**メール サーバー**ボックスに、メールボックスを作成した Windows Server ベースのサーバーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a6829-138">In the **Mail Server** box, type the name of the Windows Server-based server where you created a mailbox.</span></span>  
  
11. <span data-ttu-id="a6829-139">**認証スキーム**ボックスで、**基本的な**します。</span><span class="sxs-lookup"><span data-stu-id="a6829-139">In the **Authentication Scheme** box, select **Basic**.</span></span>  
  
12. <span data-ttu-id="a6829-140">**パスワード**ボックスで、ドロップダウン矢印をクリックし、メールボックスのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="a6829-140">In the **Password** box, click the drop-down arrow and type the password for the mailbox.</span></span>  
  
13. <span data-ttu-id="a6829-141">**ユーザー名**ボックスに、たとえば、メールボックスの完全修飾ユーザー名を入力<em>username@host.domain.toplevel_domainします。</em></span><span class="sxs-lookup"><span data-stu-id="a6829-141">In the **User Name** box, type the fully qualified user name for the mailbox, for example <em>username@host.domain.toplevel_domain.</em></span></span>  
  
14. <span data-ttu-id="a6829-142">**のポーリング間隔**ボックスに「 **1**、 をクリックして**ok**順にクリックします**OK**もう一度です。</span><span class="sxs-lookup"><span data-stu-id="a6829-142">In the **Polling Interval** box, type **1**, click **OK**, and then click **OK** again.</span></span>  
  
## <a name="create-the-send-port-and-destination-folder-on-the-biztalk-server"></a><span data-ttu-id="a6829-143">BizTalk server に送信ポートと送信先フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="a6829-143">Create the send port and destination folder on the BizTalk server</span></span>  
 <span data-ttu-id="a6829-144">送信ポートと送信先のフォルダを作成する次の手順に従って、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="a6829-144">Follow these steps to create the send port and destination folder on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span></span>  
  
1. <span data-ttu-id="a6829-145">フォルダーを作成、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ファイル システム。</span><span class="sxs-lookup"><span data-stu-id="a6829-145">Create a folder on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] file system.</span></span> <span data-ttu-id="a6829-146">送信ポートの送信先になります。</span><span class="sxs-lookup"><span data-stu-id="a6829-146">This will be the destination for the send port.</span></span>  
  
2. <span data-ttu-id="a6829-147">右クリック**送信ポート**、 をクリックして**新規、**  をクリックし、**静的な一方向送信ポート。**</span><span class="sxs-lookup"><span data-stu-id="a6829-147">Right-click **Send Ports**, click **New,** then click **Static one-way Send Port.**</span></span>  
  
3. <span data-ttu-id="a6829-148">**送信ポートのプロパティ** ダイアログ ボックスで、**トランスポートの種類**ボックスで、**ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="a6829-148">In the **Send Port Properties** dialog box, in the **Transport Type** box, select **FILE**.</span></span>  
  
4. <span data-ttu-id="a6829-149">**名前**ボックスに「 **SendToFile**します。</span><span class="sxs-lookup"><span data-stu-id="a6829-149">In the **Name** box, type **SendToFile**.</span></span>  
  
5. <span data-ttu-id="a6829-150">**トランスポート**ボックスで、、**構成**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6829-150">In the **Transport** box, click the **Configure** button.</span></span>  
  
6. <span data-ttu-id="a6829-151">横に、**先フォルダー**ボックスで、**参照**、上に作成したフォルダーを選択して、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、順にクリックします **[ok]**。</span><span class="sxs-lookup"><span data-stu-id="a6829-151">Next to the **Destination folder** box, click **Browse**, select the folder that you created on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and then click **OK**.</span></span>  
  
7. <span data-ttu-id="a6829-152">**ファイル名**ボックスに「 **%MessageID%.txt**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="a6829-152">In the **File name** box, type **%MessageID%.txt**, and then click **OK**.</span></span>  
  
8. <span data-ttu-id="a6829-153">**送信パイプライン**ボックスで、 **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**します。</span><span class="sxs-lookup"><span data-stu-id="a6829-153">In the **Send Pipeline** box, select **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**.</span></span>  
  
9. <span data-ttu-id="a6829-154">**[フィルター]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6829-154">Click **Filters**.</span></span>  
  
10. <span data-ttu-id="a6829-155">**プロパティ**ボックスで、 **BTS します。ReceivePortName**します。</span><span class="sxs-lookup"><span data-stu-id="a6829-155">In the **Property** box, select **BTS.ReceivePortName**.</span></span>  
  
11. <span data-ttu-id="a6829-156">**値**ボックスに「 **POP3Receive**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="a6829-156">In the **Value** box, type **POP3Receive**, and then click **OK**.</span></span>  
  
## <a name="enable-the-receive-location-and-start-the-send-port"></a><span data-ttu-id="a6829-157">受信場所を有効にして、送信ポートの開始</span><span class="sxs-lookup"><span data-stu-id="a6829-157">Enable the receive location and start the send port</span></span>  
 <span data-ttu-id="a6829-158">受信場所を有効にして、送信ポートを開始する次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="a6829-158">Follow these steps to enable the receive location and start the send port:</span></span>  
  
1. <span data-ttu-id="a6829-159">右クリックし、 **POP3Receive**受信場所をクリックして**を有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="a6829-159">Right-click the **POP3Receive** receive location, and then click **Enable**.</span></span>  
  
2. <span data-ttu-id="a6829-160">右クリックし、 **SendToFile**送信ポート、およびクリックして**開始**します。</span><span class="sxs-lookup"><span data-stu-id="a6829-160">Right-click the **SendToFile** send port, and then click **Start**.</span></span>  
  
   <span data-ttu-id="a6829-161">次の手順では、テスト メッセージを受信場所で監視するメールボックスに送信することによって、アプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="a6829-161">The next step is to test the application by sending a test message to the mailbox monitored by the receive location.</span></span>  
  
## <a name="configure-outlook-express-to-send-an-e-mail-message-to-the-mailbox"></a><span data-ttu-id="a6829-162">Outlook Express メールボックスへの電子メール メッセージの送信を構成します。</span><span class="sxs-lookup"><span data-stu-id="a6829-162">Configure Outlook Express to send an e-mail message to the mailbox</span></span>  
 <span data-ttu-id="a6829-163">Outlook Express メールボックスへの電子メール メッセージの送信を構成するこれらの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="a6829-163">Follow these steps to configure Outlook Express to send an e-mail message to the mailbox:</span></span>  
  
1.  <span data-ttu-id="a6829-164">クリックして**開始**、 をポイント**プログラム**、順にクリックします**Outlook Express**します。</span><span class="sxs-lookup"><span data-stu-id="a6829-164">Click **Start**, point to **Programs**, and then click **Outlook Express**.</span></span>  
  
2.  <span data-ttu-id="a6829-165">Outlook Express での**ツール** メニューのをクリックして**アカウント**します。</span><span class="sxs-lookup"><span data-stu-id="a6829-165">In Outlook Express, on the **Tools** menu, click **Accounts**.</span></span>  
  
3.  <span data-ttu-id="a6829-166">クリックして**追加** をクリックし、**メール**します。</span><span class="sxs-lookup"><span data-stu-id="a6829-166">Click **Add** and then click **Mail**.</span></span>  
  
4.  <span data-ttu-id="a6829-167">**表示名**ボックスで、表示名を入力し、 をクリックし、**次**します。</span><span class="sxs-lookup"><span data-stu-id="a6829-167">In the **Display name** box, type a display name, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="a6829-168">**インターネット電子メール アドレス** ダイアログ ボックスで、**電子メール アドレス**ボックスに「 **EmailTest @< domain_name >**、順にクリックします**次**.</span><span class="sxs-lookup"><span data-stu-id="a6829-168">In the **Internet E-mail address** dialog box, in the **E-mail address** box, type **EmailTest@<domain_name>**, and then click **Next**.</span></span>  
  
     <span data-ttu-id="a6829-169">適切な値を入力してください *< domain_name >* します。</span><span class="sxs-lookup"><span data-stu-id="a6829-169">Make sure to enter the appropriate value for *<domain_name>*.</span></span> <span data-ttu-id="a6829-170">この値は、Windows サーバーの POP3 サービスの管理インターフェイスでこのメールボックスが作成されるドメインの名前と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6829-170">This value should match the name of the domain under which this mailbox was created in the POP3 Service Administration interface on the Windows server.</span></span>  
  
6.  <span data-ttu-id="a6829-171">**電子メール サーバー名** ダイアログ ボックスで、**受信メール**と**送信メール**ボックス、サーバー名または Windows server の IP アドレスを入力および順にクリックします**次へ**します。</span><span class="sxs-lookup"><span data-stu-id="a6829-171">In the **E-mail Server names** dialog box, in the **Incoming mail** and **Outgoing mail** boxes, type the server name or IP address of the Windows server, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="a6829-172">**インターネット メール ログオン** ダイアログ ボックスで、**アカウント名**ボックスに「 **EmailTest**します。</span><span class="sxs-lookup"><span data-stu-id="a6829-172">In the **Internet Mail Logon** dialog box, in the **Account name** box, type **EmailTest**.</span></span>  
  
8.  <span data-ttu-id="a6829-173">**パスワード**ボックスに、選択、EmailTest アカウントのパスワードを入力、**パスワードを保存**オプションで、をクリックして**次**、順にクリックします **[完了]**.</span><span class="sxs-lookup"><span data-stu-id="a6829-173">In the **Password** box, type the password for the EmailTest account, select the **Remember password** option, click **Next**, and then click **Finish**.</span></span>  
  
9. <span data-ttu-id="a6829-174">作成したアカウントの選択をクリックし、クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="a6829-174">Click to select the account that you just created, and then click **Properties**.</span></span>  
  
10. <span data-ttu-id="a6829-175">**プロパティ**ダイアログ ボックスで、をクリックして、 **[詳細設定]** ] タブでオプションを選択する [**メッセージのコピーをサーバーに置く**、順にクリックします **[ok]**.</span><span class="sxs-lookup"><span data-stu-id="a6829-175">In the **Properties** dialog box, click the **Advanced** tab, click to select the option to **Leave a copy of messages on the server**, and then click **OK**.</span></span>  
  
11. <span data-ttu-id="a6829-176">**インターネット アカウント**ダイアログ ボックスで、をクリックして**閉じる**します。</span><span class="sxs-lookup"><span data-stu-id="a6829-176">In the **Internet Accounts** dialog box, click **Close**.</span></span>  
  
12. <span data-ttu-id="a6829-177">Outlook Express を使用して、テスト メッセージを作成する型**テスト**に、**サブジェクト**フィールド、および種類**EmailTest @< domain_name >** に、 **に**フィールド。</span><span class="sxs-lookup"><span data-stu-id="a6829-177">Use Outlook Express to compose a test message, type **Test** into the **Subject** field, and type **EmailTest@<domain_name>** into the **To** field.</span></span>  
  
13. <span data-ttu-id="a6829-178">クリックして**送信**テスト メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="a6829-178">Click **Send** to send the test message.</span></span> <span data-ttu-id="a6829-179">確実に、Outlook Express メッセージを送信テストすぐに、次のようにクリックします。、**送受信**、Outlook Express ツールバーのボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6829-179">To ensure that Outlook Express sends the test message immediately, click the **Send/Recv** button in the Outlook Express toolbar.</span></span>  
  
## <a name="view-the-message"></a><span data-ttu-id="a6829-180">メッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="a6829-180">View the message</span></span>  
 <span data-ttu-id="a6829-181">メッセージを表示する次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="a6829-181">Follow these steps to view the message:</span></span>  
  
1.  <span data-ttu-id="a6829-182">Windows エクスプ ローラーを使用して、として指定したフォルダーを開き、**先フォルダー**送信ポートの。</span><span class="sxs-lookup"><span data-stu-id="a6829-182">Use Windows Explorer to open the folder that you specified as the **Destination Folder** for the send port.</span></span>  
  
2.  <span data-ttu-id="a6829-183">メモ帳で、ドキュメントの内容を表示するフォルダー内のドキュメントをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6829-183">Double click the document in the folder to view the contents of the document in Notepad.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6829-184">参照</span><span class="sxs-lookup"><span data-stu-id="a6829-184">See Also</span></span>  
 [<span data-ttu-id="a6829-185">POP3 アダプターについて</span><span class="sxs-lookup"><span data-stu-id="a6829-185">What Is the POP3 Adapter?</span></span>](../core/what-is-the-pop3-adapter.md)