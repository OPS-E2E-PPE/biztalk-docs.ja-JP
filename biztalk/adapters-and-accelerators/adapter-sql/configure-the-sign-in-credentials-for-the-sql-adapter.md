---
title: SQL アダプタの資格情報 で、サインオンの構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9c20e177-0e64-4df3-a3dd-dca3fcf314db
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f07a3840524988e5f643ca89799b7c7f23ff0fc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22226242"
---
# <a name="configure-the-sign-in-credentials-for-the-sql-adapter"></a><span data-ttu-id="c88ba-102">SQL アダプタの資格情報 で、サインオンを構成します。</span><span class="sxs-lookup"><span data-stu-id="c88ba-102">Configure the sign in credentials for the SQL adapter</span></span>
<span data-ttu-id="c88ba-103">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]アダプター クライアント クライアントの資格情報を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c88ba-103">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] requires the adapter clients to provide client credentials.</span></span> <span data-ttu-id="c88ba-104">アダプターは、SQL Server でユーザーを認証し、接続を確立するために、これらの資格情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="c88ba-104">The adapter uses these credentials to authenticate the user with SQL Server and to establish a connection.</span></span>  
  
 <span data-ttu-id="c88ba-105">アダプターのクライアントがクライアント資格情報を両方を使用する場合を提供することができます[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を使用する場合と、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="c88ba-105">Adapter clients can provide the client credentials both when using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and when using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="c88ba-106">使用する場合[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]メタデータを生成する資格情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="c88ba-106">When using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], credentials are required to generate the metadata.</span></span> <span data-ttu-id="c88ba-107">使用する場合、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、資格情報が SQL Server で操作を実行するために必要です。</span><span class="sxs-lookup"><span data-stu-id="c88ba-107">When using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, credentials are required to perform operations on SQL Server.</span></span>  
  
 <span data-ttu-id="c88ba-108">このセクションでクライアントの資格情報を指定することに関する情報が[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]と[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="c88ba-108">This section provides information about specifying client credentials in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
## <a name="enter-credentials-from-visual-studio"></a><span data-ttu-id="c88ba-109">Visual Studio からの資格情報を入力してください。</span><span class="sxs-lookup"><span data-stu-id="c88ba-109">Enter credentials from Visual Studio</span></span>  
 <span data-ttu-id="c88ba-110">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を使用して資格情報を指定することができます、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="c88ba-110">From [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], you can specify the credentials using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  
  
### <a name="using-consume-adapter-service-add-in"></a><span data-ttu-id="c88ba-111">使用してアダプターを使用する追加のサービス</span><span class="sxs-lookup"><span data-stu-id="c88ba-111">Using Consume Adapter Service Add-in</span></span>  
  
1.  <span data-ttu-id="c88ba-112">BizTalk プロジェクトを右クリックし、順にポイント**追加**、し、**生成した項目の追加**です。</span><span class="sxs-lookup"><span data-stu-id="c88ba-112">Right-click your BizTalk project, point to **Add**, and then select **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="c88ba-113">**生成した項目の追加** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="c88ba-113">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="c88ba-114">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c88ba-114">Use this</span></span>|<span data-ttu-id="c88ba-115">目的</span><span class="sxs-lookup"><span data-stu-id="c88ba-115">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="c88ba-116">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="c88ba-116">**Categories**</span></span>|<span data-ttu-id="c88ba-117">をクリックして**アダプター サービスの使用**です。</span><span class="sxs-lookup"><span data-stu-id="c88ba-117">Click **Consume Adapter Service**.</span></span>|  
    |<span data-ttu-id="c88ba-118">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="c88ba-118">**Templates**</span></span>|<span data-ttu-id="c88ba-119">をクリックして**アダプター サービスの使用**です。</span><span class="sxs-lookup"><span data-stu-id="c88ba-119">Click **Consume Adapter Service**.</span></span>|  
  
3.  <span data-ttu-id="c88ba-120">開始する、**アダプター サービスの使用**ダイアログ ボックスで、をクリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="c88ba-120">To start the **Consume Adapter Service** dialog box, click **Add**.</span></span>  
  
4.  <span data-ttu-id="c88ba-121">**アダプター サービスの使用** ダイアログ ボックスから、**バインディングを選択**一覧で、選択**sqlBinding**、順にクリック**構成**です。</span><span class="sxs-lookup"><span data-stu-id="c88ba-121">In the **Consume Adapter Service** dialog box, from the **Select a binding** list, select **sqlBinding**, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="c88ba-122">**アダプターの構成** ダイアログ ボックスをクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ボックスの一覧で、次のいずれかの操作します。</span><span class="sxs-lookup"><span data-stu-id="c88ba-122">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential type** list, do one of the following:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c88ba-123">SQL server で記録される Windows ユーザーを追加する必要があります Windows 認証を使用して SQL Server に接続する場合」の説明に従って[による SQL Server を使用して Windows 認証、SQL アダプターに接続する](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="c88ba-123">If you are connecting to SQL Server using Windows Authentication, the Windows user with which you are logged in must be added to SQL Server as described in [Connect to SQL Server Using Windows Authentication with the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).</span></span>  
  
    |<span data-ttu-id="c88ba-124">このボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c88ba-124">Click this</span></span>|<span data-ttu-id="c88ba-125">目的</span><span class="sxs-lookup"><span data-stu-id="c88ba-125">To do this</span></span>|  
    |----------------|----------------|  
    |<span data-ttu-id="c88ba-126">**なし**</span><span class="sxs-lookup"><span data-stu-id="c88ba-126">**None**</span></span>|<span data-ttu-id="c88ba-127">Windows 認証を使用して SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="c88ba-127">Connect to SQL Server by using Windows authentication.</span></span>|  
    |<span data-ttu-id="c88ba-128">**Windows**</span><span class="sxs-lookup"><span data-stu-id="c88ba-128">**Windows**</span></span>|<span data-ttu-id="c88ba-129">Windows 認証を使用して SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="c88ba-129">Connect to SQL Server by using Windows authentication.</span></span>|  
    |<span data-ttu-id="c88ba-130">**ユーザー名**</span><span class="sxs-lookup"><span data-stu-id="c88ba-130">**Username**</span></span>|<span data-ttu-id="c88ba-131">ユーザー名とパスワードを指定し、SQL Server データベースで定義されているユーザーの資格情報を指定して SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="c88ba-131">Specify the user name and password to connect to SQL Server by specifying credentials for a user defined in SQL Server database.</span></span> <span data-ttu-id="c88ba-132">ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c88ba-132">Note that the user name and password are case-sensitive.</span></span> <span data-ttu-id="c88ba-133">**注:** のままにする場合、**ユーザー名**と**パスワード**フィールドを空白には、アダプターが Windows 認証を使用して SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="c88ba-133">**Note:**  If you leave the **User name** and **Password** fields as blank, the adapter connects to SQL Server using Windows authentication.</span></span>|  
  
6.  <span data-ttu-id="c88ba-134">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c88ba-134">Click **OK**.</span></span>  
  
### <a name="using-add-adapter-metadata-wizard"></a><span data-ttu-id="c88ba-135">アダプター メタデータのウィザードを使用して追加</span><span class="sxs-lookup"><span data-stu-id="c88ba-135">Using Add Adapter Metadata Wizard</span></span>  
  
1.  <span data-ttu-id="c88ba-136">BizTalk プロジェクトを右クリックし、順にポイント**追加**、し、**生成した項目の追加**です。</span><span class="sxs-lookup"><span data-stu-id="c88ba-136">Right-click your BizTalk project, point to **Add**, and then select **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="c88ba-137">**生成した項目の追加** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="c88ba-137">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="c88ba-138">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c88ba-138">Use this</span></span>|<span data-ttu-id="c88ba-139">目的</span><span class="sxs-lookup"><span data-stu-id="c88ba-139">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="c88ba-140">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="c88ba-140">**Categories**</span></span>|<span data-ttu-id="c88ba-141">をクリックして**アダプターを追加**です。</span><span class="sxs-lookup"><span data-stu-id="c88ba-141">Click **Add Adapter**.</span></span>|  
    |<span data-ttu-id="c88ba-142">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="c88ba-142">**Templates**</span></span>|<span data-ttu-id="c88ba-143">をクリックして**アダプター メタデータの追加**です。</span><span class="sxs-lookup"><span data-stu-id="c88ba-143">Click **Add Adapter Metadata**.</span></span>|  
  
3.  <span data-ttu-id="c88ba-144">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c88ba-144">Click **Add**.</span></span> <span data-ttu-id="c88ba-145">[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c88ba-145">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  
  
4.  <span data-ttu-id="c88ba-146">アダプターの追加ウィザードで選択**WCF-SQL**です。</span><span class="sxs-lookup"><span data-stu-id="c88ba-146">In the Add Adapter Wizard, select **WCF-SQL**.</span></span> <span data-ttu-id="c88ba-147">BizTalk Server がインストールされているコンピューターを選択し、BizTalk データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="c88ba-147">Select the computer on which BizTalk Server is installed and the name of the BizTalk database.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="c88ba-148">BizTalk で構成されている WCF SQL ポートがある場合からポートを選択して、**ポート** ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="c88ba-148">If you already have a WCF-SQL port configured in BizTalk, select the port from the **Port** list.</span></span>  
  
5.  <span data-ttu-id="c88ba-149">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c88ba-149">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="c88ba-150">**アダプター サービスの使用** ダイアログ ボックスから、**バインディングを選択**一覧で、選択**sqlBinding**、順にクリック**構成**です。</span><span class="sxs-lookup"><span data-stu-id="c88ba-150">In the **Consume Adapter Service** dialog box, from the **Select a binding** list, select **sqlBinding**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="c88ba-151">**アダプターの構成** ダイアログ ボックスをクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ボックスの一覧で、次のいずれかの操作します。</span><span class="sxs-lookup"><span data-stu-id="c88ba-151">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential type** list, do one of the following:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c88ba-152">SQL server で記録される Windows ユーザーを追加する必要があります Windows 認証を使用して SQL Server に接続する場合」の説明に従って[による SQL Server を使用して Windows 認証、SQL アダプターに接続する](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="c88ba-152">If you are connecting to SQL Server using Windows Authentication, the Windows user with which you are logged in must be added to SQL Server as described in [Connect to SQL Server Using Windows Authentication with the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).</span></span>  
  
    |<span data-ttu-id="c88ba-153">このボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c88ba-153">Click this</span></span>|<span data-ttu-id="c88ba-154">目的</span><span class="sxs-lookup"><span data-stu-id="c88ba-154">To do this</span></span>|  
    |----------------|----------------|  
    |<span data-ttu-id="c88ba-155">**なし**</span><span class="sxs-lookup"><span data-stu-id="c88ba-155">**None**</span></span>|<span data-ttu-id="c88ba-156">Windows 認証を使用して SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="c88ba-156">Connect to SQL Server by using Windows authentication.</span></span>|  
    |<span data-ttu-id="c88ba-157">**Windows**</span><span class="sxs-lookup"><span data-stu-id="c88ba-157">**Windows**</span></span>|<span data-ttu-id="c88ba-158">Windows 認証を使用して SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="c88ba-158">Connect to SQL Server by using Windows authentication.</span></span>|  
    |<span data-ttu-id="c88ba-159">**ユーザー名**</span><span class="sxs-lookup"><span data-stu-id="c88ba-159">**Username**</span></span>|<span data-ttu-id="c88ba-160">ユーザー名とパスワードを指定し、SQL Server データベースで定義されているユーザーの資格情報を指定して SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="c88ba-160">Specify the user name and password to connect to SQL Server by specifying credentials for a user defined in SQL Server database.</span></span> <span data-ttu-id="c88ba-161">ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c88ba-161">Note that the user name and password are case-sensitive.</span></span> <span data-ttu-id="c88ba-162">**注:** のままにする場合、**ユーザー名**と**パスワード**フィールドを空白には、アダプターが Windows 認証を使用して SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="c88ba-162">**Note:**  If you leave the **User name** and **Password** fields as blank, the adapter connects to SQL Server using Windows authentication.</span></span>|  
  
8.  <span data-ttu-id="c88ba-163">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c88ba-163">Click **OK**.</span></span>  
  
## <a name="enter-credentials-from-the-biztalk-server-administration-console"></a><span data-ttu-id="c88ba-164">BizTalk Server 管理コンソールから資格情報を入力してください。</span><span class="sxs-lookup"><span data-stu-id="c88ba-164">Enter credentials from the BizTalk Server Administration Console</span></span>  
 <span data-ttu-id="c88ba-165">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、Wcf-custom または WCF SQL ポートの構成の一部として、資格情報を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="c88ba-165">From the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you can specify the credentials as part of the WCF-Custom or WCF-SQL port configuration.</span></span>  
  
### <a name="enter-credentials-for-the-wcf-custom-port"></a><span data-ttu-id="c88ba-166">WCF カスタム ポートの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="c88ba-166">Enter credentials for the WCF-Custom port</span></span>  
  
1.  <span data-ttu-id="c88ba-167">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="c88ba-167">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="c88ba-168">コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、ポートを作成し、をクリックする、アプリケーションの順に展開および**送信ポート**または**受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="c88ba-168">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="c88ba-169">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="c88ba-169">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
3.  <span data-ttu-id="c88ba-170">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="c88ba-170">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c88ba-171">受信ポートの場所のプロパティ ダイアログ ボックスを表示するをクリックして、**受信場所の**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**です。</span><span class="sxs-lookup"><span data-stu-id="c88ba-171">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="c88ba-172">送信ポートを作成する場合、 **Wcf-custom トランスポートのプロパティ** ダイアログ ボックスをクリックして、**資格情報**タブをクリックし、次のいずれかの操作します。</span><span class="sxs-lookup"><span data-stu-id="c88ba-172">If you are creating a send port, in the **WCF-Custom Transport Properties** dialog box, click the **Credentials** tab, and do one of the following:</span></span>  
  
    -   <span data-ttu-id="c88ba-173">選択、**シングル サインオンを使用しない**オプション、およびユーザー名と SQL Server への接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="c88ba-173">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to SQL Server.</span></span> <span data-ttu-id="c88ba-174">ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c88ba-174">Note that the user name and password are case-sensitive.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="c88ba-175">Windows 認証を使用して SQL Server に接続する場合は、空白のユーザー名とパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="c88ba-175">If you want to connect to SQL Server using Windows authentication, specify a blank user name and password.</span></span> <span data-ttu-id="c88ba-176">SQL Server にで記録される Windows ユーザーを追加する必要があります、これを行う前に」の説明に従って[による SQL Server を使用して Windows 認証、SQL アダプターに接続する](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="c88ba-176">Before you do this, the Windows user with which you are logged in must be added to SQL Server as described in [Connect to SQL Server Using Windows Authentication with the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).</span></span>  
  
    -   <span data-ttu-id="c88ba-177">選択、**を使用してシングル サインオン**オプション、および関連するエンタープライズ シングル サインオン (SSO) アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="c88ba-177">Select the **Use Single Sign-On** option, and specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  
  
5.  <span data-ttu-id="c88ba-178">受信ポートを作成する場合、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**他の**タブをクリックし、次のいずれかの操作します。</span><span class="sxs-lookup"><span data-stu-id="c88ba-178">If you are creating a receive port, in the **WCF-Custom Transport Properties** dialog box, click the **Other** tab, and do one of the following:</span></span>  
  
    -   <span data-ttu-id="c88ba-179">選択、**ユーザー アカウント**オプション、およびユーザー名と SQL Server への接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="c88ba-179">Select the **User account** option, and specify the user name and password to connect to SQL Server.</span></span> <span data-ttu-id="c88ba-180">ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c88ba-180">Note that the user name and password are case-sensitive.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="c88ba-181">Windows 認証を使用して SQL Server に接続する場合は、空白のユーザー名とパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="c88ba-181">If you want to connect to SQL Server using Windows authentication, specify a blank user name and password.</span></span> <span data-ttu-id="c88ba-182">SQL Server にで記録される Windows ユーザーを追加する必要があります、これを行う前に」の説明に従って[による SQL Server を使用して Windows 認証、SQL アダプターに接続する](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="c88ba-182">Before you do this, the Windows user with which you are logged in must be added to SQL Server as described in [Connect to SQL Server Using Windows Authentication with the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).</span></span>  
  
    -   <span data-ttu-id="c88ba-183">選択、**から資格情報を取得関連アプリケーション**オプション、および SSO 関連アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="c88ba-183">Select the **Get credentials from affiliate application** option, and specify an affiliate SSO application.</span></span>  
  
6.  <span data-ttu-id="c88ba-184">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c88ba-184">Click **OK**.</span></span>  
  
### <a name="enter-credentials-for-the-wcf-sql-port"></a><span data-ttu-id="c88ba-185">WCF SQL ポートの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="c88ba-185">Enter credentials for the WCF-SQL port</span></span>  
  
1.  <span data-ttu-id="c88ba-186">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="c88ba-186">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="c88ba-187">WCF-SQL アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="c88ba-187">Add the WCF-SQL adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="c88ba-188">手順については、次を参照してください。 [SQL アダプタを BizTalk Server 管理コンソールに追加する](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md)です。</span><span class="sxs-lookup"><span data-stu-id="c88ba-188">For instructions, see [Adding the SQL Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3.  <span data-ttu-id="c88ba-189">コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、ポートを作成し、をクリックする、アプリケーションの順に展開および**送信ポート**または**受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="c88ba-189">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="c88ba-190">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="c88ba-190">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
4.  <span data-ttu-id="c88ba-191">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストは、前に追加する WCF-SQL アダプターを選択し、をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="c88ba-191">In the port properties dialog box, from the **Type** drop-down list, select the WCF-SQL adapter you added earlier, and then click **Configure**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c88ba-192">受信ポートの場所のプロパティ ダイアログ ボックスを表示するをクリックして、**受信場所の**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**です。</span><span class="sxs-lookup"><span data-stu-id="c88ba-192">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  
  
5.  <span data-ttu-id="c88ba-193">トランスポートのプロパティ ダイアログ ボックスで、送信ポートを作成する場合にクリックして、**資格情報**タブをクリックし、次のいずれかの操作します。</span><span class="sxs-lookup"><span data-stu-id="c88ba-193">If you are creating a send port, in the transport properties dialog box, click the **Credentials** tab, and do one of the following:</span></span>  
  
    -   <span data-ttu-id="c88ba-194">選択、**シングル サインオンを使用しない**オプション、およびユーザー名と SQL Server への接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="c88ba-194">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to SQL Server.</span></span> <span data-ttu-id="c88ba-195">ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c88ba-195">Note that the user name and password are case-sensitive.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="c88ba-196">Windows 認証を使用して SQL Server に接続する場合は、空白のユーザー名とパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="c88ba-196">If you want to connect to SQL Server using Windows authentication, specify a blank user name and password.</span></span> <span data-ttu-id="c88ba-197">SQL Server にで記録される Windows ユーザーを追加する必要があります、これを行う前に」の説明に従って[による SQL Server を使用して Windows 認証、SQL アダプターに接続する](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="c88ba-197">Before you do this, the Windows user with which you are logged in must be added to SQL Server as described in [Connect to SQL Server Using Windows Authentication with the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).</span></span>  
  
    -   <span data-ttu-id="c88ba-198">選択、**を使用してシングル サインオン**オプション、および関連するエンタープライズ シングル サインオン (SSO) アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="c88ba-198">Select the **Use Single Sign-On** option, and specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  
  
6.  <span data-ttu-id="c88ba-199">トランスポートのプロパティ ダイアログ ボックスで、受信ポートを作成する場合にクリックして、**他**タブをクリックし、次のいずれかの操作します。</span><span class="sxs-lookup"><span data-stu-id="c88ba-199">If you are creating a receive port, in the transport properties dialog box, click the **Other** tab, and do one of the following:</span></span>  
  
    -   <span data-ttu-id="c88ba-200">選択、**ユーザー アカウント**オプション、およびユーザー名と SQL Server への接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="c88ba-200">Select the **User account** option, and specify the user name and password to connect to SQL Server.</span></span> <span data-ttu-id="c88ba-201">ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c88ba-201">Note that the user name and password are case-sensitive.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="c88ba-202">Windows 認証を使用して SQL Server に接続する場合は、空白のユーザー名とパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="c88ba-202">If you want to connect to SQL Server using Windows authentication, specify a blank user name and password.</span></span> <span data-ttu-id="c88ba-203">SQL Server にで記録される Windows ユーザーを追加する必要があります、これを行う前に」の説明に従って[による SQL Server を使用して Windows 認証、SQL アダプターに接続する](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="c88ba-203">Before you do this, the Windows user with which you are logged in must be added to SQL Server as described in [Connect to SQL Server Using Windows Authentication with the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).</span></span>  
  
    -   <span data-ttu-id="c88ba-204">選択、**から資格情報を取得関連アプリケーション**オプション、および SSO 関連アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="c88ba-204">Select the **Get credentials from affiliate application** option, and specify an affiliate SSO application.</span></span>  
  
7.  <span data-ttu-id="c88ba-205">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c88ba-205">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c88ba-206">参照</span><span class="sxs-lookup"><span data-stu-id="c88ba-206">See Also</span></span>  
[<span data-ttu-id="c88ba-207">SQL アダプタを BizTalk アプリケーションを開発する構成要素</span><span class="sxs-lookup"><span data-stu-id="c88ba-207">Building blocks to develop BizTalk applications with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)