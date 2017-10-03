---
title: "Oracle データベースのバインド プロパティの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- binding properties, specifying at run time
- binding properties, specifying at design time
ms.assetid: c59a1b5c-b52b-4161-82de-c4d89bfce5c7
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 73b7a5205b2fbfe0bc42bf5af0930356a003d5be
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-binding-properties-for-oracle-database"></a><span data-ttu-id="c34f1-102">Oracle データベースのバインドのプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="c34f1-102">Configure the binding properties for Oracle Database</span></span>
<span data-ttu-id="c34f1-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]動作特性を制御できるようにするいくつかのバインドのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="c34f1-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] surfaces several binding properties that enable you to control some of its behavioral characteristics.</span></span> <span data-ttu-id="c34f1-104">このセクションでは、Visual Studio および BizTalk Server 管理コンソールからバインドのプロパティの設定に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c34f1-104">This section provides information about setting the binding properties from Visual Studio and from the BizTalk Server Administration console.</span></span> <span data-ttu-id="c34f1-105">Visual Studio から、特定の操作のスキーマの生成中にバインドのプロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c34f1-105">From Visual Studio, you must specify the binding properties while generating schema for specific operations.</span></span> <span data-ttu-id="c34f1-106">BizTalk Server からには、送信の一部としてのバインドのプロパティを指定または Oracle データベースからメッセージを送受信するためのポートを受信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c34f1-106">From BizTalk Server, you must specify the binding properties as part of the send or receive port for sending or receiving messages from the Oracle database.</span></span>  
  
 <span data-ttu-id="c34f1-107">バインドのプロパティについては、バインドのプロパティの一覧を含む[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[Oracle データベース アダプターのバインドのプロパティについてお読み](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="c34f1-107">For information about the binding properties, including a list of binding properties for [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span>  
  
## <a name="specifying-binding-properties-from-visual-studio"></a><span data-ttu-id="c34f1-108">Visual Studio からバインドのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="c34f1-108">Specifying Binding Properties from Visual Studio</span></span>  
 <span data-ttu-id="c34f1-109">Visual studio を使用して資格情報を指定する必要があります、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="c34f1-109">From Visual Studio, you must specify the credentials using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  
  
#### <a name="to-specify-binding-properties-using-consume-adapter-service-add-in"></a><span data-ttu-id="c34f1-110">アダプター サービスのアドインを使用してバインド プロパティを指定するには</span><span class="sxs-lookup"><span data-stu-id="c34f1-110">To specify binding properties using Consume Adapter Service Add-in</span></span>  
  
1.  <span data-ttu-id="c34f1-111">BizTalk プロジェクトを右クリックし **生成した項目の追加**です。</span><span class="sxs-lookup"><span data-stu-id="c34f1-111">Right-click your BizTalk project and then select **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="c34f1-112">**生成した項目の追加** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="c34f1-112">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="c34f1-113">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c34f1-113">Use this</span></span>|<span data-ttu-id="c34f1-114">目的</span><span class="sxs-lookup"><span data-stu-id="c34f1-114">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="c34f1-115">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="c34f1-115">**Categories**</span></span>|<span data-ttu-id="c34f1-116">をクリックして**アダプター サービスの使用**です。</span><span class="sxs-lookup"><span data-stu-id="c34f1-116">Click **Consume Adapter Service**.</span></span>|  
    |<span data-ttu-id="c34f1-117">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="c34f1-117">**Templates**</span></span>|<span data-ttu-id="c34f1-118">をクリックして**アダプター サービスの使用**です。</span><span class="sxs-lookup"><span data-stu-id="c34f1-118">Click **Consume Adapter Service**.</span></span>|  
  
3.  <span data-ttu-id="c34f1-119">開始する、**アダプター サービスの使用**ダイアログ ボックスで、をクリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="c34f1-119">To start the **Consume Adapter Service** dialog box, click **Add**.</span></span>  
  
4.  <span data-ttu-id="c34f1-120">**アダプター サービスの使用** ダイアログ ボックスから、**バインディングを選択**ドロップダウン リストを**oracleDBBinding**、 をクリック**構成**.</span><span class="sxs-lookup"><span data-stu-id="c34f1-120">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list select **oracleDBBinding**, and click **Configure**.</span></span>  
  
5.  <span data-ttu-id="c34f1-121">**アダプターの構成**ダイアログ ボックスで、をクリックして、**バインド プロパティ**タブし、さまざまなバインドのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="c34f1-121">In the **Configure Adapter** dialog box, click the **Binding Properties** tab and specify the different binding properties.</span></span>  
  
6.  <span data-ttu-id="c34f1-122">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c34f1-122">Click **OK**.</span></span>  
  
#### <a name="to-specify-binding-properties-using-add-adapter-metadata-wizard"></a><span data-ttu-id="c34f1-123">アダプター メタデータの追加ウィザードを使用してバインド プロパティを指定するには</span><span class="sxs-lookup"><span data-stu-id="c34f1-123">To specify binding properties using Add Adapter Metadata Wizard</span></span>  
  
1.  <span data-ttu-id="c34f1-124">BizTalk プロジェクトを右クリックし **生成した項目の追加**です。</span><span class="sxs-lookup"><span data-stu-id="c34f1-124">Right-click your BizTalk project and then select **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="c34f1-125">**生成した項目の追加** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="c34f1-125">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="c34f1-126">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c34f1-126">Use this</span></span>|<span data-ttu-id="c34f1-127">目的</span><span class="sxs-lookup"><span data-stu-id="c34f1-127">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="c34f1-128">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="c34f1-128">**Categories**</span></span>|<span data-ttu-id="c34f1-129">をクリックして**アダプターを追加**です。</span><span class="sxs-lookup"><span data-stu-id="c34f1-129">Click **Add Adapter**.</span></span>|  
    |<span data-ttu-id="c34f1-130">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="c34f1-130">**Templates**</span></span>|<span data-ttu-id="c34f1-131">をクリックして**アダプター メタデータの追加**です。</span><span class="sxs-lookup"><span data-stu-id="c34f1-131">Click **Add Adapter Metadata**.</span></span>|  
  
3.  <span data-ttu-id="c34f1-132">**[追加]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c34f1-132">Click **Add**.</span></span> <span data-ttu-id="c34f1-133">アダプター メタデータの追加ウィザードが開きます。</span><span class="sxs-lookup"><span data-stu-id="c34f1-133">The Add Adapter Metadata Wizard opens.</span></span>  
  
4.  <span data-ttu-id="c34f1-134">アダプター メタデータの追加ウィザードで選択**Wcf-oracledb**です。</span><span class="sxs-lookup"><span data-stu-id="c34f1-134">In the Add Adapter Metadata Wizard, select **WCF-OracleDB**.</span></span> <span data-ttu-id="c34f1-135">コンピューターを選択して[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]がインストールされていると、BizTalk データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="c34f1-135">Select the computer on which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] is installed and the name of the BizTalk database.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="c34f1-136">BizTalk で構成された Wcf-oracledb ポートがある場合からポートを選択して、**ポート** ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="c34f1-136">If you already have a WCF-OracleDB port configured in BizTalk, select the port from the **Port** list.</span></span>  
  
5.  <span data-ttu-id="c34f1-137">**[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c34f1-137">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="c34f1-138">**アダプター サービスの使用** ダイアログ ボックスから、**バインディングを選択**ドロップダウン リストを**oracleDBBinding**、 をクリック**構成**.</span><span class="sxs-lookup"><span data-stu-id="c34f1-138">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list select **oracleDBBinding**, and click **Configure**.</span></span>  
  
7.  <span data-ttu-id="c34f1-139">**アダプターの構成**ダイアログ ボックスで、をクリックして、**バインドのプロパティ**タブをクリックし、バインディングの値を指定、存在する場合、スキーマを生成する前に必要とします。</span><span class="sxs-lookup"><span data-stu-id="c34f1-139">In the **Configure Adapter** dialog box, click the **Binding Properties** tab, and specify the binding values, if any, which are required before generating the schema.</span></span> <span data-ttu-id="c34f1-140">バインドのプロパティの詳細については、次を参照してください。 [Oracle データベース アダプターのバインドのプロパティについてお読み](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="c34f1-140">For more information about binding properties, see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c34f1-141">既存の Wcf-oracledb 送信ポートを選択した場合、バインドのプロパティを指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c34f1-141">If you selected an existing WCF-OracleDB send port, you need not specify the binding properties.</span></span> <span data-ttu-id="c34f1-142">バインドのプロパティは、送信ポートの構成から取得されます。</span><span class="sxs-lookup"><span data-stu-id="c34f1-142">The binding properties are picked from the send port configuration.</span></span> <span data-ttu-id="c34f1-143">ただし、存在する場合、デザイン時に、必要なバインドのプロパティを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="c34f1-143">However, you may choose to specify the binding properties that are required at design-time, if any.</span></span> <span data-ttu-id="c34f1-144">このような場合は、バインドのプロパティの新しい値は、メタデータの生成中のデザイン時に使用されます。</span><span class="sxs-lookup"><span data-stu-id="c34f1-144">In such a case, the new values for binding properties will be used at design-time while generating the metadata.</span></span> <span data-ttu-id="c34f1-145">ただし、実行時に、バインドの送信ポートの構成のプロパティの指定値適用されます。</span><span class="sxs-lookup"><span data-stu-id="c34f1-145">However, at run-time the values specified for binding properties in the send port configuration will be applicable.</span></span>  
  
8.  <span data-ttu-id="c34f1-146">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c34f1-146">Click **OK**.</span></span>  
  
## <a name="specifying-binding-properties-from-the-biztalk-server-administration-console"></a><span data-ttu-id="c34f1-147">BizTalk Server 管理コンソールからバインドのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="c34f1-147">Specifying Binding Properties from the BizTalk Server Administration Console</span></span>  
 <span data-ttu-id="c34f1-148">BizTalk Server 管理コンソールから Wcf-custom または Wcf-oracledb ポートの構成の一部としてのバインドのプロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c34f1-148">From the BizTalk Server Administration console, you must specify the binding properties as part of the WCF-Custom or WCF-OracleDB port configuration.</span></span>  
  
#### <a name="to-specify-binding-properties-for-the-wcf-custom-port"></a><span data-ttu-id="c34f1-149">WCF カスタム ポートのバインド プロパティを指定するには</span><span class="sxs-lookup"><span data-stu-id="c34f1-149">To specify binding properties for the WCF-Custom port</span></span>  
  
1.  <span data-ttu-id="c34f1-150">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="c34f1-150">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="c34f1-151">コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、ポートを作成し、をクリックする、アプリケーションの順に展開および**送信ポート**または**受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="c34f1-151">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="c34f1-152">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="c34f1-152">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
3.  <span data-ttu-id="c34f1-153">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="c34f1-153">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c34f1-154">受信ポートの場所のプロパティ ダイアログ ボックスを表示するをクリックして、**受信場所の**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**です。</span><span class="sxs-lookup"><span data-stu-id="c34f1-154">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="c34f1-155">**Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブです。</span><span class="sxs-lookup"><span data-stu-id="c34f1-155">In the **WCF-Custom Transport Properties** dialog box, click the **Binding** tab.</span></span>  
  
5.  <span data-ttu-id="c34f1-156">**バインディングの種類**ドロップダウン リストで、 **oracleDBBinding**です。</span><span class="sxs-lookup"><span data-stu-id="c34f1-156">From the **Binding Type** drop-down list, select **oracleDBBinding**.</span></span>  
  
6.  <span data-ttu-id="c34f1-157">**構成**ボックスで異なるバインディングのプロパティの値を指定し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="c34f1-157">In the **Configuration** box, specify the values for the different binding properties and click **OK**.</span></span>  
  
#### <a name="to-specify-binding-properties-for-the-wcf-oracledb-port"></a><span data-ttu-id="c34f1-158">Wcf-oracledb ポートのバインド プロパティを指定するには</span><span class="sxs-lookup"><span data-stu-id="c34f1-158">To specify binding properties for the WCF-OracleDB port</span></span>  
  
1.  <span data-ttu-id="c34f1-159">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="c34f1-159">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="c34f1-160">Wcf-oracledb アダプターを BizTalk Server 管理コンソールに追加します。</span><span class="sxs-lookup"><span data-stu-id="c34f1-160">Add the WCF-OracleDB adapter to the BizTalk Server Administration console.</span></span> <span data-ttu-id="c34f1-161">手順については、次を参照してください。 [BizTalk Server 管理コンソールへの Oracle データベース アダプターの追加](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md)です。</span><span class="sxs-lookup"><span data-stu-id="c34f1-161">For instructions, see [Adding the Oracle Database Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3.  <span data-ttu-id="c34f1-162">コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、ポートを作成し、をクリックする、アプリケーションの順に展開および**送信ポート**または**受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="c34f1-162">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="c34f1-163">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="c34f1-163">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
4.  <span data-ttu-id="c34f1-164">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストは、前に追加する Wcf-oracledb アダプターを選択し、をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="c34f1-164">In the port properties dialog box, from the **Type** drop-down list, select the WCF-OracleDB adapter you added earlier, and then click **Configure**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c34f1-165">受信ポートの場所のプロパティ ダイアログ ボックスを表示するをクリックして、**受信場所の**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**です。</span><span class="sxs-lookup"><span data-stu-id="c34f1-165">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  
  
5.  <span data-ttu-id="c34f1-166">トランスポートのプロパティ ダイアログ ボックスをクリックして、**バインディング**タブをクリックし、バインドのプロパティの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="c34f1-166">In the transport properties dialog box, click the **Binding** tab, and specify values for binding properties.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c34f1-167">バインドのプロパティは、送信ポートまたは受信ポートを構成するかどうかに基づいてが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c34f1-167">The binding properties are displayed based on whether you are configuring a send port or a receive port.</span></span> <span data-ttu-id="c34f1-168">たとえば、通知に関連するバインド プロパティ利用できない通知が受信操作には、受信ポートの構成を必要とするために、送信ポートを構成するときにします。</span><span class="sxs-lookup"><span data-stu-id="c34f1-168">For example, binding properties related to notifications are not available while configuring a send port because notifications are inbound operations and require a receive port configuration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c34f1-169">参照</span><span class="sxs-lookup"><span data-stu-id="c34f1-169">See Also</span></span>  
[<span data-ttu-id="c34f1-170">Oracle データベースと BizTalk アプリケーションを開発する構成要素</span><span class="sxs-lookup"><span data-stu-id="c34f1-170">Building Blocks to develop BizTalk Applications with Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)