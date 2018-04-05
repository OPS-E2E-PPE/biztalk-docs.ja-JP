---
title: Oracle データベースの資格情報 で、サインオンの構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- Enter the credentials
helpviewer_keywords:
- credentials, specifying at run time
- credentials, specifying at design time
ms.assetid: d8f62829-ce77-4d82-a411-2eeefb6fe75a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eda20ad4e04a9962e471ab98eb0bc5695b391007
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-sign-in-credentials-for-the-oracle-database"></a><span data-ttu-id="a428a-102">Oracle データベースの資格情報 で、サインオンを構成します。</span><span class="sxs-lookup"><span data-stu-id="a428a-102">Configure the sign in credentials for the Oracle Database</span></span>
<span data-ttu-id="a428a-103">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]アダプター クライアント クライアントの資格情報を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a428a-103">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] requires the adapter clients to provide client credentials.</span></span> <span data-ttu-id="a428a-104">アダプターは、Oracle データベースでユーザーを認証し、接続を確立するために、これらの資格情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="a428a-104">The adapter uses these credentials to authenticate the user with the Oracle database and to establish a connection.</span></span>  
  
 <span data-ttu-id="a428a-105">アダプターのクライアントがクライアント資格情報を両方を使用する場合を提供することができます[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を使用する場合と、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="a428a-105">Adapter clients can provide the client credentials both when using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and when using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="a428a-106">使用する場合[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]メタデータを生成する資格情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="a428a-106">When using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], credentials are required to generate the metadata.</span></span> <span data-ttu-id="a428a-107">使用する場合、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、資格情報が Oracle データベースで操作を実行するために必要です。</span><span class="sxs-lookup"><span data-stu-id="a428a-107">When using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, credentials are required to perform operations on the Oracle database.</span></span> <span data-ttu-id="a428a-108">このトピックでのクライアント資格情報の指定に関する情報を提供する[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]と[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="a428a-108">This topic provides information about specifying client credentials in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
## <a name="specifying-client-credentials-from-visual-studio"></a><span data-ttu-id="a428a-109">Visual Studio からのクライアント資格情報の指定</span><span class="sxs-lookup"><span data-stu-id="a428a-109">Specifying Client Credentials from Visual Studio</span></span>  
 <span data-ttu-id="a428a-110">Visual studio を使用して資格情報を指定する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="a428a-110">From Visual Studio, you must specify the credentials using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  
  
#### <a name="to-specify-credentials-using-consume-adapter-service-add-in"></a><span data-ttu-id="a428a-111">アダプター サービスのアドインを使用して資格情報を指定するには</span><span class="sxs-lookup"><span data-stu-id="a428a-111">To specify credentials using Consume Adapter Service Add-in</span></span>  
  
1.  <span data-ttu-id="a428a-112">BizTalk プロジェクトを右クリックし **生成した項目の追加**です。</span><span class="sxs-lookup"><span data-stu-id="a428a-112">Right-click your BizTalk project, and then select **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="a428a-113">**生成した項目の追加** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="a428a-113">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="a428a-114">プロパティ</span><span class="sxs-lookup"><span data-stu-id="a428a-114">Use this</span></span>|<span data-ttu-id="a428a-115">目的</span><span class="sxs-lookup"><span data-stu-id="a428a-115">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="a428a-116">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="a428a-116">**Categories**</span></span>|<span data-ttu-id="a428a-117">をクリックして**アダプター サービスの使用**です。</span><span class="sxs-lookup"><span data-stu-id="a428a-117">Click **Consume Adapter Service**.</span></span>|  
    |<span data-ttu-id="a428a-118">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="a428a-118">**Templates**</span></span>|<span data-ttu-id="a428a-119">をクリックして**アダプター サービスの使用**です。</span><span class="sxs-lookup"><span data-stu-id="a428a-119">Click **Consume Adapter Service**.</span></span>|  
  
3.  <span data-ttu-id="a428a-120">開始する、**アダプター サービスの使用**ダイアログ ボックスで、をクリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="a428a-120">To start the **Consume Adapter Service** dialog box, click **Add**.</span></span>  
  
4.  <span data-ttu-id="a428a-121">**アダプター サービスの使用** ダイアログ ボックスから、**バインディングを選択**一覧で、選択**oracleDBBinding**、 をクリック**構成**です。</span><span class="sxs-lookup"><span data-stu-id="a428a-121">In the **Consume Adapter Service** dialog box, from the **Select a binding** list, select **oracleDBBinding**, and click **Configure**.</span></span>  
  
5.  <span data-ttu-id="a428a-122">**アダプターの構成** ダイアログ ボックスをクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **ユーザー名**ユーザー名と、Oracle データベースへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="a428a-122">In the **Configure Adapter** dialog box, click the **Security** tab and from the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the Oracle database:</span></span>  
  
    -   <span data-ttu-id="a428a-123">Oracle データベースの資格情報を使用して接続するには、内のデータベース資格情報を入力、**ユーザー名**と**パスワード**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="a428a-123">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span>  
  
    -   <span data-ttu-id="a428a-124">Windows 認証を使用して接続するには、入力 **/** で、**ユーザー名**テキスト ボックスと参加解除、**パスワード**ボックスは空白です。</span><span class="sxs-lookup"><span data-stu-id="a428a-124">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  
  
6.  <span data-ttu-id="a428a-125">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a428a-125">Click **OK**.</span></span>  
  
#### <a name="to-specify-credentials-using-add-adapter-metadata-wizard"></a><span data-ttu-id="a428a-126">アダプター メタデータの追加ウィザードを使用して資格情報を指定するには</span><span class="sxs-lookup"><span data-stu-id="a428a-126">To specify credentials using Add Adapter Metadata Wizard</span></span>  
  
1.  <span data-ttu-id="a428a-127">BizTalk プロジェクトを右クリックし、順にポイント**追加**、クリックして**生成した項目の追加**です。</span><span class="sxs-lookup"><span data-stu-id="a428a-127">Right-click your BizTalk project, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="a428a-128">**生成した項目の追加** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="a428a-128">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="a428a-129">プロパティ</span><span class="sxs-lookup"><span data-stu-id="a428a-129">Use this</span></span>|<span data-ttu-id="a428a-130">目的</span><span class="sxs-lookup"><span data-stu-id="a428a-130">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="a428a-131">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="a428a-131">**Categories**</span></span>|<span data-ttu-id="a428a-132">をクリックして**アダプターを追加**です。</span><span class="sxs-lookup"><span data-stu-id="a428a-132">Click **Add Adapter**.</span></span>|  
    |<span data-ttu-id="a428a-133">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="a428a-133">**Templates**</span></span>|<span data-ttu-id="a428a-134">をクリックして**アダプター メタデータの追加**です。</span><span class="sxs-lookup"><span data-stu-id="a428a-134">Click **Add Adapter Metadata**.</span></span>|  
  
3.  <span data-ttu-id="a428a-135">**[追加]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a428a-135">Click **Add**.</span></span> <span data-ttu-id="a428a-136">[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a428a-136">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  
  
4.  <span data-ttu-id="a428a-137">[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] **Wcf-oracledb**です。</span><span class="sxs-lookup"><span data-stu-id="a428a-137">In the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], select **WCF-OracleDB**.</span></span> <span data-ttu-id="a428a-138">コンピューターを選択して[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]がインストールされていると、BizTalk データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="a428a-138">Select the computer on which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] is installed and the name of the BizTalk database.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="a428a-139">BizTalk で構成された Wcf-oracledb ポートがある場合からポートを選択して、**ポート** ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="a428a-139">If you already have a WCF-OracleDB port configured in BizTalk, select the port from the **Port** list.</span></span>  
  
5.  <span data-ttu-id="a428a-140">**[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a428a-140">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="a428a-141">**アダプター サービスの使用** ダイアログ ボックスから、**バインディングを選択**一覧で、選択**oracleDBBinding**、クリックして**構成**.</span><span class="sxs-lookup"><span data-stu-id="a428a-141">In the **Consume Adapter Service** dialog box, from the **Select a binding** list, select **oracleDBBinding**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="a428a-142">**アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ**] タブとの間、**クライアント資格情報の種類**一覧で、[ **Username**とユーザー名と、Oracle データベースへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="a428a-142">In the **Configure Adapter** dialog box, click the **Security** tab, and from the **Client credential type** list, select **Username** and specify the user name and password to connect to the Oracle database:</span></span>  
  
    -   <span data-ttu-id="a428a-143">Oracle データベースの資格情報を使用して接続するには、内のデータベース資格情報を入力、**ユーザー名**と**パスワード**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="a428a-143">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span>  
  
    -   <span data-ttu-id="a428a-144">Windows 認証を使用して接続するには、入力 **/** で、**ユーザー名**テキスト ボックスと参加解除、**パスワード**ボックスは空白です。</span><span class="sxs-lookup"><span data-stu-id="a428a-144">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  
  
8.  <span data-ttu-id="a428a-145">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a428a-145">Click **OK**.</span></span>  
  
## <a name="specifying-client-credentials-from-the-biztalk-server-administration-console"></a><span data-ttu-id="a428a-146">BizTalk Server 管理コンソールからクライアントの資格情報の指定</span><span class="sxs-lookup"><span data-stu-id="a428a-146">Specifying Client Credentials from the BizTalk Server Administration Console</span></span>  
 <span data-ttu-id="a428a-147">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、Wcf-custom または Wcf-oracledb ポートの構成の一部として、資格情報を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a428a-147">From the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you must specify the credentials as part of the WCF-Custom or WCF-OracleDB port configuration.</span></span>  
  
#### <a name="to-specify-client-credentials-for-the-wcf-custom-port"></a><span data-ttu-id="a428a-148">WCF カスタム ポートのクライアント資格情報を指定するには</span><span class="sxs-lookup"><span data-stu-id="a428a-148">To specify client credentials for the WCF-Custom Port</span></span>  
  
1.  <span data-ttu-id="a428a-149">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="a428a-149">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="a428a-150">コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、ポートを作成し、をクリックする、アプリケーションの順に展開および**送信ポート**または**受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="a428a-150">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="a428a-151">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="a428a-151">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
3.  <span data-ttu-id="a428a-152">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="a428a-152">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
4.  <span data-ttu-id="a428a-153">送信ポートの場合に、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**資格情報**タブし、次のいずれかの操作します。</span><span class="sxs-lookup"><span data-stu-id="a428a-153">For a send port, in the **WCF-Custom Transport Properties** dialog box, click the **Credentials** tab and do one of the following:</span></span>  
  
    -   <span data-ttu-id="a428a-154">選択、**シングル サインオンを使用しない**オプション、およびユーザー名と Oracle データベースへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="a428a-154">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to an Oracle database.</span></span>  
  
        -   <span data-ttu-id="a428a-155">Oracle データベースの資格情報を使用して接続するには、内のデータベース資格情報を入力、**ユーザー名**と**パスワード**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="a428a-155">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span>  
  
        -   <span data-ttu-id="a428a-156">Windows 認証を使用して接続するには、入力 **/** で、**ユーザー名**テキスト ボックスと参加解除、**パスワード**ボックスは空白です。</span><span class="sxs-lookup"><span data-stu-id="a428a-156">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  
  
    -   <span data-ttu-id="a428a-157">選択、**を使用してシングル サインオン**オプション、および関連するエンタープライズ シングル サインオン (SSO) アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="a428a-157">Select the **Use Single Sign-On** option, and specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  
  
5.  <span data-ttu-id="a428a-158">受信ポートの場合で、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**他の**タブし、次のいずれかの操作します。</span><span class="sxs-lookup"><span data-stu-id="a428a-158">For a receive port, in the **WCF-Custom Transport Properties** dialog box, click the **Other** tab and do one of the following:</span></span>  
  
    -   <span data-ttu-id="a428a-159">選択**ユーザー アカウント**オプション、およびユーザー名と Oracle データベースへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="a428a-159">Select **User account** option, and specify the user name and password to connect to an Oracle database.</span></span>  
  
        -   <span data-ttu-id="a428a-160">Oracle データベースの資格情報を使用して接続するには、内のデータベース資格情報を入力、**ユーザー名**と**パスワード**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="a428a-160">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span>  
  
        -   <span data-ttu-id="a428a-161">Windows 認証を使用して接続するには、入力 **/** で、**ユーザー名**テキスト ボックスと参加解除、**パスワード**ボックスは空白です。</span><span class="sxs-lookup"><span data-stu-id="a428a-161">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  
  
    -   <span data-ttu-id="a428a-162">選択**から資格情報を取得関連アプリケーション**オプション、および関連アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="a428a-162">Select **Get credentials from affiliate application** option, and specify an affiliate application.</span></span>  
  
6.  <span data-ttu-id="a428a-163">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a428a-163">Click **OK**.</span></span>  
  
#### <a name="to-specify-credentials-for-the-wcf-oracledb-port"></a><span data-ttu-id="a428a-164">Wcf-oracledb ポート用の資格情報を指定するには</span><span class="sxs-lookup"><span data-stu-id="a428a-164">To specify credentials for the WCF-OracleDB port</span></span>  
  
1.  <span data-ttu-id="a428a-165">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="a428a-165">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="a428a-166">Wcf-oracledb アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="a428a-166">Add the WCF-OracleDB adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="a428a-167">手順については、次を参照してください。 [BizTalk Server 管理コンソールへの Oracle データベース アダプターの追加](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md)です。</span><span class="sxs-lookup"><span data-stu-id="a428a-167">For instructions, see [Adding the Oracle Database Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3.  <span data-ttu-id="a428a-168">コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、ポートを作成し、をクリックする、アプリケーションの順に展開および**送信ポート**または**受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="a428a-168">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="a428a-169">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="a428a-169">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
4.  <span data-ttu-id="a428a-170">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-oracledb**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="a428a-170">In the port properties dialog box, from the **Type** drop-down list, select **WCF-OracleDB**, and then click **Configure**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a428a-171">受信ポートの場所のプロパティ ダイアログ ボックスを表示するをクリックして、**受信場所の**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**です。</span><span class="sxs-lookup"><span data-stu-id="a428a-171">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  
  
5.  <span data-ttu-id="a428a-172">ポートのプロパティ ダイアログ ボックスをクリックして、**バインド**タブです。**バインディングの種類**ドロップダウン リストで、 **oracleDBBinding**です。</span><span class="sxs-lookup"><span data-stu-id="a428a-172">In the port properties dialog box, click the **Binding** tab. From the **Binding Type** drop-down list, select **oracleDBBinding**.</span></span>  
  
6.  <span data-ttu-id="a428a-173">トランスポートのプロパティ ダイアログ ボックスで、送信ポートを作成する場合にクリックして、**資格情報**タブをクリックし、次のいずれかの操作します。</span><span class="sxs-lookup"><span data-stu-id="a428a-173">If you are creating a send port, in the transport properties dialog box, click the **Credentials** tab, and do one of the following:</span></span>  
  
    -   <span data-ttu-id="a428a-174">選択、**シングル サインオンを使用しない**オプション、およびユーザー名と、Oracle データベースへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="a428a-174">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to the Oracle database.</span></span>  
  
        -   <span data-ttu-id="a428a-175">Oracle データベースの資格情報を使用して接続するには、内のデータベース資格情報を入力、**ユーザー名**と**パスワード**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="a428a-175">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span>  
  
        -   <span data-ttu-id="a428a-176">Windows 認証を使用して接続するには、入力 **/** で、**ユーザー名**テキスト ボックスと参加解除、**パスワード**ボックスは空白です。</span><span class="sxs-lookup"><span data-stu-id="a428a-176">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  
  
    -   <span data-ttu-id="a428a-177">選択、**を使用してシングル サインオン**オプション、および関連するエンタープライズ シングル サインオン (SSO) アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="a428a-177">Select the **Use Single Sign-On** option, and specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  
  
7.  <span data-ttu-id="a428a-178">トランスポートのプロパティ ダイアログ ボックスで、受信ポートを作成する場合にクリックして、**他**タブをクリックし、次のいずれかの操作します。</span><span class="sxs-lookup"><span data-stu-id="a428a-178">If you are creating a receive port, in the transport properties dialog box, click the **Other** tab, and do one of the following:</span></span>  
  
    -   <span data-ttu-id="a428a-179">選択**ユーザー アカウント**オプション、およびユーザー名と、Oracle データベースへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="a428a-179">Select **User account** option, and specify the user name and password to connect to the Oracle database.</span></span>  
  
        -   <span data-ttu-id="a428a-180">Oracle データベースの資格情報を使用して接続するには、内のデータベース資格情報を入力、**ユーザー名**と**パスワード**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="a428a-180">To connect using the Oracle database credentials, type the database credentials in the **User name** and **Password** text boxes.</span></span>  
  
        -   <span data-ttu-id="a428a-181">Windows 認証を使用して接続するには、入力 **/** で、**ユーザー名**テキスト ボックスと参加解除、**パスワード**ボックスは空白です。</span><span class="sxs-lookup"><span data-stu-id="a428a-181">To connect using Windows Authentication, type **/** in the **User name** text box and leave the **Password** text box blank.</span></span>  
  
    -   <span data-ttu-id="a428a-182">選択**から資格情報を取得関連アプリケーション**オプション、および SSO 関連アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="a428a-182">Select **Get credentials from affiliate application** option, and specify an affiliate SSO application.</span></span>  
  
8.  <span data-ttu-id="a428a-183">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a428a-183">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a428a-184">参照</span><span class="sxs-lookup"><span data-stu-id="a428a-184">See Also</span></span>  
<span data-ttu-id="a428a-185">[Oracle データベースと BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md) </span><span class="sxs-lookup"><span data-stu-id="a428a-185">[Building Blocks to develop BizTalk Applications with Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md) </span></span>  
 [<span data-ttu-id="a428a-186">Windows 認証を使用して Oracle データベースへの接続します。</span><span class="sxs-lookup"><span data-stu-id="a428a-186">Connect to the Oracle Database Using Windows Authentication</span></span>](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)