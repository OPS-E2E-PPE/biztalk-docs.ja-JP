---
title: Siebel アダプターの接続 URI の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- connection URI, specifying
ms.assetid: b89b60e9-0f3b-4305-865e-9d3b40d04648
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 804a71f3a0bb29fd41e51ec6102853df035e8d38
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371850"
---
# <a name="configure-the-connection-uri-for-the-siebel-adapter"></a><span data-ttu-id="1d232-102">Siebel アダプターの接続 URI を構成します。</span><span class="sxs-lookup"><span data-stu-id="1d232-102">Configure the connection URI for the Siebel adapter</span></span>
<span data-ttu-id="1d232-103">接続 URI は、Siebel システムに接続する接続文字列です。</span><span class="sxs-lookup"><span data-stu-id="1d232-103">A connection URI is a connection string to connect to a Siebel system.</span></span> <span data-ttu-id="1d232-104">接続 URI には、Siebel システムとの接続を確立するために必要なさまざまなパラメーターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1d232-104">The connection URI contains various parameters required to establish connection with a Siebel system.</span></span> <span data-ttu-id="1d232-105">この接続のデザイン時と実行時の両方に URI を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d232-105">You must specify this connection URI both at the design time and the run time.</span></span> <span data-ttu-id="1d232-106">デザイン時に、メタデータを生成する Siebel システムへの接続の URI を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d232-106">At design time, you must specify the URI to connect to the Siebel system to generate the metadata.</span></span> <span data-ttu-id="1d232-107">実行時に、操作を実行する Siebel システムへの接続に URI を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d232-107">At run time, you must specify the URI to connect to the Siebel system to perform operations.</span></span>  

## <a name="enter-the-connection-uri-at-design-time"></a><span data-ttu-id="1d232-108">デザイン時の接続 URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="1d232-108">Enter the connection URI at design time</span></span>  
 <span data-ttu-id="1d232-109">デザイン時に、使用して接続 URI を指定する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="1d232-109">For design time, you must specify the connection URI using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  

#### <a name="enter-the-connection-uri-using-consume-adapter-service-add-in"></a><span data-ttu-id="1d232-110">接続 Consume Adapter Service アドインを使用して URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="1d232-110">Enter the connection URI using Consume Adapter Service Add-in</span></span>  

1. <span data-ttu-id="1d232-111">BizTalk プロジェクトを右クリックし、**追加**、し、**生成した項目の追加**します。</span><span class="sxs-lookup"><span data-stu-id="1d232-111">Right-click your BizTalk project, point to **Add**, and then select **Add Generated Items**.</span></span>  

2. <span data-ttu-id="1d232-112">**生成した項目の追加** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1d232-112">In the **Add Generated Items** dialog box, do the following:</span></span>  


   |    <span data-ttu-id="1d232-113">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1d232-113">Use this</span></span>    |             <span data-ttu-id="1d232-114">目的</span><span class="sxs-lookup"><span data-stu-id="1d232-114">To do this</span></span>             |
   |----------------|------------------------------------|
   | <span data-ttu-id="1d232-115">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="1d232-115">**Categories**</span></span> | <span data-ttu-id="1d232-116">クリックして**アダプター サービスの使用**します。</span><span class="sxs-lookup"><span data-stu-id="1d232-116">Click **Consume Adapter Service**.</span></span> |
   | <span data-ttu-id="1d232-117">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="1d232-117">**Templates**</span></span>  | <span data-ttu-id="1d232-118">クリックして**アダプター サービスの使用**します。</span><span class="sxs-lookup"><span data-stu-id="1d232-118">Click **Consume Adapter Service**.</span></span> |


3. <span data-ttu-id="1d232-119">開始する、 **Consume Adapter Service**ダイアログ ボックスで、をクリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="1d232-119">To start the **Consume Adapter Service** dialog box, click **Add**.</span></span>  

4. <span data-ttu-id="1d232-120">**Consume Adapter Service**  ダイアログ ボックスから、**バインディングを選択**ドロップダウン リストを**siebelBinding**、 をクリック**構成**.</span><span class="sxs-lookup"><span data-stu-id="1d232-120">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list select **siebelBinding**, and click **Configure**.</span></span>  

5. <span data-ttu-id="1d232-121">**アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ**タブ。**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **Username**ユーザー名と Siebel システムへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="1d232-121">In the **Configure Adapter** dialog box, click the **Security** tab. From the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the Siebel system.</span></span>  

6. <span data-ttu-id="1d232-122">**アダプターの構成**ダイアログ ボックスで、をクリックして、 **URI プロパティ**タブし、さまざまなパラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="1d232-122">In the **Configure Adapter** dialog box, click the **URI Properties** tab and specify values for different parameters.</span></span> <span data-ttu-id="1d232-123">接続 URI の詳細についてはの[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を参照してください[Siebel システム接続 URI の作成](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="1d232-123">For more information about the connection URI for the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], see [Create the Siebel system connection URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md).</span></span>  

7. <span data-ttu-id="1d232-124">**アダプターの構成**ダイアログ ボックスで、 をクリックして、**バインドのプロパティ**タブし、バインドの値を指定、存在する場合は、スキーマを生成する前に指定するために必要です。</span><span class="sxs-lookup"><span data-stu-id="1d232-124">In the **Configure Adapter** dialog box, click the **Binding Properties** tab and specify the binding values, if any, which are required to be specified before generating the schema.</span></span> <span data-ttu-id="1d232-125">バインド プロパティの詳細については、次を参照してください。 [for Siebel のバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="1d232-125">For more information about binding properties, see [Read about BizTalk Adapter for Siebel Binding Properties](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span></span>  

8. <span data-ttu-id="1d232-126">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1d232-126">Click **OK**.</span></span>  

#### <a name="enter-the-connection-uri-using-add-adapter-metadata-wizard"></a><span data-ttu-id="1d232-127">アダプター メタデータの追加ウィザードを使用して、URI の接続を入力します。</span><span class="sxs-lookup"><span data-stu-id="1d232-127">Enter the connection URI using Add Adapter Metadata Wizard</span></span>  

1. <span data-ttu-id="1d232-128">BizTalk プロジェクトを右クリックし、**追加**、し、**生成した項目の追加**します。</span><span class="sxs-lookup"><span data-stu-id="1d232-128">Right-click your BizTalk project, point to **Add**, and then select **Add Generated Items**.</span></span>  

2. <span data-ttu-id="1d232-129">**生成した項目の追加** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1d232-129">In the **Add Generated Items** dialog box, do the following:</span></span>  


   |    <span data-ttu-id="1d232-130">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1d232-130">Use this</span></span>    |           <span data-ttu-id="1d232-131">目的</span><span class="sxs-lookup"><span data-stu-id="1d232-131">To do this</span></span>            |
   |----------------|---------------------------------|
   | <span data-ttu-id="1d232-132">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="1d232-132">**Categories**</span></span> |     <span data-ttu-id="1d232-133">クリックして**アダプターを追加**します。</span><span class="sxs-lookup"><span data-stu-id="1d232-133">Click **Add Adapter**.</span></span>      |
   | <span data-ttu-id="1d232-134">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="1d232-134">**Templates**</span></span>  | <span data-ttu-id="1d232-135">クリックして**アダプター メタデータの追加**します。</span><span class="sxs-lookup"><span data-stu-id="1d232-135">Click **Add Adapter Metadata**.</span></span> |


3. <span data-ttu-id="1d232-136">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1d232-136">Click **Add**.</span></span> <span data-ttu-id="1d232-137">[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1d232-137">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  

4. <span data-ttu-id="1d232-138">アダプターの追加ウィザードで選択**Wcf-siebel**します。</span><span class="sxs-lookup"><span data-stu-id="1d232-138">In the Add Adapter Wizard, select **WCF-Siebel**.</span></span> <span data-ttu-id="1d232-139">コンピューターを選択します。[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]がインストールされていると、BizTalk データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="1d232-139">Select the computer on which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] is installed and the name of the BizTalk database.</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="1d232-140">BizTalk で構成された Wcf-siebel ポート既にある場合からポートを選択して、**ポート**一覧。</span><span class="sxs-lookup"><span data-stu-id="1d232-140">If you already have a WCF-Siebel port configured in BizTalk, select the port from the **Port** list.</span></span>  

5. <span data-ttu-id="1d232-141">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1d232-141">Click **Next**.</span></span>  

6. <span data-ttu-id="1d232-142">**Consume Adapter Service**  ダイアログ ボックスから、**バインディングを選択**ドロップダウン リストを**siebelBinding**、 をクリック**構成**.</span><span class="sxs-lookup"><span data-stu-id="1d232-142">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list select **siebelBinding**, and click **Configure**.</span></span>  

7. <span data-ttu-id="1d232-143">**アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ**タブ。**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **Username**ユーザー名と Siebel システムへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="1d232-143">In the **Configure Adapter** dialog box, click the **Security** tab. From the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the Siebel system.</span></span>  

8. <span data-ttu-id="1d232-144">**アダプターの構成**ダイアログ ボックスで、をクリックして、 **URI プロパティ**タブし、さまざまなパラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="1d232-144">In the **Configure Adapter** dialog box, click the **URI Properties** tab and specify values for different parameters.</span></span> <span data-ttu-id="1d232-145">接続 URI の詳細についてはの[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を参照してください[Siebel システム接続 URI の作成](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="1d232-145">For more information about the connection URI for the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], see [Create the Siebel system connection URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md).</span></span>  

9. <span data-ttu-id="1d232-146">**アダプターの構成**ダイアログ ボックスで、 をクリックして、**バインドのプロパティ**タブし、バインドの値を指定、存在する場合は、スキーマを生成する前に指定するために必要です。</span><span class="sxs-lookup"><span data-stu-id="1d232-146">In the **Configure Adapter** dialog box, click the **Binding Properties** tab and specify the binding values, if any, which are required to be specified before generating the schema.</span></span> <span data-ttu-id="1d232-147">バインド プロパティの詳細については、次を参照してください。 [for Siebel のバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="1d232-147">For more information about binding properties, see [Read about BizTalk Adapter for Siebel Binding Properties](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="1d232-148">既存の WCF Siebel 送信ポートを選択した場合は、バインドのプロパティを指定する必要がありますできません。</span><span class="sxs-lookup"><span data-stu-id="1d232-148">If you selected an existing WCF-Siebel send port, you need not specify the binding properties.</span></span> <span data-ttu-id="1d232-149">バインドのプロパティは、送信ポートの構成から取得されます。</span><span class="sxs-lookup"><span data-stu-id="1d232-149">The binding properties are picked from the send port configuration.</span></span> <span data-ttu-id="1d232-150">ただし、存在する場合に、デザイン時に必要なバインドのプロパティを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="1d232-150">However, you may choose to specify the binding properties that are required at design-time, if any.</span></span> <span data-ttu-id="1d232-151">このような場合、メタデータの生成中にプロパティをバインドするための新しい値をデザイン時に使用されます。</span><span class="sxs-lookup"><span data-stu-id="1d232-151">In such case, the new values for binding properties will be used at design-time while generating the metadata.</span></span> <span data-ttu-id="1d232-152">ただし、実行時に送信ポートの構成でバインドのプロパティに指定された値を適用できるになります。</span><span class="sxs-lookup"><span data-stu-id="1d232-152">However, at run-time the values specified for binding properties in the send port configuration will be applicable.</span></span>  

10. <span data-ttu-id="1d232-153">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1d232-153">Click **OK**.</span></span>  

## <a name="enter-the-connection-uri-at-run-time"></a><span data-ttu-id="1d232-154">実行時に、接続 URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="1d232-154">Enter the connection URI at run time</span></span>  
 <span data-ttu-id="1d232-155">実行時にで Wcf-custom または Wcf-siebel ポート構成の一部として URI を指定する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="1d232-155">For run time, you must specify the URI as part of the WCF-Custom or WCF-Siebel port configuration in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span>  

#### <a name="enter-the-connection-uri-for-the-wcf-custom-port"></a><span data-ttu-id="1d232-156">WCF カスタム ポートの接続 URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="1d232-156">Enter the connection URI for the WCF-Custom port</span></span>  

1. <span data-ttu-id="1d232-157">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="1d232-157">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="1d232-158">コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、ポート、およびクリックを作成するアプリケーションを展開し**送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="1d232-158">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and the click **Send Ports**.</span></span> <span data-ttu-id="1d232-159">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="1d232-159">In the right pane, you can choose to create a port or select an existing port.</span></span>  

3. <span data-ttu-id="1d232-160">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="1d232-160">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  

4. <span data-ttu-id="1d232-161">**Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブ。</span><span class="sxs-lookup"><span data-stu-id="1d232-161">In the **WCF-Custom Transport Properties** dialog box, click the **General** tab.</span></span>  

5. <span data-ttu-id="1d232-162">**アドレス (URI)** テキスト ボックスで、接続、Siebel システムへの接続に URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="1d232-162">In the **Address (URI)** text box, specify the connection URI to connect to the Siebel system.</span></span> <span data-ttu-id="1d232-163">接続 URI の詳細についてはの[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を参照してください[Siebel システム接続 URI の作成](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="1d232-163">For more information about the connection URI for the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], see [Create the Siebel system connection URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md).</span></span>  

6. <span data-ttu-id="1d232-164">**Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブ。**バインドの種類**ドロップダウン リストで、 **siebelBinding**します。</span><span class="sxs-lookup"><span data-stu-id="1d232-164">In the **WCF-Custom Transport Properties** dialog box, click the **Binding** tab. From the **Binding Type** drop-down list, select **siebelBinding**.</span></span>  

7. <span data-ttu-id="1d232-165">送信ポートを作成する、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**資格情報**タブし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1d232-165">To create a send port, in the **WCF-Custom Transport Properties** dialog box, click the **Credentials** tab and do one of the following:</span></span>  

   1.  <span data-ttu-id="1d232-166">選択、**シングル サインオンを使用しないでください**オプション、およびユーザー名と Siebel システムへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="1d232-166">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to a Siebel system.</span></span>  

   2.  <span data-ttu-id="1d232-167">選択、**使用してシングル サインオン**オプション、および、ESSO 関連アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="1d232-167">Select the **Use Single Sign-On** option, and specify an affiliate ESSO application.</span></span>  

8. <span data-ttu-id="1d232-168">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1d232-168">Click **OK**.</span></span>  

#### <a name="enter-the-connection-uri-for-the-wcf-siebel-port"></a><span data-ttu-id="1d232-169">Wcf-siebel ポートの接続 URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="1d232-169">Enter the connection URI for the WCF-Siebel port</span></span>  

1. <span data-ttu-id="1d232-170">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="1d232-170">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="1d232-171">Wcf-siebel アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="1d232-171">Add the WCF-Siebel adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="1d232-172">手順については、次を参照してください。 [Siebel アダプターを BizTalk Server 管理コンソールに追加](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md)します。</span><span class="sxs-lookup"><span data-stu-id="1d232-172">For instructions, see [Add the Siebel Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md).</span></span>  

3. <span data-ttu-id="1d232-173">コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、ポート、およびクリックを作成するアプリケーションを展開し**送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="1d232-173">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and the click **Send Ports**.</span></span> <span data-ttu-id="1d232-174">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="1d232-174">In the right pane, you can choose to create a port or select an existing port.</span></span>  

4. <span data-ttu-id="1d232-175">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストでは、先ほど追加した Wcf-siebel アダプターを選択してをクリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="1d232-175">In the port properties dialog box, from the **Type** drop-down list, select the WCF-Siebel adapter you added earlier, and then click **Configure**.</span></span>  

5. <span data-ttu-id="1d232-176">トランスポートのプロパティ ダイアログ ボックスでをクリックして、**全般**タブ。</span><span class="sxs-lookup"><span data-stu-id="1d232-176">In the transport properties dialog box, click the **General** tab.</span></span>  

6. <span data-ttu-id="1d232-177">をクリックして、**構成**ボタンをクリックし、接続パラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="1d232-177">Click the **Configure** button and provide values for the connection parameters.</span></span> <span data-ttu-id="1d232-178">接続 URI の詳細についてはの[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を参照してください[Siebel システム接続 URI の作成](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="1d232-178">For more information about the connection URI for the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], see [Create the Siebel system connection URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md).</span></span>  

7. <span data-ttu-id="1d232-179">トランスポートのプロパティ ダイアログ ボックスでをクリックして、**バインド**タブし、バインドのプロパティの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="1d232-179">In the transport properties dialog box, click the **Binding** tab and specify values for binding properties.</span></span>  

8. <span data-ttu-id="1d232-180">送信ポートを作成する、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**資格情報**タブし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1d232-180">To create a send port, in the **WCF-Custom Transport Properties** dialog box, click the **Credentials** tab and do one of the following:</span></span>  

   1.  <span data-ttu-id="1d232-181">選択、**シングル サインオンを使用しないでください**オプション、およびユーザー名と Siebel システムへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="1d232-181">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to a Siebel system.</span></span>  

   2.  <span data-ttu-id="1d232-182">選択、**使用してシングル サインオン**オプション、および、ESSO 関連アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="1d232-182">Select the **Use Single Sign-On** option, and specify an affiliate ESSO application.</span></span>  

9. <span data-ttu-id="1d232-183">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1d232-183">Click **OK**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="1d232-184">参照</span><span class="sxs-lookup"><span data-stu-id="1d232-184">See Also</span></span>  
[<span data-ttu-id="1d232-185">Siebel アダプターを使用した BizTalk アプリケーションを作成する構成要素</span><span class="sxs-lookup"><span data-stu-id="1d232-185">Building blocks to create BizTalk applications with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)