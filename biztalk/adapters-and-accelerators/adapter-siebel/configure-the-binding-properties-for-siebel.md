---
title: "Siebel のバインド プロパティの構成 |Microsoft ドキュメント"
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
- how to, specify binding properties at design time
- how to, specify binding properties at run time
ms.assetid: 063e9507-8172-4fb0-8b9f-2f95e8a82f21
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b26e9e89319a14317113b730adb189f2f17587f9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-binding-properties-for-siebel"></a><span data-ttu-id="c3345-102">Siebel のバインドのプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="c3345-102">Configure the binding properties for Siebel</span></span>
<span data-ttu-id="c3345-103">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]動作特性を制御できるようにするいくつかのバインドのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="c3345-103">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] surfaces several binding properties that enable you to control some of its behavioral characteristics.</span></span> <span data-ttu-id="c3345-104">このセクションで説明および Visual Studio (設計時) からのバインドのプロパティを設定する方法について、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール (実行時)。</span><span class="sxs-lookup"><span data-stu-id="c3345-104">This section provides information about setting the binding properties from Visual Studio (design time) and from the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration Console (run time).</span></span> <span data-ttu-id="c3345-105">デザイン時に、特定の操作のスキーマを生成するバインドのプロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3345-105">At design time, you must specify the binding properties to generate schema for specific operations.</span></span> <span data-ttu-id="c3345-106">実行時に、Siebel システムへのメッセージ送信用の送信ポートの一部としてのバインドのプロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3345-106">At run time, you must specify the binding properties as part of the send port for sending messages to the Siebel system.</span></span>  
  
 <span data-ttu-id="c3345-107">バインドのプロパティについては、バインドのプロパティの一覧を含む[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を参照してください[BizTalk Adapter for Siebel のバインド プロパティ読む](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="c3345-107">For information about the binding properties, including a list of binding properties for [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], see [Read about BizTalk Adapter for Siebel Binding Properties](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span></span>  
  
## <a name="enter-the-binding-properties-at-design-time"></a><span data-ttu-id="c3345-108">デザイン時のバインドのプロパティを入力してください。</span><span class="sxs-lookup"><span data-stu-id="c3345-108">Enter the binding properties at design time</span></span>  
 <span data-ttu-id="c3345-109">デザイン時からのバインドのプロパティを指定する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="c3345-109">For design time, you must specify the binding properties from the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] dialog box.</span></span>  
  
#### <a name="enter-binding-properties-using-consume-adapter-service-add-in"></a><span data-ttu-id="c3345-110">アダプター サービスのアドインを使用してバインドのプロパティを入力してください。</span><span class="sxs-lookup"><span data-stu-id="c3345-110">Enter binding properties using Consume Adapter Service Add-in</span></span>  
  
1.  <span data-ttu-id="c3345-111">BizTalk プロジェクトを右クリックし、順にポイント**追加**、し、**生成した項目の追加**です。</span><span class="sxs-lookup"><span data-stu-id="c3345-111">Right-click your BizTalk project, point to **Add**, and then select **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="c3345-112">**生成した項目の追加** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="c3345-112">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="c3345-113">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c3345-113">Use this</span></span>|<span data-ttu-id="c3345-114">目的</span><span class="sxs-lookup"><span data-stu-id="c3345-114">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="c3345-115">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="c3345-115">**Categories**</span></span>|<span data-ttu-id="c3345-116">をクリックして**アダプター サービスの使用**です。</span><span class="sxs-lookup"><span data-stu-id="c3345-116">Click **Consume Adapter Service**.</span></span>|  
    |<span data-ttu-id="c3345-117">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="c3345-117">**Templates**</span></span>|<span data-ttu-id="c3345-118">をクリックして**アダプター サービスの使用**です。</span><span class="sxs-lookup"><span data-stu-id="c3345-118">Click **Consume Adapter Service**.</span></span>|  
  
3.  <span data-ttu-id="c3345-119">開始する、**アダプター サービスの使用**ダイアログ ボックスで、をクリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="c3345-119">To start the **Consume Adapter Service** dialog box, click **Add**.</span></span>  
  
4.  <span data-ttu-id="c3345-120">**アダプター サービスの使用** ダイアログ ボックスから、**バインディングを選択**ドロップダウン リストを**siebelBinding**、 をクリック**構成**.</span><span class="sxs-lookup"><span data-stu-id="c3345-120">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list select **siebelBinding**, and click **Configure**.</span></span>  
  
5.  <span data-ttu-id="c3345-121">**アダプターの構成**ダイアログ ボックスで、をクリックして、**バインド プロパティ** タブの値を指定します、バインディング、存在する場合は、スキーマを生成する前に指定する必要です。</span><span class="sxs-lookup"><span data-stu-id="c3345-121">In the **Configure Adapter** dialog box, click the **Binding Properties** tab and specify the binding values, if any, which are required to be specified before generating the schema.</span></span> <span data-ttu-id="c3345-122">バインドのプロパティの詳細については、次を参照してください。 [BizTalk Adapter for Siebel のバインド プロパティ読む](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="c3345-122">For more information about binding properties, see [Read about BizTalk Adapter for Siebel Binding Properties](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span></span>  
  
6.  <span data-ttu-id="c3345-123">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3345-123">Click **OK**.</span></span>  
  
#### <a name="enter-binding-properties-using-add-adapter-metadata-wizard"></a><span data-ttu-id="c3345-124">アダプター メタデータの追加ウィザードを使用してバインドのプロパティを入力してください。</span><span class="sxs-lookup"><span data-stu-id="c3345-124">Enter binding properties using Add Adapter Metadata Wizard</span></span>  
  
1.  <span data-ttu-id="c3345-125">BizTalk プロジェクトを右クリックし、順にポイント**追加**、し、**生成した項目の追加**です。</span><span class="sxs-lookup"><span data-stu-id="c3345-125">Right-click your BizTalk project, point to **Add**, and then select **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="c3345-126">**生成した項目の追加** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="c3345-126">In the **Add Generated Items** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="c3345-127">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c3345-127">Use this</span></span>|<span data-ttu-id="c3345-128">目的</span><span class="sxs-lookup"><span data-stu-id="c3345-128">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="c3345-129">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="c3345-129">**Categories**</span></span>|<span data-ttu-id="c3345-130">をクリックして**アダプターを追加**です。</span><span class="sxs-lookup"><span data-stu-id="c3345-130">Click **Add Adapter**.</span></span>|  
    |<span data-ttu-id="c3345-131">**[テンプレート]**</span><span class="sxs-lookup"><span data-stu-id="c3345-131">**Templates**</span></span>|<span data-ttu-id="c3345-132">をクリックして**アダプター メタデータの追加**です。</span><span class="sxs-lookup"><span data-stu-id="c3345-132">Click **Add Adapter Metadata**.</span></span>|  
  
3.  <span data-ttu-id="c3345-133">**[追加]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3345-133">Click **Add**.</span></span> <span data-ttu-id="c3345-134">[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c3345-134">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  
  
4.  <span data-ttu-id="c3345-135">アダプターの追加ウィザードで選択**Wcf-siebel**です。</span><span class="sxs-lookup"><span data-stu-id="c3345-135">In the Add Adapter Wizard, select **WCF-Siebel**.</span></span> <span data-ttu-id="c3345-136">コンピューターを選択して[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]がインストールされていると、BizTalk データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="c3345-136">Select the computer on which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] is installed and the name of the BizTalk database.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="c3345-137">BizTalk で構成された Wcf-siebel ポートがある場合からポートを選択して、**ポート** ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="c3345-137">If you already have a WCF-Siebel port configured in BizTalk, select the port from the **Port** list.</span></span>  
  
5.  <span data-ttu-id="c3345-138">**[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3345-138">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="c3345-139">**アダプター サービスの使用** ダイアログ ボックスから、**バインディングを選択**ドロップダウン リストを**siebelBinding**、 をクリック**構成**.</span><span class="sxs-lookup"><span data-stu-id="c3345-139">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list select **siebelBinding**, and click **Configure**.</span></span>  
  
7.  <span data-ttu-id="c3345-140">**アダプターの構成**ダイアログ ボックスで、をクリックして、**バインド プロパティ** タブの値を指定します、バインディング、存在する場合は、スキーマを生成する前に指定する必要です。</span><span class="sxs-lookup"><span data-stu-id="c3345-140">In the **Configure Adapter** dialog box, click the **Binding Properties** tab and specify the binding values, if any, which are required to be specified before generating the schema.</span></span> <span data-ttu-id="c3345-141">バインドのプロパティの詳細については、次を参照してください。 [BizTalk Adapter for Siebel のバインド プロパティ読む](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="c3345-141">For more information about binding properties, see [Read about BizTalk Adapter for Siebel Binding Properties](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c3345-142">既存の WCF Siebel 送信ポートを選択した場合、バインドのプロパティを指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c3345-142">If you selected an existing WCF-Siebel send port, you need not specify the binding properties.</span></span> <span data-ttu-id="c3345-143">バインドのプロパティは、送信ポートの構成から取得されます。</span><span class="sxs-lookup"><span data-stu-id="c3345-143">The binding properties are picked from the send port configuration.</span></span> <span data-ttu-id="c3345-144">ただし、存在する場合、デザイン時に、必要なバインドのプロパティを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="c3345-144">However, you may choose to specify the binding properties that are required at design-time, if any.</span></span> <span data-ttu-id="c3345-145">このような場合、メタデータの生成中にバインドのプロパティの新しい値をデザイン時に使用されます。</span><span class="sxs-lookup"><span data-stu-id="c3345-145">In such case, the new values for binding properties will be used at design-time while generating the metadata.</span></span> <span data-ttu-id="c3345-146">ただし、実行時に、バインドの送信ポートの構成のプロパティの指定値適用されます。</span><span class="sxs-lookup"><span data-stu-id="c3345-146">However, at run-time the values specified for binding properties in the send port configuration will be applicable.</span></span>  
  
8.  <span data-ttu-id="c3345-147">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3345-147">Click **OK**.</span></span>  
  
## <a name="enter-binding-properties-at-run-time"></a><span data-ttu-id="c3345-148">実行時のバインドのプロパティを入力してください。</span><span class="sxs-lookup"><span data-stu-id="c3345-148">Enter binding properties at run time</span></span>  
 <span data-ttu-id="c3345-149">実行時に、Wcf-custom またはで Wcf-siebel ポートの構成の一部としてのバインドのプロパティを指定する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="c3345-149">For run time, you must specify the binding properties as part of the WCF-Custom or the WCF-Siebel port configuration in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
#### <a name="enter-binding-properties-for-the-wcf-custom-port"></a><span data-ttu-id="c3345-150">WCF カスタム ポートのバインドのプロパティを入力します。</span><span class="sxs-lookup"><span data-stu-id="c3345-150">Enter binding properties for the WCF-Custom port</span></span>  
  
1.  <span data-ttu-id="c3345-151">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="c3345-151">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="c3345-152">コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、ポートを作成し、をクリックする、アプリケーションの順に展開および**送信ポート**.</span><span class="sxs-lookup"><span data-stu-id="c3345-152">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and then click **Send Ports**.</span></span> <span data-ttu-id="c3345-153">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="c3345-153">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
3.  <span data-ttu-id="c3345-154">**ポートのプロパティ** ダイアログ ボックスから、**型**ドロップダウン リストで、 **Wcf-custom**をクリックし、**構成**です。</span><span class="sxs-lookup"><span data-stu-id="c3345-154">In the **Port Properties** dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
4.  <span data-ttu-id="c3345-155">**Wcf-custom トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブです。</span><span class="sxs-lookup"><span data-stu-id="c3345-155">In the **WCF-Custom Transport Properties** dialog box, click the **Binding** tab.</span></span>  
  
5.  <span data-ttu-id="c3345-156">**バインディングの種類**ドロップダウン リストで、 **siebelBinding**です。</span><span class="sxs-lookup"><span data-stu-id="c3345-156">From the **Binding Type** drop-down list, select **siebelBinding**.</span></span>  
  
6.  <span data-ttu-id="c3345-157">**構成**ボックスで異なるバインディングのプロパティの値を指定し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="c3345-157">In the **Configuration** box, specify the values for the different binding properties and click **OK**.</span></span>  
  
#### <a name="enter-binding-properties-for-the-wcf-siebel-port"></a><span data-ttu-id="c3345-158">Wcf-siebel ポートのバインドのプロパティを入力します。</span><span class="sxs-lookup"><span data-stu-id="c3345-158">Enter binding properties for the WCF-Siebel port</span></span>  
  
1.  <span data-ttu-id="c3345-159">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="c3345-159">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="c3345-160">Wcf-siebel アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="c3345-160">Add the WCF-Siebel adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="c3345-161">手順については、次を参照してください。 [Siebel アダプターを BizTalk Server 管理コンソールに追加](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md)です。</span><span class="sxs-lookup"><span data-stu-id="c3345-161">For instructions, see [Add the Siebel Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3.  <span data-ttu-id="c3345-162">コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、ポートを作成し、をクリックする、アプリケーションの順に展開および**送信ポート**.</span><span class="sxs-lookup"><span data-stu-id="c3345-162">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and then click **Send Ports**.</span></span> <span data-ttu-id="c3345-163">右側のウィンドウでは、ポートを作成または既存のポートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="c3345-163">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
4.  <span data-ttu-id="c3345-164">**ポートのプロパティ** ダイアログ ボックスから、**型**ドロップダウン リストは、前に追加する Wcf-siebel ポートを選択し、をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="c3345-164">In the **Port Properties** dialog box, from the **Type** drop-down list, select the WCF-Siebel port you added earlier, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="c3345-165">トランスポートのプロパティ ダイアログ ボックスをクリックして、**バインディング**タブし、バインドのプロパティの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="c3345-165">In the transport properties dialog box, click the **Binding** tab and specify values for the binding properties.</span></span>  
  
6.  <span data-ttu-id="c3345-166">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3345-166">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3345-167">参照</span><span class="sxs-lookup"><span data-stu-id="c3345-167">See Also</span></span>  
[<span data-ttu-id="c3345-168">Siebel アダプターと BizTalk アプリケーションを作成する構成要素</span><span class="sxs-lookup"><span data-stu-id="c3345-168">Building blocks to create BizTalk applications with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)