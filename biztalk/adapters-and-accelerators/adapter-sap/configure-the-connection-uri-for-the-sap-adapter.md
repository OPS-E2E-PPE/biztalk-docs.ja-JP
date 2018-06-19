---
title: SAP アダプターの接続 URI の構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- connection URI, specifying at run time
- connection URI, specifying at design time
ms.assetid: 8df8e4a7-13f7-48c0-8af2-451253ced7e7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b614f3a300dbda213cd45ba7eaf9215802bc48c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218538"
---
# <a name="configure-the-connection-uri-for-the-sap-adapter"></a><span data-ttu-id="e1bf6-102">SAP アダプターの接続 URI を構成します。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-102">Configure the connection URI for the SAP adapter</span></span>
<span data-ttu-id="e1bf6-103">接続 URI は、SAP システムに接続する接続文字列です。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-103">A connection URI is a connection string to connect to an SAP system.</span></span> <span data-ttu-id="e1bf6-104">SAP システムとの接続を確立するために必要なさまざまなパラメーターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-104">It contains various parameters required to establish connection with an SAP system.</span></span> <span data-ttu-id="e1bf6-105">デザイン時に、メタデータを生成する SAP システムへの接続に URI を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-105">At design time, you must specify the URI to connect to the SAP system to generate the metadata.</span></span> <span data-ttu-id="e1bf6-106">実行時に、操作を実行する SAP システムへの接続に URI を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-106">At run time, you must specify the URI to connect to the SAP system to perform operations.</span></span>  
  
## <a name="enter-the-connection-uri-at-design-time"></a><span data-ttu-id="e1bf6-107">デザイン時に、接続 URI を入力してください。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-107">Enter the connection URI at design time</span></span>  
 <span data-ttu-id="e1bf6-108">デザイン時の接続を使用して URI を指定できます、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-108">For design time, you can specify the connection URI using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  
  
### <a name="enter-the-connection-uri-using-consume-adapter-service-add-in"></a><span data-ttu-id="e1bf6-109">接続 アダプター サービスのアドインを使用して URI を入力してください。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-109">Enter the connection URI using Consume Adapter Service Add-in</span></span>  
  
1.  <span data-ttu-id="e1bf6-110">BizTalk プロジェクトを右クリックし、順にポイント**追加**、クリックして**生成した項目の追加**です。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-110">Right-click your BizTalk project, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="e1bf6-111">**生成した項目の追加** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-111">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="e1bf6-112">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e1bf6-112">Use this</span></span>|<span data-ttu-id="e1bf6-113">目的</span><span class="sxs-lookup"><span data-stu-id="e1bf6-113">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="e1bf6-114">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="e1bf6-114">**Categories**</span></span>|<span data-ttu-id="e1bf6-115">をクリックして**アダプター サービスの使用**です。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-115">Click **Consume Adapter Service**.</span></span>|  
    |<span data-ttu-id="e1bf6-116">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="e1bf6-116">**Templates**</span></span>|<span data-ttu-id="e1bf6-117">をクリックして**アダプター サービスの使用**です。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-117">Click **Consume Adapter Service**.</span></span>|  
  
3.  <span data-ttu-id="e1bf6-118">開始する、**アダプター サービスの使用**ダイアログ ボックスで、をクリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-118">To start the **Consume Adapter Service** dialog box, click **Add**.</span></span>  
  
4.  <span data-ttu-id="e1bf6-119">**アダプター サービスの使用** ダイアログ ボックスから、**バインディングを選択**ドロップダウン リストを**sapBinding**、 をクリック**構成**.</span><span class="sxs-lookup"><span data-stu-id="e1bf6-119">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list select **sapBinding**, and click **Configure**.</span></span>  
  
5.  <span data-ttu-id="e1bf6-120">**アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ**タブです。**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **Username**ユーザー名と、SAP システムへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-120">In the **Configure Adapter** dialog box, click the **Security** tab. From the **Client credential type** drop-down list boxes, select **Username** and specify the user name and password to connect to the SAP system.</span></span>  
  
6.  <span data-ttu-id="e1bf6-121">クリックして、 **URI プロパティ**タブおよび他のパラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-121">Click the **URI Properties** tab and specify values for different parameters.</span></span> <span data-ttu-id="e1bf6-122">詳細については、接続 URI の[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を参照してください[SAP システム接続 URI を作成する](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-122">For more information about the connection URI for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], see [Create the SAP system connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span>  
  
7.  <span data-ttu-id="e1bf6-123">クリックして、**バインド プロパティ** タブの値を指定します、バインディング、存在する場合は、スキーマを生成する前に指定する必要です。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-123">Click the **Binding Properties** tab and specify the binding values, if any, which are required to be specified before generating the schema.</span></span> <span data-ttu-id="e1bf6-124">たとえばの値を指定する必要があります、 **GenerateFlatFileCompatibleIDoc** SAP システムから IDOC を受信するためのスキーマを生成する前にプロパティです。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-124">For example, you must specify a value for the **GenerateFlatFileCompatibleIDoc** property before generating schema for receiving IDOC from an SAP system.</span></span> <span data-ttu-id="e1bf6-125">バインドのプロパティの詳細については、次を参照してください。 [mySAP Business Suite のバインドのプロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-125">For more information about binding properties, see [Read about BizTalk Adapter for mySAP Business Suite binding properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
8.  <span data-ttu-id="e1bf6-126">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-126">Click **OK**.</span></span>  
  
### <a name="enter-the-connection-uri-using-add-adapter-metadata-wizard"></a><span data-ttu-id="e1bf6-127">入力アダプター メタデータの追加ウィザードを使用して、URI の接続</span><span class="sxs-lookup"><span data-stu-id="e1bf6-127">Enter the connection URI using Add Adapter Metadata Wizard</span></span>  
  
1.  <span data-ttu-id="e1bf6-128">BizTalk プロジェクトを右クリックし、順にポイント**追加**、クリックして**生成した項目の追加**です。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-128">Right-click your BizTalk project, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="e1bf6-129">**生成した項目の追加** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-129">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="e1bf6-130">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e1bf6-130">Use this</span></span>|<span data-ttu-id="e1bf6-131">目的</span><span class="sxs-lookup"><span data-stu-id="e1bf6-131">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="e1bf6-132">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="e1bf6-132">**Categories**</span></span>|<span data-ttu-id="e1bf6-133">をクリックして**アダプターを追加**です。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-133">Click **Add Adapter**.</span></span>|  
    |<span data-ttu-id="e1bf6-134">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="e1bf6-134">**Templates**</span></span>|<span data-ttu-id="e1bf6-135">をクリックして**アダプター メタデータの追加**です。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-135">Click **Add Adapter Metadata**.</span></span>|  
  
3.  <span data-ttu-id="e1bf6-136">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-136">Click **Add**.</span></span> <span data-ttu-id="e1bf6-137">[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-137">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  
  
4.  <span data-ttu-id="e1bf6-138">アダプターの追加ウィザードで選択**WCF SAP**です。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-138">In the Add Adapter Wizard, select **WCF-SAP**.</span></span> <span data-ttu-id="e1bf6-139">BizTalk Server がインストールされているコンピューターを選択し、BizTalk データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-139">Select the computer on which BizTalk Server is installed and the name of the BizTalk database.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="e1bf6-140">BizTalk で構成されている WCF SAP ポートがある場合からポートを選択して、**ポート** ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-140">If you already have a WCF-SAP port configured in BizTalk, select the port from the **Port** list.</span></span>  
  
5.  <span data-ttu-id="e1bf6-141">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-141">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="e1bf6-142">**アダプター サービスの使用** ダイアログ ボックスから、**バインディングを選択**ドロップダウン リストを**sapBinding**、 をクリック**構成**.</span><span class="sxs-lookup"><span data-stu-id="e1bf6-142">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list select **sapBinding**, and click **Configure**.</span></span>  
  
7.  <span data-ttu-id="e1bf6-143">**アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ**タブです。**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **Username**ユーザー名と、SAP システムへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-143">In the **Configure Adapter** dialog box, click the **Security** tab. From the **Client credential type** drop-down list boxes, select **Username** and specify the user name and password to connect to the SAP system.</span></span>  
  
8.  <span data-ttu-id="e1bf6-144">クリックして、 **URI プロパティ**タブおよび他のパラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-144">Click the **URI Properties** tab and specify values for different parameters.</span></span> <span data-ttu-id="e1bf6-145">詳細については、接続 URI の[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を参照してください[SAP システム接続 URI を作成する](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-145">For more information about the connection URI for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], see [Create the SAP system connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span>  
  
9. <span data-ttu-id="e1bf6-146">クリックして、**バインド プロパティ** タブの値を指定します、バインディング、存在する場合は、スキーマを生成する前に指定する必要です。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-146">Click the **Binding Properties** tab and specify the binding values, if any, which are required to be specified before generating the schema.</span></span> <span data-ttu-id="e1bf6-147">たとえばの値を指定する必要があります、 **GenerateFlatFileCompatibleIDoc** SAP システムから IDOC を受信するためのスキーマを生成する前にプロパティです。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-147">For example, you must specify a value for the **GenerateFlatFileCompatibleIDoc** property before generating schema for receiving IDOC from an SAP system.</span></span> <span data-ttu-id="e1bf6-148">バインドのプロパティの詳細については、次を参照してください。 [mySAP Business Suite のバインドのプロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-148">For more information about binding properties, see [Read about BizTalk Adapter for mySAP Business Suite binding properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e1bf6-149">既存の SAP WCF 送信ポートを選択した場合、バインドのプロパティを指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-149">If you selected an existing WCF-SAP send port, you need not specify the binding properties.</span></span> <span data-ttu-id="e1bf6-150">バインドのプロパティは、送信ポートの構成から取得されます。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-150">The binding properties are picked from the send port configuration.</span></span> <span data-ttu-id="e1bf6-151">ただし、存在する場合、デザイン時に、必要なバインドのプロパティを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-151">However, you may choose to specify the binding properties that are required at design-time, if any.</span></span> <span data-ttu-id="e1bf6-152">このような場合、メタデータの生成中にバインドのプロパティの新しい値をデザイン時に使用されます。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-152">In such case, the new values for binding properties will be used at design-time while generating the metadata.</span></span> <span data-ttu-id="e1bf6-153">ただし、実行時に、バインドの送信ポートの構成のプロパティの指定値適用されます。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-153">However, at run-time the values specified for binding properties in the send port configuration will be applicable.</span></span>  
  
10. <span data-ttu-id="e1bf6-154">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-154">Click **OK**.</span></span>  
  
## <a name="enter-the-connection-uri-at-run-time"></a><span data-ttu-id="e1bf6-155">実行時に、接続 URI を入力してください。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-155">Enter the connection URI at run time</span></span>  
 <span data-ttu-id="e1bf6-156">構成の一部として、Wcf-custom または WCF SAP ポートの URI を指定する、実行時に、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-156">For run time, you can specify the URI as part of the WCF-Custom or WCF-SAP port configuration in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
### <a name="enter-the-connection-uri-for-the-wcf-custom-port"></a><span data-ttu-id="e1bf6-157">WCF カスタム ポートの接続 URI を入力してください。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-157">Enter the connection URI for the WCF-Custom port</span></span>  
  
1.  <span data-ttu-id="e1bf6-158">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-158">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="e1bf6-159">コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、ポートを作成し、をクリックする、アプリケーションの順に展開および**送信ポート**または**受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-159">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="e1bf6-160">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-160">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
3.  <span data-ttu-id="e1bf6-161">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-161">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e1bf6-162">受信ポートの場所のプロパティ ダイアログ ボックスを表示するをクリックして、**受信場所の**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**です。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-162">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="e1bf6-163">**Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブです。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-163">In the **WCF-Custom Transport Properties** dialog box, click the **General** tab.</span></span>  
  
5.  <span data-ttu-id="e1bf6-164">**アドレス (URI)** テキスト ボックスで、接続、SAP システムへの接続に URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-164">In the **Address (URI)** text box, specify the connection URI to connect to the SAP system.</span></span> <span data-ttu-id="e1bf6-165">詳細については、接続 URI の[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を参照してください[SAP システム接続 URI を作成する](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-165">For more information about the connection URI for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], see [Create the SAP system connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span>  
  
6.  <span data-ttu-id="e1bf6-166">**Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブです。**バインディングの種類**ドロップダウン リストで、 **sapBinding**です。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-166">In the **WCF-Custom Transport Properties** dialog box, click the **Binding** tab. From the **Binding Type** drop-down list, select **sapBinding**.</span></span>  
  
7.  <span data-ttu-id="e1bf6-167">送信ポートを作成する場合、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**資格情報**タブし、次のいずれかの操作します。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-167">If you are creating a send port, in the **WCF-Custom Transport Properties** dialog box, click the **Credentials** tab and do one of the following:</span></span>  
  
    1.  <span data-ttu-id="e1bf6-168">選択、**シングル サインオンを使用しない**オプション、およびユーザー名と、SAP システムへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-168">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to the SAP system.</span></span>  
  
    2.  <span data-ttu-id="e1bf6-169">選択、**を使用してシングル サインオン**オプション、および関連するエンタープライズ シングル サインオン (SSO) アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-169">Select the **Use Single Sign-On** option, and specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  
  
8.  <span data-ttu-id="e1bf6-170">受信ポートを作成する場合、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**他の**タブし、次のいずれかの操作します。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-170">If you are creating a receive port, in the **WCF-Custom Transport Properties** dialog box, click the **Other** tab and do one of the following:</span></span>  
  
    1.  <span data-ttu-id="e1bf6-171">選択**ユーザー アカウント**オプション、およびユーザー名と、SAP システムへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-171">Select **User account** option, and specify the user name and password to connect to the SAP system.</span></span>  
  
    2.  <span data-ttu-id="e1bf6-172">選択**から資格情報を取得関連アプリケーション**オプション、および SSO 関連アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-172">Select **Get credentials from affiliate application** option, and specify an affiliate SSO application.</span></span>  
  
9. <span data-ttu-id="e1bf6-173">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-173">Click **OK**.</span></span>  
  
### <a name="enter-the-connection-uri-for-the-wcf-sap-port"></a><span data-ttu-id="e1bf6-174">WCF SAP ポートの接続 URI を入力してください。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-174">Enter the connection URI for the WCF-SAP port</span></span>  
  
1.  <span data-ttu-id="e1bf6-175">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-175">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="e1bf6-176">WCF SAP アダプターを追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-176">Add the WCF-SAP adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="e1bf6-177">手順については、次を参照してください。 [SAP アダプターを BizTalk Server 管理コンソールに追加](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md)です。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-177">For instructions, see [Add the SAP Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3.  <span data-ttu-id="e1bf6-178">コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、ポートを作成し、をクリックする、アプリケーションの順に展開および**送信ポート**または**受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-178">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="e1bf6-179">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-179">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
4.  <span data-ttu-id="e1bf6-180">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストは、前に追加する WCF SAP アダプターを選択し、をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-180">In the port properties dialog box, from the **Type** drop-down list, select the WCF-SAP adapter you added earlier, and then click **Configure**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e1bf6-181">受信ポートの場所のプロパティ ダイアログ ボックスを表示するをクリックして、**受信場所の**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**です。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-181">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  
  
5.  <span data-ttu-id="e1bf6-182">トランスポートのプロパティ ダイアログ ボックスをクリックして、**全般**タブです。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-182">In the transport properties dialog box, click the **General** tab.</span></span>  
  
6.  <span data-ttu-id="e1bf6-183">クリックして、**構成**ボタンをクリックし、接続パラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-183">Click the **Configure** button and provide values for the connection parameters.</span></span> <span data-ttu-id="e1bf6-184">詳細については、接続 URI の[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を参照してください[SAP システム接続 URI を作成する](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-184">For more information about the connection URI for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], see [Create the SAP system connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span>  
  
7.  <span data-ttu-id="e1bf6-185">トランスポートのプロパティ ダイアログ ボックスをクリックして、**バインディング**タブし、バインドのプロパティの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-185">In the transport properties dialog box, click the **Binding** tab and specify values for binding properties.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e1bf6-186">バインドのプロパティは、送信ポートまたは受信ポートを構成するかどうかに基づいてが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-186">The binding properties are displayed based on whether you are configuring a send port or a receive port.</span></span> <span data-ttu-id="e1bf6-187">たとえば、バインディングのプロパティの受信に関連する操作利用できない受信操作には、受信ポートの構成が必要とするために、送信ポートを構成するときにします。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-187">For example, binding properties related to inbound operations are not available while configuring a send port because inbound operations require a receive port configuration.</span></span>  
  
8.  <span data-ttu-id="e1bf6-188">トランスポートのプロパティ ダイアログ ボックスで、送信ポートを作成する場合にクリックして、**資格情報**タブし、次のいずれかの操作します。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-188">If you are creating a send port, in the transport properties dialog box, click the **Credentials** tab and do one of the following:</span></span>  
  
    1.  <span data-ttu-id="e1bf6-189">選択、**シングル サインオンを使用しない**オプション、およびユーザー名と、SAP システムへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-189">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to the SAP system.</span></span>  
  
    2.  <span data-ttu-id="e1bf6-190">選択、**を使用してシングル サインオン**オプション、および関連するエンタープライズ シングル サインオン (SSO) アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-190">Select the **Use Single Sign-On** option, and specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  
  
9. <span data-ttu-id="e1bf6-191">受信ポートを作成する場合、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**他の**タブし、次のいずれかの操作します。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-191">If you are creating a receive port, in the **WCF-Custom Transport Properties** dialog box, click the **Other** tab and do one of the following:</span></span>  
  
    1.  <span data-ttu-id="e1bf6-192">選択**ユーザー アカウント**オプション、およびユーザー名と、SAP システムへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-192">Select **User account** option, and specify the user name and password to connect to the SAP system.</span></span>  
  
    2.  <span data-ttu-id="e1bf6-193">選択**から資格情報を取得関連アプリケーション**オプション、および SSO 関連アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-193">Select **Get credentials from affiliate application** option, and specify an affiliate SSO application.</span></span>  
  
10. <span data-ttu-id="e1bf6-194">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e1bf6-194">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1bf6-195">参照</span><span class="sxs-lookup"><span data-stu-id="e1bf6-195">See Also</span></span>  
[<span data-ttu-id="e1bf6-196">SAP アプリケーションを作成する構成要素</span><span class="sxs-lookup"><span data-stu-id="e1bf6-196">Building blocks to create SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)