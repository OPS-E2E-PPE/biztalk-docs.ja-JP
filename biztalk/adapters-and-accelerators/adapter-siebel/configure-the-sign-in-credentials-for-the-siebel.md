---
title: Siebel の資格情報で、サインオンの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- how to, specify credentials for the Siebel system at run time
- credentials, specifying
- how to, specify credentials for the Siebel system at design time
ms.assetid: a9fef2ba-c38e-44f7-84a3-b6a95d4dc210
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 865f7fe900d009db7ac79ba933f484cae3fd3e00
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371833"
---
# <a name="configure-the-sign-in-credentials-for-the-siebel"></a><span data-ttu-id="b9fa5-102">Siebel の資格情報で、サインオンを構成します。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-102">Configure the sign in credentials for the Siebel</span></span>
<span data-ttu-id="b9fa5-103">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]アダプター クライアントのクライアント資格情報を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-103">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] requires the adapter clients to provide client credentials.</span></span> <span data-ttu-id="b9fa5-104">アダプターは、Siebel システムでユーザーを認証し、接続を確立するために、これらの資格情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-104">The adapter uses these credentials to authenticate the user with the Siebel system and to establish a connection.</span></span>  

 <span data-ttu-id="b9fa5-105">アダプター クライアントは、資格情報をデザイン時または実行時に、クライアントに提供できます。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-105">Adapter clients can provide the client credentials either at design time or run time.</span></span> <span data-ttu-id="b9fa5-106">デザイン時に、メタデータを生成する資格情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-106">At design time, credentials are required to generate the metadata.</span></span> <span data-ttu-id="b9fa5-107">実行時に、Siebel システムに対して操作を実行する資格情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-107">At run time, credentials are required to perform operations on the Siebel system.</span></span> <span data-ttu-id="b9fa5-108">このセクションでは、デザイン時および実行時にクライアントの資格情報を指定する方法の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-108">This section provides information about specifying client credentials at design time and run time.</span></span>  

## <a name="enter-the-client-credentials-at-design-time"></a><span data-ttu-id="b9fa5-109">デザイン時にクライアントの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-109">Enter the client credentials at design time</span></span>  
 <span data-ttu-id="b9fa5-110">デザイン時を使用して資格情報を指定する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-110">For design time, you must specify the credentials using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  

#### <a name="enter-client-credentials-using-consume-adapter-service-add-in"></a><span data-ttu-id="b9fa5-111">Consume Adapter Service アドインを使用してクライアント資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-111">Enter client credentials using Consume Adapter Service Add-in</span></span>  

1.  <span data-ttu-id="b9fa5-112">BizTalk プロジェクトを右クリックし、**追加**、し、**生成した項目の追加**します。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-112">Right-click your BizTalk project, point to **Add**, and then select **Add Generated Items**.</span></span>  

2.  <span data-ttu-id="b9fa5-113">**生成した項目の追加** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-113">In the **Add Generated Items** dialog box, do the following:</span></span>  

    |<span data-ttu-id="b9fa5-114">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b9fa5-114">Use this</span></span>|<span data-ttu-id="b9fa5-115">目的</span><span class="sxs-lookup"><span data-stu-id="b9fa5-115">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="b9fa5-116">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="b9fa5-116">**Categories**</span></span>|<span data-ttu-id="b9fa5-117">クリックして**アダプター サービスの使用**します。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-117">Click **Consume Adapter Service**.</span></span>|  
    |<span data-ttu-id="b9fa5-118">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="b9fa5-118">**Templates**</span></span>|<span data-ttu-id="b9fa5-119">クリックして**アダプター サービスの使用**します。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-119">Click **Consume Adapter Service**.</span></span>|  

3.  <span data-ttu-id="b9fa5-120">開始する、 **Consume Adapter Service**ダイアログ ボックスで、をクリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-120">To start the **Consume Adapter Service** dialog box, click **Add**.</span></span>  

4.  <span data-ttu-id="b9fa5-121">**Consume Adapter Service**  ダイアログ ボックスから、**バインディングを選択**一覧で、選択**siebelBinding**、順にクリックします**構成**します。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-121">In the **Consume Adapter Service** dialog box, from the **Select a binding** list, select **siebelBinding**, and then click **Configure**.</span></span>  

5.  <span data-ttu-id="b9fa5-122">**アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **ユーザー名**ユーザー名と Siebel システムへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-122">In the **Configure Adapter** dialog box, click the **Security** tab and from the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the Siebel system.</span></span>  

6.  <span data-ttu-id="b9fa5-123">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-123">Click **OK**.</span></span>  

#### <a name="enter-client-credentials-using-add-adapter-metadata-wizard"></a><span data-ttu-id="b9fa5-124">アダプター メタデータの追加ウィザードを使用してクライアント資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-124">Enter client credentials using Add Adapter Metadata Wizard</span></span>  

1. <span data-ttu-id="b9fa5-125">BizTalk プロジェクトを右クリックし、**追加**、し、**生成した項目の追加**します。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-125">Right-click your BizTalk project, point to **Add**, and then select **Add Generated Items**.</span></span>  

2. <span data-ttu-id="b9fa5-126">**生成した項目の追加** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-126">In the **Add Generated Items** dialog box, do the following:</span></span>  


   |    <span data-ttu-id="b9fa5-127">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b9fa5-127">Use this</span></span>    |           <span data-ttu-id="b9fa5-128">目的</span><span class="sxs-lookup"><span data-stu-id="b9fa5-128">To do this</span></span>            |
   |----------------|---------------------------------|
   | <span data-ttu-id="b9fa5-129">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="b9fa5-129">**Categories**</span></span> |     <span data-ttu-id="b9fa5-130">クリックして**アダプターを追加**します。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-130">Click **Add Adapter**.</span></span>      |
   | <span data-ttu-id="b9fa5-131">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="b9fa5-131">**Templates**</span></span>  | <span data-ttu-id="b9fa5-132">クリックして**アダプター メタデータの追加**します。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-132">Click **Add Adapter Metadata**.</span></span> |


3. <span data-ttu-id="b9fa5-133">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-133">Click **Add**.</span></span> <span data-ttu-id="b9fa5-134">[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-134">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  

4. <span data-ttu-id="b9fa5-135">アダプターの追加ウィザードで選択**Wcf-siebel**します。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-135">In the Add Adapter Wizard, select **WCF-Siebel**.</span></span> <span data-ttu-id="b9fa5-136">コンピューターを選択します。[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]がインストールされていると、BizTalk データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-136">Select the computer on which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] is installed and the name of the BizTalk database.</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="b9fa5-137">BizTalk で構成された Wcf-siebel ポート既にある場合からポートを選択して、**ポート**一覧。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-137">If you already have a WCF-Siebel port configured in BizTalk, select the port from the **Port** list.</span></span>  

5. <span data-ttu-id="b9fa5-138">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-138">Click **Next**.</span></span>  

6. <span data-ttu-id="b9fa5-139">**Consume Adapter Service**  ダイアログ ボックスから、**バインディングを選択**一覧で、選択**siebelBinding**、順にクリックします**構成**します。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-139">In the **Consume Adapter Service** dialog box, from the **Select a binding** list, select **siebelBinding**, and then click **Configure**.</span></span>  

7. <span data-ttu-id="b9fa5-140">**アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ** タブとの間、**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **ユーザー名**ユーザー名と Siebel システムへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-140">In the **Configure Adapter** dialog box, click the **Security** tab and from the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the Siebel system.</span></span>  

8. <span data-ttu-id="b9fa5-141">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-141">Click **OK**.</span></span>  

## <a name="enter-client-credentials-at-run-time"></a><span data-ttu-id="b9fa5-142">実行時にクライアントの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-142">Enter client credentials at run time</span></span>  
 <span data-ttu-id="b9fa5-143">実行時で Wcf-custom または Wcf-siebel ポート構成の一部としてクライアントの資格情報を指定する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-143">For run time, you must specify the client credentials as part of the WCF-Custom or WCF-Siebel port configuration in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

#### <a name="enter-credentials-for-the-wcf-custom-port"></a><span data-ttu-id="b9fa5-144">WCF カスタム ポートの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-144">Enter credentials for the WCF-Custom port</span></span>  

1. <span data-ttu-id="b9fa5-145">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-145">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="b9fa5-146">コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**をクリックして、ポートを作成するアプリケーションを展開し**送信ポート**.</span><span class="sxs-lookup"><span data-stu-id="b9fa5-146">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and then click **Send Ports**.</span></span> <span data-ttu-id="b9fa5-147">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-147">In the right pane, you can choose to create a port or select an existing port.</span></span>  

3. <span data-ttu-id="b9fa5-148">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-148">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  

4. <span data-ttu-id="b9fa5-149">送信ポートので、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、 をクリックして、**資格情報**タブし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-149">For a send port, in the **WCF-Custom Transport Properties** dialog box, click the **Credentials** tab and do one of the following:</span></span>  

   -   <span data-ttu-id="b9fa5-150">選択、**シングル サインオンを使用しないでください**オプション、およびユーザー名と Siebel システムへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-150">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to a Siebel system.</span></span>  

   -   <span data-ttu-id="b9fa5-151">選択、**使用してシングル サインオン**オプション、および、ESSO 関連アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-151">Select the **Use Single Sign-On** option, and specify an affiliate ESSO application.</span></span>  

5. <span data-ttu-id="b9fa5-152">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-152">Click **OK**.</span></span>  

> [!NOTE]
>  [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] <span data-ttu-id="b9fa5-153">また、エンタープライズ シングル サインオン (ESSO) システムをサポートします。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-153">also supports the Enterprise Single Sign-On (ESSO) system.</span></span> <span data-ttu-id="b9fa5-154">ESSO は、WCF アダプターは ESSO 関連アプリケーションを認識する、BizTalk のシナリオでは適用のみです。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-154">ESSO is only applicable in the BizTalk scenario, in which the WCF adapter is aware of ESSO affiliate applications.</span></span> <span data-ttu-id="b9fa5-155">BizTalk Server に関するセキュリティの詳細については、次を参照してください。 [Siebel アダプターと BizTalk Server でセキュリティ](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-155">For more information about security with respect to BizTalk Server, see [Security with Siebel adapter and BizTalk Server](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md).</span></span>

#### <a name="enter-credentials-for-the-wcf-siebel-port"></a><span data-ttu-id="b9fa5-156">Wcf-siebel ポートの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-156">Enter credentials for the WCF-Siebel port</span></span>  

1. <span data-ttu-id="b9fa5-157">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-157">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="b9fa5-158">Wcf-siebel アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-158">Add the WCF-Siebel adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="b9fa5-159">手順については、次を参照してください。 [Siebel アダプターを BizTalk Server 管理コンソールに追加](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md)します。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-159">For instructions, see [Add the Siebel Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md).</span></span>  

3. <span data-ttu-id="b9fa5-160">コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**をクリックして、ポートを作成するアプリケーションを展開し**送信ポート**.</span><span class="sxs-lookup"><span data-stu-id="b9fa5-160">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and then click **Send Ports**.</span></span> <span data-ttu-id="b9fa5-161">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-161">In the right pane, you can choose to create a port or select an existing port.</span></span>  

4. <span data-ttu-id="b9fa5-162">ポートのプロパティ ダイアログ ボックスから、**型**ボックスの一覧は、先ほど追加した Wcf-siebel ポートを選択し、順にクリックします**構成**します。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-162">In the port properties dialog box, from the **Type** drop-down list, select the WCF-Siebel port you added earlier, and then click **Configure**.</span></span>  

5. <span data-ttu-id="b9fa5-163">トランスポートのプロパティ ダイアログ ボックスの送信ポートをクリックして、**資格情報**タブし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-163">For a send port, in the transport properties dialog box, click the **Credentials** tab and do one of the following:</span></span>  

   -   <span data-ttu-id="b9fa5-164">選択、**シングル サインオンを使用しないでください**オプション、およびユーザー名と Siebel システムへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-164">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to a Siebel system.</span></span>  

   -   <span data-ttu-id="b9fa5-165">選択、**使用してシングル サインオン**オプション、および、ESSO 関連アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-165">Select the **Use Single Sign-On** option, and specify an affiliate ESSO application.</span></span>  

6. <span data-ttu-id="b9fa5-166">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-166">Click **OK**.</span></span>  

> [!NOTE]
>  [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] <span data-ttu-id="b9fa5-167">また、エンタープライズ シングル サインオン (ESSO) システムをサポートします。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-167">also supports the Enterprise Single Sign-On (ESSO) system.</span></span> <span data-ttu-id="b9fa5-168">ESSO は、WCF アダプターは ESSO 関連アプリケーションを認識する、BizTalk のシナリオでは適用のみです。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-168">ESSO is only applicable in the BizTalk scenario, in which the WCF adapter is aware of ESSO affiliate applications.</span></span> <span data-ttu-id="b9fa5-169">BizTalk Server に関するセキュリティの詳細については、次を参照してください。 [Siebel アダプターと BizTalk Server でセキュリティ](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="b9fa5-169">For more information about security with respect to BizTalk Server, see [Security with Siebel adapter and BizTalk Server](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b9fa5-170">参照</span><span class="sxs-lookup"><span data-stu-id="b9fa5-170">See Also</span></span>  
[<span data-ttu-id="b9fa5-171">Siebel アダプターを使用した BizTalk アプリケーションを作成する構成要素</span><span class="sxs-lookup"><span data-stu-id="b9fa5-171">Building blocks to create BizTalk applications with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)