---
title: アダプターをセキュリティで保護するためのベスト プラクティス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, security
- best practices, adapters
- adapters, permissions
- security, adapters
- permissions, adapters
- best practices, security
- adapters, best practices
ms.assetid: 004e1a01-b316-4eee-967f-5a806431de2b
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea93206c296df5c1930e699500aeba8fda253b75
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358157"
---
# <a name="best-practices-for-securing-adapters"></a><span data-ttu-id="7695f-102">アダプターをセキュリティで保護するためのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="7695f-102">Best Practices for Securing Adapters</span></span>
<span data-ttu-id="7695f-103">このトピックでは、アダプターのセキュリティに関するベスト プラクティスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7695f-103">This topic provides a list of best practices for adapter security.</span></span>  
  
 <span data-ttu-id="7695f-104">**コンピューターで信頼されていないアダプターをインストールしないでください。認定されたアダプター開発パートナーのみを使用します。**</span><span class="sxs-lookup"><span data-stu-id="7695f-104">**Do not install untrusted adapters on your computer; use only certified adapter development partners.**</span></span>  
  
 <span data-ttu-id="7695f-105">**既定のアダプター スキーマでは、顧客の機密データを格納しないでください。**</span><span class="sxs-lookup"><span data-stu-id="7695f-105">**Do not store sensitive customer data in the default adapter schema.**</span></span>  
  
 <span data-ttu-id="7695f-106">ユーザー名とパスワードの情報を構成するのは、アダプターの展開後にしてください。</span><span class="sxs-lookup"><span data-stu-id="7695f-106">You should configure the user name and password information only after you deploy an adapter.</span></span> <span data-ttu-id="7695f-107">アダプターの展開後であれば、それらの情報は SSO データベースに格納されます。</span><span class="sxs-lookup"><span data-stu-id="7695f-107">This ensures that the information gets stored in the SSO database.</span></span> <span data-ttu-id="7695f-108">SSO データベースの詳細については、次を参照してください。[を使用して SSO](../core/using-sso.md)します。</span><span class="sxs-lookup"><span data-stu-id="7695f-108">For more information about the SSO database, see [Using SSO](../core/using-sso.md).</span></span>  
  
 <span data-ttu-id="7695f-109">**共有フォルダー (受信フォルダーと送信フォルダー) 選択し、ファイルおよび EDI アダプターを使用してファイルの削除に使用するには、次の権限を付与するには。**</span><span class="sxs-lookup"><span data-stu-id="7695f-109">**Grant the following permissions on the shared folders (the Receive folder and Send folder) that are used to pick up and drop files using the File and EDI adapters:**</span></span>  
  
- <span data-ttu-id="7695f-110">**受信フォルダー**</span><span class="sxs-lookup"><span data-stu-id="7695f-110">**Receive  folder**</span></span>  
  
   <span data-ttu-id="7695f-111">ファイル アダプターで使用する受信フォルダーは、受信場所で構成できます。</span><span class="sxs-lookup"><span data-stu-id="7695f-111">The receive folder for the File adapter is configurable on the receive location.</span></span> <span data-ttu-id="7695f-112">EDI アダプターで使用する受信フォルダーは、受信ハンドラーで構成できます。</span><span class="sxs-lookup"><span data-stu-id="7695f-112">The receive folder for the EDI adapter is configurable on the receive handler.</span></span> <span data-ttu-id="7695f-113">ファイルを取得する BizTalk ホストのサービス アカウントには、ファイルシステム レベルで次のアクセス許可を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7695f-113">The service account for the BizTalk Host that picks up the file should have the following permissions at the file-system level:</span></span>  
  
  - <span data-ttu-id="7695f-114">フォルダーの一覧表示/データの読み取り</span><span class="sxs-lookup"><span data-stu-id="7695f-114">List Folder / Read Data</span></span>  
  
  - <span data-ttu-id="7695f-115">サブフォルダーとファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="7695f-115">Delete SubFolder and Files</span></span>  
  
    <span data-ttu-id="7695f-116">受信フォルダーがネットワーク共有上にある場合、ファイル共有レベルで次のアクセス許可を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7695f-116">If the receive folder is on a network share, the following permissions must be granted at the file-share level:</span></span>  
  
  - <span data-ttu-id="7695f-117">ファイルを取得する BizTalk ホストのサービス アカウントには、フル コントロール アクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="7695f-117">The service account for the BizTalk Host that picks up the file must have Full Control permissions.</span></span>  
  
  - [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="7695f-118">管理者には、トラブルシューティングのためにフル コントロール アクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="7695f-118">administrators must have Full Control permissions for troubleshooting.</span></span>  
  
  - <span data-ttu-id="7695f-119">この場所にファイルをドロップする外部のユーザーまたはプログラムには、書き込みアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="7695f-119">The external user or programs that drop files to this location must have Write permissions.</span></span>  
  
- <span data-ttu-id="7695f-120">**送信フォルダー**</span><span class="sxs-lookup"><span data-stu-id="7695f-120">**Send folder**</span></span>  
  
   <span data-ttu-id="7695f-121">ファイル アダプターおよび EDI アダプターで使用する送信フォルダーは、送信ポートで構成できます。</span><span class="sxs-lookup"><span data-stu-id="7695f-121">The send folder for the File and EDI adapters are configurable on the send port.</span></span>  
  
  - <span data-ttu-id="7695f-122">ファイルをドロップする BizTalk ホストのサービス アカウントには、書き込みアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="7695f-122">The service account for the BizTalk Host or Hosts that drop files here must have Write permissions.</span></span>  
  
  - [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="7695f-123">管理者には、フル コントロール アクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="7695f-123">administrators must have Full Control permissions.</span></span>  
  
  - <span data-ttu-id="7695f-124">ファイルを取得する外部のユーザーまたはプログラムには、読み取りアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="7695f-124">The external user or program that picks up files must have Read permissions.</span></span>  
  
  <span data-ttu-id="7695f-125">**EDI サービスが BTS_HOST_USERS SQL ロールに実行されているユーザー アカウントを追加します。**</span><span class="sxs-lookup"><span data-stu-id="7695f-125">**Add the user account under which the EDI service is running to the BTS_HOST_USERS SQL role.**</span></span>  
  
  <span data-ttu-id="7695f-126">これは、機能は、管理者権限のない BizTalk エクスプ ローラー オブジェクトの管理 (OM) へのアクセスを取得できるように、必要です。</span><span class="sxs-lookup"><span data-stu-id="7695f-126">This is required so that you can obtain BizTalk Explorer Object Management (OM) Access without administrative permissions.</span></span> <span data-ttu-id="7695f-127">ユーザー アカウントを追加するには、BizTalk 管理データベース BizTalkMgmtDb の BTS_HOST_USERS ロールに "EDI Subsystem Users" を追加します。</span><span class="sxs-lookup"><span data-stu-id="7695f-127">To do this, add "EDI Subsystem Users" to the BTS_HOST_USERS role in the BizTalk Management database, BizTalkMgmtDb.</span></span>  
  
  <span data-ttu-id="7695f-128">SQL Server 2005 で BTS_HOST_USERS ロールに "EDI Subsystem Users" を追加するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7695f-128">To add "EDI Subsystem Users" to the BTS_HOST_USERS role on SQL Server 2005, complete the following steps:</span></span>  
  
1. <span data-ttu-id="7695f-129">SQL Server Management Studio を起動**スタートでは、プログラム、Microsoft SQL Server 2008**します。</span><span class="sxs-lookup"><span data-stu-id="7695f-129">Launch SQL Server Management Studio from **Start, Programs, Microsoft SQL Server 2008**.</span></span>  
  
2. <span data-ttu-id="7695f-130">BizTalk 管理データベースを格納する SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="7695f-130">Connect to the SQL Server that houses your BizTalk Management database.</span></span>  
  
3. <span data-ttu-id="7695f-131">オブジェクト エクスプローラーでこのサーバーを展開します。</span><span class="sxs-lookup"><span data-stu-id="7695f-131">Expand this server in the Object Explorer.</span></span>  
  
4. <span data-ttu-id="7695f-132">展開**データベース**、BizTalk 管理データベースを順に展開します。</span><span class="sxs-lookup"><span data-stu-id="7695f-132">Expand **Databases**, and then expand the BizTalk Management database.</span></span>  
  
5. <span data-ttu-id="7695f-133">展開**セキュリティ**、展開**ロール**、クリックして選択し、**データベース ロール**</span><span class="sxs-lookup"><span data-stu-id="7695f-133">Expand **Security**, expand **Roles**, and then click to select **Database Roles**</span></span>  
  
6. <span data-ttu-id="7695f-134">詳細ペインで BTS_HOST_USERS ロールを右クリックし をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="7695f-134">In the details pane, right-click the BTS_HOST_USERS role, and then click **Properties**.</span></span>  
  
7. <span data-ttu-id="7695f-135">BTS_HOST_USERS ダイアログ ボックスで、**追加**、 をクリックして**参照**、EDI Subsystem Users グループに追加の横にあるボックスを確認します。</span><span class="sxs-lookup"><span data-stu-id="7695f-135">In the BTS_HOST_USERS dialog box, click **Add**, click **Browse**, and then check the box next to the EDI Subsystem Users group to add it.</span></span>  
  
    <span data-ttu-id="7695f-136">追加するユーザーの一覧に EDI Subsystem Users グループが表示されない場合、EDI Subsystem Users グループを新しいデータベース ユーザーとして BizTalk 管理データベースに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7695f-136">If the EDI Subsystem Users group is not available in the list of users to add, you must add the EDI Subsystem Users group as a new database user to the BizTalk Management database.</span></span> <span data-ttu-id="7695f-137">EDI Subsystem Users グループを新しいデータベース ユーザーとして追加するには、SQL Server Management Studio で次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7695f-137">To add the EDI Subsystem Users group as a new database user, complete the following steps in SQL Server Management Studio:</span></span>  
  
   1.  <span data-ttu-id="7695f-138">BizTalk 管理データベースを展開します。</span><span class="sxs-lookup"><span data-stu-id="7695f-138">Expand the BizTalk Management database.</span></span>  
  
   2.  <span data-ttu-id="7695f-139">展開**セキュリティ**します。</span><span class="sxs-lookup"><span data-stu-id="7695f-139">Expand **Security**.</span></span>  
  
   3.  <span data-ttu-id="7695f-140">右クリック**ユーザー**クリック**新しいユーザー**します。</span><span class="sxs-lookup"><span data-stu-id="7695f-140">Right-click **Users** and click **New User**.</span></span>  
  
   4.  <span data-ttu-id="7695f-141">テキスト ボックスの横にある省略記号 (...) ボタンをクリックします。**ログイン名**を表示する、**ログインの選択** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="7695f-141">Click the ellipses (…) button next to the text box for **Login name** to display the **Select Login** dialog box.</span></span>  
  
   5.  <span data-ttu-id="7695f-142">参照 ボタンをクリックして、入力、 **EDI Subsystem Users**グループ化、および順にクリックします**ok をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="7695f-142">Click the Browse button, enter the **EDI Subsystem Users** group, and then click **OK.**</span></span> <span data-ttu-id="7695f-143">メッセージが表示されたら、**見つかった複数のオブジェクト**ダイアログ ボックスで、 **EDI Subsystem Users**ログインとクリック **[ok]** します。</span><span class="sxs-lookup"><span data-stu-id="7695f-143">If prompted with the **Multiple Objects Found** dialog box, select the **EDI Subsystem Users** login and click **OK**.</span></span>  
  
   6.  <span data-ttu-id="7695f-144">**データベース ユーザー - 新規**ダイアログ ボックスの入力**EDI Subsystem Users**の**ユーザー名**テキスト ボックス をクリック**ok**します。</span><span class="sxs-lookup"><span data-stu-id="7695f-144">On the **Database User - New** dialog box enter **EDI Subsystem Users** for the **User name** textbox and click **OK**.</span></span>  
  
   <span data-ttu-id="7695f-145">**BizTalk サービスが EDI Subsystem Users グループに実行されているユーザー アカウントを追加します。**</span><span class="sxs-lookup"><span data-stu-id="7695f-145">**Add the user account under which the BizTalk service is running to the EDI Subsystem Users group.**</span></span>  
  
   <span data-ttu-id="7695f-146">次の手順に従い、BizTalk サービス用のユーザー アカウントを EDI Subsystem Users グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="7695f-146">Follow these steps to add the user account for the BizTalk service to the EDI Subsystem Users group.</span></span>  
  
-   <span data-ttu-id="7695f-147">**BizTalk Server を構成するにはドメイン グループを使用する: 場合**</span><span class="sxs-lookup"><span data-stu-id="7695f-147">**If BizTalk Server is configured to use domain groups:**</span></span>  
  
    1.  <span data-ttu-id="7695f-148">ドメイン内の Windows Server コンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="7695f-148">Logon to a Windows Server computer in the domain.</span></span>  
  
    2.  <span data-ttu-id="7695f-149">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**管理ツール**、順にクリックします**Active Directory ユーザーとコンピューター**します。</span><span class="sxs-lookup"><span data-stu-id="7695f-149">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="7695f-150">オブジェクトを変更する適切なドメイン レベルのアクセス許可が必要、 **Active Directory ユーザーとコンピューター**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="7695f-150">You must have appropriate domain level permissions to modify objects in the **Active Directory Users and Computers** interface.</span></span>  
  
    3.  <span data-ttu-id="7695f-151">ドメインのコンテナーを展開し、クリックして展開、**ユーザー**コンテナー。</span><span class="sxs-lookup"><span data-stu-id="7695f-151">Click to expand the domain container and click to expand the **Users** container.</span></span>  
  
    4.  <span data-ttu-id="7695f-152">ダブルクリック、 **EDI Subsystem Users**グループをこのグループのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="7695f-152">Double click the **EDI Subsystem Users** group to display the properties for this group.</span></span>  
  
    5.  <span data-ttu-id="7695f-153">をクリックして、**メンバー**のタブ、 **EDI Subsystem Users**グループ ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="7695f-153">Click the **Members** tab of the **EDI Subsystem Users** group dialog.</span></span>  
  
    6.  <span data-ttu-id="7695f-154">をクリックして、**追加**このグループに BizTalk サービスのユーザー アカウントを追加するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="7695f-154">Click the **Add** button to add the user account for the BizTalk Service to this group.</span></span>  
  
    7.  <span data-ttu-id="7695f-155">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7695f-155">Click **OK**.</span></span>  
  
-   <span data-ttu-id="7695f-156">**BizTalk Server を構成して、ローカル グループを使用します。 場合、**</span><span class="sxs-lookup"><span data-stu-id="7695f-156">**If BizTalk Server is configured to use local groups:**</span></span>  
  
    1.  <span data-ttu-id="7695f-157">BizTalk Server にログオンします。</span><span class="sxs-lookup"><span data-stu-id="7695f-157">Logon to the BizTalk Server.</span></span>  
  
    2.  <span data-ttu-id="7695f-158">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**管理ツール**、順にクリックします**コンピュータの管理**します。</span><span class="sxs-lookup"><span data-stu-id="7695f-158">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Computer Management**.</span></span>  
  
    3.  <span data-ttu-id="7695f-159">クリックして展開**システム ツール**をクリックして展開**ローカル ユーザーとグループ**をクリックして展開**グループ**します。</span><span class="sxs-lookup"><span data-stu-id="7695f-159">Click to expand **System Tools**, click to expand **Local Users and Groups**, and click to expand **Groups**.</span></span>  
  
    4.  <span data-ttu-id="7695f-160">ダブルクリック、 **EDI Subsystem Users**グループをこのグループのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="7695f-160">Double click the **EDI Subsystem Users** group to display the properties for this group.</span></span>  
  
    5.  <span data-ttu-id="7695f-161">をクリックして、**追加**BizTalk サービスのユーザー アカウントをこのグループに追加するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="7695f-161">Click the **Add** button to add the user account for the BizTalk service to this group.</span></span>  
  
    6.  <span data-ttu-id="7695f-162">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7695f-162">Click **OK**.</span></span>