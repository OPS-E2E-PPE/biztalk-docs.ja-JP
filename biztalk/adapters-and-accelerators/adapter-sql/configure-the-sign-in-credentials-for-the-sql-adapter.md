---
title: SQL アダプターの資格情報で、サインオンの構成 |Microsoft Docs
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
ms.openlocfilehash: 1644132db366e22e0c55fcd293bcfa82506a0c82
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370028"
---
# <a name="configure-the-sign-in-credentials-for-the-sql-adapter"></a><span data-ttu-id="916fb-102">SQL アダプターの資格情報で、サインオンを構成します。</span><span class="sxs-lookup"><span data-stu-id="916fb-102">Configure the sign in credentials for the SQL adapter</span></span>
<span data-ttu-id="916fb-103">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]アダプター クライアントのクライアント資格情報を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="916fb-103">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] requires the adapter clients to provide client credentials.</span></span> <span data-ttu-id="916fb-104">アダプターは、SQL Server でユーザーを認証し、接続を確立するために、これらの資格情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="916fb-104">The adapter uses these credentials to authenticate the user with SQL Server and to establish a connection.</span></span>  

 <span data-ttu-id="916fb-105">アダプター クライアントのクライアント資格情報の両方を使用する場合を提供できます[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を使用する場合と、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="916fb-105">Adapter clients can provide the client credentials both when using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and when using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="916fb-106">使用する場合[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]メタデータを生成する資格情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="916fb-106">When using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], credentials are required to generate the metadata.</span></span> <span data-ttu-id="916fb-107">使用する場合、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、資格情報が SQL Server で操作を実行するために必要です。</span><span class="sxs-lookup"><span data-stu-id="916fb-107">When using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, credentials are required to perform operations on SQL Server.</span></span>  

 <span data-ttu-id="916fb-108">このセクションで、クライアントの資格情報を指定する方法について説明します[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]と[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="916fb-108">This section provides information about specifying client credentials in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

## <a name="enter-credentials-from-visual-studio"></a><span data-ttu-id="916fb-109">Visual Studio からの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="916fb-109">Enter credentials from Visual Studio</span></span>  
 <span data-ttu-id="916fb-110">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を使用して資格情報を指定することができます、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="916fb-110">From [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], you can specify the credentials using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  

### <a name="using-consume-adapter-service-add-in"></a><span data-ttu-id="916fb-111">アダプターを使用してを使用して追加のサービス</span><span class="sxs-lookup"><span data-stu-id="916fb-111">Using Consume Adapter Service Add-in</span></span>  

1.  <span data-ttu-id="916fb-112">BizTalk プロジェクトを右クリックし、**追加**、し、**生成した項目の追加**します。</span><span class="sxs-lookup"><span data-stu-id="916fb-112">Right-click your BizTalk project, point to **Add**, and then select **Add Generated Items**.</span></span>  

2.  <span data-ttu-id="916fb-113">**生成した項目の追加** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="916fb-113">In the **Add Generated Items** dialog box, do the following:</span></span>  

    |<span data-ttu-id="916fb-114">プロパティ</span><span class="sxs-lookup"><span data-stu-id="916fb-114">Use this</span></span>|<span data-ttu-id="916fb-115">目的</span><span class="sxs-lookup"><span data-stu-id="916fb-115">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="916fb-116">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="916fb-116">**Categories**</span></span>|<span data-ttu-id="916fb-117">クリックして**アダプター サービスの使用**します。</span><span class="sxs-lookup"><span data-stu-id="916fb-117">Click **Consume Adapter Service**.</span></span>|  
    |<span data-ttu-id="916fb-118">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="916fb-118">**Templates**</span></span>|<span data-ttu-id="916fb-119">クリックして**アダプター サービスの使用**します。</span><span class="sxs-lookup"><span data-stu-id="916fb-119">Click **Consume Adapter Service**.</span></span>|  

3.  <span data-ttu-id="916fb-120">開始する、 **Consume Adapter Service**ダイアログ ボックスで、をクリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="916fb-120">To start the **Consume Adapter Service** dialog box, click **Add**.</span></span>  

4.  <span data-ttu-id="916fb-121">**Consume Adapter Service**  ダイアログ ボックスから、**バインディングを選択**一覧で、選択**sqlBinding**、順にクリックします**構成**します。</span><span class="sxs-lookup"><span data-stu-id="916fb-121">In the **Consume Adapter Service** dialog box, from the **Select a binding** list, select **sqlBinding**, and then click **Configure**.</span></span>  

5.  <span data-ttu-id="916fb-122">**アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ボックスの一覧で、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="916fb-122">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential type** list, do one of the following:</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="916fb-123">」の説明に従って、ログインしているが、Windows ユーザーを SQL Server に追加する必要があります Windows 認証を使用して SQL Server に接続する場合[による SQL Server を使用して Windows 認証、SQL アダプターに接続する](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="916fb-123">If you are connecting to SQL Server using Windows Authentication, the Windows user with which you are logged in must be added to SQL Server as described in [Connect to SQL Server Using Windows Authentication with the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).</span></span>  

    |<span data-ttu-id="916fb-124">このボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="916fb-124">Click this</span></span>|<span data-ttu-id="916fb-125">目的</span><span class="sxs-lookup"><span data-stu-id="916fb-125">To do this</span></span>|  
    |----------------|----------------|  
    |<span data-ttu-id="916fb-126">**なし**</span><span class="sxs-lookup"><span data-stu-id="916fb-126">**None**</span></span>|<span data-ttu-id="916fb-127">Windows 認証を使用して、SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="916fb-127">Connect to SQL Server by using Windows authentication.</span></span>|  
    |<span data-ttu-id="916fb-128">**Windows**</span><span class="sxs-lookup"><span data-stu-id="916fb-128">**Windows**</span></span>|<span data-ttu-id="916fb-129">Windows 認証を使用して、SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="916fb-129">Connect to SQL Server by using Windows authentication.</span></span>|  
    |<span data-ttu-id="916fb-130">**ユーザー名**</span><span class="sxs-lookup"><span data-stu-id="916fb-130">**Username**</span></span>|<span data-ttu-id="916fb-131">ユーザー名とパスワードを指定し、SQL Server データベースで定義されているユーザーの資格情報を指定して SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="916fb-131">Specify the user name and password to connect to SQL Server by specifying credentials for a user defined in SQL Server database.</span></span> <span data-ttu-id="916fb-132">ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="916fb-132">Note that the user name and password are case-sensitive.</span></span> <span data-ttu-id="916fb-133">**注:** ままにする場合、**ユーザー名**と**パスワード**フィールドを空白、アダプターが Windows 認証を使用して SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="916fb-133">**Note:**  If you leave the **User name** and **Password** fields as blank, the adapter connects to SQL Server using Windows authentication.</span></span>|  

6.  <span data-ttu-id="916fb-134">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="916fb-134">Click **OK**.</span></span>  

### <a name="using-add-adapter-metadata-wizard"></a><span data-ttu-id="916fb-135">アダプター メタデータのウィザードを使用して追加</span><span class="sxs-lookup"><span data-stu-id="916fb-135">Using Add Adapter Metadata Wizard</span></span>  

1. <span data-ttu-id="916fb-136">BizTalk プロジェクトを右クリックし、**追加**、し、**生成した項目の追加**します。</span><span class="sxs-lookup"><span data-stu-id="916fb-136">Right-click your BizTalk project, point to **Add**, and then select **Add Generated Items**.</span></span>  

2. <span data-ttu-id="916fb-137">**生成した項目の追加** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="916fb-137">In the **Add Generated Items** dialog box, do the following:</span></span>  


   |    <span data-ttu-id="916fb-138">プロパティ</span><span class="sxs-lookup"><span data-stu-id="916fb-138">Use this</span></span>    |           <span data-ttu-id="916fb-139">目的</span><span class="sxs-lookup"><span data-stu-id="916fb-139">To do this</span></span>            |
   |----------------|---------------------------------|
   | <span data-ttu-id="916fb-140">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="916fb-140">**Categories**</span></span> |     <span data-ttu-id="916fb-141">クリックして**アダプターを追加**します。</span><span class="sxs-lookup"><span data-stu-id="916fb-141">Click **Add Adapter**.</span></span>      |
   | <span data-ttu-id="916fb-142">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="916fb-142">**Templates**</span></span>  | <span data-ttu-id="916fb-143">クリックして**アダプター メタデータの追加**します。</span><span class="sxs-lookup"><span data-stu-id="916fb-143">Click **Add Adapter Metadata**.</span></span> |


3. <span data-ttu-id="916fb-144">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="916fb-144">Click **Add**.</span></span> <span data-ttu-id="916fb-145">[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="916fb-145">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  

4. <span data-ttu-id="916fb-146">アダプターの追加ウィザードで選択**WCF-SQL**します。</span><span class="sxs-lookup"><span data-stu-id="916fb-146">In the Add Adapter Wizard, select **WCF-SQL**.</span></span> <span data-ttu-id="916fb-147">BizTalk Server がインストールされているコンピューターを選択し、BizTalk データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="916fb-147">Select the computer on which BizTalk Server is installed and the name of the BizTalk database.</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="916fb-148">BizTalk で構成されている WCF SQL ポートが既にあるを場合からポートの選択、**ポート**一覧。</span><span class="sxs-lookup"><span data-stu-id="916fb-148">If you already have a WCF-SQL port configured in BizTalk, select the port from the **Port** list.</span></span>  

5. <span data-ttu-id="916fb-149">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="916fb-149">Click **Next**.</span></span>  

6. <span data-ttu-id="916fb-150">**Consume Adapter Service**  ダイアログ ボックスから、**バインディングを選択**一覧で、選択**sqlBinding**、順にクリックします**構成**します。</span><span class="sxs-lookup"><span data-stu-id="916fb-150">In the **Consume Adapter Service** dialog box, from the **Select a binding** list, select **sqlBinding**, and then click **Configure**.</span></span>  

7. <span data-ttu-id="916fb-151">**アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ボックスの一覧で、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="916fb-151">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential type** list, do one of the following:</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="916fb-152">」の説明に従って、ログインしているが、Windows ユーザーを SQL Server に追加する必要があります Windows 認証を使用して SQL Server に接続する場合[による SQL Server を使用して Windows 認証、SQL アダプターに接続する](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="916fb-152">If you are connecting to SQL Server using Windows Authentication, the Windows user with which you are logged in must be added to SQL Server as described in [Connect to SQL Server Using Windows Authentication with the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).</span></span>  

   |  <span data-ttu-id="916fb-153">このボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="916fb-153">Click this</span></span>  |                                                                                                                                                               <span data-ttu-id="916fb-154">目的</span><span class="sxs-lookup"><span data-stu-id="916fb-154">To do this</span></span>                                                                                                                                                               |
   |--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |   <span data-ttu-id="916fb-155">**なし**</span><span class="sxs-lookup"><span data-stu-id="916fb-155">**None**</span></span>   |                                                                                                                                         <span data-ttu-id="916fb-156">Windows 認証を使用して、SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="916fb-156">Connect to SQL Server by using Windows authentication.</span></span>                                                                                                                                         |
   | <span data-ttu-id="916fb-157">**Windows**</span><span class="sxs-lookup"><span data-stu-id="916fb-157">**Windows**</span></span>  |                                                                                                                                         <span data-ttu-id="916fb-158">Windows 認証を使用して、SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="916fb-158">Connect to SQL Server by using Windows authentication.</span></span>                                                                                                                                         |
   | <span data-ttu-id="916fb-159">**ユーザー名**</span><span class="sxs-lookup"><span data-stu-id="916fb-159">**Username**</span></span> | <span data-ttu-id="916fb-160">ユーザー名とパスワードを指定し、SQL Server データベースで定義されているユーザーの資格情報を指定して SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="916fb-160">Specify the user name and password to connect to SQL Server by specifying credentials for a user defined in SQL Server database.</span></span> <span data-ttu-id="916fb-161">ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="916fb-161">Note that the user name and password are case-sensitive.</span></span> <span data-ttu-id="916fb-162">**注:** ままにする場合、**ユーザー名**と**パスワード**フィールドを空白、アダプターが Windows 認証を使用して SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="916fb-162">**Note:**  If you leave the **User name** and **Password** fields as blank, the adapter connects to SQL Server using Windows authentication.</span></span> |


8. <span data-ttu-id="916fb-163">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="916fb-163">Click **OK**.</span></span>  

## <a name="enter-credentials-from-the-biztalk-server-administration-console"></a><span data-ttu-id="916fb-164">BizTalk Server 管理コンソールから資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="916fb-164">Enter credentials from the BizTalk Server Administration Console</span></span>  
 <span data-ttu-id="916fb-165">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、Wcf-custom または WCF SQL ポートの構成の一部として、資格情報を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="916fb-165">From the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you can specify the credentials as part of the WCF-Custom or WCF-SQL port configuration.</span></span>  

### <a name="enter-credentials-for-the-wcf-custom-port"></a><span data-ttu-id="916fb-166">WCF カスタム ポートの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="916fb-166">Enter credentials for the WCF-Custom port</span></span>  

1. <span data-ttu-id="916fb-167">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="916fb-167">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="916fb-168">コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、順に展開する、ポートを作成し、をクリックしアプリケーション**送信ポート**または**受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="916fb-168">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="916fb-169">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="916fb-169">In the right pane, you can choose to create a port or select an existing port.</span></span>  

3. <span data-ttu-id="916fb-170">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="916fb-170">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="916fb-171">受信ポートの場所のプロパティ ダイアログ ボックスを表示する をクリックして、**受信場所**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**します。</span><span class="sxs-lookup"><span data-stu-id="916fb-171">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  

4. <span data-ttu-id="916fb-172">送信ポートを作成する場合、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**資格情報**タブをクリックし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="916fb-172">If you are creating a send port, in the **WCF-Custom Transport Properties** dialog box, click the **Credentials** tab, and do one of the following:</span></span>  

   -   <span data-ttu-id="916fb-173">選択、**シングル サインオンを使用しないでください**オプション、およびユーザー名と SQL Server に接続するためのパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="916fb-173">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to SQL Server.</span></span> <span data-ttu-id="916fb-174">ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="916fb-174">Note that the user name and password are case-sensitive.</span></span>  

       > [!NOTE]
       >  <span data-ttu-id="916fb-175">Windows 認証を使用して SQL Server に接続する場合は、空のユーザー名とパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="916fb-175">If you want to connect to SQL Server using Windows authentication, specify a blank user name and password.</span></span> <span data-ttu-id="916fb-176">」の説明に従って、ログインしているが、Windows ユーザーを SQL Server に追加する必要がありますこれを実行する前に[による SQL Server を使用して Windows 認証、SQL アダプターに接続する](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="916fb-176">Before you do this, the Windows user with which you are logged in must be added to SQL Server as described in [Connect to SQL Server Using Windows Authentication with the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).</span></span>  

   -   <span data-ttu-id="916fb-177">選択、**使用してシングル サインオン**オプション、および関連アプリケーションにエンタープライズ シングル サインオン (SSO) を指定します。</span><span class="sxs-lookup"><span data-stu-id="916fb-177">Select the **Use Single Sign-On** option, and specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  

5. <span data-ttu-id="916fb-178">受信ポートを作成する場合、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**他**タブをクリックし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="916fb-178">If you are creating a receive port, in the **WCF-Custom Transport Properties** dialog box, click the **Other** tab, and do one of the following:</span></span>  

   -   <span data-ttu-id="916fb-179">選択、**ユーザー アカウント**オプション、およびユーザー名と SQL Server に接続するためのパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="916fb-179">Select the **User account** option, and specify the user name and password to connect to SQL Server.</span></span> <span data-ttu-id="916fb-180">ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="916fb-180">Note that the user name and password are case-sensitive.</span></span>  

       > [!NOTE]
       >  <span data-ttu-id="916fb-181">Windows 認証を使用して SQL Server に接続する場合は、空のユーザー名とパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="916fb-181">If you want to connect to SQL Server using Windows authentication, specify a blank user name and password.</span></span> <span data-ttu-id="916fb-182">」の説明に従って、ログインしているが、Windows ユーザーを SQL Server に追加する必要がありますこれを実行する前に[による SQL Server を使用して Windows 認証、SQL アダプターに接続する](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="916fb-182">Before you do this, the Windows user with which you are logged in must be added to SQL Server as described in [Connect to SQL Server Using Windows Authentication with the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).</span></span>  

   -   <span data-ttu-id="916fb-183">選択、**関連アプリケーションから資格情報を Get**オプション、および SSO 関連アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="916fb-183">Select the **Get credentials from affiliate application** option, and specify an affiliate SSO application.</span></span>  

6. <span data-ttu-id="916fb-184">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="916fb-184">Click **OK**.</span></span>  

### <a name="enter-credentials-for-the-wcf-sql-port"></a><span data-ttu-id="916fb-185">WCF SQL ポートの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="916fb-185">Enter credentials for the WCF-SQL port</span></span>  

1. <span data-ttu-id="916fb-186">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="916fb-186">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="916fb-187">WCF-SQL アダプターを追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="916fb-187">Add the WCF-SQL adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="916fb-188">手順については、次を参照してください。 [SQL アダプタを BizTalk Server 管理コンソールに追加する](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md)します。</span><span class="sxs-lookup"><span data-stu-id="916fb-188">For instructions, see [Adding the SQL Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md).</span></span>  

3. <span data-ttu-id="916fb-189">コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、順に展開する、ポートを作成し、をクリックしアプリケーション**送信ポート**または**受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="916fb-189">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="916fb-190">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="916fb-190">In the right pane, you can choose to create a port or select an existing port.</span></span>  

4. <span data-ttu-id="916fb-191">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストでは、先ほど追加した WCF-SQL アダプターを選択し、順にクリックします**構成**します。</span><span class="sxs-lookup"><span data-stu-id="916fb-191">In the port properties dialog box, from the **Type** drop-down list, select the WCF-SQL adapter you added earlier, and then click **Configure**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="916fb-192">受信ポートの場所のプロパティ ダイアログ ボックスを表示する をクリックして、**受信場所**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**します。</span><span class="sxs-lookup"><span data-stu-id="916fb-192">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  

5. <span data-ttu-id="916fb-193">トランスポートのプロパティ ダイアログ ボックスで、送信ポートを作成する場合は、クリックして、**資格情報**タブをクリックし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="916fb-193">If you are creating a send port, in the transport properties dialog box, click the **Credentials** tab, and do one of the following:</span></span>  

   -   <span data-ttu-id="916fb-194">選択、**シングル サインオンを使用しないでください**オプション、およびユーザー名と SQL Server に接続するためのパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="916fb-194">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to SQL Server.</span></span> <span data-ttu-id="916fb-195">ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="916fb-195">Note that the user name and password are case-sensitive.</span></span>  

       > [!NOTE]
       >  <span data-ttu-id="916fb-196">Windows 認証を使用して SQL Server に接続する場合は、空のユーザー名とパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="916fb-196">If you want to connect to SQL Server using Windows authentication, specify a blank user name and password.</span></span> <span data-ttu-id="916fb-197">」の説明に従って、ログインしているが、Windows ユーザーを SQL Server に追加する必要がありますこれを実行する前に[による SQL Server を使用して Windows 認証、SQL アダプターに接続する](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="916fb-197">Before you do this, the Windows user with which you are logged in must be added to SQL Server as described in [Connect to SQL Server Using Windows Authentication with the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).</span></span>  

   -   <span data-ttu-id="916fb-198">選択、**使用してシングル サインオン**オプション、および関連アプリケーションにエンタープライズ シングル サインオン (SSO) を指定します。</span><span class="sxs-lookup"><span data-stu-id="916fb-198">Select the **Use Single Sign-On** option, and specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  

6. <span data-ttu-id="916fb-199">トランスポートのプロパティ ダイアログ ボックスで、受信ポートを作成する場合にクリックして、**他**タブをクリックし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="916fb-199">If you are creating a receive port, in the transport properties dialog box, click the **Other** tab, and do one of the following:</span></span>  

   -   <span data-ttu-id="916fb-200">選択、**ユーザー アカウント**オプション、およびユーザー名と SQL Server に接続するためのパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="916fb-200">Select the **User account** option, and specify the user name and password to connect to SQL Server.</span></span> <span data-ttu-id="916fb-201">ユーザー名とパスワードでは大文字と小文字が区別されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="916fb-201">Note that the user name and password are case-sensitive.</span></span>  

       > [!NOTE]
       >  <span data-ttu-id="916fb-202">Windows 認証を使用して SQL Server に接続する場合は、空のユーザー名とパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="916fb-202">If you want to connect to SQL Server using Windows authentication, specify a blank user name and password.</span></span> <span data-ttu-id="916fb-203">」の説明に従って、ログインしているが、Windows ユーザーを SQL Server に追加する必要がありますこれを実行する前に[による SQL Server を使用して Windows 認証、SQL アダプターに接続する](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="916fb-203">Before you do this, the Windows user with which you are logged in must be added to SQL Server as described in [Connect to SQL Server Using Windows Authentication with the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).</span></span>  

   -   <span data-ttu-id="916fb-204">選択、**関連アプリケーションから資格情報を Get**オプション、および SSO 関連アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="916fb-204">Select the **Get credentials from affiliate application** option, and specify an affiliate SSO application.</span></span>  

7. <span data-ttu-id="916fb-205">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="916fb-205">Click **OK**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="916fb-206">参照</span><span class="sxs-lookup"><span data-stu-id="916fb-206">See Also</span></span>  
[<span data-ttu-id="916fb-207">SQL アダプターを使用した BizTalk アプリケーションを開発する構成要素</span><span class="sxs-lookup"><span data-stu-id="916fb-207">Building blocks to develop BizTalk applications with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)