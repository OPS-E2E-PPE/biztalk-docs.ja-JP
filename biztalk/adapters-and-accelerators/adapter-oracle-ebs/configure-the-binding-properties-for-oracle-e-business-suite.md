---
title: "Oracle E-business Suite のバインド プロパティの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cfdca8c8-4434-4a9f-8e2a-970988c2f685
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ddb414ae80e7cff6717d232d1734ec8b98cd2006
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-binding-properties-for-oracle-e-business-suite"></a><span data-ttu-id="cd721-102">Oracle E-business Suite のバインド プロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="cd721-102">Configure the binding properties for Oracle E-Business Suite</span></span>
<span data-ttu-id="cd721-103">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]動作特性を制御できるようにするいくつかのバインドのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="cd721-103">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]surfaces several binding properties that enable you to control some of its behavioral characteristics.</span></span> <span data-ttu-id="cd721-104">このセクションで説明からのバインドのプロパティを設定する方法について[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]との間、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="cd721-104">This section provides information about setting the binding properties from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and from the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="cd721-105">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、特定の操作のスキーマを生成するときに、バインドのプロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd721-105">From [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], you must specify the binding properties while generating schema for specific operations.</span></span> <span data-ttu-id="cd721-106">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]送信の一部としてのバインドのプロパティを指定または Oracle E-business Suite からメッセージを送受信するためのポートを受信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd721-106">From [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you must specify the binding properties as part of the send or receive port for sending or receiving messages from Oracle E-Business Suite.</span></span>  
  
 <span data-ttu-id="cd721-107">バインドのプロパティについては、バインドのプロパティの一覧を含め、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[BizTalk Adapter for Oracle E-business Suite バインド プロパティについて](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="cd721-107">For information about the binding properties, including a list of binding properties for the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], see [Read about the BizTalk Adapter for Oracle E-Business Suite Binding Properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span>  
  
## <a name="specifying-binding-properties-from-visual-studio"></a><span data-ttu-id="cd721-108">Visual Studio からバインドのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="cd721-108">Specifying Binding Properties from Visual Studio</span></span>  
 <span data-ttu-id="cd721-109">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を使用してバインドのプロパティを指定する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="cd721-109">From [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], you must specify the binding properties using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  
  
#### <a name="to-specify-binding-properties-using-consume-adapter-service-add-in"></a><span data-ttu-id="cd721-110">アダプター サービスのアドインを使用してバインド プロパティを指定するには</span><span class="sxs-lookup"><span data-stu-id="cd721-110">To specify binding properties using Consume Adapter Service Add-in</span></span>  
  
1.  <span data-ttu-id="cd721-111">BizTalk プロジェクトを右クリックし **生成した項目の追加**です。</span><span class="sxs-lookup"><span data-stu-id="cd721-111">Right-click your BizTalk project, and then select **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="cd721-112">**生成した項目の追加** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="cd721-112">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="cd721-113">プロパティ</span><span class="sxs-lookup"><span data-stu-id="cd721-113">Use this</span></span>|<span data-ttu-id="cd721-114">目的</span><span class="sxs-lookup"><span data-stu-id="cd721-114">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="cd721-115">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="cd721-115">**Categories**</span></span>|<span data-ttu-id="cd721-116">をクリックして**アダプター サービスの使用**です。</span><span class="sxs-lookup"><span data-stu-id="cd721-116">Click **Consume Adapter Service**.</span></span>|  
    |<span data-ttu-id="cd721-117">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="cd721-117">**Templates**</span></span>|<span data-ttu-id="cd721-118">をクリックして**アダプター サービスの使用**です。</span><span class="sxs-lookup"><span data-stu-id="cd721-118">Click **Consume Adapter Service**.</span></span>|  
  
3.  <span data-ttu-id="cd721-119">開始する、**アダプター サービスの使用**ダイアログ ボックスで、をクリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="cd721-119">To start the **Consume Adapter Service** dialog box, click **Add**.</span></span>  
  
4.  <span data-ttu-id="cd721-120">**アダプター サービスの使用** ダイアログ ボックスから、**バインディングを選択**ドロップダウン リスト、選択**oracleEBSBinding**、順にクリック**を構成します。**.</span><span class="sxs-lookup"><span data-stu-id="cd721-120">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list, select **oracleEBSBinding**, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="cd721-121">**アダプターの構成**ダイアログ ボックスで、をクリックして、**バインド プロパティ**タブをクリックし、別のバインディング プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="cd721-121">In the **Configure Adapter** dialog box, click the **Binding Properties** tab, and then specify the different binding properties.</span></span>  
  
6.  <span data-ttu-id="cd721-122">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cd721-122">Click **OK**.</span></span>  
  
#### <a name="to-specify-binding-properties-using-add-adapter-metadata-wizard"></a><span data-ttu-id="cd721-123">アダプター メタデータの追加ウィザードを使用してバインド プロパティを指定するには</span><span class="sxs-lookup"><span data-stu-id="cd721-123">To specify binding properties using Add Adapter Metadata Wizard</span></span>  
  
1.  <span data-ttu-id="cd721-124">BizTalk プロジェクトを右クリックし、順にポイント**追加**、クリックして**生成した項目の追加**です。</span><span class="sxs-lookup"><span data-stu-id="cd721-124">Right-click your BizTalk project, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="cd721-125">**生成した項目の追加** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="cd721-125">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="cd721-126">プロパティ</span><span class="sxs-lookup"><span data-stu-id="cd721-126">Use this</span></span>|<span data-ttu-id="cd721-127">目的</span><span class="sxs-lookup"><span data-stu-id="cd721-127">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="cd721-128">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="cd721-128">**Categories**</span></span>|<span data-ttu-id="cd721-129">をクリックして**アダプターを追加**です。</span><span class="sxs-lookup"><span data-stu-id="cd721-129">Click **Add Adapter**.</span></span>|  
    |<span data-ttu-id="cd721-130">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="cd721-130">**Templates**</span></span>|<span data-ttu-id="cd721-131">をクリックして**アダプター メタデータの追加**です。</span><span class="sxs-lookup"><span data-stu-id="cd721-131">Click **Add Adapter Metadata**.</span></span>|  
  
3.  <span data-ttu-id="cd721-132">**[追加]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cd721-132">Click **Add**.</span></span> <span data-ttu-id="cd721-133">[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cd721-133">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  
  
4.  <span data-ttu-id="cd721-134">[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] **Wcf-oracleebs**です。</span><span class="sxs-lookup"><span data-stu-id="cd721-134">In the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], select **WCF-OracleEBS**.</span></span> <span data-ttu-id="cd721-135">BizTalk Server がインストールされているコンピューターを選択し、BizTalk データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="cd721-135">Select the computer on which BizTalk Server is installed and the name of the BizTalk database.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="cd721-136">BizTalk で構成された Wcf-oracleebs ポートがある場合は、ポートの一覧から、ポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="cd721-136">If you already have a WCF-OracleEBS port configured in BizTalk, select the port from the Port list.</span></span>  
  
5.  <span data-ttu-id="cd721-137">**[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cd721-137">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="cd721-138">**アダプター サービスの使用** ダイアログ ボックスから、**バインディングを選択**一覧で、選択**oracleEBSBinding**、クリックして**構成**.</span><span class="sxs-lookup"><span data-stu-id="cd721-138">In the **Consume Adapter Service** dialog box, from the **Select a binding** list, select **oracleEBSBinding**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="cd721-139">をクリックして、**バインド プロパティ**タブをクリックし、バインディングの値を指定、存在する場合、スキーマを生成する前に必要とします。</span><span class="sxs-lookup"><span data-stu-id="cd721-139">Click the **Binding Properties** tab, and specify the binding values, if any, which are required before generating the schema.</span></span> <span data-ttu-id="cd721-140">バインドのプロパティの詳細については、次を参照してください。 [BizTalk Adapter for Oracle E-business Suite バインド プロパティ読む](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="cd721-140">For more information about binding properties, see [Read about the BizTalk Adapter for Oracle E-Business Suite Binding Properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cd721-141">既存の選択した場合は、Wcf-oracleebs 送信ポートをバインドのプロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd721-141">If you selected an existing WCF-OracleEBS send port, you need not specify the binding properties.</span></span> <span data-ttu-id="cd721-142">バインドのプロパティは、送信ポートの構成から取得されます。</span><span class="sxs-lookup"><span data-stu-id="cd721-142">The binding properties are picked from the send port configuration.</span></span> <span data-ttu-id="cd721-143">ただし、存在する場合、デザイン時に、必要なバインドのプロパティを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="cd721-143">However, you may choose to specify the binding properties that are required at design-time, if any.</span></span> <span data-ttu-id="cd721-144">このような場合は、バインドのプロパティの新しい値は、メタデータの生成中のデザイン時に使用されます。</span><span class="sxs-lookup"><span data-stu-id="cd721-144">In such a case, the new values for binding properties will be used at design-time while generating the metadata.</span></span> <span data-ttu-id="cd721-145">ただし、実行時に、バインドの送信ポートの構成のプロパティの指定値適用されます。</span><span class="sxs-lookup"><span data-stu-id="cd721-145">However, at run-time the values specified for binding properties in the send port configuration will be applicable.</span></span>  
  
8.  <span data-ttu-id="cd721-146">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cd721-146">Click **OK**.</span></span>  
  
## <a name="specifying-binding-properties-from-the-biztalk-server-administration-console"></a><span data-ttu-id="cd721-147">BizTalk Server 管理コンソールからバインドのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="cd721-147">Specifying Binding Properties from the BizTalk Server Administration Console</span></span>  
 <span data-ttu-id="cd721-148">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、Wcf-custom または Wcf-oracleebs ポートの構成の一部としてのバインドのプロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd721-148">From the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you must specify the binding properties as part of the WCF-Custom or WCF-OracleEBS port configuration.</span></span>  
  
#### <a name="to-specify-binding-properties-for-the-wcf-custom-port"></a><span data-ttu-id="cd721-149">WCF カスタム ポートのバインド プロパティを指定するには</span><span class="sxs-lookup"><span data-stu-id="cd721-149">To specify binding properties for the WCF-Custom port</span></span>  
  
1.  <span data-ttu-id="cd721-150">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="cd721-150">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="cd721-151">コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、ポートを作成し、をクリックする、アプリケーションの順に展開および**送信ポート**または**受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="cd721-151">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="cd721-152">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="cd721-152">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
3.  <span data-ttu-id="cd721-153">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="cd721-153">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cd721-154">受信ポートの場所のプロパティ ダイアログ ボックスを表示するをクリックして、**受信場所の**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**です。</span><span class="sxs-lookup"><span data-stu-id="cd721-154">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="cd721-155">**Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブです。</span><span class="sxs-lookup"><span data-stu-id="cd721-155">In the **WCF-Custom Transport Properties** dialog box, click the **Binding** tab.</span></span>  
  
5.  <span data-ttu-id="cd721-156">**バインディングの種類**一覧で、 **oracleEBSBinding**です。</span><span class="sxs-lookup"><span data-stu-id="cd721-156">From the **Binding Type** list, select **oracleEBSBinding**.</span></span>  
  
6.  <span data-ttu-id="cd721-157">**構成**ボックスで異なるバインディングのプロパティの値を指定し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="cd721-157">In the **Configuration** box, specify the values for the different binding properties, and then click **OK**.</span></span>  
  
#### <a name="to-specify-binding-properties-for-the-wcf-oracleebs-port"></a><span data-ttu-id="cd721-158">Wcf-oracleebs ポートのバインド プロパティを指定するには</span><span class="sxs-lookup"><span data-stu-id="cd721-158">To specify binding properties for the WCF-OracleEBS port</span></span>  
  
1.  <span data-ttu-id="cd721-159">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="cd721-159">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="cd721-160">Wcf-oracleebs アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="cd721-160">Add the WCF-OracleEBS adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="cd721-161">手順については、次を参照してください。 [、Oracle E-business Suite アダプターを BizTalk Server 管理コンソールに追加する](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md)です。</span><span class="sxs-lookup"><span data-stu-id="cd721-161">For instructions, see [Adding the Oracle E-Business Suite Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3.  <span data-ttu-id="cd721-162">コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、ポートを作成し、をクリックする、アプリケーションの順に展開および**送信ポート**または**受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="cd721-162">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="cd721-163">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="cd721-163">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
4.  <span data-ttu-id="cd721-164">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストは、前に追加する Wcf-oracleebs アダプターを選択し、をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="cd721-164">In the port properties dialog box, from the **Type** drop-down list, select the WCF-OracleEBS adapter you added earlier, and then click **Configure**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cd721-165">受信ポートの場所のプロパティ ダイアログ ボックスを表示するをクリックして、**受信場所の**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**です。</span><span class="sxs-lookup"><span data-stu-id="cd721-165">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  
  
5.  <span data-ttu-id="cd721-166">トランスポートのプロパティ ダイアログ ボックスをクリックして、**バインディング**タブし、バインドのプロパティの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="cd721-166">In the transport properties dialog box, click the **Binding** tab and specify values for binding properties.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cd721-167">バインドのプロパティは、送信ポートまたは受信ポートを構成するかどうかに基づいてが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cd721-167">The binding properties are displayed based on whether you are configuring a send port or a receive port.</span></span> <span data-ttu-id="cd721-168">たとえば、通知に関連するバインド プロパティ利用できない通知が受信操作には、受信ポートの構成を必要とするために、送信ポートを構成するときにします。</span><span class="sxs-lookup"><span data-stu-id="cd721-168">For example, binding properties related to notifications are not available while configuring a send port because notifications are inbound operations and require a receive port configuration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd721-169">参照</span><span class="sxs-lookup"><span data-stu-id="cd721-169">See Also</span></span>  
 [<span data-ttu-id="cd721-170">Oracle E-business Suite アプリケーションを作成する構成要素</span><span class="sxs-lookup"><span data-stu-id="cd721-170">Building blocks to create Oracle E-Business Suite applications</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)