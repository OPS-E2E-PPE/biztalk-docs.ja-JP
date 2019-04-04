---
title: SAP アダプターのバインドのプロパティの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- binding properties, specifying at design time
- binding properties, specifying at run time
ms.assetid: 259a5895-c19d-409c-b2fc-bfdf59d5d74b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ef599f91675d4604d9e9f56aafdef3677d2583a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001971"
---
# <a name="configure-the-binding-properties-for-the-sap-adapter"></a><span data-ttu-id="af51e-102">SAP アダプターのバインドのプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="af51e-102">Configure the binding properties for the SAP adapter</span></span>
<span data-ttu-id="af51e-103">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]動作特性を制御するためのいくつかのバインドのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="af51e-103">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces several binding properties that enable you to control some of its behavioral characteristics.</span></span> <span data-ttu-id="af51e-104">このセクションでは、および Visual Studio (デザイン時) からバインドのプロパティを設定する方法についての情報を提供します。、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールを (実行時)。</span><span class="sxs-lookup"><span data-stu-id="af51e-104">This section provides information about setting the binding properties from Visual Studio (design time) and from the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console (run time).</span></span> <span data-ttu-id="af51e-105">デザイン時に、特定の操作のスキーマを生成するバインドのプロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af51e-105">At design time, you must specify the binding properties to generate schema for specific operations.</span></span> <span data-ttu-id="af51e-106">実行時にには、送信の一部としてのバインドのプロパティを指定または SAP システムからのメッセージの送受信用のポートを受信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af51e-106">At run time, you must specify the binding properties as part of the send or receive port for sending or receiving messages from the SAP system.</span></span>  

 <span data-ttu-id="af51e-107">バインドのプロパティについては、バインドのプロパティの一覧を含む[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を参照してください[mySAP Business Suite のバインドのプロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="af51e-107">For information about the binding properties, including a list of binding properties for [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], see [Read about BizTalk Adapter for mySAP Business Suite binding properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  

## <a name="enter-binding-properties-at-design-time"></a><span data-ttu-id="af51e-108">デザイン時のバインドのプロパティを入力します。</span><span class="sxs-lookup"><span data-stu-id="af51e-108">Enter Binding Properties at Design Time</span></span>  
 <span data-ttu-id="af51e-109">デザイン時に、バインドのプロパティを使用して指定できます、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="af51e-109">For design time, you can specify the binding properties using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  

### <a name="enter-binding-properties-using-consume-adapter-service-add-in"></a><span data-ttu-id="af51e-110">Consume Adapter Service アドインを使用してバインドのプロパティを入力します。</span><span class="sxs-lookup"><span data-stu-id="af51e-110">Enter binding properties using Consume Adapter Service Add-in</span></span>  

1.  <span data-ttu-id="af51e-111">BizTalk プロジェクトを右クリックし、[**追加**、] をクリックし、**生成した項目の追加**します。</span><span class="sxs-lookup"><span data-stu-id="af51e-111">Right-click your BizTalk project, point to **Add**, and then click **Add Generated Items**.</span></span>  

2.  <span data-ttu-id="af51e-112">**生成した項目の追加** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="af51e-112">In the **Add Generated Items** dialog box, do the following:</span></span>  

    |<span data-ttu-id="af51e-113">プロパティ</span><span class="sxs-lookup"><span data-stu-id="af51e-113">Use this</span></span>|<span data-ttu-id="af51e-114">目的</span><span class="sxs-lookup"><span data-stu-id="af51e-114">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="af51e-115">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="af51e-115">**Categories**</span></span>|<span data-ttu-id="af51e-116">クリックして**アダプター サービスの使用**します。</span><span class="sxs-lookup"><span data-stu-id="af51e-116">Click **Consume Adapter Service**.</span></span>|  
    |<span data-ttu-id="af51e-117">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="af51e-117">**Templates**</span></span>|<span data-ttu-id="af51e-118">クリックして**アダプター サービスの使用**します。</span><span class="sxs-lookup"><span data-stu-id="af51e-118">Click **Consume Adapter Service**.</span></span>|  

3.  <span data-ttu-id="af51e-119">開始する、 **Consume Adapter Service**ダイアログ ボックスで、をクリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="af51e-119">To start the **Consume Adapter Service** dialog box, click **Add**.</span></span>  

4.  <span data-ttu-id="af51e-120">**Consume Adapter Service**  ダイアログ ボックスから、**バインディングを選択**ドロップダウン リストを**sapBinding**、 をクリック**構成**.</span><span class="sxs-lookup"><span data-stu-id="af51e-120">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list select **sapBinding**, and click **Configure**.</span></span>  

5.  <span data-ttu-id="af51e-121">**アダプターの構成**ダイアログ ボックスで、をクリックして、**バインド プロパティ**タブをクリックし、別のバインド プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="af51e-121">In the **Configure Adapter** dialog box, click the **Binding Properties** tab, and then specify the different binding properties.</span></span>  

6.  <span data-ttu-id="af51e-122">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af51e-122">Click **OK**.</span></span>  

### <a name="enter-binding-properties-using-add-adapter-metadata-wizard"></a><span data-ttu-id="af51e-123">アダプター メタデータの追加ウィザードを使用してバインドのプロパティを入力します。</span><span class="sxs-lookup"><span data-stu-id="af51e-123">Enter binding properties using Add Adapter Metadata Wizard</span></span>  

1. <span data-ttu-id="af51e-124">BizTalk プロジェクトを右クリックし、[**追加**、] をクリックし、**生成した項目の追加**します。</span><span class="sxs-lookup"><span data-stu-id="af51e-124">Right-click your BizTalk project, point to **Add**, and then click **Add Generated Items**.</span></span>  

2. <span data-ttu-id="af51e-125">**生成した項目の追加** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="af51e-125">In the **Add Generated Items** dialog box, do the following:</span></span>  


   |    <span data-ttu-id="af51e-126">プロパティ</span><span class="sxs-lookup"><span data-stu-id="af51e-126">Use this</span></span>    |           <span data-ttu-id="af51e-127">目的</span><span class="sxs-lookup"><span data-stu-id="af51e-127">To do this</span></span>            |
   |----------------|---------------------------------|
   | <span data-ttu-id="af51e-128">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="af51e-128">**Categories**</span></span> |     <span data-ttu-id="af51e-129">クリックして**アダプターを追加**します。</span><span class="sxs-lookup"><span data-stu-id="af51e-129">Click **Add Adapter**.</span></span>      |
   | <span data-ttu-id="af51e-130">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="af51e-130">**Templates**</span></span>  | <span data-ttu-id="af51e-131">クリックして**アダプター メタデータの追加**します。</span><span class="sxs-lookup"><span data-stu-id="af51e-131">Click **Add Adapter Metadata**.</span></span> |


3. <span data-ttu-id="af51e-132">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af51e-132">Click **Add**.</span></span> <span data-ttu-id="af51e-133">[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="af51e-133">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  

4. <span data-ttu-id="af51e-134">アダプターの追加ウィザードで選択**WCF-SAP**します。</span><span class="sxs-lookup"><span data-stu-id="af51e-134">In the Add Adapter Wizard, select **WCF-SAP**.</span></span> <span data-ttu-id="af51e-135">BizTalk Server がインストールされているコンピューターを選択し、BizTalk データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="af51e-135">Select the computer on which BizTalk Server is installed and the name of the BizTalk database.</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="af51e-136">BizTalk で構成されている WCF SAP ポート既にある場合からポートを選択して、**ポート**一覧。</span><span class="sxs-lookup"><span data-stu-id="af51e-136">If you already have a WCF-SAP port configured in BizTalk, select the port from the **Port** list.</span></span>  

5. <span data-ttu-id="af51e-137">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af51e-137">Click **Next**.</span></span>  

6. <span data-ttu-id="af51e-138">**Consume Adapter Service**  ダイアログ ボックスから、**バインディングを選択**ドロップダウン リストを**sapBinding**、 をクリック**構成**.</span><span class="sxs-lookup"><span data-stu-id="af51e-138">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list select **sapBinding**, and click **Configure**.</span></span>  

7. <span data-ttu-id="af51e-139">をクリックして、**バインドのプロパティ**タブし、バインドの値を指定、存在する場合は、スキーマを生成する前に指定するために必要です。</span><span class="sxs-lookup"><span data-stu-id="af51e-139">Click the **Binding Properties** tab and specify the binding values, if any, which are required to be specified before generating the schema.</span></span> <span data-ttu-id="af51e-140">たとえばの値を指定する必要があります、 **GenerateFlatFileCompatibleIDoc** SAP システムから IDOC を受信するためのスキーマを生成する前にプロパティ。</span><span class="sxs-lookup"><span data-stu-id="af51e-140">For example, you must specify a value for the **GenerateFlatFileCompatibleIDoc** property before generating schema for receiving IDOC from an SAP system.</span></span> <span data-ttu-id="af51e-141">バインド プロパティの詳細については、[mySAP Business Suite のバインドのプロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af51e-141">For more information about binding properties, see [Read about BizTalk Adapter for mySAP Business Suite binding properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="af51e-142">既存の SAP では WCF 送信ポートを選択した場合は、バインドのプロパティを指定する必要がありますできません。</span><span class="sxs-lookup"><span data-stu-id="af51e-142">If you selected an existing WCF-SAP send port, you need not specify the binding properties.</span></span> <span data-ttu-id="af51e-143">バインドのプロパティは、送信ポートの構成から取得されます。</span><span class="sxs-lookup"><span data-stu-id="af51e-143">The binding properties are picked from the send port configuration.</span></span> <span data-ttu-id="af51e-144">ただし、存在する場合に、デザイン時に必要なバインドのプロパティを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="af51e-144">However, you may choose to specify the binding properties that are required at design-time, if any.</span></span> <span data-ttu-id="af51e-145">このような場合、メタデータの生成中にプロパティをバインドするための新しい値をデザイン時に使用されます。</span><span class="sxs-lookup"><span data-stu-id="af51e-145">In such case, the new values for binding properties will be used at design-time while generating the metadata.</span></span> <span data-ttu-id="af51e-146">ただし、実行時に送信ポートの構成でバインドのプロパティに指定された値を適用できるになります。</span><span class="sxs-lookup"><span data-stu-id="af51e-146">However, at run-time the values specified for binding properties in the send port configuration will be applicable.</span></span>  

8. <span data-ttu-id="af51e-147">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af51e-147">Click **OK**.</span></span>  

## <a name="enter-binding-properties-at-run-time"></a><span data-ttu-id="af51e-148">実行時のバインドのプロパティを入力します。</span><span class="sxs-lookup"><span data-stu-id="af51e-148">Enter Binding Properties at Run Time</span></span>  
 <span data-ttu-id="af51e-149">WCF カスタム ポートまたは WCF SAP 構成の一部としてのバインドのプロパティを指定する、実行時に、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="af51e-149">For run time, you can specify the binding properties as part of the WCF-Custom port or WCF-SAP configuration in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

### <a name="enter-binding-properties-for-the-wcf-custom-port"></a><span data-ttu-id="af51e-150">WCF カスタム ポートのバインドのプロパティを入力します。</span><span class="sxs-lookup"><span data-stu-id="af51e-150">Enter binding properties for the WCF-Custom port</span></span>  

1. <span data-ttu-id="af51e-151">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="af51e-151">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="af51e-152">コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、順に展開する、ポートを作成し、をクリックしアプリケーション**送信ポート**または**受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="af51e-152">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="af51e-153">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="af51e-153">In the right pane, you can choose to create a port or select an existing port.</span></span>  

3. <span data-ttu-id="af51e-154">**ポートのプロパティ** ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、順にクリックします**構成**します。</span><span class="sxs-lookup"><span data-stu-id="af51e-154">In the **Port Properties** dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="af51e-155">受信ポートの場所のプロパティ ダイアログ ボックスを表示する をクリックして、**受信場所**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**します。</span><span class="sxs-lookup"><span data-stu-id="af51e-155">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  

4. <span data-ttu-id="af51e-156">**Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブ。</span><span class="sxs-lookup"><span data-stu-id="af51e-156">In the **WCF-Custom Transport Properties** dialog box, click the **Binding** tab.</span></span>  

5. <span data-ttu-id="af51e-157">**バインドの種類**ドロップダウン リストで、 **sapBinding**します。</span><span class="sxs-lookup"><span data-stu-id="af51e-157">From the **Binding Type** drop-down list, select **sapBinding**.</span></span>  

6. <span data-ttu-id="af51e-158">**構成**ボックスに、さまざまなバインドのプロパティの値を指定してクリックして**OK**。</span><span class="sxs-lookup"><span data-stu-id="af51e-158">In the **Configuration** box, specify the values for the different binding properties, and then click **OK**.</span></span>  

### <a name="enter-binging-properties-for-the-wcf-sap-port"></a><span data-ttu-id="af51e-159">WCF SAP ポートのバインドのプロパティを入力します。</span><span class="sxs-lookup"><span data-stu-id="af51e-159">Enter binging properties for the WCF-SAP port</span></span>  

1. <span data-ttu-id="af51e-160">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="af51e-160">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="af51e-161">WCF-SAP アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="af51e-161">Add the WCF-SAP adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="af51e-162">手順については、[SAP アダプターを BizTalk Server 管理コンソールに追加](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af51e-162">For instructions, see [Add the SAP Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md).</span></span>  

3. <span data-ttu-id="af51e-163">コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、順に展開する、ポートを作成し、をクリックしアプリケーション**送信ポート**または**受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="af51e-163">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="af51e-164">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="af51e-164">In the right pane, you can choose to create a port or select an existing port.</span></span>  

4. <span data-ttu-id="af51e-165">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストでは、先ほど追加した WCF-SAP アダプターを選択し、順にクリックします**構成**します。</span><span class="sxs-lookup"><span data-stu-id="af51e-165">In the port properties dialog box, from the **Type** drop-down list, select the WCF-SAP adapter you added earlier, and then click **Configure**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="af51e-166">受信ポートの場所のプロパティ ダイアログ ボックスを表示する をクリックして、**受信場所**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**します。</span><span class="sxs-lookup"><span data-stu-id="af51e-166">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  

5. <span data-ttu-id="af51e-167">トランスポートのプロパティ ダイアログ ボックスでをクリックして、**バインド**タブし、バインドのプロパティの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="af51e-167">In the transport properties dialog box, click the **Binding** tab and specify values for binding properties.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="af51e-168">バインドのプロパティは、送信ポートまたは受信ポートを構成するかどうかに基づいて表示されます。</span><span class="sxs-lookup"><span data-stu-id="af51e-168">The binding properties are displayed based on whether you are configuring a send port or a receive port.</span></span> <span data-ttu-id="af51e-169">たとえば、バインディングのプロパティに関連する受信操作をご利用いただけません受信操作には、受信ポートの構成が必要とするために、送信ポートを構成するときに。</span><span class="sxs-lookup"><span data-stu-id="af51e-169">For example, binding properties related to inbound operations are not available while configuring a send port because inbound operations require a receive port configuration.</span></span>  

6. <span data-ttu-id="af51e-170">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af51e-170">Click **OK**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="af51e-171">参照</span><span class="sxs-lookup"><span data-stu-id="af51e-171">See Also</span></span>  
[<span data-ttu-id="af51e-172">SAP アプリケーションを作成するための構成要素</span><span class="sxs-lookup"><span data-stu-id="af51e-172">Building blocks to create SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)