---
title: SAP アダプターの接続 URI の構成 |Microsoft Docs
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
ms.openlocfilehash: 88e96df27b0a8a26b20581e3ff757181ac8195cb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983051"
---
# <a name="configure-the-connection-uri-for-the-sap-adapter"></a><span data-ttu-id="ad9dd-102">SAP アダプターの接続 URI を構成します。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-102">Configure the connection URI for the SAP adapter</span></span>
<span data-ttu-id="ad9dd-103">接続 URI は、SAP システムへの接続への接続文字列です。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-103">A connection URI is a connection string to connect to an SAP system.</span></span> <span data-ttu-id="ad9dd-104">SAP システムとの接続を確立するために必要なさまざまなパラメーターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-104">It contains various parameters required to establish connection with an SAP system.</span></span> <span data-ttu-id="ad9dd-105">、デザイン時に、メタデータを生成する SAP システムに接続するための URI を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-105">At design time, you must specify the URI to connect to the SAP system to generate the metadata.</span></span> <span data-ttu-id="ad9dd-106">実行時に、操作を実行する SAP システムに接続する URI を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-106">At run time, you must specify the URI to connect to the SAP system to perform operations.</span></span>  

## <a name="enter-the-connection-uri-at-design-time"></a><span data-ttu-id="ad9dd-107">デザイン時の接続 URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-107">Enter the connection URI at design time</span></span>  
 <span data-ttu-id="ad9dd-108">デザイン時に、使用して接続 URI を指定できます、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-108">For design time, you can specify the connection URI using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  

### <a name="enter-the-connection-uri-using-consume-adapter-service-add-in"></a><span data-ttu-id="ad9dd-109">接続 Consume Adapter Service アドインを使用して URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-109">Enter the connection URI using Consume Adapter Service Add-in</span></span>  

1. <span data-ttu-id="ad9dd-110">BizTalk プロジェクトを右クリックし、[**追加**、] をクリックし、**生成した項目の追加**します。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-110">Right-click your BizTalk project, point to **Add**, and then click **Add Generated Items**.</span></span>  

2. <span data-ttu-id="ad9dd-111">**生成した項目の追加** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-111">In the **Add Generated Items** dialog box, do the following:</span></span>  


   |    <span data-ttu-id="ad9dd-112">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ad9dd-112">Use this</span></span>    |             <span data-ttu-id="ad9dd-113">目的</span><span class="sxs-lookup"><span data-stu-id="ad9dd-113">To do this</span></span>             |
   |----------------|------------------------------------|
   | <span data-ttu-id="ad9dd-114">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="ad9dd-114">**Categories**</span></span> | <span data-ttu-id="ad9dd-115">クリックして**アダプター サービスの使用**します。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-115">Click **Consume Adapter Service**.</span></span> |
   | <span data-ttu-id="ad9dd-116">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="ad9dd-116">**Templates**</span></span>  | <span data-ttu-id="ad9dd-117">クリックして**アダプター サービスの使用**します。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-117">Click **Consume Adapter Service**.</span></span> |


3. <span data-ttu-id="ad9dd-118">開始する、 **Consume Adapter Service**ダイアログ ボックスで、をクリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-118">To start the **Consume Adapter Service** dialog box, click **Add**.</span></span>  

4. <span data-ttu-id="ad9dd-119">**Consume Adapter Service**  ダイアログ ボックスから、**バインディングを選択**ドロップダウン リストを**sapBinding**、 をクリック**構成**.</span><span class="sxs-lookup"><span data-stu-id="ad9dd-119">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list select **sapBinding**, and click **Configure**.</span></span>  

5. <span data-ttu-id="ad9dd-120">**アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ**タブ。**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **Username**ユーザー名と SAP システムへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-120">In the **Configure Adapter** dialog box, click the **Security** tab. From the **Client credential type** drop-down list boxes, select **Username** and specify the user name and password to connect to the SAP system.</span></span>  

6. <span data-ttu-id="ad9dd-121">をクリックして、 **URI プロパティ**タブし、さまざまなパラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-121">Click the **URI Properties** tab and specify values for different parameters.</span></span> <span data-ttu-id="ad9dd-122">接続 URI の詳細についてはの[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を参照してください[SAP システム接続 URI の作成](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-122">For more information about the connection URI for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], see [Create the SAP system connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span>  

7. <span data-ttu-id="ad9dd-123">をクリックして、**バインドのプロパティ**タブし、バインドの値を指定、存在する場合は、スキーマを生成する前に指定するために必要です。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-123">Click the **Binding Properties** tab and specify the binding values, if any, which are required to be specified before generating the schema.</span></span> <span data-ttu-id="ad9dd-124">たとえばの値を指定する必要があります、 **GenerateFlatFileCompatibleIDoc** SAP システムから IDOC を受信するためのスキーマを生成する前にプロパティ。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-124">For example, you must specify a value for the **GenerateFlatFileCompatibleIDoc** property before generating schema for receiving IDOC from an SAP system.</span></span> <span data-ttu-id="ad9dd-125">バインド プロパティの詳細については、[mySAP Business Suite のバインドのプロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-125">For more information about binding properties, see [Read about BizTalk Adapter for mySAP Business Suite binding properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  

8. <span data-ttu-id="ad9dd-126">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-126">Click **OK**.</span></span>  

### <a name="enter-the-connection-uri-using-add-adapter-metadata-wizard"></a><span data-ttu-id="ad9dd-127">アダプター メタデータの追加ウィザードを使用して、URI の接続を入力します。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-127">Enter the connection URI using Add Adapter Metadata Wizard</span></span>  

1. <span data-ttu-id="ad9dd-128">BizTalk プロジェクトを右クリックし、[**追加**、] をクリックし、**生成した項目の追加**します。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-128">Right-click your BizTalk project, point to **Add**, and then click **Add Generated Items**.</span></span>  

2. <span data-ttu-id="ad9dd-129">**生成した項目の追加** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-129">In the **Add Generated Items** dialog box, do the following:</span></span>  


   |    <span data-ttu-id="ad9dd-130">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ad9dd-130">Use this</span></span>    |           <span data-ttu-id="ad9dd-131">目的</span><span class="sxs-lookup"><span data-stu-id="ad9dd-131">To do this</span></span>            |
   |----------------|---------------------------------|
   | <span data-ttu-id="ad9dd-132">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="ad9dd-132">**Categories**</span></span> |     <span data-ttu-id="ad9dd-133">クリックして**アダプターを追加**します。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-133">Click **Add Adapter**.</span></span>      |
   | <span data-ttu-id="ad9dd-134">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="ad9dd-134">**Templates**</span></span>  | <span data-ttu-id="ad9dd-135">クリックして**アダプター メタデータの追加**します。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-135">Click **Add Adapter Metadata**.</span></span> |


3. <span data-ttu-id="ad9dd-136">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-136">Click **Add**.</span></span> <span data-ttu-id="ad9dd-137">[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-137">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  

4. <span data-ttu-id="ad9dd-138">アダプターの追加ウィザードで選択**WCF-SAP**します。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-138">In the Add Adapter Wizard, select **WCF-SAP**.</span></span> <span data-ttu-id="ad9dd-139">BizTalk Server がインストールされているコンピューターを選択し、BizTalk データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-139">Select the computer on which BizTalk Server is installed and the name of the BizTalk database.</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="ad9dd-140">BizTalk で構成されている WCF SAP ポート既にある場合からポートを選択して、**ポート**一覧。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-140">If you already have a WCF-SAP port configured in BizTalk, select the port from the **Port** list.</span></span>  

5. <span data-ttu-id="ad9dd-141">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-141">Click **Next**.</span></span>  

6. <span data-ttu-id="ad9dd-142">**Consume Adapter Service**  ダイアログ ボックスから、**バインディングを選択**ドロップダウン リストを**sapBinding**、 をクリック**構成**.</span><span class="sxs-lookup"><span data-stu-id="ad9dd-142">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list select **sapBinding**, and click **Configure**.</span></span>  

7. <span data-ttu-id="ad9dd-143">**アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ**タブ。**クライアント資格情報の種類**ドロップダウン リスト ボックスで、 **Username**ユーザー名と SAP システムへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-143">In the **Configure Adapter** dialog box, click the **Security** tab. From the **Client credential type** drop-down list boxes, select **Username** and specify the user name and password to connect to the SAP system.</span></span>  

8. <span data-ttu-id="ad9dd-144">をクリックして、 **URI プロパティ**タブし、さまざまなパラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-144">Click the **URI Properties** tab and specify values for different parameters.</span></span> <span data-ttu-id="ad9dd-145">接続 URI の詳細についてはの[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を参照してください[SAP システム接続 URI の作成](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-145">For more information about the connection URI for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], see [Create the SAP system connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span>  

9. <span data-ttu-id="ad9dd-146">をクリックして、**バインドのプロパティ**タブし、バインドの値を指定、存在する場合は、スキーマを生成する前に指定するために必要です。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-146">Click the **Binding Properties** tab and specify the binding values, if any, which are required to be specified before generating the schema.</span></span> <span data-ttu-id="ad9dd-147">たとえばの値を指定する必要があります、 **GenerateFlatFileCompatibleIDoc** SAP システムから IDOC を受信するためのスキーマを生成する前にプロパティ。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-147">For example, you must specify a value for the **GenerateFlatFileCompatibleIDoc** property before generating schema for receiving IDOC from an SAP system.</span></span> <span data-ttu-id="ad9dd-148">バインド プロパティの詳細については、[mySAP Business Suite のバインドのプロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-148">For more information about binding properties, see [Read about BizTalk Adapter for mySAP Business Suite binding properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="ad9dd-149">既存の SAP では WCF 送信ポートを選択した場合は、バインドのプロパティを指定する必要がありますできません。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-149">If you selected an existing WCF-SAP send port, you need not specify the binding properties.</span></span> <span data-ttu-id="ad9dd-150">バインドのプロパティは、送信ポートの構成から取得されます。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-150">The binding properties are picked from the send port configuration.</span></span> <span data-ttu-id="ad9dd-151">ただし、存在する場合に、デザイン時に必要なバインドのプロパティを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-151">However, you may choose to specify the binding properties that are required at design-time, if any.</span></span> <span data-ttu-id="ad9dd-152">このような場合、メタデータの生成中にプロパティをバインドするための新しい値をデザイン時に使用されます。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-152">In such case, the new values for binding properties will be used at design-time while generating the metadata.</span></span> <span data-ttu-id="ad9dd-153">ただし、実行時に送信ポートの構成でバインドのプロパティに指定された値を適用できるになります。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-153">However, at run-time the values specified for binding properties in the send port configuration will be applicable.</span></span>  

10. <span data-ttu-id="ad9dd-154">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-154">Click **OK**.</span></span>  

## <a name="enter-the-connection-uri-at-run-time"></a><span data-ttu-id="ad9dd-155">実行時に、接続 URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-155">Enter the connection URI at run time</span></span>  
 <span data-ttu-id="ad9dd-156">実行時の URI を指定で Wcf-custom または WCF SAP ポートの構成の一部として、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-156">For run time, you can specify the URI as part of the WCF-Custom or WCF-SAP port configuration in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

### <a name="enter-the-connection-uri-for-the-wcf-custom-port"></a><span data-ttu-id="ad9dd-157">WCF カスタム ポートの接続 URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-157">Enter the connection URI for the WCF-Custom port</span></span>  

1. <span data-ttu-id="ad9dd-158">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-158">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="ad9dd-159">コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、順に展開する、ポートを作成し、をクリックしアプリケーション**送信ポート**または**受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-159">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="ad9dd-160">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-160">In the right pane, you can choose to create a port or select an existing port.</span></span>  

3. <span data-ttu-id="ad9dd-161">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-161">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="ad9dd-162">受信ポートの場所のプロパティ ダイアログ ボックスを表示する をクリックして、**受信場所**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**します。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-162">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  

4. <span data-ttu-id="ad9dd-163">**Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブ。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-163">In the **WCF-Custom Transport Properties** dialog box, click the **General** tab.</span></span>  

5. <span data-ttu-id="ad9dd-164">**アドレス (URI)** テキスト ボックスで、SAP システムに接続する接続 URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-164">In the **Address (URI)** text box, specify the connection URI to connect to the SAP system.</span></span> <span data-ttu-id="ad9dd-165">接続 URI の詳細についてはの[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を参照してください[SAP システム接続 URI の作成](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-165">For more information about the connection URI for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], see [Create the SAP system connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span>  

6. <span data-ttu-id="ad9dd-166">**Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブ。**バインドの種類**ドロップダウン リストで、 **sapBinding**します。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-166">In the **WCF-Custom Transport Properties** dialog box, click the **Binding** tab. From the **Binding Type** drop-down list, select **sapBinding**.</span></span>  

7. <span data-ttu-id="ad9dd-167">送信ポートを作成する場合、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**資格情報**タブし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-167">If you are creating a send port, in the **WCF-Custom Transport Properties** dialog box, click the **Credentials** tab and do one of the following:</span></span>  

   1.  <span data-ttu-id="ad9dd-168">選択、**シングル サインオンを使用しないでください**オプション、およびユーザー名と SAP システムへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-168">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to the SAP system.</span></span>  

   2.  <span data-ttu-id="ad9dd-169">選択、**使用してシングル サインオン**オプション、および関連アプリケーションにエンタープライズ シングル サインオン (SSO) を指定します。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-169">Select the **Use Single Sign-On** option, and specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  

8. <span data-ttu-id="ad9dd-170">受信ポートを作成する場合、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、 をクリックして、**他**タブし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-170">If you are creating a receive port, in the **WCF-Custom Transport Properties** dialog box, click the **Other** tab and do one of the following:</span></span>  

   1.  <span data-ttu-id="ad9dd-171">選択**ユーザー アカウント**オプション、およびユーザー名と SAP システムへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-171">Select **User account** option, and specify the user name and password to connect to the SAP system.</span></span>  

   2.  <span data-ttu-id="ad9dd-172">選択**関連アプリケーションから資格情報を Get**オプション、および SSO 関連アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-172">Select **Get credentials from affiliate application** option, and specify an affiliate SSO application.</span></span>  

9. <span data-ttu-id="ad9dd-173">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-173">Click **OK**.</span></span>  

### <a name="enter-the-connection-uri-for-the-wcf-sap-port"></a><span data-ttu-id="ad9dd-174">WCF SAP ポートの接続 URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-174">Enter the connection URI for the WCF-SAP port</span></span>  

1. <span data-ttu-id="ad9dd-175">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-175">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="ad9dd-176">WCF-SAP アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-176">Add the WCF-SAP adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="ad9dd-177">手順については、[SAP アダプターを BizTalk Server 管理コンソールに追加](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-177">For instructions, see [Add the SAP Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md).</span></span>  

3. <span data-ttu-id="ad9dd-178">コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、順に展開する、ポートを作成し、をクリックしアプリケーション**送信ポート**または**受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-178">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="ad9dd-179">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-179">In the right pane, you can choose to create a port or select an existing port.</span></span>  

4. <span data-ttu-id="ad9dd-180">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストでは、先ほど追加した WCF-SAP アダプターを選択し、順にクリックします**構成**します。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-180">In the port properties dialog box, from the **Type** drop-down list, select the WCF-SAP adapter you added earlier, and then click **Configure**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="ad9dd-181">受信ポートの場所のプロパティ ダイアログ ボックスを表示する をクリックして、**受信場所**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**します。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-181">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  

5. <span data-ttu-id="ad9dd-182">トランスポートのプロパティ ダイアログ ボックスでをクリックして、**全般**タブ。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-182">In the transport properties dialog box, click the **General** tab.</span></span>  

6. <span data-ttu-id="ad9dd-183">をクリックして、**構成**ボタンをクリックし、接続パラメーターの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-183">Click the **Configure** button and provide values for the connection parameters.</span></span> <span data-ttu-id="ad9dd-184">接続 URI の詳細についてはの[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を参照してください[SAP システム接続 URI の作成](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-184">For more information about the connection URI for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], see [Create the SAP system connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span>  

7. <span data-ttu-id="ad9dd-185">トランスポートのプロパティ ダイアログ ボックスでをクリックして、**バインド**タブし、バインドのプロパティの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-185">In the transport properties dialog box, click the **Binding** tab and specify values for binding properties.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="ad9dd-186">バインドのプロパティは、送信ポートまたは受信ポートを構成するかどうかに基づいて表示されます。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-186">The binding properties are displayed based on whether you are configuring a send port or a receive port.</span></span> <span data-ttu-id="ad9dd-187">たとえば、バインディングのプロパティに関連する受信操作をご利用いただけません受信操作には、受信ポートの構成が必要とするために、送信ポートを構成するときに。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-187">For example, binding properties related to inbound operations are not available while configuring a send port because inbound operations require a receive port configuration.</span></span>  

8. <span data-ttu-id="ad9dd-188">トランスポートのプロパティ ダイアログ ボックスで、送信ポートを作成する場合にクリックして、**資格情報**タブし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-188">If you are creating a send port, in the transport properties dialog box, click the **Credentials** tab and do one of the following:</span></span>  

   1.  <span data-ttu-id="ad9dd-189">選択、**シングル サインオンを使用しないでください**オプション、およびユーザー名と SAP システムへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-189">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to the SAP system.</span></span>  

   2.  <span data-ttu-id="ad9dd-190">選択、**使用してシングル サインオン**オプション、および関連アプリケーションにエンタープライズ シングル サインオン (SSO) を指定します。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-190">Select the **Use Single Sign-On** option, and specify an affiliate Enterprise Single Sign-on (SSO) application.</span></span>  

9. <span data-ttu-id="ad9dd-191">受信ポートを作成する場合、 **Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、 をクリックして、**他**タブし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-191">If you are creating a receive port, in the **WCF-Custom Transport Properties** dialog box, click the **Other** tab and do one of the following:</span></span>  

    1.  <span data-ttu-id="ad9dd-192">選択**ユーザー アカウント**オプション、およびユーザー名と SAP システムへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-192">Select **User account** option, and specify the user name and password to connect to the SAP system.</span></span>  

    2.  <span data-ttu-id="ad9dd-193">選択**関連アプリケーションから資格情報を Get**オプション、および SSO 関連アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-193">Select **Get credentials from affiliate application** option, and specify an affiliate SSO application.</span></span>  

10. <span data-ttu-id="ad9dd-194">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad9dd-194">Click **OK**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="ad9dd-195">参照</span><span class="sxs-lookup"><span data-stu-id="ad9dd-195">See Also</span></span>  
[<span data-ttu-id="ad9dd-196">SAP アプリケーションを作成するための構成要素</span><span class="sxs-lookup"><span data-stu-id="ad9dd-196">Building blocks to create SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)