---
title: "SAP システムの資格情報で、サインオンの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fb41106b-b673-4fcf-a56e-6208e3113469
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a6ace75f66bb7fdd4cfb3362f7d019ab99d73bf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-sign-in-credentials-for-the-sap-system"></a><span data-ttu-id="ca817-102">SAP システムの資格情報で、サインオンを構成します。</span><span class="sxs-lookup"><span data-stu-id="ca817-102">Configure the sign in credentials for the SAP system</span></span>
<span data-ttu-id="ca817-103">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]アダプター クライアント クライアントの資格情報を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca817-103">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] requires the adapter clients to provide client credentials.</span></span> <span data-ttu-id="ca817-104">アダプターは、SAP システムでユーザーを認証し、接続を確立するために、これらの資格情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="ca817-104">The adapter uses these credentials to authenticate the user with the SAP system and to establish a connection.</span></span>  
  
 <span data-ttu-id="ca817-105">アダプターのクライアントでは、デザイン時に、クライアント両方資格情報を提供したり、時間を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="ca817-105">Adapter clients can provide the client credentials both at design time or run time.</span></span> <span data-ttu-id="ca817-106">デザイン時に、メタデータを生成する資格情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="ca817-106">At design time, credentials are required to generate the metadata.</span></span> <span data-ttu-id="ca817-107">実行時に、SAP システムでの操作を実行する資格情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="ca817-107">At run time, credentials are required to perform operations on the SAP system.</span></span> <span data-ttu-id="ca817-108">このセクションでは、デザイン時および実行時にクライアントの資格情報を指定することに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="ca817-108">This section provides information about specifying client credentials at design time and run time.</span></span>  
  
## <a name="enter-the-client-credentials-at-design-time"></a><span data-ttu-id="ca817-109">デザイン時にクライアントの資格情報を入力してください。</span><span class="sxs-lookup"><span data-stu-id="ca817-109">Enter the client credentials at design time</span></span>  
 <span data-ttu-id="ca817-110">デザイン時にを使用して資格情報を指定することができます、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ca817-110">For design time, you can specify the credentials using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  
  
### <a name="enter-credentials-using-consume-adapter-service-add-in"></a><span data-ttu-id="ca817-111">アダプター サービスのアドインを使用して資格情報を入力してください。</span><span class="sxs-lookup"><span data-stu-id="ca817-111">Enter credentials using Consume Adapter Service Add-in</span></span>  
  
1.  <span data-ttu-id="ca817-112">BizTalk プロジェクトを右クリックし、順にポイント**追加**、クリックして**生成した項目の追加**です。</span><span class="sxs-lookup"><span data-stu-id="ca817-112">Right-click your BizTalk project, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="ca817-113">**生成した項目の追加** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="ca817-113">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="ca817-114">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ca817-114">Use this</span></span>|<span data-ttu-id="ca817-115">目的</span><span class="sxs-lookup"><span data-stu-id="ca817-115">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="ca817-116">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="ca817-116">**Categories**</span></span>|<span data-ttu-id="ca817-117">をクリックして**アダプター サービスの使用**です。</span><span class="sxs-lookup"><span data-stu-id="ca817-117">Click **Consume Adapter Service**.</span></span>|  
    |<span data-ttu-id="ca817-118">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="ca817-118">**Templates**</span></span>|<span data-ttu-id="ca817-119">をクリックして**アダプター サービスの使用**です。</span><span class="sxs-lookup"><span data-stu-id="ca817-119">Click **Consume Adapter Service**.</span></span>|  
  
3.  <span data-ttu-id="ca817-120">開始する、**アダプター サービスの使用**ダイアログ ボックスで、をクリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="ca817-120">To start the **Consume Adapter Service** dialog box, click **Add**.</span></span>  
  
4.  <span data-ttu-id="ca817-121">**アダプター サービスの使用** ダイアログ ボックスから、**バインディングを選択**一覧で、選択**sapBinding**、順にクリック**構成**です。</span><span class="sxs-lookup"><span data-stu-id="ca817-121">In the **Consume Adapter Service** dialog box, from the **Select a binding** list, select **sapBinding**, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="ca817-122">**アダプターの構成** ダイアログ ボックスをクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **ユーザー名**ユーザー名と、SAP システムへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="ca817-122">In the **Configure Adapter** dialog box, click the **Security** tab and from the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the SAP system.</span></span>  
  
6.  <span data-ttu-id="ca817-123">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca817-123">Click **OK**.</span></span>  
  
### <a name="enter-credentials-using-add-adapter-metadata-wizard"></a><span data-ttu-id="ca817-124">アダプター メタデータの追加ウィザードを使用して資格情報を入力してください。</span><span class="sxs-lookup"><span data-stu-id="ca817-124">Enter credentials using Add Adapter Metadata Wizard</span></span>  
  
1.  <span data-ttu-id="ca817-125">BizTalk プロジェクトを右クリックし、順にポイント**追加**、クリックして**生成した項目の追加**です。</span><span class="sxs-lookup"><span data-stu-id="ca817-125">Right-click your BizTalk project, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="ca817-126">**生成した項目の追加** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="ca817-126">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="ca817-127">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ca817-127">Use this</span></span>|<span data-ttu-id="ca817-128">目的</span><span class="sxs-lookup"><span data-stu-id="ca817-128">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="ca817-129">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="ca817-129">**Categories**</span></span>|<span data-ttu-id="ca817-130">をクリックして**アダプターを追加**です。</span><span class="sxs-lookup"><span data-stu-id="ca817-130">Click **Add Adapter**.</span></span>|  
    |<span data-ttu-id="ca817-131">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="ca817-131">**Templates**</span></span>|<span data-ttu-id="ca817-132">をクリックして**アダプター メタデータの追加**です。</span><span class="sxs-lookup"><span data-stu-id="ca817-132">Click **Add Adapter Metadata**.</span></span>|  
  
3.  <span data-ttu-id="ca817-133">**[追加]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca817-133">Click **Add**.</span></span> <span data-ttu-id="ca817-134">[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca817-134">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  
  
4.  <span data-ttu-id="ca817-135">アダプターの追加ウィザードで選択**WCF SAP**です。</span><span class="sxs-lookup"><span data-stu-id="ca817-135">In the Add Adapter Wizard, select **WCF-SAP**.</span></span> <span data-ttu-id="ca817-136">BizTalk Server がインストールされているコンピューターを選択し、BizTalk データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="ca817-136">Select the computer on which BizTalk Server is installed and the name of the BizTalk database.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="ca817-137">BizTalk で構成されている WCF SAP ポートがある場合からポートを選択して、**ポート** ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="ca817-137">If you already have a WCF-SAP port configured in BizTalk, select the port from the **Port** list.</span></span>  
  
5.  <span data-ttu-id="ca817-138">**[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca817-138">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="ca817-139">**アダプター サービスの使用** ダイアログ ボックスから、**バインディングを選択**一覧で、選択**sapBinding**、順にクリック**構成**です。</span><span class="sxs-lookup"><span data-stu-id="ca817-139">In the **Consume Adapter Service** dialog box, from the **Select a binding** list, select **sapBinding**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="ca817-140">**アダプターの構成** ダイアログ ボックスをクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **ユーザー名**ユーザー名と、SAP システムへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="ca817-140">In the **Configure Adapter** dialog box, click the **Security** tab and from the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the SAP system.</span></span>  
  
8.  <span data-ttu-id="ca817-141">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca817-141">Click **OK**.</span></span>  
  
## <a name="enter-client-credentials-at-run-time"></a><span data-ttu-id="ca817-142">実行時にクライアントの資格情報を入力してください。</span><span class="sxs-lookup"><span data-stu-id="ca817-142">Enter client credentials at run time</span></span>  
 <span data-ttu-id="ca817-143">実行時に、クライアントの資格情報を指定で Wcf-custom または WCF SAP ポートの構成の一部として、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="ca817-143">For run time, you can specify the client credentials as part of the WCF-Custom or WCF-SAP port configuration in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
### <a name="enter-credentials-for-the-wcf-custom-port"></a><span data-ttu-id="ca817-144">WCF カスタム ポートの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="ca817-144">Enter credentials for the WCF-Custom port</span></span>  
  
1.  <span data-ttu-id="ca817-145">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="ca817-145">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="ca817-146">コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、ポートを作成し、をクリックする、アプリケーションの順に展開および**送信ポート**または**受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="ca817-146">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="ca817-147">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="ca817-147">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
3.  <span data-ttu-id="ca817-148">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="ca817-148">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ca817-149">受信ポートの場所のプロパティ ダイアログ ボックスを表示するをクリックして、**受信場所の**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**です。</span><span class="sxs-lookup"><span data-stu-id="ca817-149">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="ca817-150">送信ポートの場合に、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**資格情報**タブし、次のいずれかの操作します。</span><span class="sxs-lookup"><span data-stu-id="ca817-150">For a send port, in the **WCF-Custom Transport Properties** dialog box, click the **Credentials** tab and do one of the following:</span></span>  
  
    -   <span data-ttu-id="ca817-151">選択、**シングル サインオンを使用しない**オプション、およびユーザー名と、SAP システムへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="ca817-151">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to an SAP system.</span></span>  
  
    -   <span data-ttu-id="ca817-152">選択、**を使用してシングル サインオン**オプション、および関連するエンタープライズ シングル サインオン (SSO) アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="ca817-152">Select the **Use Single Sign-On** option, and specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  
  
5.  <span data-ttu-id="ca817-153">受信ポートの場合で、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**他の**タブし、次のいずれかの操作します。</span><span class="sxs-lookup"><span data-stu-id="ca817-153">For a receive port, in the **WCF-Custom Transport Properties** dialog box, click the **Other** tab and do one of the following:</span></span>  
  
    -   <span data-ttu-id="ca817-154">選択**ユーザー アカウント**オプション、およびユーザー名と、SAP システムへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="ca817-154">Select **User account** option, and specify the user name and password to connect to an SAP system.</span></span>  
  
    -   <span data-ttu-id="ca817-155">選択**から資格情報を取得関連アプリケーション**オプション、および関連アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="ca817-155">Select **Get credentials from affiliate application** option, and specify an affiliate application.</span></span>  
  
6.  <span data-ttu-id="ca817-156">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca817-156">Click **OK**.</span></span>  
  
### <a name="enter-credentials-for-the-wcf-sap-port"></a><span data-ttu-id="ca817-157">WCF SAP ポートの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="ca817-157">Enter credentials for the WCF-SAP port</span></span>  
  
1.  <span data-ttu-id="ca817-158">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="ca817-158">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="ca817-159">WCF SAP アダプターを追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="ca817-159">Add the WCF-SAP adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="ca817-160">手順については、次を参照してください。 [SAP アダプターを BizTalk Server 管理コンソールに追加](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md)です。</span><span class="sxs-lookup"><span data-stu-id="ca817-160">For instructions, see [Add the SAP Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3.  <span data-ttu-id="ca817-161">コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、ポートを作成し、をクリックする、アプリケーションの順に展開および**送信ポート**または**受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="ca817-161">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="ca817-162">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="ca817-162">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
4.  <span data-ttu-id="ca817-163">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストは、前に追加する WCF SAP アダプターを選択し、をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="ca817-163">In the port properties dialog box, from the **Type** drop-down list, select the WCF-SAP adapter you added earlier, and then click **Configure**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ca817-164">受信ポートの場所のプロパティ ダイアログ ボックスを表示するをクリックして、**受信場所の**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**です。</span><span class="sxs-lookup"><span data-stu-id="ca817-164">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  
  
5.  <span data-ttu-id="ca817-165">トランスポートのプロパティ ダイアログ ボックスで、送信ポートを作成する場合にクリックして、**資格情報**タブし、次のいずれかの操作します。</span><span class="sxs-lookup"><span data-stu-id="ca817-165">If you are creating a send port, in the transport properties dialog box, click the **Credentials** tab and do one of the following:</span></span>  
  
    1.  <span data-ttu-id="ca817-166">選択、**シングル サインオンを使用しない**オプション、およびユーザー名と、SAP システムへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="ca817-166">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to the SAP system.</span></span>  
  
    2.  <span data-ttu-id="ca817-167">選択、**を使用してシングル サインオン**オプション、および関連するエンタープライズ シングル サインオン (SSO) アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="ca817-167">Select the **Use Single Sign-On** option, and specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  
  
6.  <span data-ttu-id="ca817-168">受信ポートを作成する場合、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**他の**タブし、次のいずれかの操作します。</span><span class="sxs-lookup"><span data-stu-id="ca817-168">If you are creating a receive port, in the **WCF-Custom Transport Properties** dialog box, click the **Other** tab and do one of the following:</span></span>  
  
    1.  <span data-ttu-id="ca817-169">選択**ユーザー アカウント**オプション、およびユーザー名と、SAP システムへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="ca817-169">Select **User account** option, and specify the user name and password to connect to the SAP system.</span></span>  
  
    2.  <span data-ttu-id="ca817-170">選択**から資格情報を取得関連アプリケーション**オプション、および SSO 関連アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="ca817-170">Select **Get credentials from affiliate application** option, and specify an affiliate SSO application.</span></span>  
  
7.  <span data-ttu-id="ca817-171">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca817-171">Click **OK**.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]<span data-ttu-id="ca817-172">また、エンタープライズ シングル サインオン (SSO) システムをサポートします。</span><span class="sxs-lookup"><span data-stu-id="ca817-172"> also supports the Enterprise Single Sign-On (SSO) system.</span></span> <span data-ttu-id="ca817-173">SSO は、BizTalk のシナリオで使用できるのみ、[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]は SSO 関連アプリケーションを認識します。</span><span class="sxs-lookup"><span data-stu-id="ca817-173">SSO is only applicable in the BizTalk scenario, in which the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)] is aware of SSO affiliate applications.</span></span> <span data-ttu-id="ca817-174">BizTalk Server に関するセキュリティの詳細については、次を参照してください。 [SAP アダプターと BizTalk Server によるセキュリティ](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="ca817-174">For more information about security with respect to BizTalk Server, see [Security with the SAP adapter and BizTalk Server](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ca817-175">参照</span><span class="sxs-lookup"><span data-stu-id="ca817-175">See Also</span></span>  
[<span data-ttu-id="ca817-176">SAP アプリケーションを作成する構成要素</span><span class="sxs-lookup"><span data-stu-id="ca817-176">Building blocks to create SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)