---
title: SAP システムの資格情報で、サインオンの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb41106b-b673-4fcf-a56e-6208e3113469
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c788bf8c98fc06511ce692c84600f040443dd993
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989171"
---
# <a name="configure-the-sign-in-credentials-for-the-sap-system"></a><span data-ttu-id="15572-102">SAP システムの資格情報で、サインオンを構成します。</span><span class="sxs-lookup"><span data-stu-id="15572-102">Configure the sign in credentials for the SAP system</span></span>
<span data-ttu-id="15572-103">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]アダプター クライアントのクライアント資格情報を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="15572-103">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] requires the adapter clients to provide client credentials.</span></span> <span data-ttu-id="15572-104">アダプターは、SAP システムでユーザーを認証し、接続を確立するために、これらの資格情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="15572-104">The adapter uses these credentials to authenticate the user with the SAP system and to establish a connection.</span></span>  

 <span data-ttu-id="15572-105">アダプター クライアントでは、デザイン時に両方資格情報をクライアントに提供したり、時間を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="15572-105">Adapter clients can provide the client credentials both at design time or run time.</span></span> <span data-ttu-id="15572-106">デザイン時に、メタデータを生成する資格情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="15572-106">At design time, credentials are required to generate the metadata.</span></span> <span data-ttu-id="15572-107">実行時に、SAP システムでの操作を実行する資格情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="15572-107">At run time, credentials are required to perform operations on the SAP system.</span></span> <span data-ttu-id="15572-108">このセクションでは、デザイン時および実行時にクライアントの資格情報を指定する方法の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="15572-108">This section provides information about specifying client credentials at design time and run time.</span></span>  

## <a name="enter-the-client-credentials-at-design-time"></a><span data-ttu-id="15572-109">デザイン時にクライアントの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="15572-109">Enter the client credentials at design time</span></span>  
 <span data-ttu-id="15572-110">デザイン時に、使用して資格情報を指定できます、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="15572-110">For design time, you can specify the credentials using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  

### <a name="enter-credentials-using-consume-adapter-service-add-in"></a><span data-ttu-id="15572-111">Consume Adapter Service アドインを使用して資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="15572-111">Enter credentials using Consume Adapter Service Add-in</span></span>  

1.  <span data-ttu-id="15572-112">BizTalk プロジェクトを右クリックし、[**追加**、] をクリックし、**生成した項目の追加**します。</span><span class="sxs-lookup"><span data-stu-id="15572-112">Right-click your BizTalk project, point to **Add**, and then click **Add Generated Items**.</span></span>  

2.  <span data-ttu-id="15572-113">**生成した項目の追加** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="15572-113">In the **Add Generated Items** dialog box, do the following:</span></span>  

    |<span data-ttu-id="15572-114">プロパティ</span><span class="sxs-lookup"><span data-stu-id="15572-114">Use this</span></span>|<span data-ttu-id="15572-115">目的</span><span class="sxs-lookup"><span data-stu-id="15572-115">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="15572-116">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="15572-116">**Categories**</span></span>|<span data-ttu-id="15572-117">クリックして**アダプター サービスの使用**します。</span><span class="sxs-lookup"><span data-stu-id="15572-117">Click **Consume Adapter Service**.</span></span>|  
    |<span data-ttu-id="15572-118">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="15572-118">**Templates**</span></span>|<span data-ttu-id="15572-119">クリックして**アダプター サービスの使用**します。</span><span class="sxs-lookup"><span data-stu-id="15572-119">Click **Consume Adapter Service**.</span></span>|  

3.  <span data-ttu-id="15572-120">開始する、 **Consume Adapter Service**ダイアログ ボックスで、をクリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="15572-120">To start the **Consume Adapter Service** dialog box, click **Add**.</span></span>  

4.  <span data-ttu-id="15572-121">**Consume Adapter Service**  ダイアログ ボックスから、**バインディングを選択**一覧で、選択**sapBinding**、順にクリックします**構成**します。</span><span class="sxs-lookup"><span data-stu-id="15572-121">In the **Consume Adapter Service** dialog box, from the **Select a binding** list, select **sapBinding**, and then click **Configure**.</span></span>  

5.  <span data-ttu-id="15572-122">**アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **ユーザー名**ユーザー名と SAP システムへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="15572-122">In the **Configure Adapter** dialog box, click the **Security** tab and from the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the SAP system.</span></span>  

6.  <span data-ttu-id="15572-123">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15572-123">Click **OK**.</span></span>  

### <a name="enter-credentials-using-add-adapter-metadata-wizard"></a><span data-ttu-id="15572-124">アダプター メタデータの追加ウィザードを使用して資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="15572-124">Enter credentials using Add Adapter Metadata Wizard</span></span>  

1. <span data-ttu-id="15572-125">BizTalk プロジェクトを右クリックし、[**追加**、] をクリックし、**生成した項目の追加**します。</span><span class="sxs-lookup"><span data-stu-id="15572-125">Right-click your BizTalk project, point to **Add**, and then click **Add Generated Items**.</span></span>  

2. <span data-ttu-id="15572-126">**生成した項目の追加** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="15572-126">In the **Add Generated Items** dialog box, do the following:</span></span>  


   |    <span data-ttu-id="15572-127">プロパティ</span><span class="sxs-lookup"><span data-stu-id="15572-127">Use this</span></span>    |           <span data-ttu-id="15572-128">目的</span><span class="sxs-lookup"><span data-stu-id="15572-128">To do this</span></span>            |
   |----------------|---------------------------------|
   | <span data-ttu-id="15572-129">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="15572-129">**Categories**</span></span> |     <span data-ttu-id="15572-130">クリックして**アダプターを追加**します。</span><span class="sxs-lookup"><span data-stu-id="15572-130">Click **Add Adapter**.</span></span>      |
   | <span data-ttu-id="15572-131">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="15572-131">**Templates**</span></span>  | <span data-ttu-id="15572-132">クリックして**アダプター メタデータの追加**します。</span><span class="sxs-lookup"><span data-stu-id="15572-132">Click **Add Adapter Metadata**.</span></span> |


3. <span data-ttu-id="15572-133">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15572-133">Click **Add**.</span></span> <span data-ttu-id="15572-134">[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="15572-134">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  

4. <span data-ttu-id="15572-135">アダプターの追加ウィザードで選択**WCF-SAP**します。</span><span class="sxs-lookup"><span data-stu-id="15572-135">In the Add Adapter Wizard, select **WCF-SAP**.</span></span> <span data-ttu-id="15572-136">BizTalk Server がインストールされているコンピューターを選択し、BizTalk データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="15572-136">Select the computer on which BizTalk Server is installed and the name of the BizTalk database.</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="15572-137">BizTalk で構成されている WCF SAP ポート既にある場合からポートを選択して、**ポート**一覧。</span><span class="sxs-lookup"><span data-stu-id="15572-137">If you already have a WCF-SAP port configured in BizTalk, select the port from the **Port** list.</span></span>  

5. <span data-ttu-id="15572-138">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15572-138">Click **Next**.</span></span>  

6. <span data-ttu-id="15572-139">**Consume Adapter Service**  ダイアログ ボックスから、**バインディングを選択**一覧で、選択**sapBinding**、順にクリックします**構成**します。</span><span class="sxs-lookup"><span data-stu-id="15572-139">In the **Consume Adapter Service** dialog box, from the **Select a binding** list, select **sapBinding**, and then click **Configure**.</span></span>  

7. <span data-ttu-id="15572-140">**アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **ユーザー名**ユーザー名と SAP システムへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="15572-140">In the **Configure Adapter** dialog box, click the **Security** tab and from the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the SAP system.</span></span>  

8. <span data-ttu-id="15572-141">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15572-141">Click **OK**.</span></span>  

## <a name="enter-client-credentials-at-run-time"></a><span data-ttu-id="15572-142">実行時にクライアントの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="15572-142">Enter client credentials at run time</span></span>  
 <span data-ttu-id="15572-143">実行時のクライアントの資格情報を指定で Wcf-custom または WCF SAP ポートの構成の一部として、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="15572-143">For run time, you can specify the client credentials as part of the WCF-Custom or WCF-SAP port configuration in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

### <a name="enter-credentials-for-the-wcf-custom-port"></a><span data-ttu-id="15572-144">WCF カスタム ポートの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="15572-144">Enter credentials for the WCF-Custom port</span></span>  

1. <span data-ttu-id="15572-145">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="15572-145">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="15572-146">コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、順に展開する、ポートを作成し、をクリックしアプリケーション**送信ポート**または**受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="15572-146">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="15572-147">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="15572-147">In the right pane, you can choose to create a port or select an existing port.</span></span>  

3. <span data-ttu-id="15572-148">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="15572-148">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="15572-149">受信ポートの場所のプロパティ ダイアログ ボックスを表示する をクリックして、**受信場所**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**します。</span><span class="sxs-lookup"><span data-stu-id="15572-149">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  

4. <span data-ttu-id="15572-150">送信ポートので、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、 をクリックして、**資格情報**タブし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="15572-150">For a send port, in the **WCF-Custom Transport Properties** dialog box, click the **Credentials** tab and do one of the following:</span></span>  

   -   <span data-ttu-id="15572-151">選択、**シングル サインオンを使用しないでください**オプション、およびユーザー名と SAP システムへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="15572-151">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to an SAP system.</span></span>  

   -   <span data-ttu-id="15572-152">選択、**使用してシングル サインオン**オプション、および関連アプリケーションにエンタープライズ シングル サインオン (SSO) を指定します。</span><span class="sxs-lookup"><span data-stu-id="15572-152">Select the **Use Single Sign-On** option, and specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  

5. <span data-ttu-id="15572-153">受信ポートので、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**他** タブで、次のいずれかを実行し、。</span><span class="sxs-lookup"><span data-stu-id="15572-153">For a receive port, in the **WCF-Custom Transport Properties** dialog box, click the **Other** tab and do one of the following:</span></span>  

   -   <span data-ttu-id="15572-154">選択**ユーザー アカウント**オプション、およびユーザー名と SAP システムへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="15572-154">Select **User account** option, and specify the user name and password to connect to an SAP system.</span></span>  

   -   <span data-ttu-id="15572-155">選択**関連アプリケーションから資格情報を Get**オプション、および関連アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="15572-155">Select **Get credentials from affiliate application** option, and specify an affiliate application.</span></span>  

6. <span data-ttu-id="15572-156">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15572-156">Click **OK**.</span></span>  

### <a name="enter-credentials-for-the-wcf-sap-port"></a><span data-ttu-id="15572-157">WCF SAP ポートの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="15572-157">Enter credentials for the WCF-SAP port</span></span>  

1. <span data-ttu-id="15572-158">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="15572-158">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="15572-159">WCF-SAP アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="15572-159">Add the WCF-SAP adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="15572-160">手順については、[SAP アダプターを BizTalk Server 管理コンソールに追加](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15572-160">For instructions, see [Add the SAP Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md).</span></span>  

3. <span data-ttu-id="15572-161">コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、順に展開する、ポートを作成し、をクリックしアプリケーション**送信ポート**または**受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="15572-161">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="15572-162">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="15572-162">In the right pane, you can choose to create a port or select an existing port.</span></span>  

4. <span data-ttu-id="15572-163">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストでは、先ほど追加した WCF-SAP アダプターを選択し、順にクリックします**構成**します。</span><span class="sxs-lookup"><span data-stu-id="15572-163">In the port properties dialog box, from the **Type** drop-down list, select the WCF-SAP adapter you added earlier, and then click **Configure**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="15572-164">受信ポートの場所のプロパティ ダイアログ ボックスを表示する をクリックして、**受信場所**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**します。</span><span class="sxs-lookup"><span data-stu-id="15572-164">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  

5. <span data-ttu-id="15572-165">トランスポートのプロパティ ダイアログ ボックスで、送信ポートを作成する場合にクリックして、**資格情報**タブし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="15572-165">If you are creating a send port, in the transport properties dialog box, click the **Credentials** tab and do one of the following:</span></span>  

   1.  <span data-ttu-id="15572-166">選択、**シングル サインオンを使用しないでください**オプション、およびユーザー名と SAP システムへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="15572-166">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to the SAP system.</span></span>  

   2.  <span data-ttu-id="15572-167">選択、**使用してシングル サインオン**オプション、および関連アプリケーションにエンタープライズ シングル サインオン (SSO) を指定します。</span><span class="sxs-lookup"><span data-stu-id="15572-167">Select the **Use Single Sign-On** option, and specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  

6. <span data-ttu-id="15572-168">受信ポートを作成する場合、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、 をクリックして、**他**タブし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="15572-168">If you are creating a receive port, in the **WCF-Custom Transport Properties** dialog box, click the **Other** tab and do one of the following:</span></span>  

   1.  <span data-ttu-id="15572-169">選択**ユーザー アカウント**オプション、およびユーザー名と SAP システムへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="15572-169">Select **User account** option, and specify the user name and password to connect to the SAP system.</span></span>  

   2.  <span data-ttu-id="15572-170">選択**関連アプリケーションから資格情報を Get**オプション、および SSO 関連アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="15572-170">Select **Get credentials from affiliate application** option, and specify an affiliate SSO application.</span></span>  

7. <span data-ttu-id="15572-171">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="15572-171">Click **OK**.</span></span>  

> [!NOTE]
>  [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] <span data-ttu-id="15572-172">また、エンタープライズ シングル サインオン (SSO) システムをサポートします。</span><span class="sxs-lookup"><span data-stu-id="15572-172">also supports the Enterprise Single Sign-On (SSO) system.</span></span> <span data-ttu-id="15572-173">SSO オプションは、BizTalk シナリオに該当のみ、[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]は SSO 関連アプリケーションを認識します。</span><span class="sxs-lookup"><span data-stu-id="15572-173">SSO is only applicable in the BizTalk scenario, in which the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)] is aware of SSO affiliate applications.</span></span> <span data-ttu-id="15572-174">BizTalk Server に関するセキュリティの詳細については、[SAP アダプターと BizTalk Server でセキュリティ](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15572-174">For more information about security with respect to BizTalk Server, see [Security with the SAP adapter and BizTalk Server](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="15572-175">参照</span><span class="sxs-lookup"><span data-stu-id="15572-175">See Also</span></span>  
[<span data-ttu-id="15572-176">SAP アプリケーションを作成するための構成要素</span><span class="sxs-lookup"><span data-stu-id="15572-176">Building blocks to create SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)