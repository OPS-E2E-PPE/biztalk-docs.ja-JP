---
title: Siebel アダプターの接続 URI の構成 |Microsoft ドキュメント
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
ms.openlocfilehash: 8017e5ccd2c033f26b03fe7443245d2fb88be960
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224330"
---
# <a name="configure-the-connection-uri-for-the-siebel-adapter"></a><span data-ttu-id="f1ad7-102">Siebel アダプターの接続 URI を構成します。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-102">Configure the connection URI for the Siebel adapter</span></span>
<span data-ttu-id="f1ad7-103">接続 URI は、Siebel システムに接続する接続文字列です。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-103">A connection URI is a connection string to connect to a Siebel system.</span></span> <span data-ttu-id="f1ad7-104">接続 URI には、Siebel システムとの接続を確立するために必要なさまざまなパラメーターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-104">The connection URI contains various parameters required to establish connection with a Siebel system.</span></span> <span data-ttu-id="f1ad7-105">この接続の両方で、デザイン時および実行時の URI を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-105">You must specify this connection URI both at the design time and the run time.</span></span> <span data-ttu-id="f1ad7-106">デザイン時に、メタデータを生成する Siebel システムへの接続に URI を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-106">At design time, you must specify the URI to connect to the Siebel system to generate the metadata.</span></span> <span data-ttu-id="f1ad7-107">実行時に、操作を実行する Siebel システムへの接続に URI を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-107">At run time, you must specify the URI to connect to the Siebel system to perform operations.</span></span>  
  
## <a name="enter-the-connection-uri-at-design-time"></a><span data-ttu-id="f1ad7-108">デザイン時に、接続 URI を入力してください。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-108">Enter the connection URI at design time</span></span>  
 <span data-ttu-id="f1ad7-109">デザイン時の接続を使用して URI を指定する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-109">For design time, you must specify the connection URI using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  
  
#### <a name="enter-the-connection-uri-using-consume-adapter-service-add-in"></a><span data-ttu-id="f1ad7-110">接続 アダプター サービスのアドインを使用して URI を入力してください。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-110">Enter the connection URI using Consume Adapter Service Add-in</span></span>  
  
1.  <span data-ttu-id="f1ad7-111">BizTalk プロジェクトを右クリックし、順にポイント**追加**、し、**生成した項目の追加**です。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-111">Right-click your BizTalk project, point to **Add**, and then select **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="f1ad7-112">**生成した項目の追加** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-112">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="f1ad7-113">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f1ad7-113">Use this</span></span>|<span data-ttu-id="f1ad7-114">目的</span><span class="sxs-lookup"><span data-stu-id="f1ad7-114">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="f1ad7-115">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="f1ad7-115">**Categories**</span></span>|<span data-ttu-id="f1ad7-116">をクリックして**アダプター サービスの使用**です。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-116">Click **Consume Adapter Service**.</span></span>|  
    |<span data-ttu-id="f1ad7-117">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="f1ad7-117">**Templates**</span></span>|<span data-ttu-id="f1ad7-118">をクリックして**アダプター サービスの使用**です。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-118">Click **Consume Adapter Service**.</span></span>|  
  
3.  <span data-ttu-id="f1ad7-119">開始する、**アダプター サービスの使用**ダイアログ ボックスで、をクリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-119">To start the **Consume Adapter Service** dialog box, click **Add**.</span></span>  
  
4.  <span data-ttu-id="f1ad7-120">**アダプター サービスの使用** ダイアログ ボックスから、**バインディングを選択**ドロップダウン リストを**siebelBinding**、 をクリック**構成**.</span><span class="sxs-lookup"><span data-stu-id="f1ad7-120">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list select **siebelBinding**, and click **Configure**.</span></span>  
  
5.  <span data-ttu-id="f1ad7-121">**アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ**タブです。**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **Username**ユーザー名と Siebel システムへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-121">In the **Configure Adapter** dialog box, click the **Security** tab. From the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the Siebel system.</span></span>  
  
6.  <span data-ttu-id="f1ad7-122">**アダプターの構成**ダイアログ ボックスで、をクリックして、 **URI プロパティ**タブおよび他のパラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-122">In the **Configure Adapter** dialog box, click the **URI Properties** tab and specify values for different parameters.</span></span> <span data-ttu-id="f1ad7-123">詳細については、接続 URI の[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を参照してください[Siebel システム接続 URI を作成](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-123">For more information about the connection URI for the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], see [Create the Siebel system connection URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md).</span></span>  
  
7.  <span data-ttu-id="f1ad7-124">**アダプターの構成**ダイアログ ボックスで、をクリックして、**バインド プロパティ** タブの値を指定します、バインディング、存在する場合は、スキーマを生成する前に指定する必要です。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-124">In the **Configure Adapter** dialog box, click the **Binding Properties** tab and specify the binding values, if any, which are required to be specified before generating the schema.</span></span> <span data-ttu-id="f1ad7-125">バインドのプロパティの詳細については、次を参照してください。 [BizTalk Adapter for Siebel のバインド プロパティ読む](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-125">For more information about binding properties, see [Read about BizTalk Adapter for Siebel Binding Properties](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span></span>  
  
8.  <span data-ttu-id="f1ad7-126">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-126">Click **OK**.</span></span>  
  
#### <a name="enter-the-connection-uri-using-add-adapter-metadata-wizard"></a><span data-ttu-id="f1ad7-127">入力アダプター メタデータの追加ウィザードを使用して、URI の接続</span><span class="sxs-lookup"><span data-stu-id="f1ad7-127">Enter the connection URI using Add Adapter Metadata Wizard</span></span>  
  
1.  <span data-ttu-id="f1ad7-128">BizTalk プロジェクトを右クリックし、順にポイント**追加**、し、**生成した項目の追加**です。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-128">Right-click your BizTalk project, point to **Add**, and then select **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="f1ad7-129">**生成した項目の追加** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-129">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="f1ad7-130">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f1ad7-130">Use this</span></span>|<span data-ttu-id="f1ad7-131">目的</span><span class="sxs-lookup"><span data-stu-id="f1ad7-131">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="f1ad7-132">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="f1ad7-132">**Categories**</span></span>|<span data-ttu-id="f1ad7-133">をクリックして**アダプターを追加**です。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-133">Click **Add Adapter**.</span></span>|  
    |<span data-ttu-id="f1ad7-134">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="f1ad7-134">**Templates**</span></span>|<span data-ttu-id="f1ad7-135">をクリックして**アダプター メタデータの追加**です。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-135">Click **Add Adapter Metadata**.</span></span>|  
  
3.  <span data-ttu-id="f1ad7-136">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-136">Click **Add**.</span></span> <span data-ttu-id="f1ad7-137">[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-137">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  
  
4.  <span data-ttu-id="f1ad7-138">アダプターの追加ウィザードで選択**Wcf-siebel**です。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-138">In the Add Adapter Wizard, select **WCF-Siebel**.</span></span> <span data-ttu-id="f1ad7-139">コンピューターを選択して[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]がインストールされていると、BizTalk データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-139">Select the computer on which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] is installed and the name of the BizTalk database.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="f1ad7-140">BizTalk で構成された Wcf-siebel ポートがある場合からポートを選択して、**ポート** ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-140">If you already have a WCF-Siebel port configured in BizTalk, select the port from the **Port** list.</span></span>  
  
5.  <span data-ttu-id="f1ad7-141">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-141">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="f1ad7-142">**アダプター サービスの使用** ダイアログ ボックスから、**バインディングを選択**ドロップダウン リストを**siebelBinding**、 をクリック**構成**.</span><span class="sxs-lookup"><span data-stu-id="f1ad7-142">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list select **siebelBinding**, and click **Configure**.</span></span>  
  
7.  <span data-ttu-id="f1ad7-143">**アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ**タブです。**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **Username**ユーザー名と Siebel システムへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-143">In the **Configure Adapter** dialog box, click the **Security** tab. From the **Client credential type** drop-down list box, select **Username** and specify the user name and password to connect to the Siebel system.</span></span>  
  
8.  <span data-ttu-id="f1ad7-144">**アダプターの構成**ダイアログ ボックスで、をクリックして、 **URI プロパティ**タブおよび他のパラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-144">In the **Configure Adapter** dialog box, click the **URI Properties** tab and specify values for different parameters.</span></span> <span data-ttu-id="f1ad7-145">詳細については、接続 URI の[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を参照してください[Siebel システム接続 URI を作成](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-145">For more information about the connection URI for the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], see [Create the Siebel system connection URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md).</span></span>  
  
9. <span data-ttu-id="f1ad7-146">**アダプターの構成**ダイアログ ボックスで、をクリックして、**バインド プロパティ** タブの値を指定します、バインディング、存在する場合は、スキーマを生成する前に指定する必要です。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-146">In the **Configure Adapter** dialog box, click the **Binding Properties** tab and specify the binding values, if any, which are required to be specified before generating the schema.</span></span> <span data-ttu-id="f1ad7-147">バインドのプロパティの詳細については、次を参照してください。 [BizTalk Adapter for Siebel のバインド プロパティ読む](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-147">For more information about binding properties, see [Read about BizTalk Adapter for Siebel Binding Properties](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f1ad7-148">既存の WCF Siebel 送信ポートを選択した場合、バインドのプロパティを指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-148">If you selected an existing WCF-Siebel send port, you need not specify the binding properties.</span></span> <span data-ttu-id="f1ad7-149">バインドのプロパティは、送信ポートの構成から取得されます。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-149">The binding properties are picked from the send port configuration.</span></span> <span data-ttu-id="f1ad7-150">ただし、存在する場合、デザイン時に、必要なバインドのプロパティを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-150">However, you may choose to specify the binding properties that are required at design-time, if any.</span></span> <span data-ttu-id="f1ad7-151">このような場合、メタデータの生成中にバインドのプロパティの新しい値をデザイン時に使用されます。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-151">In such case, the new values for binding properties will be used at design-time while generating the metadata.</span></span> <span data-ttu-id="f1ad7-152">ただし、実行時に、バインドの送信ポートの構成のプロパティの指定値適用されます。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-152">However, at run-time the values specified for binding properties in the send port configuration will be applicable.</span></span>  
  
10. <span data-ttu-id="f1ad7-153">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-153">Click **OK**.</span></span>  
  
## <a name="enter-the-connection-uri-at-run-time"></a><span data-ttu-id="f1ad7-154">実行時に、接続 URI を入力してください。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-154">Enter the connection URI at run time</span></span>  
 <span data-ttu-id="f1ad7-155">実行時に、Wcf-custom または Wcf-siebel のポート設定の一部として URI を指定する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-155">For run time, you must specify the URI as part of the WCF-Custom or WCF-Siebel port configuration in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span>  
  
#### <a name="enter-the-connection-uri-for-the-wcf-custom-port"></a><span data-ttu-id="f1ad7-156">WCF カスタム ポートの接続 URI を入力してください。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-156">Enter the connection URI for the WCF-Custom port</span></span>  
  
1.  <span data-ttu-id="f1ad7-157">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-157">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="f1ad7-158">コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、ポート、およびクリックを作成するアプリケーションの順に展開し、**送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-158">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and the click **Send Ports**.</span></span> <span data-ttu-id="f1ad7-159">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-159">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
3.  <span data-ttu-id="f1ad7-160">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-160">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
4.  <span data-ttu-id="f1ad7-161">**Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブです。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-161">In the **WCF-Custom Transport Properties** dialog box, click the **General** tab.</span></span>  
  
5.  <span data-ttu-id="f1ad7-162">**アドレス (URI)** テキスト ボックスで、接続、Siebel システムへの接続に URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-162">In the **Address (URI)** text box, specify the connection URI to connect to the Siebel system.</span></span> <span data-ttu-id="f1ad7-163">詳細については、接続 URI の[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を参照してください[Siebel システム接続 URI を作成](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-163">For more information about the connection URI for the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], see [Create the Siebel system connection URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md).</span></span>  
  
6.  <span data-ttu-id="f1ad7-164">**Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブです。**バインディングの種類**ドロップダウン リストで、 **siebelBinding**です。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-164">In the **WCF-Custom Transport Properties** dialog box, click the **Binding** tab. From the **Binding Type** drop-down list, select **siebelBinding**.</span></span>  
  
7.  <span data-ttu-id="f1ad7-165">送信ポートを作成する、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**資格情報**タブし、次のいずれかの操作します。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-165">To create a send port, in the **WCF-Custom Transport Properties** dialog box, click the **Credentials** tab and do one of the following:</span></span>  
  
    1.  <span data-ttu-id="f1ad7-166">選択、**シングル サインオンを使用しない**オプション、およびユーザー名と Siebel システムへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-166">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to a Siebel system.</span></span>  
  
    2.  <span data-ttu-id="f1ad7-167">選択、**を使用してシングル サインオン**オプション、および、ESSO 関連アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-167">Select the **Use Single Sign-On** option, and specify an affiliate ESSO application.</span></span>  
  
8.  <span data-ttu-id="f1ad7-168">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-168">Click **OK**.</span></span>  
  
#### <a name="enter-the-connection-uri-for-the-wcf-siebel-port"></a><span data-ttu-id="f1ad7-169">Wcf-siebel ポートの接続 URI を入力してください。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-169">Enter the connection URI for the WCF-Siebel port</span></span>  
  
1.  <span data-ttu-id="f1ad7-170">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-170">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="f1ad7-171">Wcf-siebel アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-171">Add the WCF-Siebel adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="f1ad7-172">手順については、次を参照してください。 [Siebel アダプターを BizTalk Server 管理コンソールに追加](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md)です。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-172">For instructions, see [Add the Siebel Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3.  <span data-ttu-id="f1ad7-173">コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、ポート、およびクリックを作成するアプリケーションの順に展開し、**送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-173">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and the click **Send Ports**.</span></span> <span data-ttu-id="f1ad7-174">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-174">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
4.  <span data-ttu-id="f1ad7-175">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストは、前に追加する Wcf-siebel アダプターを選択し、をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-175">In the port properties dialog box, from the **Type** drop-down list, select the WCF-Siebel adapter you added earlier, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="f1ad7-176">トランスポートのプロパティ ダイアログ ボックスをクリックして、**全般**タブです。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-176">In the transport properties dialog box, click the **General** tab.</span></span>  
  
6.  <span data-ttu-id="f1ad7-177">クリックして、**構成**ボタンをクリックし、接続パラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-177">Click the **Configure** button and provide values for the connection parameters.</span></span> <span data-ttu-id="f1ad7-178">詳細については、接続 URI の[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を参照してください[Siebel システム接続 URI を作成](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-178">For more information about the connection URI for the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], see [Create the Siebel system connection URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md).</span></span>  
  
7.  <span data-ttu-id="f1ad7-179">トランスポートのプロパティ ダイアログ ボックスをクリックして、**バインディング**タブし、バインドのプロパティの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-179">In the transport properties dialog box, click the **Binding** tab and specify values for binding properties.</span></span>  
  
8.  <span data-ttu-id="f1ad7-180">送信ポートを作成する、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**資格情報**タブし、次のいずれかの操作します。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-180">To create a send port, in the **WCF-Custom Transport Properties** dialog box, click the **Credentials** tab and do one of the following:</span></span>  
  
    1.  <span data-ttu-id="f1ad7-181">選択、**シングル サインオンを使用しない**オプション、およびユーザー名と Siebel システムへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-181">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to a Siebel system.</span></span>  
  
    2.  <span data-ttu-id="f1ad7-182">選択、**を使用してシングル サインオン**オプション、および、ESSO 関連アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-182">Select the **Use Single Sign-On** option, and specify an affiliate ESSO application.</span></span>  
  
9. <span data-ttu-id="f1ad7-183">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f1ad7-183">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1ad7-184">参照</span><span class="sxs-lookup"><span data-stu-id="f1ad7-184">See Also</span></span>  
[<span data-ttu-id="f1ad7-185">Siebel アダプターと BizTalk アプリケーションを作成する構成要素</span><span class="sxs-lookup"><span data-stu-id="f1ad7-185">Building blocks to create BizTalk applications with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)