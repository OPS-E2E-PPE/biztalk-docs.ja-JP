---
title: SQL アダプタのバインドのプロパティの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c2edbd90-039a-48b4-a6fc-d825b4957207
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a324672d21b98f88fb23f3ac95a9f4febd77a2c1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369977"
---
# <a name="configure-the-binding-properties-for-the-sql-adapter"></a><span data-ttu-id="16d83-102">SQL アダプタのバインドのプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="16d83-102">Configure the binding properties for the SQL adapter</span></span>
<span data-ttu-id="16d83-103">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]動作特性を制御するためのいくつかのバインドのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="16d83-103">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] surfaces several binding properties that enable you to control some of its behavioral characteristics.</span></span> <span data-ttu-id="16d83-104">このセクションでは、バインドのプロパティを設定する方法についての情報を提供します。[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]との間、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="16d83-104">This section provides information about setting the binding properties from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and from the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="16d83-105">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、特定の操作のスキーマを生成するバインドのプロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="16d83-105">From [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], you must specify the binding properties to generate schema for specific operations.</span></span> <span data-ttu-id="16d83-106">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]送信の一環としてバインドのプロパティを指定するか、受信ポートを送信または SQL Server からメッセージを受信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="16d83-106">From [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you must specify the binding properties as part of the send or receive port for sending or receiving messages from SQL Server.</span></span>  

 <span data-ttu-id="16d83-107">バインドのプロパティについては、バインドのプロパティの一覧を含む、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を参照してください[for SQL Server のアダプターのバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="16d83-107">For information about the binding properties, including a list of binding properties for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span>  

## <a name="enter-the-binding-properties-in-visual-studio"></a><span data-ttu-id="16d83-108">Visual Studio でのバインドのプロパティを入力します。</span><span class="sxs-lookup"><span data-stu-id="16d83-108">Enter the binding properties in Visual Studio</span></span>  
 <span data-ttu-id="16d83-109">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を使用してバインドのプロパティを指定することができます、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="16d83-109">From [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], you can specify the binding properties using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  

### <a name="using-consume-adapter-service-add-in"></a><span data-ttu-id="16d83-110">アダプターを使用してを使用して追加のサービス</span><span class="sxs-lookup"><span data-stu-id="16d83-110">Using Consume Adapter Service Add-in</span></span>  

1.  <span data-ttu-id="16d83-111">BizTalk プロジェクトを右クリックし、**生成した項目の追加**します。</span><span class="sxs-lookup"><span data-stu-id="16d83-111">Right-click your BizTalk project, and then select **Add Generated Items**.</span></span>  

2.  <span data-ttu-id="16d83-112">**生成した項目の追加** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="16d83-112">In the **Add Generated Items** dialog box, do the following:</span></span>  

    |<span data-ttu-id="16d83-113">プロパティ</span><span class="sxs-lookup"><span data-stu-id="16d83-113">Use this</span></span>|<span data-ttu-id="16d83-114">目的</span><span class="sxs-lookup"><span data-stu-id="16d83-114">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="16d83-115">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="16d83-115">**Categories**</span></span>|<span data-ttu-id="16d83-116">クリックして**アダプター サービスの使用**します。</span><span class="sxs-lookup"><span data-stu-id="16d83-116">Click **Consume Adapter Service**.</span></span>|  
    |<span data-ttu-id="16d83-117">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="16d83-117">**Templates**</span></span>|<span data-ttu-id="16d83-118">クリックして**アダプター サービスの使用**します。</span><span class="sxs-lookup"><span data-stu-id="16d83-118">Click **Consume Adapter Service**.</span></span>|  

3.  <span data-ttu-id="16d83-119">開始する、 **Consume Adapter Service**ダイアログ ボックスで、をクリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="16d83-119">To start the **Consume Adapter Service** dialog box, click **Add**.</span></span>  

4.  <span data-ttu-id="16d83-120">**Consume Adapter Service**  ダイアログ ボックスから、**バインディングを選択**ドロップダウン リスト、選択**sqlBinding**、順にクリックします**構成**.</span><span class="sxs-lookup"><span data-stu-id="16d83-120">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list, select **sqlBinding**, and then click **Configure**.</span></span>  

5.  <span data-ttu-id="16d83-121">**アダプターの構成**ダイアログ ボックスで、をクリックして、**バインド プロパティ**タブをクリックし、別のバインド プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="16d83-121">In the **Configure Adapter** dialog box, click the **Binding Properties** tab, and then specify the different binding properties.</span></span>  

6.  <span data-ttu-id="16d83-122">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="16d83-122">Click **OK**.</span></span>  

### <a name="using-add-adapter-metadata-wizard"></a><span data-ttu-id="16d83-123">アダプター メタデータのウィザードを使用して追加</span><span class="sxs-lookup"><span data-stu-id="16d83-123">Using Add Adapter Metadata Wizard</span></span>  

1. <span data-ttu-id="16d83-124">BizTalk プロジェクトを右クリックし、[**追加**、] をクリックし、**生成した項目の追加**します。</span><span class="sxs-lookup"><span data-stu-id="16d83-124">Right-click the BizTalk project, point to **Add**, and then click **Add Generated Items**.</span></span>  

2. <span data-ttu-id="16d83-125">**生成した項目の追加** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="16d83-125">In the **Add Generated Items** dialog box, do the following:</span></span>  


   |    <span data-ttu-id="16d83-126">プロパティ</span><span class="sxs-lookup"><span data-stu-id="16d83-126">Use this</span></span>    |           <span data-ttu-id="16d83-127">目的</span><span class="sxs-lookup"><span data-stu-id="16d83-127">To do this</span></span>            |
   |----------------|---------------------------------|
   | <span data-ttu-id="16d83-128">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="16d83-128">**Categories**</span></span> |     <span data-ttu-id="16d83-129">クリックして**アダプターを追加**します。</span><span class="sxs-lookup"><span data-stu-id="16d83-129">Click **Add Adapter**.</span></span>      |
   | <span data-ttu-id="16d83-130">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="16d83-130">**Templates**</span></span>  | <span data-ttu-id="16d83-131">クリックして**アダプター メタデータの追加**します。</span><span class="sxs-lookup"><span data-stu-id="16d83-131">Click **Add Adapter Metadata**.</span></span> |


3. <span data-ttu-id="16d83-132">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="16d83-132">Click **Add**.</span></span> <span data-ttu-id="16d83-133">[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="16d83-133">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  

4. <span data-ttu-id="16d83-134">アダプターの追加ウィザードで選択**WCF-SQL**します。</span><span class="sxs-lookup"><span data-stu-id="16d83-134">In the Add Adapter Wizard, select **WCF-SQL**.</span></span> <span data-ttu-id="16d83-135">BizTalk Server がインストールされているコンピューターを選択し、BizTalk データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="16d83-135">Select the computer on which BizTalk Server is installed and the name of the BizTalk database.</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="16d83-136">BizTalk で構成されている WCF SQL ポートが既にあるを場合からポートの選択、**ポート**一覧。</span><span class="sxs-lookup"><span data-stu-id="16d83-136">If you already have a WCF-SQL port configured in BizTalk, select the port from the **Port** list.</span></span>  

5. <span data-ttu-id="16d83-137">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="16d83-137">Click **Next**.</span></span>  

6. <span data-ttu-id="16d83-138">**Consume Adapter Service**  ダイアログ ボックスから、**バインディングを選択**ドロップダウン リスト、選択**sqlBinding**、順にクリックします**構成**.</span><span class="sxs-lookup"><span data-stu-id="16d83-138">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list, select **sqlBinding**, and then click **Configure**.</span></span>  

7. <span data-ttu-id="16d83-139">をクリックして、**バインド プロパティ**タブをクリックし、対象と操作に必要な場合、バインドのプロパティの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="16d83-139">Click the **Binding Properties** tab, and then specify values for the binding properties, if any, required by the operations you want to target.</span></span> <span data-ttu-id="16d83-140">バインド プロパティの詳細については、次を参照してください。 [for SQL Server のアダプターのバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="16d83-140">For more information about binding properties, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="16d83-141">既存の WCF-SQL 送信ポートを選択した場合は、バインドのプロパティを指定する必要がありますできません。</span><span class="sxs-lookup"><span data-stu-id="16d83-141">If you selected an existing WCF-SQL send port, you need not specify the binding properties.</span></span> <span data-ttu-id="16d83-142">バインドのプロパティは、送信ポートの構成から取得されます。</span><span class="sxs-lookup"><span data-stu-id="16d83-142">The binding properties are picked from the send port configuration.</span></span> <span data-ttu-id="16d83-143">ただし、存在する場合に、デザイン時に必要なバインドのプロパティを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="16d83-143">However, you may choose to specify the binding properties that are required at design-time, if any.</span></span> <span data-ttu-id="16d83-144">このような場合、メタデータの生成中にプロパティをバインドするための新しい値をデザイン時に使用されます。</span><span class="sxs-lookup"><span data-stu-id="16d83-144">In such case, the new values for binding properties will be used at design-time while generating the metadata.</span></span> <span data-ttu-id="16d83-145">ただし、実行時に送信ポートの構成でバインドのプロパティに指定された値を適用できるになります。</span><span class="sxs-lookup"><span data-stu-id="16d83-145">However, at run-time the values specified for binding properties in the send port configuration will be applicable.</span></span>  

8. <span data-ttu-id="16d83-146">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="16d83-146">Click **OK**.</span></span>  

## <a name="enter-binding-properties-from-the-biztalk-server-administration-console"></a><span data-ttu-id="16d83-147">BizTalk Server 管理コンソールからバインドのプロパティを入力します。</span><span class="sxs-lookup"><span data-stu-id="16d83-147">Enter binding properties from the BizTalk Server Administration console</span></span>  
 <span data-ttu-id="16d83-148">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、Wcf-custom または WCF SQL ポートの構成の一部としてのバインドのプロパティを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="16d83-148">From the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you can specify the binding properties as part of the WCF-Custom or WCF-SQL port configuration.</span></span>  

### <a name="enter-binding-properties-for-wcf-custom-port"></a><span data-ttu-id="16d83-149">WCF カスタム ポートのバインドのプロパティを入力します。</span><span class="sxs-lookup"><span data-stu-id="16d83-149">Enter binding properties for WCF-Custom port</span></span>  

1. <span data-ttu-id="16d83-150">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="16d83-150">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="16d83-151">コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、順に展開する、ポートを作成し、をクリックしアプリケーション**送信ポート**または**受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="16d83-151">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="16d83-152">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="16d83-152">In the right pane, you can choose to create a port or select an existing port.</span></span>  

3. <span data-ttu-id="16d83-153">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="16d83-153">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="16d83-154">受信ポートの場所のプロパティ ダイアログ ボックスを表示する をクリックして、**受信場所**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**します。</span><span class="sxs-lookup"><span data-stu-id="16d83-154">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  

4. <span data-ttu-id="16d83-155">**Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブ。</span><span class="sxs-lookup"><span data-stu-id="16d83-155">In the **WCF-Custom Transport Properties** dialog box, click the **Binding** tab.</span></span>  

5. <span data-ttu-id="16d83-156">**バインドの種類**一覧で、 **sqlBinding**します。</span><span class="sxs-lookup"><span data-stu-id="16d83-156">From the **Binding Type** list, select **sqlBinding**.</span></span>  

6. <span data-ttu-id="16d83-157">**構成**ボックスに、さまざまなバインドのプロパティの値を指定してクリックして**OK**。</span><span class="sxs-lookup"><span data-stu-id="16d83-157">In the **Configuration** box, specify the values for the different binding properties, and then click **OK**.</span></span>  

### <a name="enter-binding-properties-for-the-wcf-sql-port"></a><span data-ttu-id="16d83-158">WCF SQL ポートのバインドのプロパティを入力します。</span><span class="sxs-lookup"><span data-stu-id="16d83-158">Enter binding properties for the WCF-SQL port</span></span>  

1. <span data-ttu-id="16d83-159">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="16d83-159">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="16d83-160">WCF-SQL アダプターを追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="16d83-160">Add the WCF-SQL adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="16d83-161">手順については、次を参照してください。 [SQL アダプタを BizTalk Server 管理コンソールに追加する](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md)します。</span><span class="sxs-lookup"><span data-stu-id="16d83-161">For instructions, see [Adding the SQL Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md).</span></span>  

3. <span data-ttu-id="16d83-162">コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、順に展開する、ポートを作成し、をクリックしアプリケーション**送信ポート**または**受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="16d83-162">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="16d83-163">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="16d83-163">In the right pane, you can choose to create a port or select an existing port.</span></span>  

4. <span data-ttu-id="16d83-164">ポートのプロパティ ダイアログ ボックスから、**型**ドロップダウン リストでは、先ほど追加した WCF-SQL アダプターを選択し、順にクリックします**構成**します。</span><span class="sxs-lookup"><span data-stu-id="16d83-164">In the port properties dialog box, from the **Type** drop-down list, select the WCF-SQL adapter you added earlier, and then click **Configure**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="16d83-165">受信ポートの場所のプロパティ ダイアログ ボックスを表示する をクリックして、**受信場所**ポートのプロパティ ダイアログ ボックスの左側のウィンドウでタブをクリックして**新規**します。</span><span class="sxs-lookup"><span data-stu-id="16d83-165">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  

5. <span data-ttu-id="16d83-166">トランスポートのプロパティ ダイアログ ボックスでをクリックして、**バインド**タブし、バインドのプロパティの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="16d83-166">In the transport properties dialog box, click the **Binding** tab and specify values for binding properties.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="16d83-167">バインドのプロパティは、送信ポートまたは受信ポートを構成するかどうかに基づいて表示されます。</span><span class="sxs-lookup"><span data-stu-id="16d83-167">The binding properties are displayed based on whether you are configuring a send port or a receive port.</span></span> <span data-ttu-id="16d83-168">たとえば、通知に関連するバインドのプロパティは通知が受信操作には、受信ポートの構成を必要とするために、送信ポートを構成するときに使用できませんなりました。</span><span class="sxs-lookup"><span data-stu-id="16d83-168">For example, binding properties related to notifications are not available while configuring a send port because notifications are inbound operations and require a receive port configuration.</span></span>  

6. <span data-ttu-id="16d83-169">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="16d83-169">Click **OK**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="16d83-170">参照</span><span class="sxs-lookup"><span data-stu-id="16d83-170">See Also</span></span>  
[<span data-ttu-id="16d83-171">SQL アダプターを使用した BizTalk アプリケーションを開発する構成要素</span><span class="sxs-lookup"><span data-stu-id="16d83-171">Building blocks to develop BizTalk applications with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)