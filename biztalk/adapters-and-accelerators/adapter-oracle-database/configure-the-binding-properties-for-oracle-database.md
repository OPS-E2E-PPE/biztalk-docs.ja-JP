---
title: Oracle データベースのバインド プロパティの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- binding properties, specifying at run time
- binding properties, specifying at design time
ms.assetid: c59a1b5c-b52b-4161-82de-c4d89bfce5c7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96922feab7c343893bfaa04ccbccd7c7e2f6a743
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981083"
---
# <a name="configure-the-binding-properties-for-oracle-database"></a><span data-ttu-id="0e7dd-102">Oracle データベースのバインド プロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-102">Configure the binding properties for Oracle Database</span></span>
<span data-ttu-id="0e7dd-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]動作特性を制御するためのいくつかのバインドのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] surfaces several binding properties that enable you to control some of its behavioral characteristics.</span></span> <span data-ttu-id="0e7dd-104">このセクションでは、Visual Studio と BizTalk Server 管理コンソールから、バインドのプロパティを設定する方法についての情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-104">This section provides information about setting the binding properties from Visual Studio and from the BizTalk Server Administration console.</span></span> <span data-ttu-id="0e7dd-105">Visual studio で、特定の操作のスキーマの生成中にバインディング プロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-105">From Visual Studio, you must specify the binding properties while generating schema for specific operations.</span></span> <span data-ttu-id="0e7dd-106">BizTalk Server からには、送信の一部としてのバインドのプロパティを指定または Oracle データベースからのメッセージの送受信用のポートを受信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-106">From BizTalk Server, you must specify the binding properties as part of the send or receive port for sending or receiving messages from the Oracle database.</span></span>  

 <span data-ttu-id="0e7dd-107">バインドのプロパティについては、バインドのプロパティの一覧を含む[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[Oracle データベース アダプターのバインドのプロパティについて](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-107">For information about the binding properties, including a list of binding properties for [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span>  

## <a name="specifying-binding-properties-from-visual-studio"></a><span data-ttu-id="0e7dd-108">Visual Studio からバインドのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-108">Specifying Binding Properties from Visual Studio</span></span>  
 <span data-ttu-id="0e7dd-109">Visual studio を使用して資格情報を指定する必要があります、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-109">From Visual Studio, you must specify the credentials using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  

#### <a name="to-specify-binding-properties-using-consume-adapter-service-add-in"></a><span data-ttu-id="0e7dd-110">Consume Adapter Service アドインを使用してバインドのプロパティを指定するには</span><span class="sxs-lookup"><span data-stu-id="0e7dd-110">To specify binding properties using Consume Adapter Service Add-in</span></span>  

1.  <span data-ttu-id="0e7dd-111">BizTalk プロジェクトを右クリックし、**生成した項目の追加**します。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-111">Right-click your BizTalk project and then select **Add Generated Items**.</span></span>  

2.  <span data-ttu-id="0e7dd-112">**生成した項目の追加** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-112">In the **Add Generated Items** dialog box, do the following:</span></span>  

    |<span data-ttu-id="0e7dd-113">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0e7dd-113">Use this</span></span>|<span data-ttu-id="0e7dd-114">目的</span><span class="sxs-lookup"><span data-stu-id="0e7dd-114">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="0e7dd-115">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="0e7dd-115">**Categories**</span></span>|<span data-ttu-id="0e7dd-116">クリックして**アダプター サービスの使用**します。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-116">Click **Consume Adapter Service**.</span></span>|  
    |<span data-ttu-id="0e7dd-117">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="0e7dd-117">**Templates**</span></span>|<span data-ttu-id="0e7dd-118">クリックして**アダプター サービスの使用**します。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-118">Click **Consume Adapter Service**.</span></span>|  

3.  <span data-ttu-id="0e7dd-119">開始する、 **Consume Adapter Service**ダイアログ ボックスで、をクリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-119">To start the **Consume Adapter Service** dialog box, click **Add**.</span></span>  

4.  <span data-ttu-id="0e7dd-120">**Consume Adapter Service**  ダイアログ ボックスから、**バインディングを選択**ドロップダウン リストを**oracleDBBinding**、 をクリック**構成**.</span><span class="sxs-lookup"><span data-stu-id="0e7dd-120">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list select **oracleDBBinding**, and click **Configure**.</span></span>  

5.  <span data-ttu-id="0e7dd-121">**アダプターの構成**ダイアログ ボックスで、をクリックして、**バインドのプロパティ**タブし、さまざまなバインドのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-121">In the **Configure Adapter** dialog box, click the **Binding Properties** tab and specify the different binding properties.</span></span>  

6.  <span data-ttu-id="0e7dd-122">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-122">Click **OK**.</span></span>  

#### <a name="to-specify-binding-properties-using-add-adapter-metadata-wizard"></a><span data-ttu-id="0e7dd-123">アダプター メタデータの追加ウィザードを使用してバインドのプロパティを指定するには</span><span class="sxs-lookup"><span data-stu-id="0e7dd-123">To specify binding properties using Add Adapter Metadata Wizard</span></span>  

1. <span data-ttu-id="0e7dd-124">BizTalk プロジェクトを右クリックし、**生成した項目の追加**します。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-124">Right-click your BizTalk project and then select **Add Generated Items**.</span></span>  

2. <span data-ttu-id="0e7dd-125">**生成した項目の追加** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-125">In the **Add Generated Items** dialog box, do the following:</span></span>  


   |    <span data-ttu-id="0e7dd-126">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0e7dd-126">Use this</span></span>    |           <span data-ttu-id="0e7dd-127">目的</span><span class="sxs-lookup"><span data-stu-id="0e7dd-127">To do this</span></span>            |
   |----------------|---------------------------------|
   | <span data-ttu-id="0e7dd-128">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="0e7dd-128">**Categories**</span></span> |     <span data-ttu-id="0e7dd-129">クリックして**アダプターを追加**します。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-129">Click **Add Adapter**.</span></span>      |
   | <span data-ttu-id="0e7dd-130">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="0e7dd-130">**Templates**</span></span>  | <span data-ttu-id="0e7dd-131">クリックして**アダプター メタデータの追加**します。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-131">Click **Add Adapter Metadata**.</span></span> |


3. <span data-ttu-id="0e7dd-132">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-132">Click **Add**.</span></span> <span data-ttu-id="0e7dd-133">アダプター メタデータの追加ウィザードが開きます。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-133">The Add Adapter Metadata Wizard opens.</span></span>  

4. <span data-ttu-id="0e7dd-134">アダプター メタデータの追加ウィザードで選択**Wcf-oracledb**します。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-134">In the Add Adapter Metadata Wizard, select **WCF-OracleDB**.</span></span> <span data-ttu-id="0e7dd-135">コンピューターを選択します。[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]がインストールされていると、BizTalk データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-135">Select the computer on which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] is installed and the name of the BizTalk database.</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="0e7dd-136">BizTalk で構成された Wcf-oracledb ポート既にある場合からポートを選択して、**ポート**一覧。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-136">If you already have a WCF-OracleDB port configured in BizTalk, select the port from the **Port** list.</span></span>  

5. <span data-ttu-id="0e7dd-137">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-137">Click **Next**.</span></span>  

6. <span data-ttu-id="0e7dd-138">**Consume Adapter Service**  ダイアログ ボックスから、**バインディングを選択**ドロップダウン リストを**oracleDBBinding**、 をクリック**構成**.</span><span class="sxs-lookup"><span data-stu-id="0e7dd-138">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list select **oracleDBBinding**, and click **Configure**.</span></span>  

7. <span data-ttu-id="0e7dd-139">**アダプターの構成**ダイアログ ボックスで、をクリックして、**バインド プロパティ**タブをクリックし、バインドの値を指定、存在する場合、スキーマを生成する前に必要な。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-139">In the **Configure Adapter** dialog box, click the **Binding Properties** tab, and specify the binding values, if any, which are required before generating the schema.</span></span> <span data-ttu-id="0e7dd-140">バインド プロパティの詳細については、次を参照してください。 [Oracle データベース アダプターのバインドのプロパティについて](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-140">For more information about binding properties, see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="0e7dd-141">既存の Wcf-oracledb 送信ポートを選択した場合は、バインドのプロパティを指定する必要がありますできません。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-141">If you selected an existing WCF-OracleDB send port, you need not specify the binding properties.</span></span> <span data-ttu-id="0e7dd-142">バインドのプロパティは、送信ポートの構成から取得されます。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-142">The binding properties are picked from the send port configuration.</span></span> <span data-ttu-id="0e7dd-143">ただし、存在する場合に、デザイン時に必要なバインドのプロパティを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-143">However, you may choose to specify the binding properties that are required at design-time, if any.</span></span> <span data-ttu-id="0e7dd-144">このような場合は、メタデータの生成中にプロパティをバインドするための新しい値をデザイン時に使用されます。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-144">In such a case, the new values for binding properties will be used at design-time while generating the metadata.</span></span> <span data-ttu-id="0e7dd-145">ただし、実行時に送信ポートの構成でバインドのプロパティに指定された値を適用できるになります。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-145">However, at run-time the values specified for binding properties in the send port configuration will be applicable.</span></span>  

8. <span data-ttu-id="0e7dd-146">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-146">Click **OK**.</span></span>  

## <a name="specifying-binding-properties-from-the-biztalk-server-administration-console"></a><span data-ttu-id="0e7dd-147">BizTalk Server 管理コンソールからバインドのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-147">Specifying Binding Properties from the BizTalk Server Administration Console</span></span>  
 <span data-ttu-id="0e7dd-148">BizTalk Server 管理コンソールで、Wcf-custom または Wcf-oracledb ポート構成の一部としてのバインドのプロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-148">From the BizTalk Server Administration console, you must specify the binding properties as part of the WCF-Custom or WCF-OracleDB port configuration.</span></span>  

#### <a name="to-specify-binding-properties-for-the-wcf-custom-port"></a><span data-ttu-id="0e7dd-149">WCF カスタム ポートのバインドのプロパティを指定するには</span><span class="sxs-lookup"><span data-stu-id="0e7dd-149">To specify binding properties for the WCF-Custom port</span></span>  

1. <span data-ttu-id="0e7dd-150">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-150">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="0e7dd-151">コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、順に展開する、ポートを作成し、をクリックしアプリケーション**送信ポート**または**受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-151">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="0e7dd-152">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-152">In the right pane, you can choose to create a port or select an existing port.</span></span>  

3. <span data-ttu-id="0e7dd-153">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-153">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="0e7dd-154">受信ポートの場所のプロパティ ダイアログ ボックスを表示する をクリックして、**受信場所**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**します。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-154">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  

4. <span data-ttu-id="0e7dd-155">**Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブ。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-155">In the **WCF-Custom Transport Properties** dialog box, click the **Binding** tab.</span></span>  

5. <span data-ttu-id="0e7dd-156">**バインドの種類**ドロップダウン リストで、 **oracleDBBinding**します。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-156">From the **Binding Type** drop-down list, select **oracleDBBinding**.</span></span>  

6. <span data-ttu-id="0e7dd-157">**構成**ボックスでのさまざまなバインドのプロパティの値を指定し、をクリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-157">In the **Configuration** box, specify the values for the different binding properties and click **OK**.</span></span>  

#### <a name="to-specify-binding-properties-for-the-wcf-oracledb-port"></a><span data-ttu-id="0e7dd-158">Wcf-oracledb ポートのバインドのプロパティを指定するには</span><span class="sxs-lookup"><span data-stu-id="0e7dd-158">To specify binding properties for the WCF-OracleDB port</span></span>  

1. <span data-ttu-id="0e7dd-159">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-159">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="0e7dd-160">Wcf-oracledb アダプターを BizTalk Server 管理コンソールに追加します。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-160">Add the WCF-OracleDB adapter to the BizTalk Server Administration console.</span></span> <span data-ttu-id="0e7dd-161">手順については、次を参照してください。[を BizTalk Server 管理コンソールの Oracle データベース アダプターの追加](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md)します。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-161">For instructions, see [Adding the Oracle Database Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md).</span></span>  

3. <span data-ttu-id="0e7dd-162">コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、順に展開する、ポートを作成し、をクリックしアプリケーション**送信ポート**または**受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-162">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="0e7dd-163">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-163">In the right pane, you can choose to create a port or select an existing port.</span></span>  

4. <span data-ttu-id="0e7dd-164">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストでは、先ほど追加した Wcf-oracledb アダプターを選択してをクリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-164">In the port properties dialog box, from the **Type** drop-down list, select the WCF-OracleDB adapter you added earlier, and then click **Configure**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="0e7dd-165">受信ポートの場所のプロパティ ダイアログ ボックスを表示する をクリックして、**受信場所**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**します。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-165">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  

5. <span data-ttu-id="0e7dd-166">トランスポートのプロパティ ダイアログ ボックスでをクリックして、**バインド**タブをクリックし、バインドのプロパティの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-166">In the transport properties dialog box, click the **Binding** tab, and specify values for binding properties.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="0e7dd-167">バインドのプロパティは、送信ポートまたは受信ポートを構成するかどうかに基づいて表示されます。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-167">The binding properties are displayed based on whether you are configuring a send port or a receive port.</span></span> <span data-ttu-id="0e7dd-168">たとえば、通知に関連するバインドのプロパティは通知が受信操作には、受信ポートの構成を必要とするために、送信ポートを構成するときに使用できませんなりました。</span><span class="sxs-lookup"><span data-stu-id="0e7dd-168">For example, binding properties related to notifications are not available while configuring a send port because notifications are inbound operations and require a receive port configuration.</span></span>  

## <a name="see-also"></a><span data-ttu-id="0e7dd-169">参照</span><span class="sxs-lookup"><span data-stu-id="0e7dd-169">See Also</span></span>  
[<span data-ttu-id="0e7dd-170">Oracle データベースと BizTalk アプリケーションを開発する構成要素</span><span class="sxs-lookup"><span data-stu-id="0e7dd-170">Building Blocks to develop BizTalk Applications with Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)