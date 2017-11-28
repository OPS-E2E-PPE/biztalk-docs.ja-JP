---
title: "SAP アダプターのバインドのプロパティを構成する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- binding properties, specifying at design time
- binding properties, specifying at run time
ms.assetid: 259a5895-c19d-409c-b2fc-bfdf59d5d74b
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a16a95818ed4d63fd97b9fca1f9ea86ebd14de80
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-binding-properties-for-the-sap-adapter"></a><span data-ttu-id="7345d-102">SAP アダプターのバインドのプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="7345d-102">Configure the binding properties for the SAP adapter</span></span>
<span data-ttu-id="7345d-103">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]動作特性を制御できるようにするいくつかのバインドのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="7345d-103">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces several binding properties that enable you to control some of its behavioral characteristics.</span></span> <span data-ttu-id="7345d-104">このセクションで説明および Visual Studio (設計時) からのバインドのプロパティを設定する方法について、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール (実行時)。</span><span class="sxs-lookup"><span data-stu-id="7345d-104">This section provides information about setting the binding properties from Visual Studio (design time) and from the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console (run time).</span></span> <span data-ttu-id="7345d-105">デザイン時に、特定の操作のスキーマを生成するバインドのプロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7345d-105">At design time, you must specify the binding properties to generate schema for specific operations.</span></span> <span data-ttu-id="7345d-106">、実行時に、送信の一部としてのバインドのプロパティを指定か、SAP システムからメッセージを送受信するためのポートが表示される必要があります。</span><span class="sxs-lookup"><span data-stu-id="7345d-106">At run time, you must specify the binding properties as part of the send or receive port for sending or receiving messages from the SAP system.</span></span>  
  
 <span data-ttu-id="7345d-107">バインドのプロパティについては、バインドのプロパティの一覧を含む[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を参照してください[mySAP Business Suite のバインドのプロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="7345d-107">For information about the binding properties, including a list of binding properties for [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], see [Read about BizTalk Adapter for mySAP Business Suite binding properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
## <a name="enter-binding-properties-at-design-time"></a><span data-ttu-id="7345d-108">デザイン時のバインドのプロパティを入力してください。</span><span class="sxs-lookup"><span data-stu-id="7345d-108">Enter Binding Properties at Design Time</span></span>  
 <span data-ttu-id="7345d-109">デザイン時を使用してバインドのプロパティを指定できます、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="7345d-109">For design time, you can specify the binding properties using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  
  
### <a name="enter-binding-properties-using-consume-adapter-service-add-in"></a><span data-ttu-id="7345d-110">アダプター サービスのアドインを使用してバインドのプロパティを入力してください。</span><span class="sxs-lookup"><span data-stu-id="7345d-110">Enter binding properties using Consume Adapter Service Add-in</span></span>  
  
1.  <span data-ttu-id="7345d-111">BizTalk プロジェクトを右クリックし、順にポイント**追加**、クリックして**生成した項目の追加**です。</span><span class="sxs-lookup"><span data-stu-id="7345d-111">Right-click your BizTalk project, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="7345d-112">**生成した項目の追加** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="7345d-112">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="7345d-113">プロパティ</span><span class="sxs-lookup"><span data-stu-id="7345d-113">Use this</span></span>|<span data-ttu-id="7345d-114">目的</span><span class="sxs-lookup"><span data-stu-id="7345d-114">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="7345d-115">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="7345d-115">**Categories**</span></span>|<span data-ttu-id="7345d-116">をクリックして**アダプター サービスの使用**です。</span><span class="sxs-lookup"><span data-stu-id="7345d-116">Click **Consume Adapter Service**.</span></span>|  
    |<span data-ttu-id="7345d-117">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="7345d-117">**Templates**</span></span>|<span data-ttu-id="7345d-118">をクリックして**アダプター サービスの使用**です。</span><span class="sxs-lookup"><span data-stu-id="7345d-118">Click **Consume Adapter Service**.</span></span>|  
  
3.  <span data-ttu-id="7345d-119">開始する、**アダプター サービスの使用**ダイアログ ボックスで、をクリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="7345d-119">To start the **Consume Adapter Service** dialog box, click **Add**.</span></span>  
  
4.  <span data-ttu-id="7345d-120">**アダプター サービスの使用** ダイアログ ボックスから、**バインディングを選択**ドロップダウン リストを**sapBinding**、 をクリック**構成**.</span><span class="sxs-lookup"><span data-stu-id="7345d-120">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list select **sapBinding**, and click **Configure**.</span></span>  
  
5.  <span data-ttu-id="7345d-121">**アダプターの構成**ダイアログ ボックスで、をクリックして、**バインド プロパティ**タブをクリックし、別のバインディング プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="7345d-121">In the **Configure Adapter** dialog box, click the **Binding Properties** tab, and then specify the different binding properties.</span></span>  
  
6.  <span data-ttu-id="7345d-122">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7345d-122">Click **OK**.</span></span>  
  
### <a name="enter-binding-properties-using-add-adapter-metadata-wizard"></a><span data-ttu-id="7345d-123">アダプター メタデータの追加ウィザードを使用してバインドのプロパティを入力してください。</span><span class="sxs-lookup"><span data-stu-id="7345d-123">Enter binding properties using Add Adapter Metadata Wizard</span></span>  
  
1.  <span data-ttu-id="7345d-124">BizTalk プロジェクトを右クリックし、順にポイント**追加**、クリックして**生成した項目の追加**です。</span><span class="sxs-lookup"><span data-stu-id="7345d-124">Right-click your BizTalk project, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="7345d-125">**生成した項目の追加** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="7345d-125">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="7345d-126">プロパティ</span><span class="sxs-lookup"><span data-stu-id="7345d-126">Use this</span></span>|<span data-ttu-id="7345d-127">目的</span><span class="sxs-lookup"><span data-stu-id="7345d-127">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="7345d-128">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="7345d-128">**Categories**</span></span>|<span data-ttu-id="7345d-129">をクリックして**アダプターを追加**です。</span><span class="sxs-lookup"><span data-stu-id="7345d-129">Click **Add Adapter**.</span></span>|  
    |<span data-ttu-id="7345d-130">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="7345d-130">**Templates**</span></span>|<span data-ttu-id="7345d-131">をクリックして**アダプター メタデータの追加**です。</span><span class="sxs-lookup"><span data-stu-id="7345d-131">Click **Add Adapter Metadata**.</span></span>|  
  
3.  <span data-ttu-id="7345d-132">**[追加]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7345d-132">Click **Add**.</span></span> <span data-ttu-id="7345d-133">[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7345d-133">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  
  
4.  <span data-ttu-id="7345d-134">アダプターの追加ウィザードで選択**WCF SAP**です。</span><span class="sxs-lookup"><span data-stu-id="7345d-134">In the Add Adapter Wizard, select **WCF-SAP**.</span></span> <span data-ttu-id="7345d-135">BizTalk Server がインストールされているコンピューターを選択し、BizTalk データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="7345d-135">Select the computer on which BizTalk Server is installed and the name of the BizTalk database.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="7345d-136">BizTalk で構成されている WCF SAP ポートがある場合からポートを選択して、**ポート** ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="7345d-136">If you already have a WCF-SAP port configured in BizTalk, select the port from the **Port** list.</span></span>  
  
5.  <span data-ttu-id="7345d-137">**[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7345d-137">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="7345d-138">**アダプター サービスの使用** ダイアログ ボックスから、**バインディングを選択**ドロップダウン リストを**sapBinding**、 をクリック**構成**.</span><span class="sxs-lookup"><span data-stu-id="7345d-138">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list select **sapBinding**, and click **Configure**.</span></span>  
  
7.  <span data-ttu-id="7345d-139">クリックして、**バインド プロパティ** タブの値を指定します、バインディング、存在する場合は、スキーマを生成する前に指定する必要です。</span><span class="sxs-lookup"><span data-stu-id="7345d-139">Click the **Binding Properties** tab and specify the binding values, if any, which are required to be specified before generating the schema.</span></span> <span data-ttu-id="7345d-140">たとえばの値を指定する必要があります、 **GenerateFlatFileCompatibleIDoc** SAP システムから IDOC を受信するためのスキーマを生成する前にプロパティです。</span><span class="sxs-lookup"><span data-stu-id="7345d-140">For example, you must specify a value for the **GenerateFlatFileCompatibleIDoc** property before generating schema for receiving IDOC from an SAP system.</span></span> <span data-ttu-id="7345d-141">バインドのプロパティの詳細については、次を参照してください。 [mySAP Business Suite のバインドのプロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="7345d-141">For more information about binding properties, see [Read about BizTalk Adapter for mySAP Business Suite binding properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7345d-142">既存の SAP WCF 送信ポートを選択した場合、バインドのプロパティを指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7345d-142">If you selected an existing WCF-SAP send port, you need not specify the binding properties.</span></span> <span data-ttu-id="7345d-143">バインドのプロパティは、送信ポートの構成から取得されます。</span><span class="sxs-lookup"><span data-stu-id="7345d-143">The binding properties are picked from the send port configuration.</span></span> <span data-ttu-id="7345d-144">ただし、存在する場合、デザイン時に、必要なバインドのプロパティを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="7345d-144">However, you may choose to specify the binding properties that are required at design-time, if any.</span></span> <span data-ttu-id="7345d-145">このような場合、メタデータの生成中にバインドのプロパティの新しい値をデザイン時に使用されます。</span><span class="sxs-lookup"><span data-stu-id="7345d-145">In such case, the new values for binding properties will be used at design-time while generating the metadata.</span></span> <span data-ttu-id="7345d-146">ただし、実行時に、バインドの送信ポートの構成のプロパティの指定値適用されます。</span><span class="sxs-lookup"><span data-stu-id="7345d-146">However, at run-time the values specified for binding properties in the send port configuration will be applicable.</span></span>  
  
8.  <span data-ttu-id="7345d-147">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7345d-147">Click **OK**.</span></span>  
  
## <a name="enter-binding-properties-at-run-time"></a><span data-ttu-id="7345d-148">実行時のバインドのプロパティを入力してください。</span><span class="sxs-lookup"><span data-stu-id="7345d-148">Enter Binding Properties at Run Time</span></span>  
 <span data-ttu-id="7345d-149">実行時は、WCF カスタム ポートまたはで WCF SAP 構成の一部としてのバインドのプロパティを指定できます、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="7345d-149">For run time, you can specify the binding properties as part of the WCF-Custom port or WCF-SAP configuration in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
### <a name="enter-binding-properties-for-the-wcf-custom-port"></a><span data-ttu-id="7345d-150">WCF カスタム ポートのバインドのプロパティを入力します。</span><span class="sxs-lookup"><span data-stu-id="7345d-150">Enter binding properties for the WCF-Custom port</span></span>  
  
1.  <span data-ttu-id="7345d-151">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="7345d-151">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="7345d-152">コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、ポートを作成し、をクリックする、アプリケーションの順に展開および**送信ポート**または**受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="7345d-152">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="7345d-153">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="7345d-153">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
3.  <span data-ttu-id="7345d-154">**ポートのプロパティ** ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**をクリックし、**構成**です。</span><span class="sxs-lookup"><span data-stu-id="7345d-154">In the **Port Properties** dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7345d-155">受信ポートの場所のプロパティ ダイアログ ボックスを表示するをクリックして、**受信場所の**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**です。</span><span class="sxs-lookup"><span data-stu-id="7345d-155">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="7345d-156">**Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブです。</span><span class="sxs-lookup"><span data-stu-id="7345d-156">In the **WCF-Custom Transport Properties** dialog box, click the **Binding** tab.</span></span>  
  
5.  <span data-ttu-id="7345d-157">**バインディングの種類**ドロップダウン リストで、 **sapBinding**です。</span><span class="sxs-lookup"><span data-stu-id="7345d-157">From the **Binding Type** drop-down list, select **sapBinding**.</span></span>  
  
6.  <span data-ttu-id="7345d-158">**構成**ボックスで異なるバインディングのプロパティの値を指定し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="7345d-158">In the **Configuration** box, specify the values for the different binding properties, and then click **OK**.</span></span>  
  
### <a name="enter-binging-properties-for-the-wcf-sap-port"></a><span data-ttu-id="7345d-159">WCF SAP ポートのバインドのプロパティを入力します。</span><span class="sxs-lookup"><span data-stu-id="7345d-159">Enter binging properties for the WCF-SAP port</span></span>  
  
1.  <span data-ttu-id="7345d-160">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="7345d-160">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="7345d-161">WCF SAP アダプターを追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="7345d-161">Add the WCF-SAP adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="7345d-162">手順については、次を参照してください。 [SAP アダプターを BizTalk Server 管理コンソールに追加](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md)です。</span><span class="sxs-lookup"><span data-stu-id="7345d-162">For instructions, see [Add the SAP Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3.  <span data-ttu-id="7345d-163">コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、ポートを作成し、をクリックする、アプリケーションの順に展開および**送信ポート**または**受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="7345d-163">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="7345d-164">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="7345d-164">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
4.  <span data-ttu-id="7345d-165">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストは、前に追加する WCF SAP アダプターを選択し、をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="7345d-165">In the port properties dialog box, from the **Type** drop-down list, select the WCF-SAP adapter you added earlier, and then click **Configure**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7345d-166">受信ポートの場所のプロパティ ダイアログ ボックスを表示するをクリックして、**受信場所の**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**です。</span><span class="sxs-lookup"><span data-stu-id="7345d-166">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  
  
5.  <span data-ttu-id="7345d-167">トランスポートのプロパティ ダイアログ ボックスをクリックして、**バインディング**タブし、バインドのプロパティの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="7345d-167">In the transport properties dialog box, click the **Binding** tab and specify values for binding properties.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7345d-168">バインドのプロパティは、送信ポートまたは受信ポートを構成するかどうかに基づいてが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7345d-168">The binding properties are displayed based on whether you are configuring a send port or a receive port.</span></span> <span data-ttu-id="7345d-169">たとえば、バインディングのプロパティの受信に関連する操作利用できない受信操作には、受信ポートの構成が必要とするために、送信ポートを構成するときにします。</span><span class="sxs-lookup"><span data-stu-id="7345d-169">For example, binding properties related to inbound operations are not available while configuring a send port because inbound operations require a receive port configuration.</span></span>  
  
6.  <span data-ttu-id="7345d-170">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7345d-170">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7345d-171">参照</span><span class="sxs-lookup"><span data-stu-id="7345d-171">See Also</span></span>  
[<span data-ttu-id="7345d-172">SAP アプリケーションを作成する構成要素</span><span class="sxs-lookup"><span data-stu-id="7345d-172">Building blocks to create SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)